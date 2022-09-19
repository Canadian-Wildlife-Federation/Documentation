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

|ftnamefilter|

    Returns all features that match the given query parameters. Multiple query options can be provided in a single request, however only one of bbox or point should be specified. Query options include:
        
    - ``bbox`` - Only include features which intersect the provided bounding box. The bounding box coordinates should be provided in latitude/longitude: |bboxcoords|
    - ``point`` - Returns the nearest features to the given point.  The point should be provided in latitude/longitude: |latlong|
    - ``max-results`` - The maximum number of features to return.
    - ``types`` - The feature types to query.
    - ``filter`` - A filter string that filters features based on attributes. Can be provided more than once. Multiple filters are combined using logical AND. See below for more details on the filter format.
    - ``namefilter`` - A filter string that filters features based on all name attributes (en & fr). Multiple namefilters can be provided. If multiple are provided they are combined using logical OR. See below for more details on namefilter. 

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
    
    ``/features/dams?bbox=0,0,1,1&filter=passability_status_code:in:1,2&filter=nhn_watershed_id:eq:08GABX1``

This request will return all dam features with a passability status code of 1 (Barrier) or 2 (Partial Barrier) in the NHN work unit 08GABX1 within the bounding box [(0 0), (1 1)].

.. note::

    .. container:: toggle

        .. container:: header

            Click the arrow below to expand a **searchable list of filterable attributes** with allowable values and associated codes in brackets, if applicable.

        .. table:: 
            :class: datatable
            :widths: 15, 20, 30, 35

            ========================== ===================================== =============================== ==============================================================================================================================================================================================================================================================
            Feature Type               Attribute Name                        Filter Attribute Name           Allowable Values (Code)
            ========================== ===================================== =============================== ==============================================================================================================================================================================================================================================================
            Dams, waterfalls           Passability status                    passability_status_code         barrier(1), partial barrier(2), passable(3), unknown(4)
            Dams                       Operating status                      operating_status_code           abandoned/orphaned(1), active(2), decommissioned/removed(3), retired/closed(4), unknown(5), remediated(6)
            Dams                       Ownership type                        ownership_type_code             charity/non-profit(1), federal(2), municipal(3), private(4), provincial/territorial(5), other(6), unknown(7), indigenous(8)
            Dams                       Dam use                               use_code                        irrigation(1), hydroelectricity(2), water supply(3), flood control(4), recreation(5), navigation(6), fisheries(7), pollution control(8), invasive species control(9), other(10), unknown (11)
            Dams                       Dam size                              size_class_code                 small(1), medium(2), large(3), unknown(4)
            Dams, waterfalls, fishways Province/territory name               province_territory_code         alberta(ab), british columbia(bc), manittoba(mb), new brunswick(nb), newfoundland and labrador(nl), nova scotia(ns), northwest territories(nt), nunavut(nu), ontario(on), prince edward island(pe), quebec(qc), saskatchewan(sk), united states(us), yukon(yt)         
            Dams                       Dam height (m)                        height_m                        n/a
            Dams                       Construction year                     construction_year               n/a
            Dams                       Upstream passage type                 up_passage_type_code            denil(1), nature-like fishway(2), pool and weir(3), pool and weir with hole(4), trap and truck(5), vertical slot(6), other(7), no structure(8), unknown(9)
            Dams                       Dam function                          function_code                   storage(1), diversion(2), detention(3), debris(4), saddle(6), hydro - closed-cycle pumped storage(7), hydro - conventional storage(8), hydro - open-cycle pumped storage(9), hydro - run-of-river(10), hydro - tidal(11), other(12), unknown(13)
            Dams                       Use irrigation                        use_irrigation_code             main(1), major(2), secondary(3)
            Dams                       Use hydroelectricity                  use_electricity_code            main(1), major(2), secondary(3)
            Dams                       Use water supply                      use_supply_code                 main(1), major(2), secondary(3)
            Dams                       Use flood control                     use_floodcontrol_code           main(1), major(2), secondary(3)
            Dams                       Use recreation                        use_recreation_code             main(1), major(2), secondary(3)
            Dams                       Use navigation                        use_navigation_code             main(1), major(2), secondary(3)
            Dams                       Use fisheries                         use_fish_code                   main(1), major(2), secondary(3)
            Dams                       Use pollution control                 use_pollution_code              main(1), major(2), secondary(3)
            Dams                       Use invasive species                  use_invasivespecies_code        main(1), major(2), secondary(3)
            Dams                       Use other                             use_other_code                  main(1), major(2), secondary(3)
            Dams                       Construction type                     construction_type_code          arch(1), buttress(2), earth(3), gravity(4), multiple arch(5), rock(6), steel(7), timber(8), unknown(9), other(10), concrete(11), masonry(12)
            Dams                       Spillway type                         spillway_type_code              combined(1), free(2), gated(3), other(4), none(5), unknown(6)
            Dams                       Turbine type                          turbine_type_code               cross-flow(1), francis(2), kaplan(3), pelton(4), unknown(5), other(6)
            Dams                       Downstream passage route              down_passage_route_code         bypass(1), river channel(2), spillway(3), turbine(4)
            Dams, waterfalls, fishways Completeness level                    complete_level_code             unverified(1), minimal(2), moderate(3), complete(4)
            Dams                       Lake control                          lake_control_code               yes(1), enlarged(2), maybe(3)
            Dams                       Dam condition                         condition_code                  good(1), fair(2), poor(3), unreliable(4)
            Waterfalls                 Waterfall height                      fall_height_m                   n/a
            Fishways                   Fishway type                          fishpass_type_code              denil(1), nature-like fishway(2), pool and weir(3), pool and weir with hole(4), trap and truck(5), vertical slot(6), other(7), no structure(8), unknown(9)
            Fishways                   Year constructed                      year_constructed                n/a
            Dams, waterfalls, fishways Municipality                          municipality                    n/a
            Dams                       Dam name (English)                    dam_name_en                     n/a
            Dams                       Dam name (French)                     dam_name_fr                     n/a
            Dams, waterfalls, fishways Waterbody name (English)              waterbody_name_en               n/a
            Dams, waterfalls, fishways Waterbody name (French)               waterbody_name_fr               n/a
            Dams, waterfalls, fishways Barrier/system Identifier             cabd_id                         n/a
            Dams                       Reservoir name (English)              reservoir_name_en               n/a
            Dams                       Reservoir name (French)               reservoir_name_fr               n/a
            Dams, waterfalls, fishways NHN Watershed ID                      nhn_watershed_id                n/a
            Dams, waterfalls, fishways Used for Network Analysis             use_analysis                    true, false
            Waterfalls                 Waterfall name (English)              fall_name_en                    n/a
            Waterfalls                 Waterfall name (French)               fall_name_fr                    n/a
            Dams                       Generating capacity (MWh)             generating_capacity_mwh         n/a
            Dams                       Federal compliance status             federal_compliance_status       n/a
            Dams                       Provincial compliance status          provincial_compliance_status    n/a
            Dams, fishways             Operating notes                       operating_notes                 n/a 
            Dams                       Removed year                          removed_year                    n/a
            Dams                       Assessment schedule                   assess_schedule                 n/a 
            Dams                       Expected life (years)                 expected_life                   n/a 
            Dams                       Next maintenance date                 maintenance_next                n/a
            Dams                       Last maintenance date                 maintenance_last                n/a 
            Dams                       Dam length (m)                        length_m                        n/a 
            Dams                       Spillway Capacity (m3/s)              spillway_capacity               n/a 
            Dams                       Reservoir present                     reservoir_present               true, false
            Dams                       Reservoir area(km2)                   reservoir_area_skm              n/a
            Dams                       Reservoir depth (m)                   reservoir_depth_m               n/a 
            Dams                       Storage Capacity (mcm)                storage_capacity_mcm            n/a 
            Dams                       Average rate of discharge (L/s)       avg_rate_of_discharge_ls        n/a 
            Dams                       Degree of regulation (%)              degree_of_regulation_pc         n/a 
            Dams                       Provincial flow requirements (m3/s)   provincial_flow_req             n/a 
            Dams                       Federal flow requirements (m3/s)      federal_flow_req                n/a 
            Dams                       Catchment Area (km2)                  catchment_area_skm              n/a 
            Dams                       Hydro peaking system                  hydro_peaking_system            n/a 
            Dams                       Number of turbines                    turbine_number                  n/a
            Dams, waterfalls, fishways Last modified                         last_modified                   n/a 
            Dams, waterfalls, fishways Comments                              comments                        n/a 
            Dams                       Upstream linear length (km)           upstream_linear_km              n/a 
            Dams                       Facility name (English)               facility_name_en                n/a 
            Dams                       Facility name (French)                facility_name_fr                n/a 
            Fishways                   Monitoring equipment                  monitoring_equipment            n/a 
            Fishways                   Architect                             architect                       n/a 
            Fishways                   Contracted by                         contracted_by                   n/a 
            Fishways                   Constructed by                        constructed_by                  n/a 
            Fishways                   Plans held by                         plans_held_by                   n/a 
            Fishways                   Purpose                               purpose                         n/a 
            Fishways                   Dam Identifier                        dam_id                          n/a 
            Fishways                   Designed based on biology             designed_on_biology             n/a 
            Fishways                   Fishway length (m)                    length_m                        n/a 
            Fishways                   Elevation (m)                         elevation_m                     n/a 
            Fishways                   Gradient (%)                          gradient                        n/a 
            Fishways                   Depth (m)                             depth (m)                       n/a 
            Fishways                   Entrance location                     entrance_location_code          midstream(1), bank(2)
            Fishways                   Entrance position                     entrance_position_code          bottom(1), surface(2), bottom and surface(3), mid-column(4)
            Fishways                   Is modified                           modified                        n/a 
            Fishways                   Modification year                     modification_year               n/a 
            Fishways                   Modification purpose                  modification_purpose            n/a 
            Fishways                   Structure name (English)              structure_name_en               n/a 
            Fishways                   Structure name (French)               structure_name_fr               n/a 
            Fishways                   Operated by                           operated_by                     n/a 
            Fishways                   Operation period                      operation_period                n/a 
            Fishways                   Has evaluating studies                has_evaluating_studies          true, false
            Fishways                   Nature of evaluating studies          nature_of_evaluation_studies    n/a 
            Fishways                   Engineering notes                     engineering_notes               n/a 
            Fishways                   Maximum Velocity of Water Flow (m/s)  max_fishway_velocity_ms         n/a
            Fishways                   Average Velocity of Water Flow (m/s)  mean_fishway_velocity_ms        n/a 
            Fishways                   Attraction Estimate (%)               estimate_of_attraction_pct      n/a 
            Fishways                   Transit Success Estimate (%)          estimate_of_passage_success_pct n/a
            Fishways                   Evaluating study/reference identifier fishway_reference_id            n/a
            Fishways                   River name (English)                  river_name_en                   n/a
            Fishways                   River name (French)                   river_name_fr                   n/a
            ========================== ===================================== =============================== ==============================================================================================================================================================================================================================================================
    
