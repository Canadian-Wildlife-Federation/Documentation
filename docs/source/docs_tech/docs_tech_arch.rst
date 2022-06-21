.. _application-architecture:

========================
Application Architecture
========================

This section contains technical details about the current implementation of the Canadian Aquatic Barriers Database (CABD) back-end application, including feaure and vector tile services and the CABD data dictionary. The intended audience are software developers and similar technical users looking to upgrade/maintain the current system or use the API endpoints.

Section Contents
----------------

-----

`Features and Database Models <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_models.html#>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* `Existing Implementation <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_models.html#existing-implementation>`_
    
* `CABD Feature Model <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_models.html#cabd-feature-model>`_
    
  * `Generic Feature Model <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_models.html#generic-feature-model>`_
    
  * `Implemented Feature Model <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_models.html#implemented-feature-model>`_
    
* `CABD Database Model <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_models.html#cabd-database-model>`_
    
  * `Views <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_models.html#views>`_
    
  * `Core Tables <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_models.html#core-tables>`_
    
  * `Shared Attribute Tables <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_models.html#shared-attribute-tables>`_
    
  * `Feature Tables <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_models.html#feature-tables>`_
    
  * `Feature Type Attribute Data Sources <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_models.html#feature-type-attribute-data-sources>`_
    
* `How To Add a New Feature Type <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_models.html#how-add-a-new-feature-type>`_

`REST Services (API Endpoints) <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_api.html>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* `API End Points <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_api.html#api-end-points>`_

  * `Feature Type End Points <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_api.html#feature-type-end-points>`_

  * `Feature End Points <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_api.html#feature-end-points>`_

  * `Filter <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_api.html#filter>`_

  * `Format <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_api.html#format>`_

  * `Maximum Features <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_api.html#maximum-features>`_

* `Feature Data Source End Point <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_api.html#feature-data-source-end-point>`_

  * `Format <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_api.html#feature-datasource-endpoint-format>`_

`Vector Tile Service <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_tiles.html>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* `Format <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_tiles.html#format>`_

* `CHyF API End Points <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_tiles.html#chyf-api-end-points>`_

`Data Dictionary <https://cabd-docs.netlify.app/docs_tech/docs_tech_arch/docs_tech_arch_data_dict.html>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. toctree::
    :hidden:
    
    docs_tech_arch/docs_tech_arch_models
    docs_tech_arch/docs_tech_arch_api
    docs_tech_arch/docs_tech_arch_tiles
    docs_tech_arch/docs_tech_arch_data_dict