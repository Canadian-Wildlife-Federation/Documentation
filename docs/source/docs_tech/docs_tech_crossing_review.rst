=========================================
Data Processing Methods: Stream Crossings
=========================================

Stream crossings in the CABD are compiled from a variety of sources. The starting point are “modelled stream crossings” - which are identified by finding places where the stream network intersects a road, railway, or trail. 

Then, inventories of bridges, culverts, and other structures help fill in data gaps by identifying structure types for modelled crossings.

Finally, stream crossing assessment data is incorporated to fill in more detailed information that will help in determining whether the crossing is passable to fish, such as the number of crossing structures, crossing condition, outlet shape, and whether the water depth and velocity through the crossing match the natural stream conditions.

Generate modelled stream crossings
----------------------------------

Modelling stream crossings is an important first step to identify areas where human-made structures may be blocking fish passage. The CABD team compiles authoritative data about transportation networks - roads, railways, and trails - for each province and territory and runs a model that identifies all the areas where these transportation networks intersect a stream from NRCan’s National Hydrographic Network (NHN).

The model automatically clusters crossings within a specified distance (which may differ between provinces and territories) and removes duplicate stream crossings based on a set of rules. Some of these rules include:

- If there are multiple modelled crossings within 20 m of each other, keep only the most downstream crossing
- Flag crossings for removal that are on winter roads, canoe routes, or ferry routes
- Flag crossings for removal where the transportation network indicates the crossing has been removed

Since crossings associated with railway networks are often separate from those on other nearby roads or trails, modelled crossings on railways are generally clustered and de-duplicated separately. However, in some areas of Canada, old railway lines have been converted to ‘rail trails’, which may result in two crossings being generated on each of the railway and trail lines. In these cases, the modelled crossing on the railway is kept, but relevant information from the trail layer (trail name and trail association) is added to these points, along with a comment indicating that the point is on a rail trail.

The scripts used to generate modelled stream crossings are available at https://github.com/Canadian-Wildlife-Federation/CABD/tree/main/cabd-database/barriers/stream_crossings.

Clean up modelled stream crossings
----------------------------------

As modelled stream crossings are generated from the intersection of transportation networks and stream networks, there are often useful pieces of information from these networks that can be added to the crossing, such as:

- road/railway/trail name
- stream name
- stream order - this is a proxy for stream size, where larger streams fed by multiple tributaries typically have a larger stream order
- type of road - e.g., highway, residential, arterial
- type of crossing - some networks may have separate sections that indicate bridges, culverts, or other structures
- owner or operator of the road, railway, or trail

Crossings that are on a stream order 6 or higher are also automatically given a crossing type of ‘bridge’, as it’s assumed that most crossings on these larger streams would be bridges.

Incorporate structure inventories
---------------------------------

When structure inventories are openly available for a province/territory, city, or region, this information is added to stream crossings to help identify the locations of culverts and bridges.

As each inventory is unique, the CABD team reviews each dataset for relevant information, determines an appropriate distance for matching structure points to modelled crossings, and checks the results of these matches before finalizing.

Bridges are particularly important to identify, as these structures are passable to fish in almost all cases. Finding the locations of bridges lets us remove these from the count of barriers to fish in a watershed.

To identify if a structure inventory was used to help fill in information about a particular crossing, refer to the `crossing_type_source` and cross-reference this value with the CABD data sources page: https://cabd-docs.netlify.app/docs_user/docs_user_data_sources

Manual review
-------------

The CABD team also carries out a number of checks manually using satellite imagery to supplement the information described above. Some of these checks include:

- Review all crossings classified as bridges based on stream order.
    - During this check, some crossings may be changed to ‘culvert’ or ‘multiple culvert’, or marked for removal if there is no permanent stream crossing infrastructure at that location.
    - Some bridges may also have multiple crossing points representing them - in these cases, only a single crossing point is kept.
- Review all crossings within 25 m of another crossing to confirm if there are multiple separate crossings in that location
- Review all crossings within 45 m of a dam to confirm if the crossing exists, and is separate from the dam structure
- Review all crossings that are on the same transportation network segment and stream segment. These typically result from streams that are represented as flowing nearly parallel to a transportation network, but may occur in other areas with a high density of roads or railways such as highway on/off ramps and interchanges, train yards, and residential areas.
- Review all crossings on a named watercourse where the name includes ‘River’ or ‘Rivière’. These are often bridges.