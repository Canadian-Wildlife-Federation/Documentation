===================
Submit Data Updates
===================

A user may record and submit updates to the attribute information for one or multiple feature type records in the CABD using the user submitted updates template for dams, fishways or waterfalls. 

Downloading the Template
------------------------

-----

Download the appropriate template for the feature type you are looking to submit updates for from the options below: 

:download:`Dam Updates Template <downloads/damstemplate4202022.xlsx>`

*Fishway Updates Template (coming soon)*

*Waterfall Updates Template (coming soon)*

.. important::
    As changes to the CABD data structure may occur at any time, it is important to check this page and **verify that you have the most recent version** of the user submitted updates template for the feature type you are looking to submit data for. 

Populating the Template
-----------------------

-----

Updating Existing Records
~~~~~~~~~~~~~~~~~~~~~~~~~
1. The cabd_id field is the first column in the template and it is required in order to update attributes for an existing feature. The cabd_id value for a feature is located in the detailed view of a feature’s attribute popup information window and will be called either ‘Barrier Identifier’ or ‘System Identifier’. Copy this value and paste it into the next available cell of the cabd_id column in the template.

.. image:: img/use_submitted_updates/barrierid.jpg
   :align: center

.. image:: img/use_submitted_updates/cabd_id.jpg
   :align: center

.. note::
    Skip this step if the information being added if for a feature that does not yet exist in the CABD. The cabd_id for new features will be generated when initially loaded into the database. 

2. If the location of a feature point needs to be updated or corrected, populate latitude and longitude with the updated coordinates in decimal degrees. If not, leave the latitude and longitude fields blank.

.. note::
    Latitude and longitude values *must* be populated when adding information for a new feature point.  

3. Enter a reference or link to the data source that the updated information comes from. This could be a website, scientific article, news article, technical report, etc.

.. image:: img/use_submitted_updates/datasrc.jpg
   :align: center

4. Next, select the attribute(s) for which new information will be added, from the options available in the drop down list. 

.. image:: img/use_submitted_updates/list1.png
   :align: center

.. important::
    Only attribute information pertaining to the specific data source indicated should be present in the row. If additional information from a different data source is being used to update the same feature, create a second row with the same cabd_id for attribute information pertaining to the second data source.

5. Populate the information for the chosen attributes.

   a. If an attribute has a defined list of allowable values, these can be selected via the dropdown that is present next to each cell in the column below the chosen attribute. 
   
   .. image:: img/use_submitted_updates/list2.png
      :align: center

   b. If there is no defined list of allowable values for the selected attribute, type the information directly into the cell. 

.. note::
    Before entering the information for the chosen attribute, consult the `Data Catalogue <https://cabd-docs.netlify.app/docs_user/docs_user_data_catalogue.html>`_ page to check the definition and allowable values for the attribute. 
   
6. Add and populate additional attributes (and rows if needed) until all the information for the specific feature is present in the template.


Submitting the Updated Template
-------------------------------

-----

The updated template should be submitted to cabd@cwf-fcf.org.

Once received, our team will review the content and update the database with the provided information.

.. important::
    To help us identify your submission as quickly as possible, please use the following as the email subject line: "CABD - User Submitted Updates".

Thank you for your contribution!