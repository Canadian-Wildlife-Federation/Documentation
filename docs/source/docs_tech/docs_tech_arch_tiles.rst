======================
CHyF REST API Services
======================

Overview
--------

-----

Projection
~~~~~~~~~~

All coordinates are returned in latitude/longitude (EPSG:4617).

Max Features
~~~~~~~~~~~~

For all the feature API end points below, the application returns a maximum of 5000 features. This is configurable and may be modified if required.

.. note::
    The data available through the CHyF end points at this time only includes the data available for our 8 pilot regions - this extent can be seen on the CABD web tool’s ‘Hydro Networks’ layer. The CABD team is hard at work preparing new hydro network data to be added in the future!

API Specification
~~~~~~~~~~~~~~~~~

The latest Open API v3 specification can be found on the server:

https://chyf-web.azurewebsites.net/chyf-web/v3/api-docs.yaml (YAML)

https://chyf-web.azurewebsites.net/chyf-web/v3/api-docs (JSON)

Feature End Points
------------------

-----

Format
~~~~~~

The base API server for the CHyF end points is https://chyf-web.azurewebsites.net/chyf-web/

The only format supported for feature end points is GeoJSON. 

GeoJSON feature attributes differ per feature type, but will include some subset of the following:

* ``id`` - System identifier

* ``ef_type`` - Code representing the flowpath feature type  

* ``ef_type_name`` - English description of ef_type. 

* ``ec_type`` - Code representing the catchment feature type  

* ``ec_type_name`` - English description of ec_type.

* ``rank`` - Rank (primary/secondary) associated with flowpath

* ``length`` - Length of flowpath

* ``aoi_id`` - CHyF AOI identifier

* ``aoi_name`` - CHyF AOI name

* ``ecatchment_id`` - Catchment that contains flowpath

* ``rivernameid1`` - Primary CHyF name identifier

* ``rivername1_en`` - English name of feature

* ``rivername1_fr`` - French name of feature

* ``rivernameid2`` - Secondary CHyF name identifier

* ``rivername2_en`` - English name of feature

* ``rivername2_fr`` - French name of feature

* ``lakenameid1`` - Primary CHyF lake name identifier

* ``lakename1_en`` - English name of feature

* ``lakename1_fr`` - French name of feature

* ``lakenameid2`` - Secondary CHyF lake name identifier

* ``lakename2_en`` - English name of feature

* ``lakename2_fr`` - French name of feature 

Find a single feature
~~~~~~~~~~~~~~~~~~~~~

|chyfuuid|

Returns the individual feature represented by the uuid. This feature can be a flowpath, catchment or shoreline. Please note that returning nexus features is not supported at this time.

Search by feature name or type (single or multiple features)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

|singlemultisearch|

Returns all features that match the search parameters.
   
* ``name`` - REQUIRED - The feature name to search for. All searches are case insensitive.

* ``max-results`` - OPTIONAL - The maximum number of features to return. Default value is 5000.

* ``result-type`` - OPTIONAL (but recommended) - Defines how the results are returned. Valid values are BBOX, ALL, GROUPBYTYPE, GROUPBYNAME. Default is BBOX. We recommend testing the same query with different ``result-type`` parameters to identify the ``result-type`` that works best for your needs.  
  
  * ``BBOX`` - For each matching name, a single feature is returned with the geometry representing the boundary box of all matched features.

  * ``ALL`` - For each matching name, every database row that is matched is returned as a feature with the original geometry (linestring/polygon).

  * ``GROUPBYTYPE`` - For each matching name, the matching database rows are merged by geometry type. So there will be a maximum of two features returned per name, one for linestrings and one for polygons.  

  * ``GROUPBYNAME`` - For each matching names, the matching database rows are merged into a single feature. So one feature will be returned per name, and this feature will contain a geometry collection of linestrings and polygons.

* ``match-type`` - OPTIONAL - The type of match to perform. Valid values are EXACT, CONTAINS. Default is CONTAINS. 

* ``feature-type`` - OPTIONAL - The type of feature to search. Valid values include WATERBODY, FLOWPATH, CATCHMENT. Can be supplied multiple times to search multiple feature types. If not specified, all feature types are searched.

Examples
++++++++

Returns information for a single feature with an id of ‘f2e7c275-5425-4d19-9db5-d6916b940799’:
``https://chyf-web.azurewebsites.net/chyf-web/features/f2e7c275-5425-4d19-9db5-d6916b940799``

Returns all database rows for any feature type that match the name ‘South Berland’:
``https://chyf-web.azurewebsites.net/chyf-web/features?name=South+Berland&result-type=ALL``

Returns a maximum of 5 database rows for any feature type that match the name ‘Berland’ (case insensitive):
``https://chyf-web.azurewebsites.net/chyf-web/features?name=Berland&result-type=ALL&max-results=5``

Returns a maximum of 5 database rows for flowpaths that match the name ‘Berland’ (case insensitive):
``https://chyf-web.azurewebsites.net/chyf-web/features?name=Berland&result-type=ALL&max-results=5&feature-type=FLOWPATH``


Network Exports
---------------

-----

CHyF network datasets can be extracted using the graph API. This export includes all flowpaths, nexuses, and catchments for the requested area with the appropariate network information included on the features.
  
Format
~~~~~~

Geopackage is the only supported format for network exports.

API
~~~

Network exports are limited to 500,000 flowpath features. The area of interest can be specified by supplying a bounding box or one or more AOIs.

* ``aoi`` - OPTIONAL - A common delimited list of AOI short names
* ``bbox`` - OPTIONAL - The extent of features to include in export: 'minlong,minlat,maxlong,maxlat'

At least one, either aoi or bbox, must be supplied.

Example
~~~~~~~

Returns graph export for AOI 02OJ000:
``https://chyf-web.azurewebsites.net/chyf-web/graph?aoi=02OJ000``
  


Vector Tile Service
-------------------

-----

Format
~~~~~~

The only format supported for the vector tile services is mvt (mapbox vector tile).

End Points
~~~~~~~~~~

``/chyf-web/tiles/water/{z}/{x}/{y}.{format}``

End point for water features.  This includes single-line streams and polygonal waterbody features. The output features include the following attributes:

.. csv-table:: 
    :file: tbl/flow_attributes.csv
    :widths: 30, 70
    :header-rows: 1

``/chyf-web/tiles/ecatchment/{z}/{x}/{y}.{format}``

Contains catchments.  Currently there are no catchments loaded into CHyF database, so these vector tiles will be empty. The output features include the following attributes:

.. csv-table:: 
    :file: tbl/catch_attributes.csv
    :widths: 30, 70
    :header-rows: 1

``/chyf-web/tiles/nhnworkunit/{z}/{x}/{y}.{format}``

End point for NHN work unit polygonal features. The output features include the following attributes:

.. csv-table:: 
    :file: tbl/wu_attributes.csv
    :widths: 30, 70
    :header-rows: 1
