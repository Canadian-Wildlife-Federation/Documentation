============
Stream Order
============

This document describes the tool developed to compute stream orders, mainstems and other attributes for CHyF2 compliant datasets.

The software is open source under the Apache 2 license. It is written in Java SE 11 (Long Term Support). It can be run directly or by using Python scripts, for example, if desired.

Workflow
--------

-----

The stream order processing is designed to be executed after the hydro network has been converted into the CHyF model. Stream order values should be recomputed whenever any updates are made to the CHyF datasets. Processing is done on the entire CHyF dataset.

.. figure:: img/stream_order/highlvlworkflow.png
    :align: center

    *Figure 1. High level workflow* 

Inputs and Outputs
------------------

-----

The CHyF mainstem/order processing tool requires the CHyF data to be hosted in a PostgreSQL database.  All inputs and outputs are read/written directly from/to the database.

Inputs
~~~~~~

The input data meets the CHyF2 model specifications. The input database schema for the datasets is provided as a parameter (see Running the Software). The stream order computer uses the following tables and associated fields.

.. csv-table:: 
    :file: tbl/so_inputs.csv
    :widths: 30, 70
    :header-rows: 1

Outputs
~~~~~~~

The output table/schema for the results is provided as a parameter (see Running the Software). If the output table exists, it will be dropped and recreated. The table below describes the values computed and the fields in the output table.

.. csv-table:: 
    :file: tbl/so_outputs.csv
    :widths: 20, 10, 70
    :header-rows: 1

Graph ID
++++++++

Each connected graph component is assigned a unique identifier. The graph components are connected subgraphs which have no flowpath connections between them. While not required for mainstem or order processing, it is computed for performance reasons and may be useful for future computations. The graph id is applied to all edges (primary and secondary).

.. figure:: img/stream_order/graphid.png
    :align: center

    *Figure 2. Example data coloured by graph id* 

Mainstem ID
+++++++++++

Mainstems are computed based on the stream network formed by selecting primary, non-bank flowpath edges. All secondary and bank flowpath edges are not assigned a mainstem.

There are two options for computing mainstems:

#. Based entirely on the longest upstream path.
#. Based on both names and the longest upstream path.

Longest Upstream Path Only
``````````````````````````
When computing mainstems based on the longest upstream path, for each sink the flow network is traversed upstream. At each confluence the path with the longest length to the headwaters is selected for the mainstem.  All other edges represent the start of a new mainstem.

.. figure:: img/stream_order/mainstemid.png
    :align: center

    *Figure 3. Example data coloured by mainstem id.*

Names and Longest Upstream Path
```````````````````````````````

Similar to longest upstream path, except at each confluence:

* First look for the upstream edge with the same name as the downstream edge. If found, use this upstream path for the mainstem.
* Second, look for any named upstream edge. If found, use this upstream path for the mainstem. If multiple named edges are found, use the one with the longest length to the headwaters.
* Lastly, use the path with the longest length to the headerwaters.

Mainstem Sequence Number
++++++++++++++++++++++++

The mainstem sequence number orders mainstem edges from the sink to the headwaters. This only applies to edges with mainstems (primary, non-bank flowpath edges).

.. figure:: img/stream_order/mainstemseqnum.png
    :align: center

    *Figure 4. Example data labeled by mainstem sequence numbers.*

Maximum Upstream length
+++++++++++++++++++++++

The maximum upstream length is used for computing mainstem. As with mainstems it is based on the stream network formed by selecting primary, non-bank flowpath edges. All secondary and bank flowpath edges are not assigned upstream length values.

The maximum upstream length is the longest path to a headwaters from the upstream nexus of the edge. As a result, headwater edges will have a value of 0. Length is computed in the same units as the flowpath edge length property.

.. figure:: img/stream_order/uplength.png
    :align: center

    *Figure 5. Example data displayed with values for upstream length (black) and individual edge length (blue).*

