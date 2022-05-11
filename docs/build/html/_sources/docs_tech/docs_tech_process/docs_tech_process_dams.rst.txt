======================
Feature Review Process
======================

Reviewing existing datasets is an important step in preparing data for the Canadian Aquatic Barriers Database (CABD). This document will walk you through how to examine these datasets and identify and record duplicate features between datasets to be loaded into the CABD.

Setup
-----

-----

1. Go to the feature review folder on the CWF shared drive: J:\Conservation Program\GIS\Freshwater\cabd\feature_review.

2. Open the qgis_projects folder, select the folder for the province or territory you are reviewing, and open the QGIS project file (.qgz) file saved there – this will be named something like “qc_dam_review” or “qc_waterfall_review”.

3.	Once the project loads, you’ll want to double check a few things before you get started:

    a.	Go to **View > Panels** and ensure the **Identify Results** panel is enabled. Change the mode at the bottom of this panel to **Layer Selection**.

    b.	Go to **Project > Properties** and click the **Data Sources** tab. Ensure that the satellite imagery layers (e.g., Bing VirtualEarth) and the NHN WMS layer are not identifiable, and that all the source datasets and the review layer (e.g., featurecopy.dams) are identifiable.

    c.	Ensure the NHN work units layer (e.g., qc_workunits) is toggled on in the layers panel, and that it is not filtered. You can also set this to be not identifiable in the **Data Sources** tab noted in the previous step.

    d.	Go to **Settings > Options** and click the **Map Tools** tab. Change your “search radius for identifying features and displaying map tips” to at least 5 mm – this will make it easier to query features from the map for this exercise.

    e.	Double check the symbology for all the source dataset layers to ensure features are visible and you can easily distinguish between the datasets.

Reviewing and Adding Features 
-----------------------------

-----

We need to do three main things when reviewing source datasets:

1.	Find any duplicate features from other datasets

2.	Identify if a feature should be used for analysis

3.	Determine if the feature is visible

For most features, it should be straightforward to evaluate all three items when you initially review the area.

The review layer you’re working with has been created ahead of time and captures most duplicate features and their IDs based on joining attributes by nearest features. When you open the project, this layer will be symbolized based on the use_analysis field – the features symbolized with a question mark are the ones that haven’t been checked yet.

Find Any Duplicate Features From Other Datasets
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1.	Ensure all the source datasets are toggled on, select the **Identify** tool, and click the area you want to query. If there are multiple features at that location, a window will pop up beside your cursor – click **Identify All** to bring up a list of all the features in the **Identify** panel. 

2. The display name for all layers should be set to their unique ID by default, so if you expand each layer using the accordion icon, you will see all the unique IDs for features at that location:

3.	Referring to the **Identify Results** panel for unique IDs, check the data_source_text and data_source_id fields for the point in the review layer, as well as any fields populated in the **Duplicates** tab of the review layer. Note that the visibility of the **Duplicates** tab is controlled by the duplicates field checkbox – when it is toggled, the **Duplicates** tab will be shown.

.. image:: img/uniqueids.png
    :align: center

4.	If all the unique IDs are accounted for:

    * Expand the individual entries in the **Identify Results** panel and double check that any names available in the source datasets match. If they do match, you’re done this step. If they don’t match, check the imagery and the attributes of other nearby points to see if this feature needs two separate points to represent it.

5.	If you’re missing some unique IDs:

    * Refer to the **Identify Results** panel, check the names in the source datasets, and add them in the appropriate field in the **Duplicates** tab of your review layer.

6.	If there is no existing feature in the review layer:

    * Add a new point feature to the review layer and fill in the appropriate fields. You can use any of the unique IDs for the data_source_text and data_source fields, then add the remaining unique IDs in the **Duplicates** tab of the review layer.

7.	To ensure you get the correct unique for a dataset, please right click the unique id field in the **Identify** panel and click ‘copy attribute value’.

.. image:: img/duplicates.png
    :align: center

8.	In some cases, the review layer may include several distinct points close to each other that refer to the same feature. In this case, check the attributes of the source datasets at that location. If the source datasets all appear to refer to a single feature (e.g., a large dam structure), remove any extra points from the review layer until you have a single point, then add all the unique IDs for that feature to the single point.

Identify if Features Should Be Used for Analysis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Some attributes from source datasets may also indicate if a feature should be used for analysis. For example, in most cases, we wouldn’t use features marked as “embankments”, “canals”, or “dykes” for analysis.

* Fishway features will also not be used for analysis and should be stored as separate features from dams. Leaving the **Use in analysis?** box blank, just add the data source and data source id, and check the **Is this a fishway?** box on the **Fishways** tab. If there’s a corresponding record in the CANFISHPASS database, add the unique ID as well. Finally, make sure your point isn’t snapped to a flowpath on the hydro network, and that it reflects the real-world location of the fishway.