.. _feature-endpoints-namefilter:


Name Filter
~~~~~~~~~~~

Provides an option for filtering features based on all the name attributes associated with the feature types. The “name” attributes are different for different features type and specified by the database metadata. Generally it will just include the english and french names, but it may include other fields as well.
- Works in addition to the ``bbox`` filter described above (logically ANDed with the bbox)
- Multiple filters can be provided and they will be combined with logical ``OR``, represented by the ``&`` symbol in API requests
- All comparisons are case insensitive (holden = Holden = HOLDEN) 

Name Filter request format:

|namefilterreq|

.. csv-table:: 
    :file: tbl/namefilter-format.csv
    :widths: 30, 70
    :header-rows: 1

.. admonition:: Example
    
    ``/features/dams?bbox=0,0,1,1&filtername=like:holden``

This will return all dam features within the bounding box [(0 0), (1 1)] and an english or french name like “holden”.

.. _feature-endpoints-format:

Format
~~~~~~

The default output format is GeoJSON, however by supplying the format query parameter additional formats are supported.

.. admonition:: Example
    
    ``/features/dams_medium_large?filter=nhn_watershed_id:eq:08GABX1&format=geopackage``

Supported Formats:

The following formats are supported for feature endpoints that return a collection of features.

- ``geopackage`` (or ``gpkg``) - outputs geopackage files
- ``shp`` – outputs shapefile
- ``kml`` – outputs kml file
- ``json``/``geojson`` - outputs geojson (default)
- ``csv`` – outputs csv file 

