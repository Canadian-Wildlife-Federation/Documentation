.. _data-catalogue:

==============
Data Catalogue
==============

The CABD data catalogue contains the the information you need to make sense of the attributes for each CABD feature type (dams, waterfalls, and fishways), including human-readable field names, breakdowns of allowable field values, and definitions. If you have questions about any of the information on this page, you can reach out to us at cabd@cwf-fcf.org.

Feature Types
-------------

-----

.. _dams-layer:

Dams
~~~~
Definition:	
    *A dam is a structure that is constructed to divert or hold back water of a stream, river, or lake for a specific purpose, e.g., hydroelectricity, water storage, or flood control. These structures impede the ability of fish to travel upstream unless there is a fishway installed on the structure. In the CABD, dams are defined as: small dams (i.e., having a height of less than 5 m), medium dams (i.e., having a height between 5 and 15 m), and large dams (i.e., having height of 15 m or greater, or a height between 5 m and 15 m that impounds more than 3 million m3).* 
    
    *Currently, the CABD dams layer also includes other types of structures, including weirs, powerhouses, spillways, canals, and lateral structures (e.g., embankments or saddle dams). Some of these structures don't necessarily fragment freshwater systems in the upstream-downstream plane. As such, these structures should not be used for connectivity network analyses or barrier prioritization exercises. These data points can be filtered out using the* :ref:`Used for Network Analysis <useanalysis>` *field (``use_analysis = false`` in the data).*
Attributes:
    :ref:`Assessment Schedule <assessment-schedule>`, :ref:`Average Rate of Discharge (L/s) <avgrate>`, :ref:`Barrier Identifier <bid>`, :ref:`Comments <commentdef>`, :ref:`Completeness Level <complvl>`, :ref:`Construction Material <conmaterial>`, :ref:`Construction Year <conyear>`, :ref:`Dam Condition <damcon>`, :ref:`Dam Function <damfunc>`, :ref:`Dam Name (English) <damnameen>`, :ref:`Dam Name (French) <damnamefr>`, :ref:`Dam Size <damsize>`, :ref:`Dam Use <damuse>`, :ref:`Degree of Regulation <degreg>`, :ref:`Downstream Passage Route <downpass>`, :ref:`Expected Life (Years) <explife>`, :ref:`Facility Name (English) <facilnameen>`, :ref:`Facility Name (French) <facilnamefr>`, :ref:`Feature Data Source Details <ftdatasrc>`, :ref:`Feature Type <fttype>`, :ref:`Federal Compliance Status <fedcompstat>`, :ref:`Federal Flow Requirements (m3/s) <fedflowreq>`, :ref:`Generating Capacity (MWh) <gencap>`, :ref:`Has Hydro Peaking System <hydropeak>`, :ref:`Height (m) <damheight>`, :ref:`Lake Control <lakectrl>`, :ref:`Last Maintenance Date <lastmaint>`, :ref:`Last Modified <lastmod>`, :ref:`Latitude <lat>`, :ref:`Length (m) <length>`, :ref:`Longitude <long>`, :ref:`Municipality <municipality>`, :ref:`Next Maintenance Date <nextmaint>`, :ref:`NHN Watershed ID <nhnid>`, :ref:`NHN Watershed Name <nhnname>`, :ref:`Number of Turbines <turbcount>`, :ref:`Operating Note <opnote>`, :ref:`Operating Status <opstat>`, :ref:`Owner <owner>`, :ref:`Ownership Type <owntype>`, :ref:`Passability Status <passstat>`, :ref:`Passability Status Note <passstatnote>`, :ref:`Province/Territory Name <provterr>`, :ref:`Provincial Compliance Status <provcompstat>`, :ref:`Provincial Flow Requirements (m3/s) <provflowreq>`, :ref:`Removed Year <remyear>`, :ref:`Reservoir Area (km2) <resarea>`, :ref:`Reservoir Depth (m) <resdepth>`, :ref:`Reservoir Name (English) <resnameen>`, :ref:`Reservoir Name (French) <resnamefr>`, :ref:`Reservoir Present <respres>`, :ref:`Spillway Capacity <spillcap>`, :ref:`Spillway Type <spilltype>`, :ref:`Storage Capacity (mcm) <storagecap>`, :ref:`Structure Type <structype>`, :ref:`Turbine Type <turbtype>`, :ref:`Upstream Catchment Area (km2) <upcatcharea>`, :ref:`Upstream Linear Length (km) <uplength>`, :ref:`Upstream Passage Type <uppasstype>`, :ref:`Use Conservation <useconservation>`, :ref:`Use Fisheries <usefish>`, :ref:`Use Flood Control <useflood>`, :ref:`Use Hydroelectric <usehydro>`, :ref:`Use Invasive Species Control <useais>`, :ref:`Use Irrigation <useirr>`, :ref:`Use Navigation <usenav>`, :ref:`Use Other <useother>`, :ref:`Use Pollution Control <usepoll>`, :ref:`Use Recreation <userec>`, :ref:`Use Water Supply <usesupply>`, :ref:`Used for Network Analysis <useanalysis>`, :ref:`Waterbody Name (English) <waterbodynameen>`, :ref:`Waterbody Name (French) <waterbodynamefr>`

