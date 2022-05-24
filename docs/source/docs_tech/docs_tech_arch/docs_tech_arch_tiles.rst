===================
Vector Tile Service
===================

Format
------

-----

The only format supported for the vector tile services is mvt (mapbox vector tile).

CHyF API End Points
-------------------

-----

``/chyf-web/tiles/water/{z}/{x}/{y}.{format}``

End point for water features.  This includes single line streams and polygonal waterbody features. The output features include the following attributes:

.. csv-table:: 
    :file: tbl/flow_attributes.csv
    :widths: 30, 70
    :header-rows: 1

``/chyf-web/tiles/ecatchment/{z}/{x}/{y}.{format}``

Contains catchments.  Currently there are no catchments loaded into CHyF database so these vector tiles will be empty. The output features include the following attributes:

.. csv-table:: 
    :file: tbl/catch_attributes.csv
    :widths: 30, 70
    :header-rows: 1

``/chyf-web/tiles/nhnworkunit/{z}/{x}/{y}.{format}``

End point for NHN work unit polygonal features. The output features include the following attributes:

.. csv-table:: 
    :file: tbl/wu_attributes.csv
    :widths: 30, 70
    :header-rows: 1
