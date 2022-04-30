====================
Dam & Fishway Review
====================

Reviewing existing datasets is an important step in preparing data for the Canadian Aquatic Barriers Database (CABD). This document will walk you through how to examine these datasets and identify and record duplicate features between datasets to be loaded into the CABD.

Setup
-----

-----

1. Go to the dam review folder on the CWF shared drive: J:\Conservation Program\Freshwater\Fish Passage\National Aquatic Barrier Database\GIS work folder\Dam_Review.

2. Open the qgis_projects folder, select the folder for the province or territory you are reviewing, and open the QGIS project file (.qgz) file saved there.

3. Once the project is loaded in, you’ll want to double check a few things before you get started:
   
   a. Go to **View > Panels** and ensure the **Identify Results** panel is enabled. Change the mode at the bottom of this panel to **Layer Selection**.
   
   b. Go to **Project > Properties** and click the **Data Sources** tab. Ensure that the satellite imagery layers (e.g., Bing VirtualEarth) and the NHN WMS layer are not identifiable. You should also confirm that all the source datasets and the dam review geopackage are identifiable.
   
   c. Ensure the NHN work units layer (e.g., sk_workunits) is toggled on in the layers panel, and that it is not filtered.
   
   d. Go to **Settings > Options** and click the **Map Tools** tab. Change your “search radius for identifying features and displaying map tips” to at least 5 mm – this will make it easier to query features from the map for this exercise.
   
   e. Double check the symbology for all the source dataset layers to ensure features are visible and you can easily distinguish between the datasets – feel free to change the symbols to what suits you best!

Adding a Feature 
--------------

-----

We need to do three main things when reviewing dam datasets:

1.	Find any duplicate features from other datasets

2.	Identify if a feature should be used for analysis

3.	Determine if a structure is visible

For most structures, it should be straightforward to evaluate all three items when you initially review an area with the dam.

Find any duplicate features from other datasets
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1.	Ensure all the source datasets (including fishways) are toggled on. You can easily toggle these on by selecting the first dataset in the layers list, hitting CTRL + SHIFT and left click the last dataset in the layers list, then ENTER to toggle all selected layers on or off.

2.	Click the area you want to query. If there are multiple features at that location, a window will pop up beside your cursor – click **Identify All** to bring up a list of all the features in the **Identify** panel. 

3. The display name for all layers should be set to their unique ID by default, so if you expand each layer using the accordion icon, you will see all the unique IDs for features at that location.

.. image:: img/uniqueids.png
    :align: center

4.	Toggle editing on for your dam review geopackage and add a point feature at the location of the dam. A new form will pop up where you can fill in some information about the feature.

5.	First, assign the source dataset from one of the features at the dam location. The source dataset layers have been ordered in each project where the “best source of data” is at the top, and less authoritative or broader datasets are at the bottom. Choose the source dataset that is closest to the top of the layer list. You can start typing the name of a dataset and the form will suggest the source dataset name for you.

6.	In the **Identify** panel, right click the unique id for a dataset and click “copy attribute value” to ensure you have the right value. Paste this value into the data_source_id field.

7.	If there are multiple features from datasets at this location, check the **Duplicates**? box. A new tab will pop up at the bottom where you can add the unique IDs from the other datasets. Again, use “copy attribute value” to ensure you have the right values.

.. image:: img/duplicates.png
    :align: center

Identify if dam features should be used for analysis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* There are some features we don’t want to use for fish passage or connectivity analysis because they don’t block passage and/or aren’t part of the hydro network. You can check this by toggling on the NHN WMS layer and looking at the flow direction for an area.

* For example, in the image below, the leftmost structure shouldn’t be used for analysis because there isn’t any flow through it. However, there is flow passing through the structure on the right, so there’s a good chance we want to use it for analysis.

.. image:: img/useanalysis.png
    :align: center

* Some attributes from source datasets may also indicate if a feature should be used for analysis. For example, in most cases, we wouldn’t use structures marked as “embankments”, “canals”, “dykes”, or “freeboard”.

* Fishway features will also not be used for analysis. Leaving the Use in analysis? box blank, just add the data source and data source id, and check the Is this a fishway? box on the Fishways tab. If there’s a corresponding record in the CANFISHPASS database, add the unique ID as well. Finally, make sure your point in the dam review gpkg isn’t snapped to a flowpath on the hydro network, and that it reflects the real-world location of the fishway.

* If a structure should be used for analysis:

  1. Check the **Use in analysis?** box

  2. Ensure your point in the dam review gpkg is relatively close to a flowpath

  3. If there are multiple flowpaths near a structure, move your point to coincide with the flowpath you want it to be snapped to