Waterfalls
~~~~~~~~~~
Definition:
    *A natural structure that may impede the ability of fish to travel upstream due to changes in elevation and increased flow velocity.*
Attributes:	
    :ref:`Barrier Identifier <bid>`, :ref:`Comments <commentdef>`, :ref:`Completeness Level <complvl>`, :ref:`Last Modified <lastmod>`, :ref:`Fall Height (m) <fallheight>`, :ref:`Fall Name (English) <fallnameen>`, :ref:`Fall Name (French) <fallnamefr>`, :ref:`Feature Data Source Details <ftdatasrc>`, :ref:`Feature Type <fttype>`, :ref:`Latitude <lat>`, :ref:`Longitude <long>`, :ref:`Municipality <municipality>`, :ref:`NHN Watershed ID <nhnid>`, :ref:`NHN Watershed Name <nhnname>`, :ref:`Passability Status <passstat>`, :ref:`Province/Territory Name <provterr>`, :ref:`Used for Network Analysis <useanalysis>`, :ref:`Waterbody Name (English) <waterbodynameen>`, :ref:`Waterbody Name (French) <waterbodynamefr>` 

Fishways
~~~~~~~~
Definition:
    *A structure that is constructed to facilitate the passage of fish up- and/or downstream of an aquatic barrier (e.g., a dam or waterfall).*
Attributes:
    :ref:`Architect <architect>`, :ref:`Attraction Estimate (%) <attraction>`, :ref:`Average Velocity of Water Flow (m/s) <avgvelocity>`, :ref:`Completeness Level <complvl>`, :ref:`Constructed By <constructby>`, :ref:`Contracted By <contractby>`, :ref:`Dam Identifier <damid>`, :ref:`Designed Based on Biology <biodesign>`, :ref:`Elevation (m) <elevation>`, :ref:`Engineering Notes <engnotes>`, :ref:`Entrance Location <enterlocal>`, :ref:`Entrance Position <enterpos>`, :ref:`Evaluating Study <evalstudy>`, :ref:`Feature Data Source Details <ftdatasrc>`, :ref:`Feature Type <fttype>`, :ref:`Fishway Type <fishwaytype>`, :ref:`Gradient <gradient>`, :ref:`Has Evaluating Studies <hasevalstudy>`, :ref:`Is Modified <ismod>`, :ref:`Latitude <lat>`, :ref:`Length (m) <length>`, :ref:`Longitude <long>`, :ref:`Maximum Velocity of Water Flow (m/s) <maxvelo>`, :ref:`Mean Channel Depth (m) <meandepth>`, :ref:`Modification Purpose <modpurpose>`, :ref:`Modification Year <modyear>`, :ref:`Monitoring Equipment <monitor>`, :ref:`Municipality <municipality>`, :ref:`Nature of Evaluating Studies <natureevalstudy>`, :ref:`NHN Watershed ID <nhnid>`, :ref:`NHN Watershed Name <nhnname>`, :ref:`Operated By <opby>`, :ref:`Operating Note <opnote>`, :ref:`Operation Period <opperiod>`, :ref:`Plans Held By <plansheld>`, :ref:`Province/Territory Name <provterr>`, :ref:`Purpose of Fishway  <fishwaypurpose>`, :ref:`River/Stream Name (English) <rivnameen>`, :ref:`River/Stream Name (French) <rivnamefr>`, :ref:`Species Known to Not Use <knowntouse>`, :ref:`Species Known to Use <knowntouse>`, :ref:`Structure Name (English) <strucnameen>`, :ref:`Structure Name (French) <strucnamefr>`, :ref:`System Identifier <systemid>`, :ref:`Transit Success Estimate (%) <success>`, :ref:`Waterbody Name (English) <waterbodynameen>`, :ref:`Waterbody Name (French) <waterbodynamefr>`, :ref:`Year Constructed <yearconst>`


