===========================
Feature Data Source Details
===========================

This page provides a breakdown of the data source information available for a specific structure. The information is provided in csv format, which can be obtained through the `Canadian Aquatic Barriers Database's web-map <https://aquaticbarriers.ca/>`_ by navigating to the **Feature Data Source Details** entry in the attribute popup window for the desired structure and clicking the download link. 

.. figure:: img/download_link.png
    :align: center
    :width: 400

CSV Contents
--------------

-----

The image below is an example of what the data sources csv table looks like. The example is marked up with numbered sections that correspond with the descriptions listed below. 

.. figure:: img/csv_download.png
    :align: center
    :width: 600

1. The name of the structure.

2. The unique barrier/system identifier (cabd_id) for the structure.
	
3. The link to the `Data Sources <https://cabd-docs.netlify.app/docs_user/docs_user_data_sources.html>`_ page that holds the attribution information for the data held in the database. 
    
   .. note:: 
       
       The shortened data source names in the CSV can be cross referenced with the `Data Sources <https://cabd-docs.netlify.app/docs_user/docs_user_data_sources.html>`_ page to identify the full name and reference information for each data source. 
	
4. The list of spatial data sources used to populate attribute information for the structure. 
	
5. The list of unique ids associated with the data source name listed in the same row of the table. This unique id corresponds with the feature in the listed data source that was identified as a duplicate of the structure for which relevant attribute information for the structure was carried forwards into the cabd.
	
6. The list of non-spatial data sources used to populate attribute information for the structure.
	
7. The list of attributes available in the CABD for the selected feature type.

8. The list of data sources representing which dataset was used to populate information for that specific attribute. 