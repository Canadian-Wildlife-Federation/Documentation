======================
Feature Review Process
======================

Reviewing existing datasets is an important step in preparing data for the Canadian Aquatic Barriers Database (CABD). This section provides a summary of the methods used to validate, deduplicate and standardize existing spatial datasets in an effort to create a harmonized national-scale database of barriers to aquatic connectivity, and associated structures, in Canada.

.. note::

    In the CABD, the term ‘feature’ is used to reference an individual structure that represents a dam, waterfall, or fishway. In this section, the term ‘feature point’ is used to represent the geographic point location of a feature.

Duplicate identification and tracking
-------------------------------------

Generating the review layer
~~~~~~~~~~~~~~~~~~~~~~~~~~~

The first step of the review process is to generate a review layer, which will then be manually reviewed and verified. Generating the review layer requires that all known and publicly available source datasets for a predefined area of interest (AOI) be examined to identify the source dataset with the highest number of feature points in the AOI. The feature points of this dataset are extracted to form the foundation of the ‘starting layer’. The review layer is then buffered to determine the most appropriate tolerance that will encircle the majority of the feature points from the other source datasets that represent the same structures (i.e., duplicates), while avoiding those that represent separate structures (i.e., nonduplicates); typically around 50 m.

Next, the ‘Join attributes by nearest’ tool in QGIS is used to join the unique ids from a second source dataset with the features of the review layer, based on the determined tolerance. The resulting output is a new version of the review layer that contains an additional field in the attribute table which holds the unique id of each assumed duplicate from the second source dataset. This tool is run repeatedly for the remaining source datasets, using the generated output of each run as the first input layer for the next join. 

Once all runs have completed, features points from each source dataset that fall outside the determined tolerance, but within the AOI, are selected and the entire process is repeated, begging with the layer that has the most features selected. Once most source dataset features are captured, output layers are merged to create the final version of the review layer. To facilitate the review process, a handful of fields were added to the review layer for the purpose of tracking specific details about a feature and an attributes form was created.

Verifying the location of structures using satellite imagery
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To begin verifying review layer feature points, the first step is to try and verify that the feature point is in the correct location. To do this, the reviewer will examine the feature point’s position relative to the location of the corresponding structure in satellite imagery, if visible. If a structure is not visible in the satellite imagery, the reviewer will use the feature point attributes to research the structure online to confirm the location of the structure or determine if the structure has been removed/decommissioned, and relocate the feature point if necessary. 

If the structure has not been decommissioned, the reviewer will then assess the location of the feature point relative to the hydrographic network. If the feature point is located more than 50 m away from the closest hydro network flowpath, the reviewer will relocate the feature point to where the structure intersects with the flowpath.

Unless the attribute information or additional research indicates that a structure has been removed, is it assumed that all feature point structures from the source datasets are real. Therefore, in the event that a reviewer cannot confirm the existence or location of the feature point structure, the feature point is left in it’s original location.

Review and verify duplicate feature points of the review layer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

While the semi-automated process of generating the review layer is used to quickly capture most duplicate ids, it isn’t expected to produce a perfect result. Therefore, each feature point requires manual review to verify that all duplicate ids from the source datasets are being tracked correctly in the review layer, and to add any feature points that were missed during the join process. 

This is done by cross referencing the unique ids present in the ‘Duplicates’ tab (fig. 1) of the review layer’s attribute form with the corresponding ids from source dataset features (fig. 2) that are located nearby. If a feature’s unique id is missing from the ‘Duplicates’ tab, the feature is investigated further (e.g., checking if structure names match, examining the satellite imagery for an additional structure) to determine if it is a true duplicate. If the missing feature is determined to be a duplicate, the unique id is manually added to the corresponding datasource field in the ‘Duplicates’ tab. If the feature is not a duplicate and was just missed when generating the review layer, a new feature point is manually added to the review layer, inputting the source dataset name and id from the original source dataset.