Attributes 
----------

-----

Attributes Common to Multiple Feature Types
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _bid:

Barrier Identifier
++++++++++++++++++
 **Definition:**	*A unique, static identifier for each barrier point.* 
 
 **Field name:** cabd_id

|dcdamsreturn|

.. _commentdef:

Comments
++++++++
 **Definition:** *Unstructured comments about the feature.*
 
 **Field name:** comments

|dcdamsreturn|

.. _complvl:

Completeness Level
++++++++++++++++++
 **Definition:** *The level of information available for the feature in the CABD.*
 
 **Field name:** complete_level_code

 **Allowable Values:** 

.. csv-table:: 
    :file: tbl/complvl.csv
    :widths: 15, 20, 25, 25, 25
    :header-rows: 1

|dcdamsreturn|

.. _ftdatasrc:

Feature Data Source Details
+++++++++++++++++++++++++++
 **Definition:** *A link to download a CSV of data source information for all attributes of a single feature.* 
 
 **Fields included in download:**

.. csv-table:: 
    :file: tbl/ftdatasrc.csv
    :widths: 25, 75
    :header-rows: 1

|dcdamsreturn|

.. _fttype:

Feature Type
++++++++++++
 **Definition:** *The type of feature the data point represents.*
 
 **Allowable Values:**		

.. csv-table:: 
    :file: tbl/fttype.csv
    :widths: 15, 85
    :header-rows: 1

|dcdamsreturn|

.. _lastmod:

Last Modified
+++++++++++++
 **Definition:** *The release date of the data source most recently used to create, revise, or confirm the feature record.*
 
 **Field name:** last_modified

|dcdamsreturn|

.. _lat:

Latitude
++++++++
 **Definition:** *The geographic x-coordinate representing the location of the feature.* 
 
|dcdamsreturn|

.. _length:

Length (m)
++++++++++
 **Definition:** *Dam - the length of the crest from one bank (or abutment) to the other in meters. Fishway - the length of the fishway in metres.*
 
 **Field name:** length_m

|dcdamsreturn|

.. _long:

Longitude
+++++++++
 **Definition:** *The geographic y-coordinate representing the location of the feature.* 
 
|dcdamsreturn|

.. _municipality:

Municipality
++++++++++++
 **Definition:** *The municipality in which the feature is located.*
 
 **Field name:** municipality

|dcdamsreturn|

.. _nhnid:

NHN Watershed ID
++++++++++++++++
 **Definition:** *A code referencing the work unit ‘Dataset Name’ from the National Hydrographic Network (NHN) in which the feature is located.* 
 
 **Field name:** nhn_watershed_id

|dcdamsreturn|

.. _nhnname:

NHN Watershed Name
++++++++++++++++++
 **Definition:** *The name of the sub-sub watershed in which the feature is located. The name will have a corresponding nhn_watershed_id.*
 
 **Field name:** sub_sub_drainage_area

|dcdamsreturn|

.. _opnote:

Operating Note
++++++++++++++
 **Definition:** *Unstructured comments on important operation considerations for the dam structure or fishway.* 
 
 **Field name:** operating_notes

|dcdamsreturn|

.. _passstat:

Passability Status
++++++++++++++++++
 **Definition:** *The degree to which the feature acts as a barrier to fish in the upstream direction.* 
 
 **Field name:** passability_status_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/passstat.csv
    :widths: 15, 15, 30, 20, 20
    :header-rows: 1

|dcdamsreturn|

.. _passstatnote:

Passability Status Note
+++++++++++++++++++++++
 **Definition:** *Unstructured notes to provide context for the assigned passability status (e.g., species restrictions).*
 
 **Field name:** passability_status_note

|dcdamsreturn|

.. _provterr:

Province/Territory Name
+++++++++++++++++++++++
 **Definition:** *The Province or Territory in which the feature is located.*
 
 **Field name:** province_territory_code

|dcdamsreturn|

.. _waterbodynameen:

Waterbody Name (English)
++++++++++++++++++++++++
 **Definition:** *Name of waterbody in which the feature is recorded (English).* 
 
 **Field name:** waterbody_name_en

|dcdamsreturn|

.. _waterbodynamefr:

Waterbody Name (French)
+++++++++++++++++++++++
 **Definition:** *Name of waterbody in which the feature is recorded (French).* 
 
 **Field name:** waterbody_name_fr

|dcdamsreturn|

.. _useanalysis:

