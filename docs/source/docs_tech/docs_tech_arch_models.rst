..
    Raw html added to assign styling only to codeblocks being used as headers in this document

.. raw:: html

    <style> .codeblocksize {line-height: 2.5; font-size: x-large; background-color: rgb(175 184 193 / 20%); border-radius: 6px; color: #CC3600; padding: 0.2em 0.4em; padding-top: 0.2em; padding-right: 0.4em; padding-bottom: 0.2em; padding-left: 0.4em;}</style>

.. role:: codeblocksize

.. _application-architecture:

========================
Application Architecture
========================

This section contains technical details about the current implementation of the Canadian Aquatic Barriers Database (CABD) back-end application, including feaure and vector tile services and the CABD data dictionary. The intended audience are software developers and similar technical users looking to upgrade/maintain the current system or use the API endpoints.

.. _current-application-architecture:

Existing Implementation
-----------------------

-----

The current application runs on two Microsoft Azure Java Web App servers, ``cabd-web`` (for CABD data) and ``chyf-web`` (for CHyF data).

.. image:: img/app-arch3.jpg
    :align: center

.. _cabd-feature-model:

.. _cabd-models:

Features and Database Models
----------------------------

-----

CABD Feature Model
~~~~~~~~~~~~~~~~~~

.. _generic-feature-model:

Generic Feature Model
+++++++++++++++++++++

Features in CABD have an optional hierarchical structure. Feature types can be combined to form “super feature types”. 

There are no structures in the software/database that enforce this model. The database views (see section below) are used to define the various feature types and super types. It would be possible for a feature type to be associated with multiple super types, if desired.

.. image:: img/genericmodel.jpg
    :align: center
    :width: 500

.. _implemented-feature-model:

Implemented Feature Model
+++++++++++++++++++++++++

There are currently three feature types and one super type implemented in CABD. Adding additional feature types is expected and the instructions for this are outlined below (How to add new Feature Type).

.. image:: img/implementedmodel.jpg
    :align: center
    :width: 500

Feature types:

- ``barriers`` - a super feature type that includes dams structures and waterfalls.
- ``dams`` - a feature type for features classified as a dam structure.
- ``waterfalls`` - a feature type for features classified as a waterfall.
- ``fishways`` - a feature type for features classified as a fishway structure.
- ``medium`` - a feature type created for testing the increase in data volume expected for stream crossing data.
- ``big`` - a feature type created for testing the increase in data volume expected for stream crossing data.

.. _cabd-database-model:

CABD Database Model
~~~~~~~~~~~~~~~~~~~

The database is structured into multiple schemas.  Each feature type has its own schema, with a common ``cabd`` schema for shared data and feature metadata.

.. _cabd-views:

Views
+++++

Each feature type and super feature type has two associated views which supports the api - one view for engligh (_en) and one view for french (_fr). These views should include all fields required for output (either for display on the UI or to support the future editing api).  The view ``cabd.all_features_view_XX`` supports all features api endpoint. 

The views are used to support the CABD APIs that list features. Each feature type is linked to a database view. When requesting features of a specific type the view associated with this type is queried. The fields returned by this view populate the attributes of the feature returned by the API. Feature type views will generally query a single data table (for example, the ``dams`` view queries the dams data table). Super feature types will generally query multiple data tables (for example, the ``barriers`` view queries both the dams data table and the waterfalls data table).

.. _core-tables:

Core Tables
+++++++++++

These tables are the core tables for the system and required regardless of the feature types loaded. They support the definition of feature types.

:codeblocksize:`cabd.feature_types`

Lists all the feature types supported by the system.

.. csv-table:: 
    :file: tbl/core-tables.csv
    :widths: 30, 70
    :header-rows: 1

:codeblocksize:`cabd.feature_type_metadata`

Lists all the attributes for a given feature view and the metadata details about the attribute.

.. csv-table:: 
    :file: tbl/feature-type-metadata.csv
    :widths: 30, 70
    :header-rows: 1

:codeblocksize:`cabd.data_source`

Lists data sources. Supports data source tracking for feature type attributes.

.. csv-table:: 
    :file: tbl/data-source.csv
    :widths: 30, 70
    :header-rows: 1


.. _shared-attribute-tables:

Shared Attribute Tables
+++++++++++++++++++++++

All of these tables store data that are shared between multiple feature types. Generally, each of these tables have a unique code (for references), a name, and a description.

* ``cabd.barrier_ownership_type_codes``
* ``cabd.fish_species``
* ``cabd.nhn_workunit``
* ``cabd.passability_status_codes``
* ``cabd.province_territory_codes``
* ``cabd.upstream_passage_type_codes``
* ``cabd.census_subdivisions``

.. _feature-tables:

Feature Tables
++++++++++++++

The feature type data tables are found in their corresponding schema. Generally, there will be one feature data table and a number of reference tables that represent attribute values.  Details for current feature types can be found in the Data Dictionary document.

.. _feature-type-attribute-data-sources:

Feature Type Attribute Data Sources
+++++++++++++++++++++++++++++++++++

The CABD database has the option of storing the data source for each attribute associated with the feature type. This has been implemented by having ``<featuretype>.<featuretype>_feature_source`` and ``<featuretype>.<featuretype>_attribute_source`` tables for the feature type.

The ``<featuretype>_feature_source``  table contains for each cabd feature a link to the data source and associated data source feature id.

.. csv-table:: 
    :file: tbl/feature-source.csv
    :widths: 30, 70
    :header-rows: 1

The ``<featuretype>_attribute_source`` table contains the cabd_id and one column for each attribute that requires data source tracking.  The column, ``<attribute>_ds``, links to the ``cabd.data_source table`` to identify the data source for the attribute value.

.. _add-new-feature-type: