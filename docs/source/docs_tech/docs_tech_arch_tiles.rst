==================
CHyF REST Services
==================

Feature End Points
------------------

Format
^^^^^^

The only format supported for feature end points is geojson. 

GeoJson feature attributes differ per feature type, but will include some subset of the following:

   - ``id`` - System identifier
   - ``ef_type`` - Code representing the flowapth feature type  
   - ``ef_type_name`` - English description of ef_type. 
   - ``ec_type`` - Code representing the catchment feature type  
   - ``ec_type_name`` - English description of ec_type.
   - ``rank`` - Rank (primary/secondary) associated with flowpath
   - ``length`` - Length of flowpath
   - ``aoi_id`` - CHyF AOI identifier
   - ``aoi_name`` - CHyF AOI name
   - ``ecatchment_id`` - Catchment that contains flowpath
   - ``rivernameid1`` - Primary CHyF name identifier
   - ``rivername1_en`` - English name of feature
   - ``rivername1_fr`` - French name of feature
   - ``rivernameid2`` - Secondary CHyF name identifier
   - ``rivername2_en`` - English name of feature
   - ``rivername2_fr`` - French name of feature
   - ``lakenameid1`` - Primary CHyF lake name identifier
   - ``lakename1_en`` - English name of feature
   - ``lakename1_fr`` - French name of feature
   - ``lakenameid2`` - SEcondary CHyF lake name identifier
   - ``lakename2_en`` - English name of feature
   - ``lakename2_fr`` - French name of feature 



End Points
^^^^^^^^^^
``/chyf-web/features/<uuid>``

   Returns the indiviual feature represented by the uuid. This feature can be flowapth, catchment or shoreline. Nexus not supported as this time.

``/chyf-web/features?name=ABC&max-results=XXX&result-type=[BBOX,ALL,GROUPBYTYPE,GROUPBYNAME]&feature-type[WATERBODY,FLOWPATH,CATCHMENT]&match-type[EXACT,CONTAINS]``

   Returns all features that match the search parameters.
   
    - ``name`` - REQUIRED - The feature name to search for. All searches are case insenstive.
    - ``max-results`` - OPTIONAL - The maximum number of features to return. Default value is 5000.
    - ``match-type`` - OPTIONAL - The type of match to perform. Valid values are EXACT, CONTAINS. Default is CONTAINS. 
    - ``feature-type`` - OPTIONAL - The type of feature to search. Valid values include WATERBODY, FLOWAPTH, CATCHMENT. Can be supplied multiple times to search multiple feature types. If not specified all feature types are searched.
    - ``result-type`` - OPTIONAL - Defines how the results are returned. Valid values are BBOX, ALL, GROUPBYTYPE, GROUPBYNAME. Default is BBOX.
    
         - ``BBOX`` - For each matching name a single feature is returned with the geometry representing the boundary box of all matched features. 
         - ``ALL`` - For each matching name, every database row that is matched is returned as a feature with the original geometry (linestring/polygon).
         - ``GROUPBYTYPE`` - For each matching name, the matching database rows are merged by geometry type. So there will be a maximum of two features returned per name, one for linestring and one for polygons.  
         - ``GROUPBYNAME`` - For each matching names, the matching database rows are merged into a single feature. So one feature will be returned per name, and this feature will contain a geometry collection of linestrings and polygons.



Vector Tile Service
-------------------

Format
^^^^^^

The only format supported for the vector tile services is mvt (mapbox vector tile).

End Points
^^^^^^^^^^

``/chyf-web/tiles/water/{z}/{x}/{y}.{format}``

End point for water features.  This includes single line streams and polygonal waterbody features. The output features include the following attributes:

.. csv-table:: 
    :file: tbl/flow_attributes.csv
    :widths: 30, 70
    :header-rows: 1

``/chyf-web/tiles/ecatchment/{z}/{x}/{y}.{format}``

Contains catchments.  Currently there are no catchments loaded into CHyF database so these vector tiles will be empty. The output features include the following attributes:

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