.. figure:: img/duplicates.png
    :align: center
    :width: 75%

    Figure 1. The review layer attributes form showing the data source and data source id of a feature point, and the unique ids of feature points (recorded in the ‘Duplicates’ tab) that were identified as duplicates from other source datasets.

.. figure:: img/uniqueids.png
    :align: center
    :width: 75%

    Figure 2. Unique ids of source dataset feature points.

Occasionally, the review layer may include several feature points that appear to correspond to a single structure on the ground. In this case, the attributes of each source dataset feature point in the location are compared and all feature points identified as duplicates are removed from the review layer; unique ids of each duplicate are added to the appropriate data source fields in the ‘Duplicates’ tab of the single remaining feature point. In this case, the feature point with the most attribute information is retained. 

To snap, or not to snap
-----------------------

Does the structure block flow?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Considering that not all feature points representing a dam act as a potential longitudinal barrier to flow, a flag was implemented to specify if a feature point should or should not be snapped to the hydrographic network layer and thus used for geospatial analysis. This flag is a boolean field called ‘use_analysis’, or ‘Use for analysis?’ in the attribute form (fig. 1). 

When reviewing a feature point, the reviewer assesses it’s location relative to the flowpath (i.e., a stream or river) or waterbody (i.e., lake or double line river) and examines the information provided in the attribute table. If the attribute information available for the feature is limited, the reviewer may need to perform additional research to determine the nature of structure. 

If a feature is identified as a barrier blocking up- and downstream flow, the reviewer would check the box next to the ‘Use for analysis’ row in the attribute form to set the ‘use_analysis’ field value for the feature point to ‘true’. Once feature review is complete, all features with a value of ‘true’ in the ‘use_analysis’ field will be snapped to a hydro network flowpath using a python script. 

If a feature is identified as an auxiliary structure (e.g., saddle dam, dyke, canal wall, etc.,), it is considered a lateral barrier (i.e., not blocking up- and downstream flow). In this case, the reviewer would leave the ‘Use for analysis?’ checkbox unchecked to set the ‘use_analysis’ field value for the feature point to ‘false’. All features with a value of ‘false’ in the ‘use_analysis’ field would not be snapped to the hydro network and thus omitted from future geospatial analysis.

.. figure:: img/useanalysis.png
    :align: center
    :width: 75%

    Figure 3. An example illustrating the logic used when determining if a feature point should or should not be used for analysis, snapped or not snapped to the hydrographic network, respectively. Shown are three feature points, each from a different source dataset: blue - dyke that is acting as a lateral barrier, red - embankment dam acting as a longitudinal barrier, green - duplicate of the red feature point. The flow in this area is represented by the red dotted line; arrows indicate the flow direction. 

Fishway structures are treated differently than barrier structures as their purpose is to facilitate fish passage past structures like dams, culverts or waterfalls. Considering that fishway structures do not act as barriers to fish passage, these features are always assigned a ‘use_analysis’ value of ‘false’, and flagged as a fishway by checking the ‘Is this a fishway’ check box under the ‘Fishway’ tab at the bottom of the review layer attribute form. If the feature point identified as a fishway corresponds to an existing record from the CANFISHPASS database, the unique id is used.

Structures that block flow in multiple locations
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Occasionally, a single feature will be blocking flow at multiple locations (fig. 4). In a case like this, a single feature point is not sufficient and a multipoint feature in required to place a point at each location where flow is blocked by the structure.

However, the CABD does not currently support the use of multipoint features, so a flag was created in the review layer attribute form that allows the reviewer to mark a single point feature as a future multipoint feature (i.e., the ‘Multipoint in future?’ checkbox).

.. figure:: img/multidamb.png
    :align: center
    :width: 75%

    Figure 4. An embankment structure that is blocking flow at two separate locations. A multipoint feature is required.

Last steps
----------

Once the review process is complete, and all feature points in the review layer are verified, the final review layer and all source dataset layers are loaded into the database in preparation for source dataset attribute mapping. 