Used for Network Analysis
+++++++++++++++++++++++++
**Definition:** *Indicates whether a barrier should be snapped to the stream network and used for network connectivity analysis.*

**Field name:** use_analysis

**Allowable Values:**	

.. csv-table:: 
    :file: tbl/useanalysis.csv
    :widths: 15, 25, 30, 30
    :header-rows: 1

|dcdamsreturn|

Attributes Unique to Dams
~~~~~~~~~~~~~~~~~~~~~~~~~

.. _assessment-schedule:

Assessment Schedule
+++++++++++++++++++
 **Definition:** *The frequency with which the dam structure is assessed/maintained by an owner or regulatory body.*
 
 **Field name:** assess_schedule

|dcdamsreturn|

.. _avgrate:

Average Rate of Discharge (L/s)
+++++++++++++++++++++++++++++++
 **Definition:** *The average rate of discharge at the dam location in litres per second.*
 
 **Field name:** avg_rate_of_discharge_ls

|dcdamsreturn|

.. _conmaterial:

Construction Material
+++++++++++++++++++++
**Definition:** *The primary construction material of the structure.*

**Field name:** construction_material_code

.. csv-table:: 
    :file: tbl/materialtype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

.. _conyear:

Construction Year
+++++++++++++++++
 **Definition:** *The year dam construction was completed (sometimes a best estimate).*
 
 **Field name:** construction_year

|dcdamsreturn|

.. _damcon:

Dam Condition
+++++++++++++
 **Definition:** *The dam’s physical condition.*
 
 **Field name:** condition_code

 **Allowable Values:**

.. csv-table:: 
    :file: tbl/damcon.csv
    :widths: 15, 15, 70
    :header-rows: 1

|dcdamsreturn|

.. _damfunc:

Dam Function
++++++++++++
 **Definition:** *The intended function of the structure.* 
 
 **Field name:** function_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/damfunc.csv
    :widths: 15, 25, 70
    :header-rows: 1

|dcdamsreturn|

.. _damnameen:

Dam Name (English)
++++++++++++++++++
 **Definition:** *Given or known name of the dam structure (English).*
 
 **Field name:** dam_name_en

|dcdamsreturn|

.. _damnamefr:

Dam Name (French)
+++++++++++++++++
 **Definition:** *Given or known name of the dam structure (French).*
 
 **Field name:** dam_name_fr

|dcdamsreturn|

.. _damsize:

Dam Size
++++++++
 **Definition:** *The size category of the dam based on the height of the dam in meters (‘Height (m)’).* 
 
 **Field name:** size_class_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/damsize.csv
    :widths: 15, 15, 70
    :header-rows: 1

|dcdamsreturn|

.. _damuse:

Dam Use
+++++++
 **Definition:** *The primary use of the dam.*
 
 **Field name:** use_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/damuse.csv
    :widths: 15, 25, 60
    :header-rows: 1

|dcdamsreturn|

.. _degreg:

Degree of Regulation
++++++++++++++++++++
 **Definition:** *Degree of Regulation (DOR) in percent; equivalent to “residence time” of water in the reservoir.*
 
 **Field name:** degree_of_regulation_pc

|dcdamsreturn|

.. _downpass:

Downstream Passage Route
++++++++++++++++++++++++
 **Definition:** *The type of downstream fish passage route associated with the dam.*
 
 **Field name:** down_passage_route_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/downpass.csv
    :widths: 15, 15, 70
    :header-rows: 1

|dcdamsreturn|

.. _explife:

Expected Life (Years)
+++++++++++++++++++++
 **Definition:** *The year the structure will reach its expected end of life.* 
 
 **Field name:** expected_life

|dcdamsreturn|

.. _facilnameen:

Facility Name (English)
+++++++++++++++++++++++
 **Definition:** *The given or known name of the larger facility of which the dam is a part (e.g., a hydroelectric generating station or mining operation); English.*
 
 **Field name:** facility_name_en

|dcdamsreturn|

.. _facilnamefr:

Facility Name (French)
++++++++++++++++++++++
 **Definition:** *The given or known name of the larger facility that the dam is a part (e.g., a hydroelectric generating station or mining operation); French.*
 
 **Field name:** facility_name_fr

|dcdamsreturn|

.. _fedcompstat:

Federal Compliance Status
+++++++++++++++++++++++++
 **Definition:** *The regulatory authorizations that have been approved for the dam by the federal licensing body.*
 
 **Field name:** federal_compliance_status

|dcdamsreturn|