* If a structure shouldn’t be used for analysis:

  1. Leave the **Use in analysis?** box blank

  2. Ensure your point in the dam review gpkg isn’t snapped to a flowpath on the hydro network (it’s ok for them to be snapped to waterbody polygons)

* If you’re not sure about a certain feature, add a comment to that feature in your dam review geopackage and schedule a chat with one of your team members to discuss later along with any other features that come up during your review.

Verify the presence of a structure
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Generally, dam structures are characterized by being perpendicular to a watercourse/waterbody and having calm water on one side and disturbed water on the other side:

.. image:: img/presence.png
    :align: center

* For our purposes, we assume that all dams from source datasets exist and are active (i.e., not decommissioned) unless research or attributes from our source data tell us otherwise.

* If you have a clear view of the hydro network from imagery, but you can’t see any structures near a dam’s location, set the **reviewer_classification** field in the **Comments** tab to “No structures present”.

* If the imagery quality is poor or the dam location is obscured, set the **reviewer_classification** field in the **Comments** tab to “Obscured in imagery”.

Finishing a work unit or province/territory
-------------------------------------------

-----

As you go through dam review, you’ll want to track your progress and coordinate with anyone else reviewing dams in the same geographic area to avoid duplicating work. Some helpful tips are provided below.

A work unit is complete
~~~~~~~~~~~~~~~~~~~~~~~

* Select the work unit, toggle on editing, and click the **Modify attributes** button:

.. image:: img/modatts.png
    :align: center

* On the new form that pops up, check the Complete box, deselect the work unit, and save your edits. The default symbology for work units will shade incomplete areas in light yellow, and complete areas with just a white border.

* Since only one person can edit a geopackage at one time, if you’re collaborating on dam review with another person, discuss at the beginning of the day which work units each of you will take on. 
  
  * Then, each of you should make a local copy of the dam review geopackage and the province/territory’s work unit geopackage to work on for the day.
  
  * Have one person be responsible for updating the work unit geopackage at the end of the day to track progress, and ensure the other person sends their list of complete work units to them.

An entire province/territory is complete
++++++++++++++++++++++++++++++++++++++++

* Amazing! All you need to do now is split your main geopackage into individual geopackages for each work unit. With your dam review layer selected, open the Split Vector Layer tool in QGIS and set the unique ID field to nhn_workunit_id. Save the output files to J:\Conservation Program\Freshwater\Fish Passage\National Aquatic Barrier Database\GIS work folder\Dam_Review\completed_geopackages. **This will take some time to run.**

Troubleshooting and helpful tips
--------------------------------

-----

* If you come across a dam that’s located outside of the Canadian border, don’t add it to the dam_review geopackage. We will go through a separate review of dams across the border but within NHN work unit boundaries at a later date.

* If you find working off the VPN is too slow, you can copy your project and the source datasets to your local drive to work on for the day – just make sure to copy your work back to the server at the end of the day! Closing the **Browser** panel can also help speed up QGIS performance.

* For long dam structures where there are multiple points from source datasets, choose the side that’s furthest downstream (based on the NHN flowpaths) to include in your geopackage – you should not include both.

* If there are two points for a dam feature from the same dataset, only include one point in your geopackage, ideally the one which has the most attribute information about that dam.

* When reviewing a dam facility that has many structures, you may find it easiest to start by identifying the main dam structure by looking at the NHN flowpaths or any details about the dam facility you can find online.

* For multi-dam complexes, use your best judgement to determine which source data points are closest to each dam. You should also check the names and group all the points with common names together for a feature – e.g., Alvin Main Dam vs Alvin Freeboard Dam.

.. image:: img/multidam.png
    :align: center

.. image:: img/multidamb.png
    :align: center

Using the Reviewer_Classification and Reviewer_Comments fields correctly
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The reviewer_classification field lets our team quickly categorize different uncertainties about dam features. For instance, after we process a hydro network using the CHyF tools, we might want to check several dams to ensure they’re situated on the primary flowpath for that area. If we pre-emptively mark the dams where this might happen as “Verify primary flowpath”, we don’t need to check every dam in the work unit.

The reviewer_comments field is where you’ll add any other comments you have about a feature and is meant to hold comments that aren’t widely applicable to other dams. For instance, you might include a note on a particular feature saying “Part of Churchill Falls generating station?” or “See link for dam dimensions”.

You can select multiple options for a feature in the reviewer_classification field:

.. csv-table:: 
    :file: tbl/damreviewclass.csv
    :widths: 30, 70
    :header-rows: 1

