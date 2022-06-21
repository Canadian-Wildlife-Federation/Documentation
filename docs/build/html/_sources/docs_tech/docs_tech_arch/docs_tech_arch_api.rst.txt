.. raw:: html

    <style> .green {color: #2a997d} </style>

.. role:: green    


.. _cabd-rest-services:

=============================
REST Services (API Endpoints)
=============================

.. _api-overview:

Overview
--------

-----

.. _api-projection:

Projection
~~~~~~~~~~

All coordinates are returned in latitude/longitude (EPSG:4617).

.. _api-max-features:

Max Features
~~~~~~~~~~~~

For all the feature API end points below, the application returns a maximum of 15000 features. This is configurable and may be modified if required.

.. _api-specification:

API Specification
~~~~~~~~~~~~~~~~~

The latest Open API v3 specification can be found on the server:

https://cabd-web.azurewebsites.net/cabd-api/v3/api-docs.yaml (YAML)

https://cabd-web.azurewebsites.net/cabd-api/v3/api-docs (JSON)

.. _api-endpoints:

API End Points
--------------

-----

The base API server for the CABD end points is: ``https://cabd-web.azurewebsites.net/cabd-api``.

.. note::
    
    The API requests detailed in the following sections may contain one or more parameters (enclosed in chevrons, i.e. < >, and accentuated with the colour :green:`green`). If an API request is being made using one or more of the parameters listed, the chosen parameter must be replaced with an appropriate pre-defined value. 
    
    **Example:**

    |requestex1|


.. _feature-type-endpoints:

Feature Type End Points
~~~~~~~~~~~~~~~~~~~~~~~

The output format of all Feature Type End points is ``json``.

Existing feature types are: ``barriers``, ``dams``, ``waterfalls``, ``fishways``, ``medium``, and ``big``. See :ref:`Implemented Feature Model<implemented-feature-model>` for definitions of each feature type.

``/features/types/``

    Returns the list of feature types. Each feature type object includes a URL that lists the metadata for that feature type and a URL to list all features for that time.  
    
    .. note::
        
        Some types may be super types that contain data from a collection of other types (e.g., barriers is a super type that contains dam and waterfall features).

|fttype|

    Returns a description of the feature type. This description includes all attributes, names, and other metadata associated with the feature type. In addition, the metadata includes display details for attributes, including the details of which attributes should be included in the “simple” display and which included in the “all” attributes display.

    .. admonition:: Example
        
        ``https://cabd-web.azurewebsites.net/cabd-api/features/types/dams`` returns a ``json`` with the description of the ``dams`` feature type.

.. _feature-endpoints:

Feature End Points
~~~~~~~~~~~~~~~~~~

|ftid|

    Returns a single feature based on its ID, which is provided as ``<feature-id>``. This will include all of the attributes specific to the type of feature. Thus, the schema of this resource is variable based on the feature type.

``/features``

|ftbbox|

|ftpoint|

|ftfilter|

    Returns all features that match the given query parameters. Multiple query options can be provided in a single request, however only one of bbox or point should be specified. Query options include:
        
    - ``bbox`` - Only include features which intersect the provided bounding box. The bounding box coordinates should be provided in latitude/longitude: |bboxcoords|
    - ``point`` - Returns the nearest features to the given point.  The point should be provided in latitude/longitude: |latlong|
    - ``max-results`` - The maximum number of features to return.
    - ``types`` - The feature types to query.
    - ``filter`` - A filter string that filters features based on attributes. Can be provided more than once. Multiple filters are combined using logical AND. See below for more details on the filter format.

|ftstype|

|ftsbbox|

|ftspoint|

|ftsfilter|

    Returns a list of the features of the given type. Query options are the same as for the /features endpoint (see above).

``/tiles/z/x/y.mvt``

    Returns a vector tile of all barrier features.

|tilestype|

    Returns a vector tile of all features for the given type.

.. _feature-endpoints-filter:

Filter
~~~~~~

Provides a basic option for filtering features based on the feature attributes.

- If the filter attribute name provided is not valid for the feature type, then an error will be returned (HTTP status code ``400 - Bad Request``)
- Works in addition to the ``bbox`` filter described above (logically ANDed with the bbox)
- Multiple filters can be provided and they will be combined with logical ``AND``, represented by the ``&`` symbol in API requests
- String filters are case insensitive (for ``eq``, ``neq``, ``in`` and ``like`` operators)

Filter request format:

|filterreq|

.. csv-table:: 
    :file: tbl/filter-format.csv
    :widths: 30, 70
    :header-rows: 1

.. admonition:: Example
    
    ``/features/dams?bbox=0,0,1,1&filter=passability_status_code:in:1,2&filter=nhn_workunit_id:eq:08GABX1``

This request will return all dam features with a passability status code of 1 (Barrier) or 2 (Partial Barrier) in the NHN work unit 08GABX1 within the bounding box [(0 0), (1 1)].

.. _feature-endpoints-format:

Format
~~~~~~

The default output format is GeoJSON, however by supplying the format query parameter additional formats are supported.

.. admonition:: Example
    
    ``/features/dams_medium_large?filter=nhn_workunit_id:eq:08GABX1&format=geopackage``

Supported Formats:

The following formats are supported for feature endpoints that return a collection of features.

- ``geopackage`` (or ``gpkg``) - outputs geopackage files
- ``shp`` – outputs shapefile
- ``kml`` – outputs kml file
- ``json``/``geojson`` - outputs geojson (default)

The single feature endpoints only return geojson output.

.. _feature-endpoints-max-features:

Maximum Features
~~~~~~~~~~~~~~~~

A maximum of 15,000 features will be returned.  If a feature api request would result in more than 15,000 features the system will return an error with a HTTP Status code of 403 (Forbidden), and a message telling the user they should add additional filter to limit the query results.

The value ``15000`` is an application parameter and can be modified if required (see ``application.properties`` file).

.. _feature-datasource-endpoint:

Feature Data Source End Point
-----------------------------

-----

|ftdsid|

|ftdsidflds|

    Returns the data source details for each attribute associated with the given feature id.  By default this returns a reduced set of attributes: ``feature id``, ``attribute field``, ``data source name``, and ``data source feature id``. To include the complete set of attributes (``feature id``, ``attribute field``, ``attribute name``, ``data source name``, ``data source date``, ``data source version``, ``ata source feature id``, add the query parameter ``fields=all`` to the request.

.. _feature-datasource-endpoint-format:

Format
~~~~~~

The default output format of this end point is CSV.

JSON format is also supported by providing the ``format=json`` query parameter: |ftdsidjson|.