.. _fedflowreq:

Federal Flow Requirements (m3/s)
++++++++++++++++++++++++++++++++
 **Definition:** *The minimum flow recommendations for the dam structure in cubic meters per second (m3/s). Based on assessments by Fisheries and Oceans Canada for the protection of fish and fish habitat.*
 
 **Field name:** federal_flow_req

|dcdamsreturn|

.. _gencap:

Generating Capacity (MWh)
+++++++++++++++++++++++++
 **Definition:** *The amount of electricity the hydroelectric facility can produce in megawatt hours.*
 
 **Field name:** generating_capacity_mwh

|dcdamsreturn|

.. _hydropeak:

Has Hydro Peaking System
++++++++++++++++++++++++
 **Definition:** *Indicates if the dam uses a hydro peaking system.*
 
 **Field name:** hydro_peaking_system

|dcdamsreturn|

.. _damheight:

Height (m)
++++++++++
 **Definition:** *The reported height of the dam in meters. Depending on the data source this can be height of the dam wall, crest height, or head height.* 
 
 **Field name:** height_m

|dcdamsreturn|

.. _lakectrl:

Lake Control
++++++++++++
 **Definition:** *Indicates if a reservoir has been built at the location of an existing natural lake, with the dam acting as a lake control structure.*
 
 **Field name:** lake_control_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/lakectrl.csv
    :widths: 15, 15, 70
    :header-rows: 1

|dcdamsreturn|

.. _lastmaint:

Last Maintenance Date
+++++++++++++++++++++
 **Definition:** *The date of last maintenance or renovation work.*
 
 **Field name:** maintenance_last

|dcdamsreturn|

.. _nextmaint:

Next Maintenance Date
+++++++++++++++++++++
 **Definition:** *The date of the next scheduled maintenance or renovation work.*
 
 **Field name:** maintenance_next

|dcdamsreturn|

.. _turbcount:

Number of Turbines
++++++++++++++++++
 **Definition:** *The number of turbines associated with the dam structure.*
 
 **Field name:** turbine_number

|dcdamsreturn|

.. _opstat:

Operating Status
++++++++++++++++
 **Definition:** *The operating status of the dam.*
 
 **Field name:** operating_status_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/opstat.csv
    :widths: 15, 25, 60
    :header-rows: 1

|dcdamsreturn|

.. _owner:

Owner
+++++
 **Definition:** *The person, company, organization, government unit, public utility, corporation, or other entity which either holds a water license to operate a dam or retains the legal property title on the dam site.* 
 
 **Field name:** owner

|dcdamsreturn|

.. _owntype:

Ownership Type
++++++++++++++
 **Definition:** *The ownership category associated with the dam.*
 
 **Field name:** ownership_type_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/owntype.csv
    :widths: 15, 25, 60
    :header-rows: 1

|dcdamsreturn|

.. _provcompstat:

Provincial Compliance Status
++++++++++++++++++++++++++++
 **Definition:** *The regulatory authorizations that have been approved for the dam by the provincial licensing body.* 
 
 **Field name:** provincial_compliance_status

|dcdamsreturn|

.. _provflowreq:

Provincial Flow Requirements (m3/s)
+++++++++++++++++++++++++++++++++++
 **Definition:** *The legislated flow requirements for the dam structure in cubic meters per second (m^3/s) regulated by the provincial licensing body.*
 
 **Field name:** provincial_flow_req

|dcdamsreturn|

.. _remyear:

Removed Year
++++++++++++
 **Definition:** *The year the dam was decommissioned, removed, replaced, subsumed, or destroyed.*
 
 **Field name:** removed_year

|dcdamsreturn|

.. _resarea:

Reservoir Area (km2)
++++++++++++++++++++
 **Definition:** *The surface area of the reservoir in square kilometers.* 
 
 **Field name:** reservoir_area_skm

|dcdamsreturn|

.. _resdepth:

Reservoir Depth (m)
+++++++++++++++++++
 **Definition:** *The average depth of the reservoir in meters.*
 
 **Field name:** reservoir_depth_m

|dcdamsreturn|

.. _resnameen:

Reservoir Name (English)
++++++++++++++++++++++++
 **Definition:** *Name of the reservoir or controlled lake (English).* 
 
 **Field name:** reservoir_name_en

|dcdamsreturn|

.. _resnamefr:

Reservoir Name (French)
+++++++++++++++++++++++
 **Definition:** *Name of the reservoir or controlled lake (French).* 
 
 **Field name:** reservoir_name_fr

