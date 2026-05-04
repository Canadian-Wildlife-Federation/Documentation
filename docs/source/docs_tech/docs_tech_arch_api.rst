.. raw:: html

    <style> .green {color: #2a997d} </style>

.. role:: green    


.. _cabd-rest-services:

CABD REST API Services
######################

.. _api-overview:

Overview
********

-----

.. _api-projection:

Projection
==========

All coordinates are returned in latitude/longitude (EPSG:4617).

.. _api-max-features:

Max Features
============

For all the feature API end points below, the application returns a maximum of 55,000 features. This is configurable and may be modified if required.

.. _api-specification:

API Specification
=================

The latest Open API v3 specification can be found on the server:

https://cabd-web.azurewebsites.net/cabd-api/v3/api-docs.yaml (YAML)

https://cabd-web.azurewebsites.net/cabd-api/v3/api-docs (JSON)

.. _api-endpoints:

API End Points
**************

-----

The base API server for the CABD end points is: ``https://cabd-web.azurewebsites.net/cabd-api``.

.. note::
    
    The API requests detailed in the following sections may contain one or more parameters (enclosed in chevrons, i.e. < >, and accentuated with the colour :green:`green`). If an API request is being made using one or more of the parameters listed, the chosen parameter must be replaced with an appropriate pre-defined value. 
    
    **Example:**

    |requestex1|


.. _feature-type-endpoints:

Feature Type Metadata End Points
================================

The output format of all Feature Type End points is ``JSON``.

Existing feature types are: ``barriers``, ``dams``, ``waterfalls``, ``fishways``, ``modelled crossings``, and ``stream crossings``. See :ref:`Implemented Feature Model<implemented-feature-model>` for definitions of each feature type.

``/features/types/``

    Returns the list of feature types. Each feature type object includes a URL that lists the metadata for that feature type and a URL to list all features for that time.  
    
    .. note::
        
        Some types may be super types that contain data from a collection of other types (e.g., barriers is a super type that contains dam and waterfall features).

|fttype|

    Returns a description of the feature type. This description includes all attributes, names, and other metadata associated with the feature type. In addition, the metadata includes display details for attributes, including the details of which attributes should be included in the “simple” display and which included in the “all” attributes display.

    .. admonition:: Example
        
        ``https://cabd-web.azurewebsites.net/cabd-api/features/types/dams`` returns a ``JSON`` with the description of the ``dams`` feature type.

.. _feature-endpoints:

Feature End Points
==================

|ftid|

    Returns a single feature based on its ID, which is provided as ``<feature-id>``. This will include all of the attributes specific to the type of feature. Therefore, the schema of this resource is variable based on the feature type.

``/features``

|ftbbox|

|ftpoint|

|ftfilter|

|ftnamefilter|

    Returns all features that match the given query parameters. Multiple query options can be provided in a single request, however only one of ``bbox`` or ``point`` should be specified. Query options include:
        
    - ``bbox`` - Only include features which intersect the provided bounding box. The bounding box coordinates should be provided in latitude/longitude: |bboxcoords|
    - ``point`` - Returns the nearest features to the given point.  The point should be provided in latitude/longitude: |latlong|
    - ``max-results`` - The maximum number of features to return.
    - ``types`` - The feature types to query.
    - ``filter`` - A filter string that filters features based on attributes. Can be provided more than once. Multiple filters are combined using logical AND. See below for more details on the filter format.
    - ``namefilter`` - A filter string that filters features based on all name attributes (en & fr). Multiple namefilters can be provided. If multiple are provided, they are combined using logical OR. See below for more details on namefilter. 

|ftstype|

|ftsbbox|

|ftspoint|

|ftsfilter|

    Returns a list of the features of the given type (e.g., dams, waterfalls, etc.). Query options are the same as for the ``/features`` endpoint (see above).

``/tiles/z/x/y.mvt``

    Returns a vector tile of all barrier features.

|tilestype|

    Returns a vector tile of all features for the given type.

Feature End Point Examples
--------------------------

Return all dam features in the NHN watershed 02OE000:
``https://cabd-web.azurewebsites.net/cabd-api/features/dams?filter=nhn_watershed_id:eq:02OE000``

Return all fishway features within the bounding box [(-95.16,41.66), (-74.34,56.86)]:
``https://cabd-web.azurewebsites.net/cabd-api/features/fishways?bbox=-95.16,41.66,-74.34,56.86``

Return all waterfall features in Quebec:
``https://cabd-web.azurewebsites.net/cabd-api/features/waterfalls?filter=province_territory_code:eq:qc``

Return all fishway features that are associated with a dam structure:
``https://cabd-web.azurewebsites.net/cabd-api/features/fishways?filter=dam_id:notnull:``

Return all dam features with a use code of 2 (Hydroelectricity):
``https://cabd-web.azurewebsites.net/cabd-api/features/dams?filter=use_code:eq:2``

Return all dam features with a use code of 2 (Hydroelectricity) and a pool and weir fishway (up_passage_type_code = 3):
``https://cabd-web.azurewebsites.net/cabd-api/features/dams?filter=use_code:eq:2&filter=up_passage_type_code:eq:3``

.. _feature-endpoints-filter:

Filter
------

Provides a basic option for filtering features based on the feature attributes.

- If the filter attribute name provided is not valid for the feature type, then an error will be returned (HTTP status code ``400 - Bad Request``)
- Works in addition to the ``bbox`` filter described above (logically ANDed with the bbox)
- Multiple filters can be provided, and they will be combined with logical ``AND``, represented by the ``&`` symbol in API requests
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

        .. container:: header

            For a list of attributes and coded values, visit the :ref:`Data Catalogue <data-catalogue>`

            Please note that filters on any attributes with coded values need to specify the code instead of the associated name (i.e., a filter on the operating_status_code attribute should specify a value of 1 for abandoned/orphaned dams: ``&filter=operating_status_code:eq:1``).

.. _feature-endpoints-namefilter:


Name Filter
-----------

Provides an option for filtering features based on all the name attributes associated with the feature types. The “name” attributes are different for each feature type and specified by the database metadata. Generally, name attributes will just include the English and French names for a feature, but may include other fields as well.

The name filter works in addition to the ``bbox`` filter described above (logically ANDed with the bbox). Multiple name filters can be provided and they will be combined with logical ``OR``, represented by the ``&`` symbol in API requests. All comparisons are case insensitive (holden = Holden = HOLDEN).

Name Filter request format:

|namefilterreq|

.. csv-table:: 
    :file: tbl/namefilter-format.csv
    :widths: 30, 70
    :header-rows: 1

.. admonition:: Example
    
    ``/features/dams?bbox=0,0,1,1&filtername=like:holden``

This will return all dam features within the bounding box [(0 0), (1 1)] and an english or french name like “holden”.

Examples
^^^^^^^^

Return all dam features with an English or French name like “holden” (case insensitive):
``https://cabd-web.azurewebsites.net/cabd-api/features/dams?&namefilter=like:holden``

Return all dam features with an English or French name like “churchill falls” (case insensitive):
``https://cabd-web.azurewebsites.net/cabd-api/features/dams?&namefilter=like:churchill+falls``

Return all dam features with an English or French name like “churchill falls” or “revelstoke” (case insensitive):
``https://cabd-web.azurewebsites.net/cabd-api/features/dams?&namefilter=like:churchill+falls&namefilter=like:revelstoke``

Return all fishway features with a structure name like “grand falls” (case insensitive):
``https://cabd-web.azurewebsites.net/cabd-api/features/fishways?&namefilter=like:grand+falls``

.. _feature-endpoints-format:

Format
------

The default output format is GeoJSON, but additional formats can be returned by supplying the format query parameter. The format parameter can be combined with the attribute filters and name filters described above.

Examples
^^^^^^^^
    
Return all dam features in the NHN watershed 08GABX1 in geopackage format:
``https://cabd-web.azurewebsites.net/cabd-api/features/dams?filter=nhn_watershed_id:eq:08GABX1&format=geopackage``

Return all dam features with a use code of 2 (Hydroelectricity) in geopackage format:
``https://cabd-web.azurewebsites.net/cabd-api/features/dams?filter=use_code:eq:2&format=geopackage``

Supported Formats
^^^^^^^^^^^^^^^^^

The following formats are supported for feature endpoints that return a collection of features.

- ``geopackage``/ ``gpkg`` - outputs geopackage file
- ``shp`` – outputs shapefile
- ``kml`` – outputs kml file
- ``json``/ ``geojson`` - outputs GeoJSON (default)
- ``csv`` – outputs csv file 

The single feature endpoints only return GeoJSON output.

All exports (except csv) include data metadata that includes the feature type version number, download datetime, and license information. For json, this is included in the feature collection metadata; for shp, an additional csv metadata file is included in the zip package; for kml, it is included as "extendedData"; and for geopackage, it is included as an additional non-spatial metadata layer.  

.. note::

   The best way to download data for multiple feature types using the API is to use the ``/features/<type>``
   
   While the /features/ endpoint will return features from multiple feature types, the list of attributes returned are very limited compared to the list of attributes returned when the ``<type>`` is specified.

.. _feature-endpoints-locale:

Locale
------

Results are supported in both English and French. The language returned is determined by the ``Accept-Language`` header. Default is English.


.. _feature-endpoints-max-features:

Maximum Features
----------------

A maximum of 55,000 features will be returned.  If a feature API request would result in more than 55,000 features, the system will return an error with a HTTP Status code of 403 (Forbidden), and a message telling the user they should add additional filters to limit the query results.

The value ``55000`` is an application parameter and can be modified if required (see ``application.properties`` file).

.. _feature-endpoints-feature-totals:

Feature API Result Totals
-------------------------

The Feature API response includes a Content-Range header that summarizes the total number of features that match the filters vs the total number of features returned. This can be used along with the max-results parameter to access the number of features that match a filter without having to load all features.

Example
^^^^^^^

``https://cabd-web.azurewebsites.net/cabd-api/features/waterfalls?filter=fall_name_en:like:fall&max-results=5``
    
The API call will return 5 features (max-results=5). However, the response header will also include a Content-Range header that looks like:  ``Content-Range: features 0-5/65``. The 0-5 tells us the only the first 5 features are included in the results, the 65 tells us a total of 65 features matched the provided filters.

Therefore, if you want to just get the total feature count and no features, you can use a max-results=0 parameter:

``https://cabd-web.azurewebsites.net/cabd-api/features/waterfalls?max-results=0``

This will return an empty feature collection, but the response headers will include Content-Range: ``Content-Range: features 0-0/729``, which tells you there are 729 waterfalls in the database.

    

.. _feature-datasource-endpoint:

Feature Data Source End Point
=============================

-----

|ftdsid|

|ftdsidflds|

    Returns the data source details for each attribute associated with the given feature id.  
    
    For features types that are not site/structure types by default this returns a reduced set of attributes: ``feature id``, ``attribute field``, ``data source name``, and ``data source feature id``. To include the complete set of attributes (``feature id``, ``attribute field``, ``attribute name``, ``data source name``, ``data source date``, ``data source version``, ``data source feature id``, add the query parameter ``fields=all`` to the request.

    For site/structure feature types the fields returned are attribute_name, datasource_name and assessment type. The datasource name is the assessment identifier. A link to the full assessment details is included at the top of the results for all assessment data sources.

.. _feature-datasource-endpoint-format:

Format
------

The default output format of this end point is CSV.

JSON format is also supported by providing the ``format=json`` query parameter: |ftdsidjson|

.. _submit-feature-update-end-point:

Feature Update End Point
========================

-----

This end point allows users to submit feature update requests. These requests are logged in the database and reviewed by CABD administrators before updates are applied to the feature.


* URL: /features/<feature-id>
* METHOD: PUT
* CONTENT-TYPE: application-json
* BODY: json string containing feature update information
 * name, email, and description are required
 * organization, mailinglist, and datasource are optional
 * if a contact exists in the system with the given email then the name, description, organization, and mailinglist properties are overwritten with the new properties (if provided)

::

   {
     "name": "First Last", 
     "email": "first.last@host.com", 
     "organization": "<Optional>", 
     "mailinglist": <true|false>, 
     "description": "Description of feature update", 
     "datasource": "Optional. Information about source of data update"
   }


.. _submit-contact-end-point:

Contact End Point
=================

-----

This end point allows users to create a new contact or update an existing contact. Contacts are identified by their email address. If a contact already exists in the database, it will be updated with the information supplied. If an optional field is not provided, that field is not updated.


* URL: /contacts
* METHOD: PUT
* CONTENT-TYPE: application-json
* BODY: json string containing feature update information
 * name and email are required 
 * organization and mailinglist are optional

::

   {
     "name": "First Last", 
     "email": "first.last@host.com", 
     "organization": "<Optional>", 
     "mailinglist": <true|false>
   }


.. _feature-vector-tile-service:

Vector Tile Service
===================

-----

The vector tile service creates vector tiles for the barrier feature types.

Format
------

The only format supported for the vector tile services is mvt (mapbox vector tile).

End Point
---------

``https://cabd-web.azurewebsites.net/cabd-api/tiles/{type}/{z}/{x}/{y}.{format}``

``type`` must be a valid feature type. 

The attributes included in the vector tile are those whose "include_vector_tile" value in the feature_type_metadata table are true.


Assessment End Points

-----

These end points allow users to access short form and long for assessment data for individual assessments or cabd features.

Assessment Details
------

``/assessments/<assessment-id>``

    Returns the complete details of the given assessment. The exact json fields returned depend on the assessment type.


``/assessments/cabd/<feature-id>``

    Returns an array of all assessments associated with the given cabd feature id. If there are no assessments an empty array is returned.

Assessment Type Details
------

``/assessments/types``

    Returns a list of the assessment types supported by the system.

``/assessments/types/<assessment-type>``

    Returns a description of all the fields associated with the provided assessment type.
Community Data

-----

The community data API supports the collection of data from community users. This API was developed to be used in conjunction with the Mobile Data Application. 

The data submitted to the community API immediately gets written to a community data table without 
any validation or processing.  A separate job takes data from this community data table, 
parses the feature type, photos, user information and stores the parsed data in the appropriate feature staging 
table. Any features provided without a cabd_id are assigned a new one. 
Once in the feature staging table it is up to Data Reviews to review the data and update the appropriate CABD features.

Authentication
-------------------------------

The entire community data api is secured behind Auth0. All requests must include a valid JSON Web Token (JWT) supplied as a bearer token in the ``Authorization`` header. Request that omit the header, present a malformed or invalid token will be rejected with an HTTP ``401 Unauthorized`` response.


Submit Community Data End Point
-------------------------------

This end point allows user to submit new community data.

* URL: /community
* METHOD: POST
* CONTENT-TYPE: application/geo+json 
* AUTHORIZATION: Bearer <token>
* BODY: Either a single GeoJson feature or array of GeoJson features. At a minimum each GeoJson feature needs a feature_type and valid geometry.
A cabd_id property should be provided if an existing feature is updated. All other properties are retained and available to the data reviewer. All photo data should be submitted as base64 encoded png images. 

::

   { 
     "type": "Feature", 
     "geometry": { 
      "type": "Point", 
      "coordinates": [ -123.36089100000027, 48.46620700000054] 
     }, 
     "properties": { 
      "feature_type": "dams",  
      "cabd_id": "F515F5FB-2519-400F-A258-EEF7219C40BE", 
      "dropImage": "<imagedata>", 
      "streamFlowing": "true", 
      "downstreamImage": "<imagedata>", 
      "notes": "", 
      "passability_status": "passable",
      "structureFlowing": "true", 
      "blockagesOther": "false", 
      "blockagesFencing": "false", 
      "blockageImage": "<imagedata>", 
      "selectedType": "bridge", 
      "physicalBlockages": "true", 
      "blockageDebris": "false", 
      "outletDrop": ">20", 
      "blockagesDeformation": "true", 
      "lat": 48.46620700000054, 
      "blockagesDam": "true", 
      "lng": -123.36089100000027 
     } 
   } 

* RETURN: JSON containing a unique identifer

::

   { 
     "id": "e217b9b7-3f2e-4fe4-8b7b-61e09e2cff98" 
   } 


This unique identifier can be used to determine if there was a problem with the submission.
The end point ``/community/status/<uuid>`` will return 404 (not found) if the data was processed correctly or 200 with some error information if there was an issue with processing the submitted data (or processing is still in progress). This was written strictly for testing the submission API and may be removed at a future date. 
This id is not used anywhere else in the system.
 
List Community Data Features
-----------------------

This api returns all the features submitted to the community data with a limited set of attributes


``https://cabd-web.azurewebsites.net/community/data?fromdate=2026-04-28T20:58:28Z&todate=2026-04-28T20:58:28Z&max-results=20``

``https://cabd-web.azurewebsites.net/community/data/{type}?fromdate=2026-04-28T20:58:28Z&todate=2026-04-28T20:58:28Z&max-results=20``

``type`` must be a valid feature type. 

    Returns all features that match the given query parameters. Query options include:
        
    - ``fromdate`` - The earliest upload date to return results for. ISO 8601 UTC date/time. Date only (not time) is also accepted. Exclusive.
    - ``todate`` - The latest upload date to return results for. ISO 8601 UTC date/time. Date only (not time) is also accepted. Exclusive.
    - ``max-results`` - The maximum number of features to return (if not provided will default to system maximum)
    

The attributes included in the response are:
 - id - unique id for the community feature. Not related to the id returned by the upload API
 - cabd_id - the cabd_id 
 - feature_type - the feautre type
 - is_owner - if this feature was submitted by the current user or not
 - uploaded_datetime - the date/time the feature was uploaded


::

   {
     "type": "FeatureCollection",
     "crs": "EPSG:4617",
     "features": [
       {
          "type": "Feature",
          "geometry": {
            "type": "Point",
            "coordinates": [125.6,10.1]
          },
          "properties": {
            "cabd_id": "8c7fe8c2-0890-4d65-884c-ec8087368800",
            "feature_type": "dams",
            "is_owner": true,
            "uploaded_datetime": "2026-04-24T22:25:56.226352Z",
            "id": "0e0170ab-03c6-4dc8-988c-27eba419f82f"
         }
       },
       {
          "type": "Feature",
          "geometry": {
            "type": "Point",
            "coordinates": [125.6,10.1]
          },
          "properties": {
            "cabd_id": "2c4693c1-f4f8-4686-9314-ecc074694a29",
            "feature_type": "stream_crossings"
            "is_owner": false,
            "uploaded_datetime": "2026-04-22T21:05:23.3421Z",
            "id": "fa44eff1-2e9f-4266-86ea-94679e991d9a"
          }
        } 
      ]    
    }  
   
 
Community Feature Details
-----------------------

This api returns the details of an individual community feature


``https://cabd-web.azurewebsites.net/community/data/{id}``

``id`` is the community feature id (the id property of the community feature returned by the /community/data api )

The results are provided as a geojson feature will all of the original properties provided in the community data with the following modifications:
 - image data is removed and replaced with a filename. In the future this filename will allow you to view the image
 - an uploaded_datetime field is added that represents the date/time the community data was uploaded
 - an id field is added that represents the system id assigned to the community feature (will match the id in the url)
 - user_email field (if provided) is removed
 
::

  {
    "type": "Feature",
    "geometry": {
      "type": "Point",
      "coordinates": [-73.95183384418488,46.409556709382144]
    },
    "properties": {
      "id": "63ec44c8-5016-4ac2-bea4-da82d5fa5484",
      "uploaded_datetime": "2024-10-10T07:35:27.214788-07:00",
      "weir": "true",
      "notes": "This is a simple example.",
      "cabd_id": "174db114-c7cc-4c75-be1f-30b337905c71",
      "uploaded": "false",
      "dam_height": "<5m",
      "feature_type": "dams",
      "dam_name_known": "false",
      "has_fish_structure": "false",
      "passability_status": "Obstacle",
      "physical_blockages": "false",
      "partial_dam_removal": "false",
      "side_channel_bypass": "false",
      "upstream_side_image": "63ec44c850164ac2bea4da82d5fa5484_upstream_side_image.jpeg",
      "downstream_side_image": "63ec44c850164ac2bea4da82d5fa5484_downstream_side_image.jpeg",
      "structure_type_correct": "yes",
      "upstream_direction_image": "63ec44c850164ac2bea4da82d5fa5484_upstream_direction_image.jpeg",
      "downstream_direction_image": "63ec44c850164ac2bea4da82d5fa5484_downstream_direction_image.jpeg"
    }
  }


   
