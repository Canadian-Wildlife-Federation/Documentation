====================
Flowpath Constructor
====================

Modification Date
 2020 April 6

Purpose
-------

* The Flowpath Constructor may be used to generate all elementary flowpaths found in polygonal waterbodies, such as lakes, estuaries and double-line (i.e. comparatively wide) rivers, or subdivisions of such waterbodies. It may for example be of interest to break large lakes or rivers into multiple subdivisions.
* In some situations existing skeletons in lakes are available that are considered worth retaining, in terms of both their geometry and associated attributes. In this case, the Flowpath Constructor can be run such that only bank flowpaths are generated. Where a bank flowpath intersects an existing skeleton flowpath, the existing skeleton flowpath is broken into two skeleton flowpaths, with identical attribution.
* In addition to the skeletonizer the Flowpath Constructor includes a directionalizer that can determine the direction of a flowpath if newly created or if the direction is unknown.
* The tool can also assess whether a flowpath represents a primary or secondary flow; this is of particular interest in areas where the flowpaths do not all follow a dendritic pattern, i.e., at points of divergence. The resulting primary flowpaths do form a dendritic pattern. Any cycles in the network (where water can flow around a loop back to its starting position) are corrected where practical.