|dcdamsreturn|

.. _respres:

Reservoir Present
+++++++++++++++++
 **Definition:** *Indicates if a reservoir is present due to construction of the dam.* 
 
 **Field name:** reservoir_present

|dcdamsreturn|

.. _spillcap:

Spillway Capacity
+++++++++++++++++
 **Definition:** *The designed capacity of the spillway in m^3/s.* 
 
 **Field name:** spillway_capacity

|dcdamsreturn|

.. _spilltype:

Spillway Type
+++++++++++++
 **Definition:** *The type of spillway associated with the dam structure.* 
 
 **Field name:** spillway_type_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/spilltype.csv
    :widths: 15, 15, 70
    :header-rows: 1

|dcdamsreturn|

.. _storagecap:

Storage Capacity (mcm)
++++++++++++++++++++++
 **Definition:** *The storage capacity of the reservoir in million cubic meters.*
 
 **Field name:** storage_capacity_mcm

|dcdamsreturn|

.. _structype:

Structure Type
+++++++++++++++++
 **Definition:** *The type of structure.* 
 
 **Field name:** structure_type_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/structype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

.. _turbtype:

Turbine Type
++++++++++++
 **Definition:** *The type of turbine in the dam structure.* 
 
 **Field name:** turbine_type_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/turbtype.csv
    :widths: 10, 25, 65
    :header-rows: 1

|dcdamsreturn|

.. _upcatcharea:

Upstream Catchment Area (km2)
+++++++++++++++++++++++++++++
 **Definition:** *The area of the upstream catchment draining into the stream or reservoir in square kilometers.*
 
 **Field name:** catchment_area_skm

|dcdamsreturn|

.. _uplength:

Upstream Linear Length (km)
+++++++++++++++++++++++++++
 **Definition:** *The amount of unobstructed linear kilometers upstream of the dam that would become available to aquatic species if the dam were to be remediated.*
 
 **Field name:** upstream_linear_km

|dcdamsreturn|

.. _uppasstype:

Upstream Passage Type
+++++++++++++++++++++
 **Definition:** *The type of upstream fish passage measure associated with the dam.*
 
 **Field name:** up_passage_type_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/uppasstype.csv
    :widths: 15, 25, 60
    :header-rows: 1

|dcdamsreturn|

.. _useconservation:

Use Conservation
++++++++++++++++
 **Definition:** *Indicates the dam is used for wildlife conservation purposes, and the extent to which wildlife conservation is a planned use.*
 
 **Field name:** use_conservation_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/usetype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

.. _usefish:

Use Fisheries
+++++++++++++
 **Definition:** *Indicates the dam is used for fisheries purposes, and the extent to which fisheries are a planned use.*
 
 **Field name:** use_fish_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/usetype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

.. _useflood:

Use Flood Control
+++++++++++++++++
 **Definition:** *Indicates the dam is used for flood control purposes, and the extent to which flood control is a planned use.*
 
 **Field name:** use_floodcontrol_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/usetype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

.. _usehydro:

Use Hydroelectric
+++++++++++++++++
 **Definition:** *Indicates the dam is used for hydroelectric energy production, and the extent to which hydroelectric production is a planned use.*
 
 **Field name:** use_eletricity_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/usetype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

.. _useais:

Use Invasive Species Control
++++++++++++++++++++++++++++
 **Definition:** 	Indicates the dam is used to control invasive species and the extent to which invasive species control is a planned use.
 
 **Field name:** use_invasivespecies_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/usetype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

.. _useirr:

Use Irrigation
++++++++++++++
 **Definition:** *Indicates the dam is used for irrigation purposes, and the extent to which irrigation is a planned use.* 
 
 **Field name:** use_irrigation_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/usetype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

.. _usenav:

Use Navigation
++++++++++++++
 **Definition:** *Indicates the dam is used for navigation, and the extent to which navigation is a planned use.*
 
 **Field name:** use_navigation_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/usetype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

.. _useother:

Use Other
+++++++++
 **Definition:** *Indicates the dam is used for “other” purposes, and the extent to which it is a planned use.*
 
 **Field name:** use_other_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/usetype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

.. _usepoll:

Use Pollution Control
+++++++++++++++++++++
 **Definition:** *Indicates the dam is used for pollution control purposes, and the extent to which pollution control is a planned use.*
 
 **Field name:** use_pollution_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/usetype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

.. _userec:

Use Recreation
++++++++++++++
 **Definition:** *Indicates the dam is used for recreation purposes, and the extent to which recreation is a planned use.*
 
 **Field name:** use_recreation_code

 **Allowable Values:**	
 
