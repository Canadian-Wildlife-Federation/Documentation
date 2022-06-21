===================
Submit Data Updates
===================

A user may submit updates to the attribute information for one or multiple feature type records in the CABD by: 1) sharing the informaion via email, or 2) filling out the appropriate feature template (dams, fishways or waterfalls).

1. Submit Updates via Email
---------------------------

-----

The email should be addressed to cabd@cwf-fcf.org.

.. important::
    
    To help us identify your submission as quickly as possible, please use the following as the email subject line: "CABD - User Submitted Updates".

The body of the email **must** include:

* The barrier id (cabd_id) of the feature who's attribute information is to be updated (this can be acquired through the web mapping tool. See section *Update Existing Records* below, bullet 2, for more details).

* A URL link for the information source.

* A list detailing the information to be updated.

Once received, our team will review the content and update the database with the provided information.


2. Submit Updates Using a Feature Type Template
-----------------------------------------------

-----

Download the Template
~~~~~~~~~~~~~~~~~~~~~

Download the appropriate template for the feature type you are looking to submit updates for from the options below: 

:download:`Dam Updates Template <downloads/damstemplate06082022.xlsx>` *(released: 06/21/2022)*

:download:`Fishway Updates Template <downloads/fishwaystemplate06132022.xlsx>` *(released: 06/13/2022)*

:download:`Waterfall Updates Template <downloads/waterfallstemplate06132022.xlsx>` *(released: 06/13/2022)*

.. important::
    As changes to the CABD data structure may occur at any time, it is important to check this page and **verify that you have the most recent version** of the user submitted updates template for the feature type you are looking to submit data for. 

Populate the Template
~~~~~~~~~~~~~~~~~~~~~

Update Existing Records
+++++++++++++++++++++++

1. Upon opening the template, the first field in column A is the 'entry_classification' field which is used to define the purpose of the information being provided in that row. Please select the most appropriate option from the list of values and descriptions provided below for the feature in question:

   * **new_feature**: The information being submitted pertains to a feature that is not yet present in the CABD. A new feature point must be generated.

   * **modify_feature**: The information being submitted is meant to update attribute information for an existing feature point in the CABD. The existing data is currently unknown, incorrect, or out of date.

   * **delete_feature**: The feature, identified via cabd_id, does not exist and should be removed from the CABD.

   .. important::
       Decommissioned structures should **not** be considered for deletion. If a structure is found to be decommissioned/removed, the operating status field should be updated to reflect this information. 

   .. figure:: img/use_submitted_updates/entryclass.jpg
       :align: center
       :width: 800

2. The cabd_id field is the second column in the template and it is required in order to update attributes for an existing feature. The cabd_id value for a feature is located in the detailed view of a feature’s attribute popup window and will be called either ‘Barrier Identifier’ or ‘System Identifier’. To bring up a feature's attribute popup window, open the `web mapping tool <https://aquaticbarriers.ca/>`_, locate the feature point of interest, and click on the point to open the attribute information.

   .. figure:: img/use_submitted_updates/barrierid.jpg
       :align: center
       :width: 500

   Copy the value displayed for ‘Barrier Identifier’, or ‘System Identifier’, and paste it into the next available cell of the cabd_id column in the template, as shown in the image below.

   .. figure:: img/use_submitted_updates/cabd_id.jpg
      :align: center
      :width: 800

   .. note::
       a. If the information being added is for a feature that does not yet exist in the CABD, skip this step. The cabd_id for a new feature will be generated when initially loaded into the database. 

       b. If a feature is being submitted for deletion, then only the **cabd_id** and the **coordinates** (i.e., latitude and longitude) of the feature are required as input.

3. When modifying an existing feature, if the location of a feature point needs to be updated or corrected, populate latitude and longitude with the new coordinates in decimal degrees. If not, leave the latitude and longitude fields blank.

   .. note::
       Latitude and longitude values are **required** when adding information for a new feature point.  

4. Enter a link to the data source that the updated information comes from. This may be a website, scientific article, news article, technical report, etc.

   .. figure:: img/use_submitted_updates/datasource.jpg
      :align: center
      :width: 800

5. Next, select the attribute(s) for which new information will be added, from the options available in the drop down list. 

   .. figure:: img/use_submitted_updates/list1.jpg
      :align: center
      :width: 800

   .. important::
       Only attribute information pertaining to the specific data source indicated should be present in the row. If additional information for the feature is coming from a second (or third etc.) data source, create a new row with the same cabd_id to input the attribute information obtained from the new data source.

6. Populate the information for the chosen attributes.

   a. If an attribute has a defined list of allowable values, these can be selected via the dropdown that is present next to each cell in the column below the chosen attribute. 
   
   b. If there is no defined list of allowable values for the selected attribute, type the information directly into the cell. 

   .. figure:: img/use_submitted_updates/fieldentry.jpg
      :align: center
      :width: 800

   .. note::
       Before entering the information for the chosen attribute, consult the `Data Catalogue <https://cabd-docs.netlify.app/docs_user/docs_user_data_catalogue.html>`_ page to check the definition and allowable values for the attribute. 
   
7. Add and populate additional attributes (and rows if needed) until all the information for the specific feature(s) is present in the template. 


Submit the Updated Template
~~~~~~~~~~~~~~~~~~~~~~~~~~~

The updated template should be submitted to cabd@cwf-fcf.org.

Once received, our team will review the content and update the database with the provided information.

.. important::
    To help us identify your submission as quickly as possible, please use the following as the email subject line: "CABD - User Submitted Updates".

Thank you for your contribution!