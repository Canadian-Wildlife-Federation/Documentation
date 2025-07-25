..
    Raw html added to assign styling only to codeblocks being used as headers in this document

.. raw:: html

    <style> .codeblocksize {line-height: 2.5; font-size: x-large; background-color: rgb(175 184 193 / 20%); border-radius: 6px; color: #CC3600; padding: 0.2em 0.4em; padding-top: 0.2em; padding-right: 0.4em; padding-bottom: 0.2em; padding-left: 0.4em;}</style>

.. role:: codeblocksize

.. _application-architecture:

Application Architecture
########################

This section contains technical details about the current implementation of the Canadian Aquatic Barriers Database (CABD) back-end application, including feature and vector tile services and the CABD data dictionary. The intended audience are software developers and similar technical users looking to upgrade/maintain the current system or use the API endpoints.

.. _current-application-architecture:

Existing Implementation
***********************

-----

The current application runs on two Microsoft Azure Java Web App servers, ``cabd-web`` (for CABD data) and ``chyf-web`` (for CHyF data).

.. image:: img/app-arch3.jpg
    :align: center

.. _cabd-feature-model:

.. _cabd-models:

Features and Database Models
****************************

-----

CABD Feature Model
==================

.. _generic-feature-model:

Generic Feature Model
---------------------

Features in CABD have an optional hierarchical structure. Feature types can be combined to form “super feature types”. 

There are no structures in the software/database that enforce this model. The database views (see section below) are used to define the various feature types and super types. It would be possible for a feature type to be associated with multiple super types, if desired.

.. image:: img/genericmodel.jpg
    :align: center
    :width: 500

.. _implemented-feature-model:

Implemented Feature Model
-------------------------

There are currently four feature types and one super type implemented in CABD. Adding additional feature types is expected, and the instructions for this are outlined below (How to add new Feature Type).

.. image:: img/implementedmodel.jpg
    :align: center
    :width: 500

Feature types:

- ``barriers`` - a super feature type that includes dams, other structures, waterfalls, and modelled crossings.
- ``dams`` - a feature type for features classified as a dam or other structure.
- ``waterfalls`` - a feature type for features classified as a waterfall.
- ``fishways`` - a feature type for features classified as a fish passage structure.
- ``modelled crossings`` - a feature type for features classified as a modelled stream crossing.
- ``stream crossings`` - a feature type for features classified as a stream crossing.

.. _cabd-database-model:

CABD Database Model
===================

The database is structured into multiple schemas.  Each feature type has its own schema, with a common ``cabd`` schema for shared data and feature metadata.

.. _cabd-feature-views:

Feature Views
-------------

Each feature type and super feature type has two associated views which support the API - one view for English (_en) and one view for French (_fr). These views should include all fields required for output (either for display on the UI or to support the future editing API). 

|enfr| 

Views are used to support the CABD APIs that list features. Each feature type is linked to a database view. When requesting features of a specific type, the view associated with this type is queried. The fields returned by this view populate the attributes of the feature returned by the API. Feature type views will generally query a single data table (for example, the ``dams`` view queries the dams data table). Super feature types will generally query multiple data tables (for example, the ``barriers`` view queries both the dams data table and the waterfalls data table).

.. _cabd-feature-update-view:

Feature Update View
-------------------

By design, each feature includes an updates_pending attribute that is populated with true or false depending on if there are feature updates pending review in the system. This field is populated by the system using the ``cabd.updates_pending`` view. This view should return a single column, cabd_id, for each feature that has a review pending in the database. 


.. _core-tables:

Core Tables
-----------

These tables are the core tables for the system and required regardless of the feature types loaded. They support the definition of feature types.

:codeblocksize:`cabd.feature_types`

Lists all the feature types supported by the system.

.. csv-table:: 
    :file: tbl/core-tables.csv
    :widths: 30, 70
    :header-rows: 1

:codeblocksize:`cabd.attribute_set`

Lists the attribute sets supported by the system. Attribute sets allows user to specify which attributes they want included in API results that list features.

Notes:
 * The attribute set should not have the name "vectortile". The system generates a vectortile attribute set automatically that is linked to the include_vector_tile field in the cabd.feature_type_metadata and used for the vector tile service.
 * The attribute "url" which provides a url to link to the full CABD feature is included in all JSON output for all attribute sets. There is no option to remove it. It is NOT included in other export formats (shape, geopackage, kml). 

.. csv-table:: 
    :file: tbl/attribute-set.csv
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

:codeblocksize:`cabd.contacts`

A list of contacts relevant to the CABD database.  Currently, contacts are only created when a user submits a feature update.

.. csv-table:: 
    :file: tbl/contacts.csv
    :widths: 30, 70
    :header-rows: 1


:codeblocksize:`cabd.user_feature_updates`

Users can use the Features API to submit updates to features. All submissions are stored in this table.

.. csv-table:: 
    :file: tbl/user_feature_updates.csv
    :widths: 30, 70
    :header-rows: 1
    
        
Shared Attribute Tables
-----------------------

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
--------------

The feature type data tables are found in their corresponding schema. Generally, there will be one feature data table and a number of reference tables that represent attribute values.  Details for current feature types can be found in the Data Dictionary document.

.. _feature-type-attribute-data-sources:

Feature Type Attribute Data Sources
-----------------------------------

The CABD database has the option of storing the data source for each attribute associated with the feature type. This has been implemented by having ``<featuretype>.<featuretype>_feature_source`` and ``<featuretype>.<featuretype>_attribute_source`` tables for the feature type (e.g., ``dams.dams_feature_source`` and ``dams.dams_attribute_source``).

For each cabd feature, the ``<featuretype>_feature_source``  table contains a link to the data sources and associated data source feature ids that the feature was found in. For example, a dam feature that was found in both the nrcan_canvec_mm and bceccs_fiss data sources would have two entries for its ``cabd_id`` in the ``<featuretype>_feature_source`` table.

:codeblocksize:`<featuretype>_feature_source`

.. csv-table:: 
    :file: tbl/feature-source.csv
    :widths: 30, 70
    :header-rows: 1

The ``<featuretype>_attribute_source`` table contains the cabd_id and one column for each attribute that requires data source tracking.  The column, ``<attribute>_ds``, links to the ``cabd.data_source table`` to identify the data source for the attribute value.

:codeblocksize:`<featuretype>_attribute_source`

.. csv-table:: 
    :file: tbl/feature-attribute.csv
    :widths: 30, 70
    :header-rows: 1



    
.. _community_data:
    
Community Data
--------------

The community data API supports the collection of data from community users. This API was developed to be used in conjunction with the Mobile Data Application.

The data submitted to the community API immediately gets written to the cabd.community_data_raw table without any 
validation or processing.  A separate job takes data from this community data table, parses the feature type, 
photos, and user information and places the photos onto the azure infrastructure, 
and the remaining data into the appropriate feature staging table in the database. 
Any features provided without a cabd_id are assigned a new one. 
Once in the feature staging table it is up to Data Reviews to review the data and update the appropriate CABD features.

Community data submissions can include images. These images are expected to be provided in the JSON as base64 encoded
JPEG files. The processing of the raw data includes converting this data into a jpeg file which is placed on the Azure
blob storage. The name of the file is referenced in the parsed json data.

:codeblocksize:`cabd.community_data_raw`

.. csv-table:: 
    :file: tbl/community_data_raw.csv
    :widths: 30, 70
    :header-rows: 1

Community data users are stored in a separate cabd.community_contact table.

:codeblocksize:`cabd.community_contact`

.. csv-table:: 
    :file: tbl/community_contact.csv
    :widths: 30, 70
    :header-rows: 1
    
Each feature type supported needs a feature staging table (<featuretype>_community_staging). 
This table name is specified in the cabd.feature_types metadata table. Each feature type staging table has a status column. 
By default the value is NEW. Once the data has been reviewed and appropriate features created/updated, 
this status column should be updated to something other than NEW.

:codeblocksize:`<featuretype>.community_data_<feature_type>`

.. csv-table:: 
    :file: tbl/community_data_featuretype.csv
    :widths: 30, 70
    :header-rows: 1


Each cabd feature has an updates_pending flag, and this flag includes features 
from the community data staging table that have a status of NEW.

Ghost features are features which have been submitted to the community data API without a cabd id 
and have not yet been reviewed and added to the official feature dataset. These features also rely on the 
feature type community data stating table status column (only features with a status of NEW 
will be considered for ghost features).


.. _audit_log:
    
Audit Log / Change Tracking
---------------------------

The CABD database has tracks changes to the following tables:

* cabd.contacts
* cabd.fish_species
* cabd.data_source
* dams.dams
* dams.dams_attribute_source
* dams.dams_feature_source
* waterfalls.waterfalls
* waterfalls.waterfalls_attribute_source
* waterfalls.waterfalls_feature_source
* fishways.fishways
* fishways.fishways_attribute_source
* fishways.fishways_feature_source
* fishways.species_mapping

New feature types can also include change tracking by applying the appropriate triggers to any new database tables that require change tracking.

All changes are logged in the ``cabd.audit_log`` table. This table has the following columns:

.. csv-table:: 
    :file: tbl/audit_log_table.csv
    :widths: 30, 70
    :header-rows: 1
    