.. csv-table:: 
    :file: tbl/usetype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

.. _usesupply:

Use Water Supply
++++++++++++++++
 **Definition:** *Indicates the dam is used for water supply purposes, and the extent to which water supply is a planned use.*
 
 **Field name:** use_supply_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/usetype.csv
    :widths: 15, 20, 65
    :header-rows: 1

|dcdamsreturn|

Attributes Unique to Waterfalls
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _fallheight:

Fall Height (m)
+++++++++++++++
 **Definition:** *Height of the waterfall in metres.* 
 
 **Field name:** fall_height_m

|dcfallreturn|

.. _fallnameen:

Fall Name (English)
+++++++++++++++++++
 **Definition:** *Given or known name of the waterfall (English).*
 
 **Field name:** fall_name_en

|dcfallreturn|

.. _fallnamefr:

Fall Name (French)
++++++++++++++++++
 **Definition:** *Given or known name of the waterfall (French).*
 
 **Field name:** fall_name_fr

|dcfallreturn|

Attributes Unique to Fishways
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. _architect:

Architect
+++++++++
 **Definition:** *Company/organization that designed the fishway structure.* 
 
 **Field name:** architect

|dcfishreturn|

.. _attraction:

Attraction Estimate (%)
+++++++++++++++++++++++
 **Definition:** *Portion of individuals attracted to the fishway in percent.* 
 
 **Field name:** estimate_of_attraction_pct

|dcfishreturn|

.. _avgvelocity:

Average Velocity of Water Flow (m/s)
++++++++++++++++++++++++++++++++++++
 **Definition:** *Average velocity of water flow through the fishway in m/s.* 
 
 **Field name:** mean_fishway_velocity_ms

|dcfishreturn|

.. _constructby:

Constructed By
++++++++++++++
 **Definition:** *Name of the company that constructed the fishway.* 
 
 **Field name:** constructed_by

|dcfishreturn|

.. _contractby:

Contracted By
+++++++++++++
 **Definition:** *Name of the agency that contracted the fishway.* 
 
 **Field name:** contracted_by

|dcfishreturn|

.. _damid:

Dam Identifier
++++++++++++++
 **Definition:** *The unique barrier identifier (cabd_id) corresponding to the dam that the fishway structure is associated with.* 
 
 **Field name:** dam_id

|dcfishreturn|

.. _biodesign:

Designed Based on Biology
+++++++++++++++++++++++++
 **Definition:** *Indicates whether the fishway was designed based on the biology of the species.* 
 
 **Field name:** designed_on_biology

|dcfishreturn|

.. _elevation:

Elevation (m)
+++++++++++++
 **Definition:** *Change in height between fishway exit and entrance in meters.* 
 
 **Field name:** elevation_m

|dcfishreturn|

.. _engnotes:

Engineering Notes
+++++++++++++++++
 **Definition:** *Notes regarding design and construction of the fishway* 
 
 **Field name:** engineering_notes

|dcfishreturn|

.. _enterlocal:

Entrance Location
+++++++++++++++++
 **Definition:** *Indicates if the entrance of the fishway is located mid-stream or on the bank.* 
 
 **Field name:** entrance_location_code

 **Allowable Values:** Midstream(1), Bank(2)

|dcfishreturn|

.. _enterpos:

Entrance Position
+++++++++++++++++
 **Definition:** *Indicates the entrance position of the fishway in the water column.*
 
 **Field name:** entrance_position_code 

 **Allowable Values:** Bottom(1), Surface(2), Bottom and Surface(3), Mid-column(4)

|dcfishreturn|

.. _evalstudy:

Evaluating Study
++++++++++++++++
 **Definition:** *The reference for the literature (peer-reviewed and ‘‘grey’’) used to gather additional information about the fishway.* 
 
 **Field name:** fishway_reference_id

|dcfishreturn|

.. _fishwaytype:

Fishway Type
++++++++++++
 **Definition:** *The type of fishway structure (values are consistent with ‘Upstream Passage Type’ values for dams).* 
 
 **Field name:** fishpass_type_code

 **Allowable Values:**	

.. csv-table:: 
    :file: tbl/uppasstype.csv
    :widths: 25, 15, 60
    :header-rows: 1
	
|dcfishreturn|

.. _gradient:

Gradient
++++++++
 **Definition:** *The fishway’s angle of inclination in percent.* 
 
 **Field name:** gradient

|dcfishreturn|

