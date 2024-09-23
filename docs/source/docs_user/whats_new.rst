.. _whats-new:

===================
What's new?
===================

This page contains the latest announcements related to the CABD, including any releases of new versions of the data layers.

If you'd like to be added to a mailing list to receive email notifications when new data updates are released, send us an email at **cabd@cwf-fcf.org**.

-----

Announcements
-------------

**September 23, 2024**

We are pleased to announce the release of stream crossings in the CABD. This initial release of stream crossings includes 'modelled' stream crossing points, automatically generated where streams intersect with transportation networks (such as roads, railways, and trails). These points represent locations where structures like bridges, culverts, or fords are likely to exist. Future updates will integrate field verification and existing stream crossing assessments information.

For more information about the modelled stream crossings data structure, please visit the Data Catalogue: https://cabd-docs.netlify.app/docs_user/docs_user_data_catalogue#ft_modelled_crossings.

For more information about how modelled stream crossings were compiled, please visit the Data Processing Methods page: https://cabd-docs.netlify.app/docs_tech/docs_tech_crossing_review.

With this release, we are launching a new feature that allows anyone to provide information on aquatic barriers directly through the `CABD web tool <https://aquaticbarriers.ca/en>`_. This feature is a simple form that is intended to make sharing information you may have about structures in your area as easy as possible. You can access this feature by navigating to the CABD web tool and opening the attribute popup for the structure in question by clicking on it in the map. From there, clicking on the ‘Update This Information' tab within the popup will open the form, which you can then fill out. As part of this form, you can also choose to be added to the CABD mailing list to receive updates on new releases and other news. 

For more information about the 'Update This Information' feature, please visit the Submit Data Updates page: https://cabd-docs.netlify.app/docs_user/docs_user_submitted_updates.


**April 24, 2024**

Two new passability statuses were added to the CABD:

*   NA - no structure
*   NA - removed/decommissioned

As a result of this change, any structures with an operating_status of 'removed/decommissioned' will also now have a passability_status of 'NA - removed/decommissioned' instead of 'passable'.

You will also notice that there are new symbols used to represent these passability statuses in the web tool. We hope this helps users better distinguish between structures that have been removed/decommissioned versus those that have been made passable through fish passage rehabilitation projects.

**May 15, 2023**

The CABD web tool has been updated to make searching, filtering, and visualizing data easier and faster for our users.

*   You can now search by structure name, facility name, and cabd_id.
*   Decimal degree coordinates are now entered in a single box when searching by latitude and longitude.
*   Filtering by watershed has been improved to address issues with selecting and deselecting watersheds from the map.
*   After applying filters, you will now see a count of the filtered features out of the total count of features available in the CABD.
*   When downloading data, the default option will be to download a filtered version of the dataset with any filters you have applied. If you have not applied any filters, this will download the full dataset.

In addition to these UI improvements, several updates were made to dams and waterfalls in BC and PEI based on new information from local groups. Please see the :ref:`Data Releases <data-releases>` table for more information on these changes.

**September 25, 2022**

We are pleased to announce the release of version 1.0 of the CABD (CABD 1.0), which is the baseline version and includes complete national coverage for three types of data across Canada:

#.	Dams v1.0
#.	Waterfalls v1.0
#.	Fishways v1.0

You can also now explore, filter, and download the data through the CABD web tool! We’re continuing to work hard to fill data gaps and incorporate additional barrier types (e.g., stream crossings) in the CABD, so stay tuned and check back here periodically for new updates and data releases.

.. _data-releases:

Data Releases
-------------

.. csv-table:: 
    :file: tbl/data-releases.csv
    :widths: 15, 20, 55, 20
    :header-rows: 1
