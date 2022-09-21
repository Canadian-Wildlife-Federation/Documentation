.. _cabd-overview:

===================
CABD Overview
===================

The Database
------------

The CABD is a standardized, curated, central, and open database for barrier and connectivity data in Canada. Currently, the CABD 1.0 offers three types of data:

#.	Dams v1.0 (and associated structures)
#.	Waterfalls v1.0
#.	Fishways v1.0

.. important::
   One of the :ref:`defined uses <use-cases>` for the CABD is creating an inventory of infrastructe locations and conditions. As such, in addition to the main dam structure, the CABD also includes ancillary and lateral structures associated with dam facilities (e.g., saddle dams, lateral embankments, canal walls) that don't necessarily fragment freshwater systems in the upstream-downstream plane. As such, these structure should not be used for connectivity network analyses or barrier prioritization exercises (unless you are specifically interested in these ancillary structures). To help users filter out these structures, data points that should not be used for network analysis are identified using the :ref:`Used for Network Analysis <useanalysis>` field(``use_analysis = false`` in the data).

We know that aquatic barriers are prevalent across Canada, that barrier removal is needed to restore connectivity and access to vital habitat for aquatic species, and that restoration projects are expensive. But we don’t have the answers to some important questions: How many barriers exist in Canada? How much habitat is not accessible for fish and other species? How do we identify the most important barriers to restore and maximize benefits for these species? We need a comprehensive information source to answer these questions, which is where the CABD comes in! The CABD will allow CWF and other organizations across the country to assess and report on the status of habitat connectivity and inform management and regulatory decisions relating to infrastructure construction and management. It also supports barrier restoration planning and prioritization of projects to improve connectivity and fish passages for important species. Additionally, the database will inform research and monitoring initiatives to better understand the effects these barriers have on freshwater ecosystems and the species they support and provide a national forum for sharing resources, best practices, and success stories to support education and public outreach.

Is the CABD 1.0 a perfect dataset? **No!** Data gaps exist in our datasets -- we are going to be missing structures and need to fill in attribute gaps for the majority of existing points (you'll see a lot of "Unknowns" in the layers). For CABD 1.0 we have relied on compiling :ref:`existing spatial data sources <data-sources>` and performing de-duplication, geolocation, attribute mapping (i.e., bringing in and tracking attributes that come from various sources for an individual feature), and standardizing to the CABD data structures. To date, we have compiled over 100 dam, waterfall, and fishway data sources. As such, while not perfect, the CABD datasets do represent the most comprehensive information source for dams, waterfalls, and fishways in Canada.

We are working hard to begin to fill existing data gaps by reviewing non-spatial data sources (e.g., reports, scientific studies, websites) that can provide additional information for structures. Filling these data gaps is a huge job and we’re hoping people across Canada can help! We’re working on some new tools to allow users to submit information through the CABD web tool, but in the meantime check out the :ref:`Submit Data Updates page <submit-updates>` or reach out to us to learn how you can help us fill these data gaps. We’ll release data updates periodically with new information, so stay tuned for :ref:`future release announcements <whats-new>`!

Check out our `blog post <INSERT LINK TO BLOG POST HERE>`_ for more information on the CABD 1.0 release, and the `Canadian Wildlife Federation website <https://cwf-fcf.org/en/explore/fish-passage/aquatic-barrier-database.html>`_ for more project details, including FAQs.

*Data in the CABD is made available through the* `CC BY-SA 4.0 <https://creativecommons.org/licenses/by-nc-sa/4.0/>`_ *license. This license allows you to share and adapt this data, as long as you provide proper credit and distribute any derivative data under the same CC BY-SA 4.0 license.*

The Web Tool
------------

We're really excited about the `CABD web tool <https://aquaticbarriers.ca/>`_, which provides an easy way to explore and access the data through your web browser. Currently, the tool (and this documentation site) are only available in English, but we will be releasing French versions in Winter 2022/23.

Through the web mapping interface, you can:

- Explore the barrier and fishway data, and click on points to view their attributes
- Toggle between a standard basemap and satellite imagery
- Filter layers based on location (e.g., province or watershed) or attributes (e.g., dam use)
- Download the data in various formats -- shapefile, geopackage, kml, and csv
- View the data sources used (so far) to compile the CABD

Visit the :ref:`Tutorials <tutorials>` section to learn out to navigate and use the web tool.

What's coming up next?
----------------

We have some ambitious plans for the CABD -- and will continue to focus on filling data gaps for dams, waterfalls, and fishways across Canada -- but our main focus in the coming months will be to begin compiling stream crossing data and integrating it into the CABD.

CABD 1.0 is a vital step towards meeting the data needs to support connectivity conservation and fish passage restoration work; however, dams are only one type of human-made structures that fragment freshwater ecosystems in Canada. While dams are often major barriers to connectivity, smaller structures like stream crossings (e.g., roads, rail lines, or trail cross streams) -- of which there are over a million in Canada -- combine to create major concerns for freshwater connectivity through the cumulative effects of the sheer volume of these structures. As part of the next stage of the CABD, CWF is working on incorporating stream crossings by developing a standardized data structure and beginning to compile existing data sources. CWF will continue to work with partners, stakeholders, and interested parties to ensure that the stream crossing data is useful and available to practitioners across the country.