.. _hasevalstudy:

Has Evaluating Studies
++++++++++++++++++++++
 **Definition:** *Indicates whether an evaluation study has been performed at the fishway.* 
 
 **Field name:** has_evaluating_studies

|dcfishreturn|

.. _ismod:

Is Modified
+++++++++++
 **Definition:** *Indicates if the fishway has had any post-construction modifications.* 
 
 **Field name:** modified

|dcfishreturn|

.. _maxvelo:

Maximum Velocity of Water Flow (m/s)
++++++++++++++++++++++++++++++++++++
 **Definition:** *Maximum velocity of water flow recorded in the fishway in m/s.* 
 
 **Field name:** max_fishway_velocity_ms

|dcfishreturn|

.. _meandepth:

Mean Channel Depth (m)
++++++++++++++++++++++
 **Definition:** *Depth of fishway channel, in meters, during operation.* 
 
 **Field name:** depth_m

|dcfishreturn|

.. _modpurpose:

Modification Purpose
++++++++++++++++++++
 **Definition:** *Purpose of post-construction modifications.*
 
 **Field name:** modification_purpose

|dcfishreturn|

.. _modyear:

Modification Year
+++++++++++++++++
 **Definition:** *The year that post-construction modifications were completed.*
 
 **Field name:** modification_year

|dcfishreturn|

.. _monitor:

Monitoring Equipment
++++++++++++++++++++
 **Definition:** *Monitoring equipment used at the fishway.*
 
 **Field name:** monitoring_equipment

|dcfishreturn|

.. _natureevalstudy:

Nature of Evaluating Studies
++++++++++++++++++++++++++++
 **Definition:** *The type of evaluation study performed.*
 
 **Field name:** nature_of_evaluation_studies

|dcfishreturn|

.. _opby:

Operated By
+++++++++++
 **Definition:** *Agency responsible for operating the fishway.*

 **Field name:** operated_by

|dcfishreturn|

.. _opperiod:

Operation Period
++++++++++++++++
 **Definition:** *The dates the fishway is in operation.*
 
 **Field name:** operation_period

|dcfishreturn|

.. _plansheld:

Plans Held By
+++++++++++++
 **Definition:** *Name of the agency that possesses the plans for the fishway.*
 
 **Field name:** plans_held_by

|dcfishreturn|

.. _fishwaypurpose:

Purpose of Fishway
++++++++++++++++++
 **Definition:** *The reason the fishway was designed and implemented.* 
 
 **Field name:** purpose

|dcfishreturn|

.. _rivnameen:

River/Stream Name (English)
+++++++++++++++++++++++++++
 **Definition:** *Name of river/stream in which the feature is recorded (English).* 
 
 **Field name:** river_name_en

|dcfishreturn|

.. _rivnamefr:

River/Stream Name (French)
++++++++++++++++++++++++++
 **Definition:** *Name of river/stream in which the feature is recorded (French).* 
 
 **Field name:** river_name_fr

|dcfishreturn|

.. _knownnotuse:

Species Known to Not Use
++++++++++++++++++++++++
 **Definition:** *Species where it is known that the fishway presents a significant barrier to migration.*
 
 **Field name:** known_to_not_use

|dcfishreturn|

.. _knowntouse:

Species Known to Use
++++++++++++++++++++
 **Definition:** *Species that are known to use the fishway.* 

 **Field name:** known_to_use
 
|dcfishreturn|

.. _strucnameen:

Structure Name (English)
++++++++++++++++++++++++
 **Definition:** *The given or known name of the fishway structure or the dam with which it is associated (English).* 
 
 **Field name:** structure_name_en

|dcfishreturn|

.. _strucnamefr:

Structure Name (French)
+++++++++++++++++++++++
 **Definition:** *The given or known name of the fishway structure or the dam it is associated with (French).* 
 
 **Field name:** structure_name_fr

|dcfishreturn|

.. _systemid:

System Identifier
+++++++++++++++++
 **Definition:** *Unique identifier for each fishway point.* 
 
 **Field name:** cabd_id

|dcfishreturn|

.. _success:

Transit Success Estimate (%)
++++++++++++++++++++++++++++
 **Definition:** *Estimated percentage of individuals that successfully pass through the fishway.*
 
 **Field name:** estimate_of_passage_success_pct

|dcfishreturn|

.. _yearconst:

Year Constructed
++++++++++++++++
 **Definition:** *Year in which the fishway structure was built.* 
 
 **Field name:** year_constructed
 
|dcfishreturn|