The single feature endpoints only return geojson output.

.. _feature-endpoints-locale:

Locale
~~~~~~

Results are supported in both English and French. The language returned is determined by the ``Accept-Language`` header. Default is English.


.. _feature-endpoints-max-features:

Maximum Features
~~~~~~~~~~~~~~~~

A maximum of 15,000 features will be returned.  If a feature api request would result in more than 15,000 features the system will return an error with a HTTP Status code of 403 (Forbidden), and a message telling the user they should add additional filter to limit the query results.

The value ``15000`` is an application parameter and can be modified if required (see ``application.properties`` file).

.. _feature-endpoints-feature-totals:

Feature API Result Totals
~~~~~~~~~~~~~~~~~~~~~~~~~

The Feature API response includes a Content-Range header that summarizes the total number of features that match the filters vs the total number of features returned. This can be used along with the max-results parameter to access the number of features that match a filter without having to load all features.

``http://localhost:8080/features/waterfalls?filter=fall_name_en:like:fall&max-results=5``
    
The API call will return 5 features (max-results=5). However the response header will also include a Content-Range header that looks like:  ``Content-Range: features 0-5/65``. The 0-5 tells us the only the first 5 features are included in the results, the 65 tells us a total of 65 features matched the provided filters.

Therefore, if you want to just get the total feature count and no features you can use a max-results=0 parameter:

``http://localhost:8080/features/waterfalls?max-results=0``

This will return an empty feature collection, but the response headers will include Content-Range: ``Content-Range: features 0-0/729``.  Which tells you there are 729 waterfalls in the database.

    

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


.. _feature-vector-tile-service

Vector Tile Service
-------------------

-----

The vector tile service creates vector tiles for the barrier feature types.

Format
~~~~~~

The only format supported for the vector tile services is mvt (mapbox vector tile).

End Point
~~~~~~~~~

``http://localhost:8080/tiles/{type}/{z}/{x}/{y}.{format}``

``type`` must be a valid feature type. 

The attributes included in the vector tile are those whose "include_vector_tile" value in the feature_type_metadata table are true.
