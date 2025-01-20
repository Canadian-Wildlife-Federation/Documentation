.. _api:

===================
Connect to an API in GIS 
===================
An API is a tool that allows different applications to interact and share information (e.g., GIS software interacting with the Aquatic Barriers Database), making it easier to access and integrate spatial data. 

Connecting to the Aquatic Barriers API enables access to real-time barrier data (e.g., dams, waterfalls, fishways) in an efficient and streamless process; rather than downloading these datasets individually. 

The base URL for any API query in the CABD is : https://cabd-web.azurewebsites.net/cabd-api. This refers to the root address or endpoint from which all API requests are made. It serves as the foundation for the complete API URL, which is combined with distinctive paths or parameters to access specific resources or data within the API. For more information on the API or to view detailed examples, visit `CABD REST API Services <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch_api>`_. 

Below you will find instructions for connecting to an API in either QGIS or ArcGIS Pro. 

.. note::
    For any API query, a maximum of 55,000 features is returned. If a particular request is unable to load, you may need to be more specific so that your request returns a subset of features that is within the allowable limit of 55,000 features. 

Connecting to an API in QGIS 
--------------------------------

To add an API layer in QGIS, you need to navigate to add new **vector layer** tab. In the vector layer tab, you will select/input the following:

- Source Type: Protocol: HTTP(S), cloud, etc. 
- Encoding: automatic
- Type: GeoJSON
- URI: API Request (e.g., https://cabd-web.azurewebsites.net/cabd-api/features/fishways)
- Configurations: default

.. figure:: img/api_vector_layer.jpg
    :align: center
    :width: 1400

After inputting the details above, you can now add the vector layer to your map. Depending on the request, the API layer may take a few minutes to display. For this specific example, you will see a new layer in your layers tab named fishways and points representing fishway locations. 

.. figure:: img/api_fishway_map.jpg
    :align: center
    :width: 1400

Connecting to an API in ArcGIS Pro
---------------------------------
**Connecting to an API via Python Script**

To add an API layer in ArcGIS Pro, you need to open Python and insert a number of lines to specify the data you are interested in.

.. admonition:: Python Example

    | ``import os``
    | ``import requests``
    | ``import re``
    | # Define the directory where you want to save the downloaded files 
    | ``download_directory = 'your_directory'``
    | #List of hyperlinks (URLs) to download data from - you will specify the barrier data (e.g., dams, waterfalls, fishways) you are interested in along with other criteria (e.g., province/territory, operating status, etc.) 
    | ``urls = [``
    | ``"insert here"``
    | ``"you can insert more than one"``
    | ``]``
    | #Predefined filenames (you can modify this list as needed - names will coordinate in the same order as the URLs)
    | ``filenames = [``
    |  ``"first_name",``
    |  ``"second_name",``
    | ``]``

Below is an example with Ontario dams and waterfalls specified.

.. admonition::  Python Example with Ontario Dams and Waterfalls

    | ``import os``
    | ``import requests``
    | ``import re``
    | # Define the directory where you want to save the downloaded files 
    | ``download_directory = 'your_directory'``
    | #List of hyperlinks (URLs) to download data from - you will specify the barrier data (e.g., dams, waterfalls, fishways) you are interested in along with other criteria (e.g., province/territory, operating status, etc.) 
    | ``urls = [``
    | ``"https://cabd-web.azurewebsites.net/cabd-api/features/dams?filter=province_territory_code:eq:on&format=geopackage"``
    | ``"https://cabd-web.azurewebsites.net/cabd-api/features/waterfalls?filter=province_territory_code:eq:on&format=geopackage"``
    | ``]``
    | #Predefined filenames (you can modify this list as needed - names will coordinate in the same order as the URLs)
    | ``filenames = [``
    |  ``"on_dams",``
    |  ``"on_waterfalls",``
    | ``]``

.. note::
    This page provides a basic guidance for connecting to an API in GIS software. Overtime, this page will provide more detailed guidance and be further refined as needed. Feel free to adapt or expand the script based on your specific requirements. 