.. image:: img/useanalysis.png
    :align: center

* If a feature should be used for analysis:

  1. Check the **Use in analysis?** box

  2. Ensure your point in the review layer is relatively close to a flowpath

  3. If there are multiple flowpaths near a structure, move your point to coincide with the flowpath you want it to be snapped to

* If a structure shouldn’t be used for analysis:
  
  1. Leave the **Use in analysis?** box blank

  2. Ensure your point in the review layer isn’t snapped to a flowpath on the hydro network (it’s ok for them to be snapped to waterbody polygons)

Single Point and Multi-point Features
+++++++++++++++++++++++++++++++++++++

* In some cases, you may want to represent a dam as a multi-point feature. Our database structure currently does not support multi-point features, so in this case, just check the “Multipoint in future?” checkbox in the review layer.

* If you have several distinct structures that each block flow through an area, you will generally want to store these as single points. For each structure, store them as a single point with the unique ids from any corresponding source datasets. If there are no corresponding source datasets, simply mark the source as ‘cwf’ and add any information you find about that structure in the freeform reviewer_comments field.

* If the dam has a name, you should do a quick search to see if you can find any additional information or drawings describing the structures that make up the dam complex. You should also check the source dataset points surrounding the structures for names of these structures and to identify which points represent each structure.


Determine if a Feature Is Visible
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Generally, dam structures are characterized by being perpendicular to a watercourse/waterbody and having calm water on one side and disturbed water on the other side:

.. image:: img/presence.png
    :align: center

* For our purposes, we assume that all feature from source datasets exist and are active (i.e., not decommissioned) unless research or attributes from our source data tell us otherwise.

* If you have a clear view of the hydro network from imagery, but you can’t see any structures near a feature’s location, set the **reviewer_classification** field in the **Comments** tab to “No structures present”.

* If the imagery quality is poor or the feature location is obscured, set the **reviewer_classification** field in the **Comments** tab to “Obscured in imagery”.

Finishing a Work Unit or Province/Territory
-------------------------------------------

-----

Since our data is saved in Postgres, multiple people can work on the same province/territory at the same time. As you go through feature review, you’ll want to track your progress and coordinate with anyone else reviewing features in the same geographic area to avoid duplicating work.

A Work Unit Is Complete
~~~~~~~~~~~~~~~~~~~~~~~

* Select the work unit, toggle on editing, and click the **Modify attributes** button:

.. image:: img/modatts.png
    :align: center

* On the new form that pops up, check the **Complete** box for the appropriate feature type (e.g., dams_complete) and save your edits. The default symbology for work units will shade incomplete areas in light yellow, and complete areas with just a black border.

An Entire Province/Territory Is Complete
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* Do a quick once-over of the area to confirm all points have been accounted for. At this point, you should also double-check for any features with the same data_source_id (the other duplicates fields are evaluated as you input data). 

  * You can do this by selecting by expression on the review layer: ``count (1, “data_source_id”) > 1``. 

  * Then, open the attribute table, change the display to ‘Selected features’ and sort by data_source to check for any duplicates within individual data sources. You can ignore duplicate data source ids that come from different datasets (e.g., canvec and nhn).

Appendix A: Troubleshooting and Tips
------------------------------------

-----

* When reviewing a dam facility with many structures, you may find it easiest to start by identifying the main structure by looking at the NHN flowpaths or any details about the facility found online.

* For multi-dam complexes, use your best judgement to determine which source data points are closest to each dam. You should also check the names and group all the points with common names together for a feature – e.g., Alvin Main Dam vs Alvin Freeboard Dam:

.. image:: img/multidam.png
    :align: center

.. image:: img/multidamb.png
    :align: center

* If there are two points for the same feature from one dataset, only include one point in your review layer, ideally the one which has the most attribute information about that feature.

* For long dam structures where there are multiple points from source datasets, choose the side that’s furthest downstream (based on the NHN flowpaths) to include in your review layer – you should not include both.

Appendix B: Reviewer_Classification and Reviewer_Comments
---------------------------------------------------------

-----

The reviewer_classification field lets our team quickly categorize uncertainty about features, so we can verify their existence with local groups in the future.

The reviewer_comments field is where you’ll add any other comments you have about a feature – e.g., “See link for dam dimensions” or “Part of Churchill Falls generating station?” 

You can select multiple options for a feature in the reviewer_classification field.

.. csv-table:: 
    :file: tbl/damreviewclass.csv
    :widths: 30, 70
    :header-rows: 1

