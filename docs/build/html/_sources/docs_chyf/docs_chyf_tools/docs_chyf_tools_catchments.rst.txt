=====================
Catchment Delineator
=====================

Modification Date
 2020 April 6

Purpose
-------

-----

* This tool is used to create CHyF compliant catchments from hydrographic data in combination with a gridded Digital Elevation Model that represents the elevation of the bare earth. 
* It takes into account the surface hydrography and a digital elevation model representing the ground surface. In very flat areas where the elevation data may not be very helpful, the results approximate a medial axis approach, with each catchment boundary placed about halfway between the nearby linear or polygonal waterbodies. Where local elevation differences are more significant, the boundaries are located such that the slopes on either side are oriented toward different waterbodies. The software makes a natural and continuous progression between these cases.
* CHyF compliant catchments delineated by the tool include reach catchments and bank catchments. Water catchments, which may for example correspond to lakes, wide streams, or estuaries - or subdivisions of such features - are provided by the user as input. 
* The reach catchments, bank catchments and water catchments form a complete coverage of the Area of Interest. 
* Empty catchments are out of scope with this version of the delineator. This means that depressions that do not contain linear or polygonal waterbodies and are not bordering such waterbodies will be absorbed into adjacent catchments.  
* Special treatment of built-up areas is also out of scope at this time.  
