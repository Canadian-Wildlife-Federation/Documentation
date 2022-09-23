.. _data-sources:

============
Data Sources
============

.. note::
    
    If you're visiting from the CABD web tool, and accidently closed your tab, you can navigate back to the web tool `here <https://aquaticbarriers.ca>`_.


The CABD only exists due to all the painstaking work done by many groups and organizations who have compiled and maintained existing barrier inventories across North America, and either made them openly available or entered into data-sharing agreements with us. A special thank you to these groups! The CABD simply builds off this existing work, and we hope that our work to fill data gaps can benefit original data holders in return. If you are the maintainer of one of the data sources on this page, and would like to chat about how we can share some of our data updates back to you, please contact us at cabd@cwf-fcf.org.

A lot of the work done on the CABD involved de-duplicating and combining attributes for where two or more data sources have a point representing the same structure. This means that for a single point in the CABD, attribute information may be coming from multiple different sources, which makes data-source attribution a bit tricky! We've come up with a solution to map where each attribute in a CABD data point comes from, check out the :ref:`Feature Data Source Details Download <data-source-details>` page for more information.

.. _searchtable:

Data Sources Search Table
-------------------------

-----

You can filter through the data sources using the search table below. To find a data source, enter any number of keywords into the search box and the table will update automatically with the matching results. To view additional details for a data source including formal reference, simply click on the data source short name. This is a link that will bring you to the details for the data source entry. An arrow, |ds_searchtbl_return|, below each entry will return you to the top of the search table.

.. table:: 
   :class: datatable
   :widths: 5, 5, 40, 45, 5

   =========== ======================== ============================================================================================== ============================================================================================================================================================== ==========================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================
   Data Type   Source Type              Organization Name                                                                              Data Source Name                                                                                                                                               Data Source Short Name                                                                                                                                                                                      
   =========== ======================== ============================================================================================== ============================================================================================================================================================== ==========================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================
   Spatial     Federal                  Natural Resources Canada (NRCan)                                                               Canadian Geographical Names Database                                                                                                                           :ref:`nrcan_cgndb <nrcan_cgndb>`                                                                                                                                                                                                                                        
   Spatial     Federal                  Natural Resources Canada (NRCan)                                                               CanVec Series – Manmade Features                                                                                                                               :ref:`nrcan_canvec_mm <nrcan_canvec_mm>`                                                                                                                                                                                             
   Spatial     Federal                  Natural Resources Canada (NRCan)                                                               CanVec Series - Hydrographic Features                                                                                                                          :ref:`nrcan_canvec_hyf <nrcan_canvec_hyf>`                                                                                                                                                                                            
   Spatial     Federal                  Natural Resources Canada (NRCan)                                                               National Hydrographic Network (NHN)                                                                                                                            :ref:`nrcan_nhn <nrcan_nhn>`                                                                                                                                                                                                   
   Spatial     Federal                  Statistics Canada                                                                              Intercensal - Census Subdivision Boundary Files                                                                                                                :ref:`statscan_census_subs <statscan_census_subs>`                                                                                                                                                                                        
   Spatial     Federal                  United States Army Corps of Engineers                                                          National Inventory of Dams                                                                                                                                     :ref:`usace_nid <usace_nid>`                                                                                                                                                                                                   
   Spatial     Provincial/State         Alberta - Environment and Parks (AEP)                                                          Base Features Hydrography                                                                                                                                      :ref:`aep_bf_hy <aep_bf_hy>`                                                                                                                                                                                                   
   Spatial     Provincial/State         British Columbia - Environment and Climate Change Strategy                                     Provincial Obstacles to Fish Passage (FISS)                                                                                                                    :ref:`bceccs_fiss <bceccs_fiss>`                                                                                                                                                                                                 
   Spatial     Provincial/State         British Columbia - Forests, Lands, Natural Resource Operations and Rural Development (FLNRORD) BC Geographic Warehouse – Public Dams                                                                                                                          :ref:`bcflnrord_wris_pubdams <bcflnrord_wris_pubdams>`                                                                                                                                                                                      
   Spatial     Provincial/State         British Columbia - Forests, Lands, Natural Resource Operations and Rural Development (FLNRORD) BC Public Dams KML                                                                                                                                             :ref:`bcflnrord_kml_pubdams <bcflnrord_kml_pubdams>`                                                                                                                                                                                       
   Spatial     Provincial/State         British Columbia - Forests, Lands, Natural Resource Operations and Rural Development (FLNRORD) Freshwater Atlas (FWA) Obstructions                                                                                                                            :ref:`bcflnrord_fwa <bcflnrord_fwa>`                                                                                                                                                                                               
   Spatial     Provincial/State         Maine - Office of Geographic Information Systems                                               Impounds                                                                                                                                                       :ref:`megis_impounds <megis_impounds>`                                                                                                                                                                                              
   Spatial     Provincial/State         New Brunswick - Energy and Resource Development                                                New Brunswick Hydrographic Network (NBHN)                                                                                                                      :ref:`nberd_nbhn_mmh, nberd_nbhn_ho <nberd_nbhn_mmh-nberd_nbhn_ho>`                                                                                                                                                                               
   Spatial     Provincial/State         Newfoundland and Labrador - Environment, Climate Change and Municipalities                     Provincial Dam Inventory (NLPDI)                                                                                                                               :ref:`nleccm_nlpdi <nleccm_nlpdi>`                                                                                                                                                                                                
   Spatial     Provincial/State         Nova Scotia - Environment                                                                      Topographic Database – Water Feature Points (a), Lines (b), Polygons (c)                                                                                       :ref:`nse_td_wf <nse_td_wf>`                                                                                                                                                                                                   
   Spatial     Provincial/State         Nova Scotia - Environment                                                                      Water Control Structure Database (accessed from Gillian Fielding unpublished thesis, 2011)                                                                     :ref:`nse_wcsd_gfielding <nse_wcsd_gfielding>`                                                                                                                                                                                          
   Spatial     Provincial/State         Ontario - Northern Development, Mines, Natural Resources and Foretry (MNDMNRF)                 Ontario Dam Inventory (ODI)                                                                                                                                    :ref:`mndmnrf_odi <mndmnrf_odi>`                                                                                                                                                                                                
   Spatial     Provincial/State         Ontario - Northern Development, Mines, Natural Resources and Foretry (MNDMNRF)                 Ontario Hydro Network (OHN) - Hydrographic Points (a), Lines (b), Polygons (c)                                                                                 :ref:`mndmnrf_ohn <mndmnrf_ohn>`                                                                                                                                                                                                 
   Spatial     Provincial/State         Québec – Ministère de l’Environnement et de la Lutte contre les changements climatiques        Répertoire des Barrages                                                                                                                                        :ref:`qmelcc_repbarrages <qmelcc_repbarrages>`                                                                                                                                                                                          
   Spatial     Academic Institution/NGO Canadian Wildlife Federation (CWF)                                                             CANFISHPASS Database (inherited from Cooke Lab – Carleton University)                                                                                          :ref:`cwf_canfish <cwf_canfish>`                                                                                                                                                                                                 
   Spatial     Academic Institution/NGO Canadian Wildlife Federation (CWF)                                                             Barrier points identified through visual inspection of satellite imagery                                                                                       :ref:`cwf <cwf>`
   Spatial     Academic Institution/NGO Food and Agriculture Organization (FAO) of the United Nations                                  AQUASTAT Dam Database                                                                                                                                          :ref:`fao_aquastat <fao_aquastat>`                                                                                                                                                                                                
   Spatial     Academic Institution/NGO Global Dam Watch                                                                               Global Reservoir and Dam Database (GRanD)                                                                                                                      :ref:`gdw_grand <gdw_grand>`                                                                                                                                                                                                   
   Spatial     Academic Institution/NGO Global Dam Watch                                                                               Global Georeferenced Database of Dams (GOODD)                                                                                                                  :ref:`gdw_goodd <gdw_goodd>`                                                                                                                                                                                                   
   Spatial     Academic Institution/NGO Nature Conservancy of Canada (NCC)                                                             Canadian Hydrologic Units – Aquatic Barriers                                                                                                                   :ref:`ncc_chu_ab <ncc_chu_ab>`                                                                                                                                                                                                  
   Spatial     Academic Institution/NGO Stanford University                                                                            National Performance of Dams Program (NPDP) Dam Database                                                                                                       :ref:`su_npdp <su_npdp>`                                                                                                                                                                                                     
   Spatial     Academic Institution/NGO Superior Watershed Partnership and Land Conservancy                                            Lake Superior Dam Inventory (funded by the U.S Fish and Wildlife Service)                                                                                      :ref:`swp_lsdi <swp_lsdi>`                                                                                                                                                                                                    
   Spatial     Academic Institution/NGO Wisconsin Institute for Discovery                                                              Fishwerks                                                                                                                                                      :ref:`wid_fishwerks <wid_fishwerks>`                                                                                                                                                                                               
   Spatial     Miscellaneous            MR Maps                                                                                        Waterfalls of New Brunswick                                                                                                                                    :ref:`mrmaps_nbwf <mrmaps_nbwf>`                                                                                                                                                                                                 
   Spatial     Miscellaneous            MR Maps                                                                                        Waterfalls of Nova Scotia                                                                                                                                      :ref:`mrmaps_nswf <mrmaps_nswf>`                                                                                                                                                                                                 
   Spatial     Provincial               Manitoba - Infrastructure                                                                      Manitoba Provincial Waterways                                                                                                                                  :ref:`mi_prov_ww <mi_prov_ww>`                                                                                                                                                                                                                                                                                                                                                          
   Spatial     Provincial               Saskatchewan - Water Security Agency                                                           WSA Owned Dams                                                                                                                                                 :ref:`wsa_sk_owned_dams <wsa_sk_owned_dams>`
   Spatial     Provincial               Saskatchewan - Ministry of Environment                                                         Saskatchewan Hydrography                                                                                                                                       :ref:`skmoe_hydrography <skmoe_hydrography>`
   Non-spatial Federal                  Environment and Climate Change Canada                                                          Canadian Environmental Assessment Agency                                                                                                                       :ref:`ecc_ceaa_090152237 <ecc_ceaa_090152237>`                                                                                                                                                                                          
   Non-spatial Federal                  Fisheries and Oceans (DFO)                                                                     Administration and Enforcement of the Fish Habitat Protection and Pollution Prevention Provisions of the Fisheries Act (2003-2004 Annual Report to Parliament) :ref:`dfo_annu_rep_2003_4 <dfo_annu_rep_2003_4>`                                                                                                                                                                                         
   Non-spatial Federal                  Fisheries and Oceans (DFO)                                                                     Information in Support of a Recovery Potential Assessment of Bull Trout                                                                                        :ref:`dfo_sawatsky_2016 <dfo_sawatsky_2016>`                                                                                                                                                                                           
   Non-spatial Federal                  Fisheries and Oceans (DFO)                                                                     Recovery Strategy for the Atlantic Whitefish                                                                                                                   :ref:`sarpr_atlantic_wfish <sarpr_atlantic_wfish>`                                                                                                                                                                                        
   Non-spatial Federal                  Natural Resources Canada (NRCan)                                                               Atlantic Salmon Rehabilitation Project                                                                                                                         :ref:`dfo_atl_sal_rehab_ns <dfo_atl_sal_rehab_ns>`                                                                                                                                                                                        
   Non-spatial Federal                  Prairie Farm Rehabilitation Administration (PFRA)                                              PFRA Dam Inventory                                                                                                                                             :ref:`pfra_dams <pfra_dams>`                                                                                                                                                                                                   
   Non-spatial Provincial               Alberta – Agriculture, Forestry and Rural Economic Development                                 Alberta Irrigation Information                                                                                                                                 :ref:`aafred_aii <aafred_aii>`                                                                                                                                                                                                  
   Non-spatial Provincial               Alberta – Environment and Parks                                                                Alberta Dam Safety Map                                                                                                                                         :ref:`aep_dsm <aep_dsm>`                                                                                                                                                                                                     
   Non-spatial Provincial               Alberta – Environment and Parks                                                                Berry Creek (Carolside) Reservoir Fisheries Management Objectives                                                                                              :ref:`aep_fmo_berry_crk <aep_fmo_berry_crk>`                                                                                                                                                                                           
   Non-spatial Provincial               Alberta – Environment and Parks                                                                Bow River Basin – TransAlta Operations                                                                                                                         :ref:`aep_tao_bow_riv_basin <aep_tao_bow_riv_basin>`                                                                                                                                                                                       
   Non-spatial Provincial               Alberta – Environment and Parks                                                                Coal Lake Dam – Planning Study (Assessment of Spillway & Drainage/Seepage at Downstream Toe)                                                                   :ref:`aep_cldps <aep_cldps>`                                                                                                                                                                                                   
   Non-spatial Provincial               Alberta – Environment and Parks                                                                Fish Stocking Maps                                                                                                                                             :ref:`aep_fsm_moundred_res <aep_fsm_moundred_res>`, :ref:`aep_fsm_open_crk <aep_fsm_open_crk>`                                                                                                                                                                      
   Non-spatial Provincial               Alberta – Environment and Parks                                                                Little Bow Reservoir FIN Summary                                                                                                                               :ref:`aep_littlebow_res_fin_2020 <aep_littlebow_res_fin_2020>`                                                                                                                                                                                 
   Non-spatial Provincial               Alberta - Natural Resources Conservation Board                                                 Pine Coolee Water Management Project                                                                                                                           :ref:`nrcb_earp_app9401 <nrcb_earp_app9401>`                                                                                                                                                                                           
   Non-spatial Provincial               Alberta – Sustainable Resource Development                                                     Bathymetry Maps                                                                                                                                                :ref:`asrd_bathym_chin <asrd_bathym_chin>`, :ref:`asrd_bathym_forty_mile <asrd_bathym_forty_mile>`, :ref:`asrd_bathym_jensen <asrd_bathym_jensen>`, :ref:`asrd_bathym_keho <asrd_bathym_keho>`, :ref:`asrd_bathym_newell <asrd_bathym_newell>`, :ref:`asrd_bathym_mcgregor <asrd_bathym_mcgregor>`, :ref:`asrd_bathym_payne <asrd_bathym_payne>`, :ref:`asrd_bathym_st_mary <asrd_bathym_st_mary>`, :ref:`asrd_bathym_stafford <asrd_bathym_stafford>`, :ref:`asrd_bathym_travers <asrd_bathym_travers>`  
   Non-spatial Provincial               Newfoundland and Labrador – Municipal Affairs and Environment                                  Permits to Alter a Body of Water                                                                                                                               :ref:`nl_mae_permit_alt9067 <nl_mae_permit_alt9067>`, :ref:`nl_mae_permit_alt9371 <nl_mae_permit_alt9371>`                                                                                                                                                                
   Non-spatial Provincial               Nova Scotia – Agriculture                                                                      Dykeland Sites                                                                                                                                                 :ref:`ns_dykeland_sites <ns_dykeland_sites>`                                                                                                                                                                                          
   Non-spatial Municipal                City of Calgary, Alberta                                                                       Glenmore Dam Infrastructure Improvements                                                                                                                       :ref:`ab_cal_gdii <ab_cal_gdii>`                                                                                                                                                                                                 
   Non-spatial Municipal                City of Calgary, Alberta                                                                       Glenmore Reservoir Dam Operations                                                                                                                              :ref:`ab_cal_grdo <ab_cal_grdo>`                                                                                                                                                                                                 
   Non-spatial Municipal                City of Dawson Creek, British Columbia                                                         Drinking Water Quality Reports                                                                                                                                 :ref:`bc_dc_wqar2019 <bc_dc_wqar2019>`, :ref:`bc_dc_wqar2016 <bc_dc_wqar2016>`, :ref:`bc_dc_wqap2015 <bc_dc_wqap2015>`                                                                                                                                                             
   Non-spatial Municipal                Eastern Irrigation District, Alberta                                                           Bassano Dam                                                                                                                                                    :ref:`aeid_bassano <aeid_bassano>`                                                                                                                                                                                                
   Non-spatial Municipal                Halifax Water                                                                                  Chain Lakes Emergency Water Supply Watershed Area – Source Water Protection Plan                                                                               :ref:`ns_hal_clews_swpp <ns_hal_clews_swpp>`                                                                                                                                                                                           
   Non-spatial Municipal                Halifax Water                                                                                  Chain Lake Dam and Pockwock Lake Dam – Consultant Services                                                                                                     :ref:`ns_hal_p25_2021 <ns_hal_p25_2021>`                                                                                                                                                                                             
   Non-spatial Municipal                Halifax Water                                                                                  Halifax Water Dam Safety Review                                                                                                                                :ref:`ns_hal_p24_2019 <ns_hal_p24_2019>`                                                                                                                                                                                             
   Non-spatial Municipal                Halifax Water                                                                                  Integrated Resource Plan – Water System Review                                                                                                                 :ref:`ns_hal_hwirp_v3 <ns_hal_hwirp_v3>`                                                                                                                                                                                             
   Non-spatial Energy Company           Irrican Power                                                                                  Chin Chute Power Plant                                                                                                                                         :ref:`irrican_chin_chute <irrican_chin_chute>`                                                                                                                                                                                          
   Non-spatial Energy Company           Irrican Power                                                                                  Drops 4, 5, and 6 Power Plant                                                                                                                                  :ref:`irrican_drops_456 <irrican_drops_456>`                                                                                                                                                                                           
   Non-spatial Energy Company           Irrican Power                                                                                  Raymond Reservoir Power Plant                                                                                                                                  :ref:`irrican_ray_res <irrican_ray_res>`                                                                                                                                                                                             
   Non-spatial Energy Company           Lower Churchill Management Corporation                                                         Muskrat Falls Dams – Cold Climate Considerations in Design and Construction                                                                                    :ref:`lcmc_protulipac_et_al_2018 <lcmc_protulipac_et_al_2018>`                                                                                                                                                                                  
   Non-spatial Energy Company           NB Power                                                                                       Hydro Tour                                                                                                                                                     :ref:`nbpower_hydro_tour <nbpower_hydro_tour>`                                                                                                                                                                                          
   Non-spatial Energy Company           Newfoundland and Labrador Hydro                                                                Audit Dam Safety Review for Pudops Dam, North Salmon Dam and Spillway (RFP# 2017-70503)                                                                        :ref:`nlhydro_adsr_2017_70503 <nlhydro_adsr_2017_70503>`                                                                                                                                                                                     
   Non-spatial Energy Company           Newfoundland and Labrador Hydro                                                                Depreciation Methodology and Asset Service Lives                                                                                                               :ref:`nlhydro_ca_nlh_155 <nlhydro_ca_nlh_155>`                                                                                                                                                                                          
   Non-spatial Energy Company           Newfoundland and Labrador Hydro                                                                Operations – Hydro Generation                                                                                                                                  :ref:`nlhydro_ops_hydro <nlhydro_ops_hydro>`                                                                                                                                                                                           
   Non-spatial Energy Company           Newfoundland Power                                                                             2019 Depreciation Study – Hydro Plant Decommissioning Report                                                                                                   :ref:`nlp_depreciation_2019 <nlp_depreciation_2019>`                                                                                                                                                                                       
   Non-spatial Energy Company           Newfoundland Power                                                                             Dam Safety Inspection Reports                                                                                                                                  :ref:`nlp_dsi_2007 <nlp_dsi_2007>`                                                                                                                                                                                                
   Non-spatial Energy Company           Newfoundland Power                                                                             Facility Rehabilitation                                                                                                                                        :ref:`nlp_fac_rehab_2014 <nlp_fac_rehab_2014>`, :ref:`nlp_fac_rehab_2012 <nlp_fac_rehab_2012>`                                                                                                                                                                      
   Non-spatial Energy Company           Newfoundland Power                                                                             Potential Projects to Increase Energy Production                                                                                                               :ref:`nlp_ppiep_2009 <nlp_ppiep_2009>`                                                                                                                                                                                             
   Non-spatial Energy Company           Newfoundland Power                                                                             Public Safety Around Dams                                                                                                                                      :ref:`nlp_pub_safety_2016 <nlp_pub_safety_2016>`                                                                                                                                                                                         
   Non-spatial Energy Company           Newfoundland Power                                                                             Rattling Brook Fisheries Compensation                                                                                                                          :ref:`nlp_rbfc_2011 <nlp_rbfc_2011>`                                                                                                                                                                                               
   Non-spatial Energy Company           Newfoundland Power                                                                             Sustainable Electricity Program                                                                                                                                :ref:`nlp_sep_2008 <nlp_sep_2008>`                                                                                                                                                                                                
   Non-spatial Energy Company           Nova Scotia Power                                                                              Nova Scotia Power Incorporated Hydro Asset Study – Redacted                                                                                                    :ref:`nsp_ihas <nsp_ihas>`                                                                                                                                                                                                    
   Non-spatial Energy Company           Suncor Energy                                                                                  Investor Mining and Tailings Safety Initiative Disclosure Table                                                                                                :ref:`suncor_safety_initiative <suncor_safety_initiative>`                                                                                                                                                                                    
   Non-spatial Energy Company           TransAlta                                                                                      Barrier Power Plant                                                                                                                                            :ref:`transalta_barrier <transalta_barrier>`                                                                                                                                                                                           
   Non-spatial Energy Company           TransAlta                                                                                      Bearspaw Plant                                                                                                                                                 :ref:`transalta_bearspaw <transalta_bearspaw>`                                                                                                                                                                                          
   Non-spatial Energy Company           TransAlta                                                                                      Belly River Hydro Facility                                                                                                                                     :ref:`transalta_belly <transalta_belly>`                                                                                                                                                                                            
   Non-spatial Energy Company           TransAlta                                                                                      Bighorn Plant                                                                                                                                                  :ref:`transalta_bighorn <transalta_bighorn>`                                                                                                                                                                                           
   Non-spatial Energy Company           TransAlta                                                                                      Brazeau Plant                                                                                                                                                  :ref:`transalta_brazeau <transalta_brazeau>`                                                                                                                                                                                           
   Non-spatial Energy Company           TransAlta                                                                                      Cascade Plant                                                                                                                                                  :ref:`transalta_cascade <transalta_cascade>`                                                                                                                                                                                           
   Non-spatial Energy Company           TransAlta                                                                                      Ghost Plant                                                                                                                                                    :ref:`transalta_ghost <transalta_ghost>`                                                                                                                                                                                            
   Non-spatial Energy Company           TransAlta                                                                                      Horseshoe Plant                                                                                                                                                :ref:`transalta_horseshoe <transalta_horseshoe>`                                                                                                                                                                                         
   Non-spatial Energy Company           TransAlta                                                                                      Interlakes Plant                                                                                                                                               :ref:`transalta_interlakes <transalta_interlakes>`                                                                                                                                                                                        
   Non-spatial Energy Company           TransAlta                                                                                      Kananaskis Plant                                                                                                                                               :ref:`transalta_kananaskis <transalta_kananaskis>`                                                                                                                                                                                       
   Non-spatial Energy Company           TransAlta                                                                                      Pocaterra Plant                                                                                                                                                :ref:`transalta_pocaterra <transalta_pocaterra>`                                                                                                                                                                                         
   Non-spatial Energy Company           TransAlta                                                                                      Rundle Plant                                                                                                                                                   :ref:`transalta_rundle <transalta_rundle>`                                                                                                                                                                                            
   Non-spatial Energy Company           TransAlta                                                                                      Sheerness Generating Station                                                                                                                                   :ref:`transalta_sheerness <transalta_sheerness>`                                                                                                                                                                                         
   Non-spatial Energy Company           TransAlta                                                                                      Spray Hydro Facility                                                                                                                                           :ref:`transalta_spray <transalta_spray>`                                                                                                                                                                                             
   Non-spatial Energy Company           TransAlta                                                                                      St. Mary Hydro Facility                                                                                                                                        :ref:`transalta_st_mary <transalta_st_mary>`                                                                                                                                                                                           
   Non-spatial Energy Company           TransAlta                                                                                      Taylor Hydro Facility                                                                                                                                          :ref:`transalta_taylor <transalta_taylor>`                                                                                                                                                                                            
   Non-spatial Energy Company           TransAlta                                                                                      Three Sisters Plant                                                                                                                                            :ref:`transalta_three_sisters <transalta_three_sisters>`                                                                                                                                                                                     
   Non-spatial Energy Company           TransAlta                                                                                      Waterton Hydro Facility                                                                                                                                        :ref:`transalta_waterton <transalta_waterton>`                                                                                                                                                                                          
   Non-spatial Academic Institution/NGO Alberta WaterPortal Society                                                                    Bow River Irrigation District                                                                                                                                  :ref:`awps_brid <awps_brid>`                                                                                                                                                                                                   
   Non-spatial Academic Institution/NGO Alberta WaterPortal Society                                                                    St. Mary River Irrigation District                                                                                                                             :ref:`awps_smrid <awps_smrid>`                                                                                                                                                                                                  
   Non-spatial Academic Institution/NGO Alberta Wilderness Association                                                                                                                                                                                                                                :ref:`awa_obed_spill <awa_obed_spill>`                                                                                                                                                                                              
   Non-spatial Academic Institution/NGO Shubenacadie Canal Commission                                                                  The Locks                                                                                                                                                      :ref:`scc_locks <scc_locks>`                                                                                                                                                                                                   
   Non-spatial Academic Institution/NGO South East Alberta Watershed Alliance (SEAWA)                                                  Pakowki Lake Watershed Profile                                                                                                                                 :ref:`seawa_pakowki_lake <seawa_pakowki_lake>`                                                                                                                                                                                          
   Non-spatial Consulting Reports       Advanced Construction Techniques Ltd.                                                          St. Mary Dam Spillway Replacement Project                                                                                                                      :ref:`act_st_mary_spillway <act_st_mary_spillway>`                                                                                                                                                                                        
   Non-spatial Consulting Reports       AMEC Americas Ltd.                                                                             Flood Risk Mapping Project                                                                                                                                     :ref:`amec_frmp_2013 <amec_frmp_2013>`                                                                                                                                                                                              
   Non-spatial Consulting Reports       AMEC Americas Ltd.                                                                             South Saskatchewan River Basin in Alberta: Water Supply Study                                                                                                  :ref:`amec_ssrba_wss <amec_ssrba_wss>`                                                                                                                                                                                              
   Non-spatial Consulting Reports       East Coast Aquatics Inc.                                                                       Biological Assessment for Proposed Liverpool Wind Farm                                                                                                         :ref:`eca_bio_assess <eca_bio_assess>`                                                                                                                                                                                              
   Non-spatial Consulting Reports       Golder Associates Inc.                                                                         Genesee Cooling Pond Thermal and Water Quality Modelling Study                                                                                                 :ref:`golder_genesee_2013 <golder_genesee_2013>`                                                                                                                                                                                         
   Non-spatial Consulting Reports       Golder Associates Inc.                                                                         Inventory and Assessment of Dams in Eastern Newfoundland                                                                                                       :ref:`golder_inv_nl_2016 <golder_inv_nl_2016>`                                                                                                                                                                                          
   Non-spatial Consulting Reports       Golder Associates Inc.                                                                         Inventory and Assessment of Dams in Newfoundland and Labrador Year Three                                                                                       :ref:`golder_inv_nl_2019 <golder_inv_nl_2019>`                                                                                                                                                                                          
   Non-spatial Consulting Reports       Golder Associates Inc.                                                                         Inventory and Assessment of Dams in Newfoundland and Labrador Year Two                                                                                         :ref:`golder_inv_nl_2017 <golder_inv_nl_2017>`                                                                                                                                                                                          
   Non-spatial Consulting Reports       MPE Engineering Ltd.                                                                           Provincial Inventory of Potential Water Storage Sites and Diversion Scenarios                                                                                  :ref:`mpe_aep_prov_inventory <mpe_aep_prov_inventory>`                                                                                                                                                                                      
   Non-spatial Consulting Reports       Power Advisory LLC                                                                             Review of the Newfoundland and Labrador Electricity System                                                                                                     :ref:`pallc_nl_elec <pallc_nl_elec>`                                                                                                                                                                                               
   Non-spatial Consulting Reports       SNC-Lavalin Group Inc.                                                                         Lower Churchill Project Design Criteria                                                                                                                        :ref:`sncl_lower_churchill <sncl_lower_churchill>`                                                                                                                                                                                        
   Non-spatial Peer-reviewed Articles   Alberta Law Review                                                                                                                                                                                                                                            :ref:`alrs_spray_lakes <alrs_spray_lakes>`                                                                                                                                                                                            
   Non-spatial Peer-reviewed Articles   Canadian Geotechnical Journal                                                                                                                                                                                                                                 :ref:`cgj_williams_etal_1983 <cgj_williams_etal_1983>`                                                                                                                                                                                      
   Non-spatial Miscellaneous            Wikipedia                                                                                      Dickson Dam                                                                                                                                                    :ref:`wiki_dickson_dam <wiki_dickson_dam>`                                                                                                                                                                                            
   Non-spatial Miscellaneous            Wikipedia                                                                                      List of Canadian Waterfalls                                                                                                                                    :ref:`wiki_cdn_wfs <wiki_cdn_wfs>`                                                                                                                                                                                                
   Non-spatial Miscellaneous            Wikipedia                                                                                      List of Generating Stations in British Columbia                                                                                                                :ref:`wiki_gs_bc <wiki_gs_bc>`                                                                                                                                                                                                  
   Non-spatial Miscellaneous            Wikipedia                                                                                      List of Generating Stations in New Brunswick                                                                                                                   :ref:`wiki_nb_hydro <wiki_nb_hydro>`                                                                                                                                                                                               
   Non-spatial Miscellaneous            Wikipedia                                                                                      Little Bow Lake Reservoir                                                                                                                                      :ref:`wiki_lbr <wiki_lbr>`                                                                                                                                                                                                    
   =========== ======================== ============================================================================================== ============================================================================================================================================================== ========================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================== 

Spatial Data Sources
--------------------

-----

Federal Sources
~~~~~~~~~~~~~~~

Natural Resources Canada (NRCan)
++++++++++++++++++++++++++++++++

.. _nrcan_cgndb:

Canadian Geographical Names Database
````````````````````````````````````

    Natural Resources Canada, 2020. Canadian Geographical Names Database. Government of Canada Open Government Portal. Accessed July 28, 2021, from https://open.canada.ca/data/en/dataset/e27c6eba-3c5d-4051-9db2-082dc6411c2c
    
    **Geographic coverage:** National
    
    **Source ID field:** CGNDB_ID
    
    **Short name:** nrcan_cgndb

|ds_searchtbl_return|

.. _nrcan_canvec_mm:

CanVec Series – Manmade Features
````````````````````````````````

    Natural Resources Canada, 2019. Constructions and Land Use in Canada - CanVec Series - Manmade Features. Government of Canada Open Government Portal. Accessed July 20, 2019, from https://open.canada.ca/data/en/dataset/fd4369a4-21fe-4070-914a-067474da0fd6

    **Geographic coverage:** National

    **Source ID field:** feature_id

    **Short name:** nrcan_canvec_mm

|ds_searchtbl_return|

.. _nrcan_canvec_hyf:

CanVec Series - Hydrographic Features
`````````````````````````````````````

    Natural Resources Canada, 2019. Lakes, Rivers and Glaciers in Canada - CanVec Series - Hydrographic Features. Government of Canada Open Government Portal. Accessed July 20, 2019, from https://open.canada.ca/data/en/dataset/9d96e8c9-22fe-4ad2-b5e8-94a6991b744b

    **Geographic coverage:** National

    **Source ID field:** feature_id

    **Short name:** nrcan_canvec_hyf

|ds_searchtbl_return|

.. _nrcan_nhn:

National Hydrographic Network (NHN)
```````````````````````````````````

    Natural Resources Canada, 2016. National Hydro Network - NHN - GeoBase Series. Government of Canada Open Government Portal. Accessed July 24, 2019, from https://open.canada.ca/data/en/dataset/a4b190fe-e090-4e6d-881e-b87956c07977

    **Geographic coverage:** National

    **Source ID field:** nid

    **Short name:** nrcan_nhn

|ds_searchtbl_return|

Statistics Canada
+++++++++++++++++

.. _statscan_census_subs:

Intercensal - Census Subdivision Boundary Files
```````````````````````````````````````````````

    Statistics Canada, 2020. Intercensal - Census Subdivision Boundary Files. Accessed November 13, 2020, from https://www12.statcan.gc.ca/census-recensement/2011/geo/bound-limit/bound-limit-s-eng.cfm?year=20

    **Geographic coverage:** National

    **Source ID field:** csduid

    **Short name:** statscan_census_subs

|ds_searchtbl_return|

United States Army Corps of Engineers
+++++++++++++++++++++++++++++++++++++

.. _usace_nid:

National Inventory of Dams
``````````````````````````

    United States Army Corps of Engineers, 2022. National Inventory of Dams. United States Army. Accessed February 15, 2022, from https://nid.sec.usace.army.mil/#/downloads 

    **Geographic coverage:** United States

    **Source ID field:** federal_id

    **Short name:** usace_nid

|ds_searchtbl_return|

Provincial/State Sources
~~~~~~~~~~~~~~~~~~~~~~~~

Alberta – Environment and Parks (AEP)
+++++++++++++++++++++++++++++++++++++

.. _aep_bf_hy:

Base Features Hydrography
`````````````````````````

    Alberta Environment and Parks, 2000. Base Features Hydrography. Alberta Open Government Portal. Accessed January 31, 2020, from https://www.altalis.com/map;id=116

    **Geographic coverage:** Alberta

    **Source ID field:** bf_id

    **Short name:** aep_bf_hy

|ds_searchtbl_return|

British Columbia – Environment and Climate Change Strategy
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. _bceccs_fiss:

Provincial Obstacles to Fish Passage (FISS)
```````````````````````````````````````````

    Government of British Columbia Knowledge Management, 2007. Provincial Obstacles to Fish Passage. British Columbia Data Catalogue. Accessed October 2, 2019, from https://catalogue.data.gov.bc.ca/dataset/provincial-obstacles-to-fish-passage

    **Geographic coverage:** British Columbia

    **Source ID field:** fish_obstacle_point_id

    **Short name:** bceccs_fiss

|ds_searchtbl_return|

British Columbia – Forests, Lands, Natural Resource Operations and Rural Development (FLNRORD)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. _bcflnrord_wris_pubdams:

BC Geographic Warehouse – Public Dams
`````````````````````````````````````

    Government of British Columbia Water Management, 1997. BC Dams. British Columbia Data Catalogue. Accessed March 9, 2019, from https://catalogue.data.gov.bc.ca/dataset/bc-dams

    **Geographic coverage:** British Columbia

    **Source ID field:** objectid

    **Short name:** bcflnrord_wris_pubdams

|ds_searchtbl_return|

.. _bcflnrord_kml_pubdams:

BC Public Dams KML
``````````````````

    Government of British Columbia, 2014. Dams-public-20140626.kmz. Accessed from https://www2.gov.bc.ca/assets/gov/farming-natural-resources-and-industry/natural-resource-use/land-water-use/water-use/dam-safety/dams-public-20140626-2.kmz 

    **Geographic coverage:** British Columbia

    **Source ID field:** objectid

    **Short name:** bcflnrord_kml_pubdams

|ds_searchtbl_return|

.. _bcflnrord_fwa:

Freshwater Atlas (FWA) Obstructions 
```````````````````````````````````

    GeoBC, 2008. Freshwater Atlas Obstructions. British Columbia Data Catalogue. Accessed December 17, 2019, from https://catalogue.data.gov.bc.ca/dataset/freshwater-atlas-obstructions

    **Geographic coverage:** British Columbia

    **Source ID field:** obstruction_id

    **Short name:** bcflnrord_fwa

|ds_searchtbl_return|

Maine Office of Geographic Information Systems
++++++++++++++++++++++++++++++++++++++++++++++

.. _megis_impounds:

Impounds
````````

    Army Corp of Engineers (USACE), Maine Emergency Management Agency (MEMA), Maine Department of Environmental Protection (MEDEP), Maine Office of Geographic Information Systems, 2006. Impounds. Augusta, ME: Maine Office of Geographic Systems. Accessed January 26, 2022, from https://www1.maine.gov/geolib/catalog/indexaz.shtml.

    **Geographic coverage:** State of Maine, United States of America

    **Source ID field:** unique_id

    **Short name:** megis_impounds

|ds_searchtbl_return|

Manitoba – Infrastructure 
+++++++++++++++++++++++++

.. _mi_prov_ww:

Manitoba Provincial Waterways
`````````````````````````````

    Manitoba Infrastructure, 2021. Manitoba Provincial Waterways. Accessed July 15, 2021 from https://www.arcgis.com/home/item.html?id=38142a3ccca9472fb4fd29cb0282a8ec

    **Geographic coverage:** Manitoba

    **Source ID field:** objectid

    **Short name:** mi_prov_ww

|ds_searchtbl_return|

New Brunswick – Energy and Resource Development 
+++++++++++++++++++++++++++++++++++++++++++++++

.. _nberd_nbhn_mmh-nberd_nbhn_ho:

New Brunswick Hydrographic Network (NBHN)
`````````````````````````````````````````

    Government of New Brunswick Energy and Resource Development, 2020. New Brunswick Hydrographic Network (NBHN). Government of New Brunswick Open Data Portal. Accessed from https://gnb.socrata.com/Geographic-Data/New-Brunswick-Hydrographic-Network-NBHN-R-seau-Hyd/v2ft-66he

    **Geographic coverage:** New Brunswick 

    **Source ID field:** nid

    **Short name (manmade hydrographic features):** nberd_nbhn_mmh

    **Short name (hydrographic obstacle features):** nberd_nbhn_ho

|ds_searchtbl_return|

Newfoundland and Labrador – Environment, Climate Change and Municipalities 
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. _nleccm_nlpdi:

Provincial Dam Inventory (NLPDI)
````````````````````````````````

    Government of Newfoundland and Labrador Water Resources Management, no date. Water Resources - Dams. Newfoundland and Labrador Water Resources Portal. Accessed January 27, 2021, from https://maps.gov.nl.ca/water/mapbrowser/Default.aspx

    **Geographic coverage:** Newfoundland and Labrador

    **Source ID field:** dam_index_num

    **Short name:** nleccm_nlpdi

|ds_searchtbl_return|

Nova Scotia – Environment 
+++++++++++++++++++++++++

.. _nse_td_wf:

Topographic Database – Water Feature Points (a), Lines (b), Polygons (c)
````````````````````````````````````````````````````````````````````````

    a. Service Nova Scotia and Internal Services, 2002. Nova Scotia Topographic DataBase - Water Features (Point Layer). Government of Nova Scotia Open Data Portal. Accessed April 5, 2019, from https://data.novascotia.ca/Lands-Forests-and-Wildlife/Nova-Scotia-Topographic-DataBase-Water-Features-Po/458x-dmz3
    
    b. Service Nova Scotia and Internal Services, 2002. Nova Scotia Topographic DataBase - Water Features (Line Layer). Government of Nova Scotia Open Data Portal. Accessed April 5, 2019, from https://data.novascotia.ca/Lands-Forests-and-Wildlife/Nova-Scotia-Topographic-DataBase-Water-Features-Li/fpca-jrmt
    
    c. Service Nova Scotia and Internal Services, 2002. Nova Scotia Topographic DataBase - Water Features (Polygon Layer). Government of Nova Scotia Open Data Portal. Accessed April 5, 2019, from https://data.novascotia.ca/Lands-Forests-and-Wildlife/Nova-Scotia-Topographic-DataBase-Water-Features-Po/h8jb-hzrm

    **Geographic coverage:** Nova Scotia

    **Source ID field:** shape_fid

    **Short name:** nse_td_wf

|ds_searchtbl_return|

.. _nse_wcsd_gfielding:

Water Control Structure Database (accessed from Gillian Fielding unpublished thesis, 2011)
``````````````````````````````````````````````````````````````````````````````````````````

    Fielding, G., 2011. Barriers to Fish Passage in Nova Scotia: The Evolution of Water Control Barriers in Nova Scotia’s Watershed. [Undergraduate thesis, Dalhousie University]. Accessed from https://cdn.dal.ca/content/dam/dalhousie/pdf/science/environmental-science-program/Honours%20Theses/GillianFielding.pdf

    **Geographic coverage:** Nova Scotia

    **Source ID field:** dam_id_number

    **Short name:** nse_wcsd_gfielding

|ds_searchtbl_return|

Ontario – Northern Development, Mines, Natural Resources and Forestry (MNDMNRF)
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. _mndmnrf_odi:

Ontario Dam Inventory (ODI)
```````````````````````````

    Ontario Ministry of Natural Resources and Forestry, 2014. Ontario Dam Inventory. Ontario GeoHub. Accessed July 30, 2020, from https://geohub.lio.gov.on.ca/datasets/mnrf::ontario-dam-inventory/about

    **Geographic coverage:** Ontario

    **Source ID field:** dam_id

    **Short name:** mndmnrf_odi

|ds_searchtbl_return|

.. _mndmnrf_ohn:

Ontario Hydro Network (OHN) - Hydrographic Points (a), Lines (b), Polygons (c)
``````````````````````````````````````````````````````````````````````````````

    a. Ontario Ministry of Natural Resources and Forestry, 2010. Ontario Hydro Network (OHN) – Hydrographic Point. Ontario GeoHub. Accessed October 8, 2019, from https://geohub.lio.gov.on.ca/datasets/mnrf::ontario-hydro-network-ohn-hydrographic-point/about

    b. Ontario Ministry of Natural Resources and Forestry, 2010. Ontario Hydro Network (OHN) – Hydrographic Lines. Ontario GeoHub. Accessed October 8, 2019, from https://geohub.lio.gov.on.ca/datasets/mnrf::ontario-hydro-network-ohn-hydrographic-line/about

    c. Ontario Ministry of Natural Resources and Forestry, 2010. Ontario Hydro Network (OHN) – Hydrographic Polygons. Ontario GeoHub. Accessed October 8, 2019, from https://geohub.lio.gov.on.ca/datasets/mnrf::ontario-hydro-network-ohn-hydrographic-poly/about

    **Geographic coverage:** Ontario

    **Source ID field:** ogf_id

    **Short name:** mndmnrf_ohn

|ds_searchtbl_return|

Québec – Ministère de l'Environnement et de la Lutte contre les changements climatiques 
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. _qmelcc_repbarrages:

Répertoire des Barrages
```````````````````````

    Gouvernement du Québec Ministère de l’Environnement et de la Lutte contre les changements climatiques, no date. Répertoire des barrages. Gouvernement du Québec. Accessed October 20, 2020, from https://www.cehq.gouv.qc.ca/barrages/default.asp

    **Geographic coverage:** Québec

    **Source ID field:** numéro_barrage

    **Short name:** qmelcc_repbarrages

|ds_searchtbl_return|

Saskatchewan - Ministry of Environment
++++++++++++++++++++++++++++++++++++++

.. _skmoe_hydrography:

Saskatchewan Hydrography
````````````````````````

    Saskatchewan Ministry of Environment, no date. Hydrography. Accessed July 19, 2021, from https://gis.saskatchewan.ca/arcgis/rest/services/Hydrography/MapServer

    **Geographic coverage:** Saskatchewan

    **Source ID field:** feature_id

    **Short name:** skmoe_hydrography

|ds_searchtbl_return|

Saskatchewan Water Security Agency
++++++++++++++++++++++++++++++++++

.. _wsa_sk_owned_dams:

    Saskatchewan Water Security Agency, no date. WSA Owned Dams. Accessed July 8, 2021, from https://gis.wsask.ca/WSAOwnedDams/
   
    **Geographic coverage:** Saskatchewan

    **Source ID field:** objectid

    **Short name:** wsa_sk_owned_dams

|ds_searchtbl_return|

Academic Institutions/NGO Sources
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Canadian Wildlife Federation (CWF)
++++++++++++++++++++++++++++++++++

.. _cwf:

Barrier Points Identified Through Visual Inspection of Satellite Imagery
````````````````````````````````````````````````````````````````````````

    Canadian Wildlife Federation, 2022. Barrier points identified through visual inspection of satellite imagery.

    **Geographic coverage:** National

    **Source ID field:** n/a

    **Short name:** cwf

|ds_searchtbl_return|

.. _cwf_canfish:

CANFISHPASS Database (inherited from Cooke Lab – Carleton University)
`````````````````````````````````````````````````````````````````````

    Cooke, S., Hatry, C., Smokorowksi, K., Clarke, K., Katopodis, C., Binder, T., Hasler, C., & Thiem, J., 2013. CanFishPass: Inventory of Canadian Fish Passage Facilities. Cooke Lab. Accessed from http://www.fecpl.ca/projects/canfishpass-inventory-of-canadian-fish-passage-facilities/ 

    **Geographic coverage:** National
 
    Nova Scotia Salmon Association, 2013. Fish Ladder Database, Adopt a Stream Program. Nova Scotia Salmon Association, unpublished electronic data.

    **Geographic coverage:** Nova Scotia

    **Source ID field:** fid

    **Short name:** cwf_canfish


|ds_searchtbl_return|

Food and Agriculture Organization (FAO) of the United Nations 
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. _fao_aquastat:

AQUASTAT Dam Database
`````````````````````

    Food and Agriculture Organization of the United Nations, 2016. AQUASTAT - FAO’s Global Information System on Water and Agriculture. Food and Agriculture Organization. Accessed from https://www.fao.org/aquastat/en/databases/dams

    **Geographic coverage:** Global

    **Source ID field:** id_fao

    **Short name:** fao_aquastat

|ds_searchtbl_return|

Global Dam Watch
++++++++++++++++

.. _gdw_grand:

Global Reservoir and Dam Database (GRanD)
`````````````````````````````````````````

    Global Dam Watch, 2019. GDW’s Global Dam and Reservoir Datasets. Accessed February 1, 2019, from http://globaldamwatch.org/data/#core_global

    **Geographic coverage:** Global

    **Source ID field:** grand_id

    **Short name:** gdw_grand

|ds_searchtbl_return|

.. _gdw_goodd:

Global Georeferenced Database of Dams (GOODD)
`````````````````````````````````````````````

    Global Dam Watch, 2020. GOODD, a global dataset of more than 38,000 georeferenced dams. Accessed August 16, 2019, from http://globaldamwatch.org/data/#core_global

    **Geographic coverage:** Global

    **Source ID field:** dam_id

    **Short name:** gdw_goodd

|ds_searchtbl_return|

Nature Conservancy of Canada (NCC)
++++++++++++++++++++++++++++++++++

.. _ncc_chu_ab:

Canadian Hydrologic Units – Aquatic Barriers
````````````````````````````````````````````

    Nature Conservancy of Canada, 2019. NCC Canadian Hydrologic Units. Conservation Biology Institute Data Basin. Accessed October 9, 2019, from https://databasin.org/datasets/a2097617294f49529f87c3630149d63c/

    **Geographic coverage:** Maritimes

    **Source ID field:** unique_id

    **Short name:** ncc_chu_ab

|ds_searchtbl_return|

Stanford University
+++++++++++++++++++

.. _su_npdp:

National Performance of Dams Program (NPDP) Dam Database
````````````````````````````````````````````````````````

    Stanford University Department of Civil and Environmental Engineering, 2019. NPDP Dams Database. National Performance of Dams Program. Accessed October 9, 2019, from https://npdp.stanford.edu/dams_database

    **Geographic coverage:** Global

    **Source ID field:** npdp_id

    **Short name:** su_npdp

|ds_searchtbl_return|

Superior Watershed Partnership and Land Conservancy
+++++++++++++++++++++++++++++++++++++++++++++++++++

.. _swp_lsdi:

Lake Superior Dam Inventory (funded by the U.S Fish and Wildlife Service)
`````````````````````````````````````````````````````````````````````````

    Superior Watershed Partnership and Land Conservancy, no date. Lake Superior Dam Inventory. Funded by the United States Fish and Wildlife Service. Accessed December 4, 2019 from data provided by Jeff Koch of the Superior Watershed Partnership and Land Conservancy.

    **Short name:** swp_lsdi

|ds_searchtbl_return|

Wisconsin Institute for Discovery 
+++++++++++++++++++++++++++++++++

.. _wid_fishwerks:

Fishwerks
`````````

    Wisconsin Institute for Discovery, no date. Fishwerks. Great Lakes Connectivity. Accessed October 9, 2019, from https://greatlakesconnectivity.org/

    **Geographic coverage:** Great Lakes Region

    **Source ID field:** barrier_id

    **Short name:** wid_fishwerks

|ds_searchtbl_return|

Miscellaneous Sources
~~~~~~~~~~~~~~~~~~~~~

MR Maps 
+++++++

.. _mrmaps_nbwf: 

Waterfalls of New Brunswick
```````````````````````````


    Richard, M., 2019. Waterfalls of New Brunswick. MR Maps. Accessed from https://www.mrmaps.ca/home/2019/5/19/waterfalls-of-new-brunswick

    **Geographic coverage:** New Brunswick

    **Source ID field:** nb_id

    **Short name:** mrmaps_nbwf

|ds_searchtbl_return|

.. _mrmaps_nswf:

Waterfalls of Nova Scotia
`````````````````````````

    Richard, M., 2019. Waterfalls of Nova Scotia. MR Maps. Accessed June 4, 2021, from https://www.mrmaps.ca/home/2019/5/30/waterfalls-of-nova-scotia 

    **Geographic coverage:** Nova Scotia

    **Source ID field:** ns_id

    **Short name:** mrmaps_nswf

|ds_searchtbl_return|

Non-Spatial Data Sources
------------------------

-----

Federal Sources
~~~~~~~~~~~~~~~

Environment and Climate Change Canada
+++++++++++++++++++++++++++++++++++++

.. _ecc_ceaa_090152237:

Canadian Environmental Assessment Agency
````````````````````````````````````````

    Canadian Environmental Assessment Agency, 2012. Archived - Carseland Very Low Head (VLH) Hydro Project. Accessed May 6, 2022, from https://www.ceaa-acee.gc.ca/052/details-eng.cfm?pid=52237

    **Short name:** ecc_ceaa_090152237

|ds_searchtbl_return|

Fisheries and Oceans (DFO)
++++++++++++++++++++++++++

.. _dfo_annu_rep_2003_4:

Administration and Enforcement of the Fish Habitat Protection and Pollution Prevention Provisions of the Fisheries Act (2003-2004 Annual Report to Parliament)
``````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````

    Fisheries and Oceans Canada, 2004. 2003-2004 Annual report to Parliament on the administration and enforcement of the fish habitat protection and pollution prevention provisions of the Fisheries Act. pp. 35-36. Ottawa, ON: Fisheries and Oceans Canada. Accessed from https://waves-vagues.dfo-mpo.gc.ca/Library/357831eng.pdf

    **Short name:** dfo_annu_rep_2003_4

|ds_searchtbl_return|

.. _dfo_sawatsky_2016:

Information in Support of a Recovery Potential Assessment of Bull Trout
```````````````````````````````````````````````````````````````````````

    Sawatzky, C.D., 2016. Information in support of a recovery potential assessment of Bull Trout (Salvelinus confluentus) (Saskatchewan – Nelson rivers populations) in Alberta. Fisheries and Oceans Canada Canadian Science Advisory Secretariat Research Document 2016/113. pp. 43, 47, 52.  Accessed from https://waves-vagues.dfo-mpo.gc.ca/Library/40580180.pdf

    **Short name:** dfo_sawatsky_2016

|ds_searchtbl_return|

.. _sarpr_atlantic_wfish:

Recovery Strategy for the Atlantic Whitefish
````````````````````````````````````````````

    Department of Fisheries and Oceans. 2006. Recovery Strategy for the Atlantic Whitefish (Coregonus huntsmani) in Canada [Proposed]. Species at Risk Act Recovery Strategy Series. Ottawa: Fisheries and Oceans Canada. 42 pp. Accessed February 8, 2022, from https://sararegistry.gc.ca/default.asp?lang=En&n=B2C0EB3D-1&offset=5

    **Short name:** sarpr_atlantic_wfish

|ds_searchtbl_return|

Natural Resources Canada (NRCan)
++++++++++++++++++++++++++++++++

.. _dfo_atl_sal_rehab_ns:

Atlantic Salmon Rehabilitation Project
``````````````````````````````````````

    Department of Fisheries and Forestry of Canada - Resource Development Branch - Fisheries Service, no date. Atlantic Salmon Rehabilitation Project - East River, Sheet Harbour, Nova Scotia. Halifax, NS: Department of Fisheries and Forestry of Canada. Accessed February 8, 2022 from https://waves-vagues.dfo-mpo.gc.ca/Library/83454.pdf

    **Short name:** dfo_atl_sal_rehab_ns

|ds_searchtbl_return|

Prairie Farm Rehabilitation Administration (PFRA)
+++++++++++++++++++++++++++++++++++++++++++++++++

.. _pfra_dams:

PFRA Dam Inventory 
``````````````````

    Prairie Farm Rehabilitation Administration, 1992. PFRA Dam Inventory. pp. 16-18. Accessed from http://www.pfra.ca/doc/Dams/PFRA%20Dam%20Inventory_PFRA_Jan%201992.pdf 
    
    **Short name:** pfra_dams

|ds_searchtbl_return|

Provincial Sources
~~~~~~~~~~~~~~~~~~

Alberta – Agriculture, Forestry and Rural Economic Development
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. _aafred_aii:

Alberta Irrigation Information 
``````````````````````````````

    Alberta Agriculture and Forestry, 2018. Alberta Irrigation Information. pp. 19-20. Accessed  from https://www1.agric.gov.ab.ca/$Department/deptdocs.nsf/all/irr7401/$FILE/alta_irrig_info2017.pdf

    **Short name:** aafred_aii

|ds_searchtbl_return|

Alberta – Environment and Parks
+++++++++++++++++++++++++++++++

.. _aep_dsm:

Alberta Dam Safety Map
``````````````````````

    Alberta Environment and Parks, no date. Alberta Dam Safety Map. Government of Alberta. Accessed December 13, 2021, from http://damsafetymap.alberta.ca/

    **Short name:** aep_dsm

|ds_searchtbl_return|

.. _aep_fmo_berry_crk:

Berry Creek (Carolside) Reservoir Fisheries Management Objectives
`````````````````````````````````````````````````````````````````

    Alberta Fish and Wildlife, 2018. Berry Creek (Carolside) Reservoir Fisheries Management Objectives. Alberta Environment and Parks. Accessed from https://mywildalberta.ca/fishing/regulations/documents/BerryCreekCarolsideReservoir-FMO-Jul01-2018.pdf

    **Short name:** aep_fmo_berry_crk

|ds_searchtbl_return|

.. _aep_tao_bow_riv_basin:

Bow River Basin – TransAlta Operations
``````````````````````````````````````

    Alberta Environment and Parks, 2021. Bow River Basin – TransAlta operations. Government of Alberta. Accessed December 13, 2021, from https://www.alberta.ca/bow-river-basin-transalta-operations.aspx

    **Short name:** aep_tao_bow_riv_basin

|ds_searchtbl_return|

.. _aep_cldps:

Coal Lake Dam – Planning Study (Assessment of Spillway & Drainage/Seepage at Downstream Toe)
````````````````````````````````````````````````````````````````````````````````````````````

    Alberta Environment and Sustainable Resource Development, 2015. Coal Lake Dam – Planning Study (Assessment of Spillway & Drainage/Seepage at Downstream Toe). Accessed May 6, 2022, from https://legacy.merx.com/English/SUPPLIER_Menu.asp?WCE=Show&TAB=1&PORTAL=MERX&State=7&id=AB-2015-02510&src=osr&FED_ONLY=0&ACTION=NEXT&rowcount=2000&lastpage=200&MoreResults=&PUBSORT=2&CLOSESORT=0&IS_SME=N&langswitch=1&hcode=sTvMTncPfnbG4oSXtP%2fDhw%3d%3d

    **Short name:** aep_cldps

|ds_searchtbl_return|

Fish Stocking Maps
``````````````````

.. _aep_fsm_moundred_res:

    a. Alberta Environment and Parks, 2021. Stocking Maps - Mound Red Reservoir. My Wild Alberta. Accessed December 13, 2021, from https://mywildalberta.ca/fishing/fish-stocking/stocking-maps.aspx?id=6737

    **Short name:** aep_fsm_moundred_res

|ds_searchtbl_return|

.. _aep_fsm_open_crk:

    b.	Alberta Environment and Parks, 2021. Stocking Maps - Open Creek Reservoir. My Wild Alberta. Accessed December 13, 2021, from https://mywildalberta.ca/fishing/fish-stocking/stocking-maps.aspx?id=6726

    **Short name:** aep_fsm_open_crk

|ds_searchtbl_return|

.. _aep_littlebow_res_fin_2020:

Little Bow Reservoir FIN Summary
````````````````````````````````

    Alberta Fish and Wildlife, 2020. Little Bow Reservoir FIN Summary 2020. Alberta Environment and Parks. p. 1. Accessed from https://open.alberta.ca/dataset/dfe0c6b7-5f3a-478b-a0aa-e66ffc9c6c07/resource/7289e415-eaf7-4e78-a51b-57e842e282b4/download/aep-little-bow-reservoir-fin-summary-2020.pdf

    **Short name:** aep_littlebow_res_fin_2020

|ds_searchtbl_return|

Alberta - Natural Resources Conservation Board
++++++++++++++++++++++++++++++++++++++++++++++

.. _nrcb_earp_app9401:

Pine Coolee Water Management Project
````````````````````````````````````

    Natural Resources Conservation Board/Environmental Assessment and Review Process Joint Review Panel, 1995. NCRB Application #9401: Pine Coulee Water Management Project, Willow Creek Basin, Southwest of Staveley, Alberta. Accessed May 6, 2022, from https://publications.gc.ca/collections/collection_2018/acee-ceaa/En106-167-1995-eng.pdf

    **Short name:** nrcb_earp_app9401

|ds_searchtbl_return|

Alberta – Sustainable Resource Development
++++++++++++++++++++++++++++++++++++++++++

Bathymetry Maps
```````````````

.. _asrd_bathym_chin:

    a. Alberta Resource Information Unit, 2004. Bathymetry of Chin Lakes, 1:20,000. Lethbridge, AB: Alberta Sustainable Resource Development. Accessed from https://open.alberta.ca/publications/chin-lakes-bathymetry

    **Short name:** asrd_bathym_chin

|ds_searchtbl_return|

.. _asrd_bathym_forty_mile:

    b. Alberta Resource Information Unit, 2002. Bathymetry of Forty Mile Coulee Reservoir, 1:10,000. Lethbridge, AB: Alberta Sustainable Resource Development. Accessed from https://open.alberta.ca/publications/forty-mile-coulee-reservoir-bathymetry

    **Short name:** asrd_bathym_forty_mile

|ds_searchtbl_return|

.. _asrd_bathym_jensen:

    c. Alberta Resource Information Unit, 2002. Bathymetry of Jensen (Pothole) Reservoir, 1:5,000. Lethbridge, AB: Alberta Sustainable Resource Development. Accessed from  https://open.alberta.ca/publications/jensen-pothole-reservoir-bathymetry

    **Short name:** asrd_bathym_jensen

|ds_searchtbl_return|

.. _asrd_bathym_keho:

    d. Alberta Resource Information Unit, 2002. Bathymetry of Keho Lake, 1:10,000. Lethbridge, AB: Alberta Sustainable Resource Development. Accessed from   https://open.alberta.ca/publications/keho-lake-bathymetry

    **Short name:** asrd_bathym_keho

|ds_searchtbl_return|

.. _asrd_bathym_newell:

    e. Alberta Resource Information Unit, 2004. Bathymetry of Lake Newell, 1:15,000. Lethbridge, AB: Alberta Sustainable Resource Development. Accessed from  https://open.alberta.ca/publications/lake-newell-bathymetry

    **Short name:** asrd_bathym_newell

|ds_searchtbl_return|

.. _asrd_bathym_mcgregor:

    f. Alberta Resource Information Unit, 2002. Bathymetry of McGregor Lake,1:20,000. Lethbridge, AB: Alberta Sustainable Resource Development. Accessed from  https://open.alberta.ca/publications/mcgregor-lake-bathymetry

    **Short name:** asrd_bathym_mcgregor

|ds_searchtbl_return|

.. _asrd_bathym_payne:

    g. Alberta Resource Information Unit, 2005. Bathymetry of Payne Lake, 1:7500. Lethbridge, AB: Alberta Sustainable Resource Development. Accessed from  https://open.alberta.ca/publications/payne-lake-bathymetry

    **Short name:** asrd_bathym_payne

|ds_searchtbl_return|

.. _asrd_bathym_st_mary:

    h. Alberta Resource Information Unit, 2004. Bathymetry of St. Mary Reservoir, 1:15,000. Lethbridge, AB: Alberta Sustainable Resource Development. Accessed from  https://open.alberta.ca/publications/st-mary-reservoir-bathymetry

    **Short name:** asrd_bathym_st_mary

|ds_searchtbl_return|

.. _asrd_bathym_stafford:

    i. Alberta Resource Information Unit, 2003. Bathymetry of Stafford Reservoir, 1:10,000. Lethbridge, AB: Alberta Sustainable Resource Development. Accessed from https://open.alberta.ca/publications/stafford-reservoir-bathymetry

    **Short name:** asrd_bathym_stafford

|ds_searchtbl_return|

.. _asrd_bathym_travers:

    j. Alberta Resource Information Unit, 2003. Bathymetry of Travers Reservoir, 1:15,000. Lethbridge, AB: Alberta Sustainable Resource Development. Accessed from https://open.alberta.ca/publications/travers-reservoir-bathymetry

    **Short name:** asrd_bathym_travers

|ds_searchtbl_return|


Newfoundland and Labrador – Municipal Affairs and Environment
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++


Permits to Alter a Body of Water
````````````````````````````````

.. _nl_mae_permit_alt9067:

    a. Newfoundland and Labrador Department of Municipal Affairs and Environment - Water Resources Management Division, 2017. Permit to Alter a Body of Water - Permit No. ALT9067-2017. Accessed from https://www.gov.nl.ca/ecc/files/waterres-permits-water-alt-dams-2017-r-alt9067-2017.pdf

    **Short name:** nl_mae_permit_alt9067

|ds_searchtbl_return|

.. _nl_mae_permit_alt9371:

    b. Newfoundland and Labrador Department of Municipal Affairs and Environment - Water Resources Management Division, 2017. Permit to Alter a Body of Water - Permit No. ALT9371-2017. Accessed from https://www.gov.nl.ca/ecc/files/waterres-permits-water-alt-dams-2017-r-alt9371-2017.pdf

    **Short name:** nl_mae_permit_alt9371

|ds_searchtbl_return|

Nova Scotia – Agriculture
+++++++++++++++++++++++++

.. _ns_dykeland_sites:

Dykeland Sites
``````````````

    Government of Nova Scotia, no date. Working With the Tides - Dykeland Sites. Accessed February 8, 2022, from https://novascotia.ca/dykeland-system-upgrades/dykeland-sites/

    **Short name:** ns_dykeland_sites

|ds_searchtbl_return|

Municipal Sources
~~~~~~~~~~~~~~~~~

City of Calgary, Alberta
++++++++++++++++++++++++

.. _ab_cal_gdii:

Glenmore Dam Infrastructure Improvements
````````````````````````````````````````

    City of Calgary, 2020. Glenmore Dam infrastructure improvements. Accessed December 13, 2021, from https://www.calgary.ca/uep/water/construction-projects/construction-projects-and-upgrades/glenmore-dam-infrastructure-improvements.html

    **Short name:** ab_cal_gdii

|ds_searchtbl_return|

.. _ab_cal_grdo:

Glenmore Reservoir Dam Operations
`````````````````````````````````

    City of Calgary, no date. Glenmore Reservoir Dam Operations. Accessed December 13, 2021, from https://www.calgary.ca/uep/water/water-and-wastewater-systems/water-treatment/glenmore-reservoir-dam-operations.html

    **Short name:** ab_cal_grdo

|ds_searchtbl_return|

City of Dawson Creek, British Columbia
++++++++++++++++++++++++++++++++++++++

Drinking Water Quality Reports
``````````````````````````````

.. _bc_dc_wqar2019:

    a. City of Dawson Creek, 2020. 2019 Drinking Water Quality Annual Report. p. 6. Accessed from https://www.dawsoncreek.ca/wordpress/wp-content/uploads/annual-reports/WTP-Annual-Water-Quality-Report-FINAL_DA_KG.pdf

    **Short name:** bc_dc_wqar2019

|ds_searchtbl_return|

.. _bc_dc_wqar2016:

    b. City of Dawson Creek, 2017. 2016 Drinking Water Quality Annual Report. p. 6. Accessed from https://www.dawsoncreek.ca/wordpress/wp-content/uploads/annual-reports/Water-Quality-Report-2016.pdf

    **Short name:** bc_dc_wqar2016

|ds_searchtbl_return|

.. _bc_dc_wqap2015:

    c. City of Dawson Creek, 2015. Drinking Water Quality Assurance Plan Update Final Report. pp. 4, 33. Accessed from https://www.dawsoncreek.ca/wordpress/wp-content/uploads/annual-reports/Water-Quality-Assurance-Plan-2015.pdf

    **Short name:** bc_dc_wqap2015

|ds_searchtbl_return|

Eastern Irrigation District, Alberta 
++++++++++++++++++++++++++++++++++++

.. _aeid_bassano:

Bassano Dam
```````````

    Eastern Irrigation District, no date. Bassano Dam. Accessed December 13, 2021, from https://www.eid.ca/documents/publications/Brochure_Bassano_Dam.pdf

    **Short name:** aeid_bassano

|ds_searchtbl_return|

Halifax Water 
+++++++++++++

.. _ns_hal_clews_swpp:

Chain Lakes Emergency Water Supply Watershed Area – Source Water Protection Plan
````````````````````````````````````````````````````````````````````````````````

    Halifax Water, 2017. Chain Lakes Emergency Water Supply Watershed Area - Source Water Protection Plan. pp. 23, 66. Accessed from https://www.halifaxwater.ca/sites/default/files/2019-01/chainlakes-swp-plan.pdf

    **Short name:** ns_hal_clews_swpp

|ds_searchtbl_return|

.. _ns_hal_p25_2021:

Chain Lake Dam and Pockwock Lake Dam – Consultant Services
``````````````````````````````````````````````````````````

    Halifax Water, 2021. RFP #P25.2021 - Chain Lake Dam and Pockwock Lake Dam - Consultant Services. pp. 5. Accessed from https://procurement.novascotia.ca/pt_files/tenders/P252021.pdf

    **Short name:** ns_hal_p25_2021

|ds_searchtbl_return|

.. _ns_hal_p24_2019:

Halifax Water Dam Safety Review
```````````````````````````````

    Halifax Water, 2019. RFP #P24.2019 - Halifax Water Dam Safety Review (2019); Appendix E. Accessed from https://procurement.novascotia.ca/pt_files/tenders/P242019.pdf

    **Short name:** ns_hal_p24_2019

|ds_searchtbl_return|

.. _ns_hal_hwirp_v3:

Integrated Resource Plan – Water System Review
``````````````````````````````````````````````

    Halifax Water, 2012. Halifax Water Integrated Resource Plan; Volume 3 Appendix A - Water System Review. pp. 41-42. Accessed from https://www.halifax.ca/sites/default/files/documents/home-property/water/HW_IntegratedResourcePlan_AppendixA.pdf

    **Short name:** ns_hal_hwirp_v3

|ds_searchtbl_return|

Energy Company Sources
~~~~~~~~~~~~~~~~~~~~~~

Irrican Power
+++++++++++++

.. _irrican_chin_chute:

Chin Chute Power Plant
``````````````````````

    Irrican Power, no date. Chin Chute Power Plant. St. Mary’s River Irrigation District. Accessed December 13, 2021, from https://www.smrid.com/wp-content/uploads/2020/09/irrican-CHIN.pdf

    **Short name:** irrican_chin_chute

|ds_searchtbl_return|

.. _irrican_drops_456:

Drops 4, 5, and 6 Power Plant
`````````````````````````````

    Irrican Power, 2020. Drops 4, 5, and 6 Power Plant. St. Mary’s River Irrigation District. Accessed December 13, 2021, from https://www.smrid.com/wp-content/uploads/2020/09/irrican-456-brochure.pdf

    **Short name:** irrican_drops_456

|ds_searchtbl_return|

.. _irrican_ray_res:

Raymond Reservoir Power Plant
`````````````````````````````

    Irrican Power, 2020. Raymond Reservoir Plant. St. Mary’s River Irrigation District. Accessed December 13, 2021, from https://www.smrid.com/wp-content/uploads/2020/09/Raymond-Hydro-2.pdf

    **Short name:** irrican_ray_res

|ds_searchtbl_return|

Lower Churchill Management Corporation
++++++++++++++++++++++++++++++++++++++

.. _lcmc_protulipac_et_al_2018:

Muskrat Falls Dams – Cold Climate Considerations in Design and Construction
```````````````````````````````````````````````````````````````````````````

    Protulipac, D., Smith, T., Snyder, G., O’Brien, J., & Chislett, T., 2018. Muskrat Falls Dams – Cold Climate Considerations in Design and Construction. CDA 2018 Annual Conference, Québec, Québec. pp. 4-5. Accessed from `https://www.researchgate.net/publication/328365634_MUSKRAT_FALLS_DAMS_-_COLD_CLIMATE_CONSIDERATIONS_IN_DESIGN_AND_CONSTRUCTION <https://www.researchgate.net/publication/328365634_MUSKRAT_FALLS_DAMS_-_COLD_CLIMATE_CONSIDERATIONS_IN_DESIGN_AND_CONSTRUCTION>`_

    **Short name:** lcmc_protulipac_et_al_2018

|ds_searchtbl_return|

NB Power 
++++++++

.. _nbpower_hydro_tour:

Hydro Tour
``````````

    NB Power, no date. Hydro Tour. Accessed February 8, 2022, from https://www.nbpower.com/en/about-us/learning/learn-about-electricity/hydro/hydro-tour/

    **Short name:** nbpower_hydro_tour

|ds_searchtbl_return|

Newfoundland and Labrador Hydro
+++++++++++++++++++++++++++++++

.. _nlhydro_adsr_2017_70503:

Audit Dam Safety Review for Pudops Dam, North Salmon Dam and Spillway (RFP# 2017-70503)
```````````````````````````````````````````````````````````````````````````````````````

    Newfoundland and Labrador Hydro, 2017. RFP # 2017-70503 - Audit Dam Safety Review for Pudops Dam, North Salmon Dam and Spillway; Appendix VI: Inventory of Dams and Dykes. Accessed from https://bids.nalcorenergy.com/Module/Tenders/en/Document/Preview/c33bf56c-20b9-453d-914a-4d779ce9ed0e

    **Short name:** nlhydro_adsr_2017_70503

|ds_searchtbl_return|

.. _nlhydro_ca_nlh_155:

Depreciation Methodology and Asset Service Lives
````````````````````````````````````````````````

    Newfoundland Hydro, 2009. CA-NLH-155 Attachment 1 - Depreciation Methodology and Asset Service Lives. Accessed from http://www.pub.nl.ca/applications/ARCHIVE/NLH2012Depreciation/files/rfi/CA-NLH-155.pdf

    **Short name:** nlhydro_ca_nlh_155

|ds_searchtbl_return|

.. _nlhydro_ops_hydro:

Operations – Hydro Generation
`````````````````````````````

    Newfoundland and Labrador Hydro, no date. Operations - Hydro Generation. Accessed February 8, 2022, from https://nlhydro.com/operations/hydro-generation/

    **Short name:** nlhydro_ops_hydro

|ds_searchtbl_return|

Newfoundland Power
++++++++++++++++++

.. _nlp_depreciation_2019:

2019 Depreciation Study – Hydro Plant Decommissioning Report
````````````````````````````````````````````````````````````

    Newfoundland Power, 2019. 2019 Depreciation Study - Hydro Plant Decommissioning Report. pp. 4-83. Accessed from http://publicinfo.nlh.nl.ca/Newfoundland%20Power's%202022%20CBA/RFI%20Responses/CA-NP-021.pdf

    **Short name:** nlp_depreciation_2019

|ds_searchtbl_return|

.. _nlp_dsi_2007:

Dam Safety Inspection Reports
`````````````````````````````

    Newfoundland Power, 2007. 2007 Dam Safety Inspection Report - Tors Cove / Rocky Pond Developments. Accessed from http://www.pub.nf.ca/applications/NP2009Capital/files/rfi/CA-NP-10.pdf

    **Short name:** nlp_dsi_2007

|ds_searchtbl_return|

Facility Rehabilitation
```````````````````````

.. _nlp_fac_rehab_2014:

    a. Newfoundland Power, 2013. 2014 Facility Rehabilitation. pp. 3, 5-6. Accessed from http://www.pub.nf.ca/applications/IslandInterconnectedSystem/files/rfi/PUB-NP-175.pdf

    **Short name:** nlp_fac_rehab_2014

|ds_searchtbl_return|

.. _nlp_fac_rehab_2012:

    b.	Newfoundland Power, 2011. 2012 Facility Rehabilitation. pp. 1-3. Accessed from http://www.pub.nl.ca/applications/NP2012Capital/files/applic/NP2012Application-Generation.pdf

    **Short name:** nlp_fac_rehab_2012

|ds_searchtbl_return|

.. _nlp_ppiep_2009:

Potential Projects to Increase Energy Production
````````````````````````````````````````````````

    Newfoundland Power, 2009. Potential Projects to Increase Energy Production. pp. 2-25. Accessed from http://pub.nl.ca/applications/NP2010Capital/files/rfi/PUB-NP-009.pdf

    **Short name:** nlp_ppiep_2009

|ds_searchtbl_return|

.. _nlp_pub_safety_2016:

Public Safety Around Dams
`````````````````````````

    Newfoundland Power, 2016. Public Safety Around Dams. pp. 2-20. Accessed from http://www.pub.nf.ca/applications/NP2017Capital/files/applications/FromNP-2017CapitalBudgetApplication-2016-07-19.pdf

    **Short name:** nlp_pub_safety_2016

|ds_searchtbl_return|

.. _nlp_rbfc_2011:

Rattling Brook Fisheries Compensation
`````````````````````````````````````

    Newfoundland Power, 2011. Rattling Brook Fisheries Compensation. pp. 3-4. Accessed from http://www.pub.nl.ca/applications/NP2012Capital/files/applic/NP2012Application-Generation.pdf

    **Short name:** nlp_rbfc_2011

|ds_searchtbl_return|

.. _nlp_sep_2008:

Sustainable Electricity Program
```````````````````````````````

    Newfoundland Power, 2009. 2008 Submission - Sustainable Electricity Program. pp. 4. Accessed from https://secure.newfoundlandpower.com/-/media/PDFs/About-Us/Sustainable-Electricity/SEP-2008-Report.pdf

    **Short name:** nlp_sep_2008

|ds_searchtbl_return|

Nova Scotia Power
+++++++++++++++++

.. _nsp_ihas:

Nova Scotia Power Incorporated Hydro Asset Study – Redacted
```````````````````````````````````````````````````````````

    Nova Scotia Power Inc., 2018. Nova Scotia Power Incorporated Hydro Asset Study - Redacted; Appendix B. pp. 16-68. Accessed from https://irp.nspower.ca/files/key-documents/background-materials/20181221-NS-Power-Hydro-Asset-Study-REDACTED.pdf

    **Short name:** nsp_ihas

|ds_searchtbl_return|

Suncor Energy
+++++++++++++

.. _suncor_safety_initiative:

Investor Mining and Tailings Safety Initiative Disclosure Table
```````````````````````````````````````````````````````````````

    Suncor Energy, no date. Investor Mining and Tailings Safety Initiative Disclosure Table. Sustainability at Suncor. Accessed December 13, 2021, from https://sustainability-prd-cdn.suncor.com/-/media/project/ros/shared/documents/other-disclosures/suncor-industry-disclosure-table-en.pdf?la=en&modified=20201216022314&hash=FF951A51BA9699AF9ACC4A631A5AC36A999663FB

    **Short name:** suncor_safety_initiative

|ds_searchtbl_return|

TransAlta
+++++++++

.. _transalta_barrier:

Barrier Power Plant
```````````````````

    TransAlta, n.d. Barrier. Accessed December 13, 2021, from https://transalta.com/plants-operation/barrier/

    **Short name:** transalta_barrier

|ds_searchtbl_return|

.. _transalta_bearspaw:

Bearspaw Plant
``````````````

    TransAlta, n.d. Bearspaw. Accessed December 13, 2021, from https://transalta.com/plants-operation/bearspaw/

    **Short name:** transalta_bearspaw

|ds_searchtbl_return|

.. _transalta_belly:

Belly River Hydro Facility
``````````````````````````

    TransAlta, n.d. Belly River. Accessed December 13, 2021, from https://transalta.com/plants-operation/belly-river/

    **Short name:** transalta_belly

|ds_searchtbl_return|

.. _transalta_bighorn:

Bighorn Plant
`````````````

    TransAlta, n.d. Bighorn. Accessed December 13, 2021, from https://transalta.com/plants-operation/bighorn/

    **Short name:** transalta_bighorn

|ds_searchtbl_return|

.. _transalta_brazeau:

Brazeau Plant
`````````````

    TransAlta, n.d. Brazeau. Accessed December 13, 2021, from https://transalta.com/plants-operation/brazeau/

    **Short name:** transalta_brazeau

|ds_searchtbl_return|

.. _transalta_cascade:

Cascade Plant
`````````````

    TransAlta, n.d. Cascade. Accessed December 13, 2021, from https://transalta.com/plants-operation/cascade/

    **Short name:** transalta_cascade

|ds_searchtbl_return|

.. _transalta_ghost:

Ghost Plant
```````````

    TransAlta, n.d. Ghost. Accessed December 13, 2021, from https://transalta.com/plants-operation/ghost/

    **Short name:** transalta_ghost

|ds_searchtbl_return|

.. _transalta_horseshoe:

Horseshoe Plant
```````````````

    TransAlta, n.d. Horseshoe. Accessed December 13, 2021, from https://transalta.com/plants-operation/horseshoe/
    
    **Short name:** transalta_horseshoe

|ds_searchtbl_return|

.. _transalta_interlakes:

Interlakes Plant
````````````````

    TransAlta, n.d. Interlakes. Accessed May 6, 2022, from https://transalta.com/plants-operation/interlakes/

    **Short name:** transalta_interlakes

|ds_searchtbl_return|

.. _transalta_kananaskis:

Kananaskis Plant
````````````````

    TransAlta, n.d. Kananaskis. Accessed December 13, 2021, from https://transalta.com/plants-operation/kananaskis/

    **Short name:** transalta_kananaskis

|ds_searchtbl_return|

.. _transalta_pocaterra:

Pocaterra Plant
```````````````

    TransAlta, n.d. Pocaterra. Accessed December 13, 2021, from https://transalta.com/plants-operation/pocaterra/

    **Short name:** transalta_pocaterra

|ds_searchtbl_return|

.. _transalta_rundle:

Rundle Plant
````````````

    TransAlta, n.d. Rundle. Accessed December 13, 2021, from https://transalta.com/plants-operation/rundle/

    **Short name:** transalta_rundle

|ds_searchtbl_return|

.. _transalta_sheerness:

Sheerness Generating Station
````````````````````````````

    TransAlta, n.d. Sheerness. Accessed December 13, 2021, from https://transalta.com/plants-operation/sheerness/

    **Short name:** transalta_sheerness

|ds_searchtbl_return|

.. _transalta_spray:

Spray Hydro Facility
````````````````````

    TransAlta, n.d. Spray. Accessed December 13, 2021, from https://transalta.com/plants-operation/spray/

    **Short name:** transalta_spray

|ds_searchtbl_return|

.. _transalta_st_mary:

St. Mary Hydro Facility
```````````````````````

    TransAlta, n.d. St. Mary. Accessed December 13, 2021, from https://transalta.com/plants-operation/st-mary/

    **Short name:** transalta_st_mary

|ds_searchtbl_return|

.. _transalta_taylor:

Taylor Hydro Facility
`````````````````````

    TransAlta, n.d. Taylor. Accessed December 13, 2021, from https://transalta.com/plants-operation/taylor-hydro/

    **Short name:** transalta_taylor

|ds_searchtbl_return|

.. _transalta_three_sisters:

Three Sisters Plant
```````````````````

    TransAlta, n.d. Three Sisters. Accessed December 13, 2021, from https://transalta.com/plants-operation/three-sisters/

    **Short name:** transalta_three_sisters

|ds_searchtbl_return|

.. _transalta_waterton:

Waterton Hydro Facility
```````````````````````

    TransAlta, n.d. Waterton. Accessed December 13, 2021, from https://transalta.com/plants-operation/waterton/

    **Short name:** transalta_waterton

|ds_searchtbl_return|

Academic Institutions/NGO Sources
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Alberta WaterPortal Society
+++++++++++++++++++++++++++

.. _awps_brid:

Bow River Irrigation District
`````````````````````````````

    Alberta WaterPortal Society, 2022. Bow River Irrigation District. Accessed May 6, 2022, from https://albertawater.com/latest/8786-bow-river-irrigation-district/

    **Short name:** awps_brid

|ds_searchtbl_return|

.. _awps_smrid:

St. Mary River Irrigation District
``````````````````````````````````

    Alberta WaterPortal Society, 2022. St. Mary River Irrigation District. Accessed May 6, 2022, from https://albertawater.com/latest/8795-st-mary-river-irrigation-district-projects-overview/

    **Short name:** awps_smrid

|ds_searchtbl_return|

.. _awa_obed_spill:

Alberta Wilderness Association
++++++++++++++++++++++++++++++

    Alberta Wilderness Association, 2017. News Release: 4 Years After Obed Spill, Questions Remain. Accessed May 6, 2022, from https://albertawilderness.ca/news-release-4-years-obed-spill-questions-remain/

    **Short name:** awa_obed_spill

|ds_searchtbl_return|

Shubenacadie Canal Commission
+++++++++++++++++++++++++++++

.. _scc_locks:

The Locks
`````````

    Shubenacadie Canal Commission, no date. The Locks. Accessed February 8, 2022, from https://www.shubenacadiecanal.ca/the-locks

    **Short name:** scc_locks

|ds_searchtbl_return|

South East Alberta Watershed Alliance (SEAWA)
+++++++++++++++++++++++++++++++++++++++++++++

.. _seawa_pakowki_lake:

Pakowki Lake Watershed Profile
``````````````````````````````

    South East Alberta Watershed Alliance, 2020. Pakowki Lake. Accessed December 13, 2021, from https://seawa.ca/your-watershed/profile-of-the-seawa-watershed/pakowki-lake

    **Short name:** seawa_pakowki_lake

|ds_searchtbl_return|

Consulting Reports
~~~~~~~~~~~~~~~~~~

Advanced Construction Techniques Ltd.
+++++++++++++++++++++++++++++++++++++

.. _act_st_mary_spillway:

St. Mary Dam Spillway Replacement Project
`````````````````````````````````````````

    Advanced Construction Techniques Ltd., no date. St. Mary Dam Spillway Replacement Project. Advanced Construction Techniques. Accessed December 13, 2021, from http://www.advancedconstructiontechniques.com/St-Mary-Dam-Spillway-Replacement-Project.asp

    **Short name:** act_st_mary_spillway

|ds_searchtbl_return|

AMEC Americas Ltd.
++++++++++++++++++

.. _amec_frmp_2013:

Flood Risk Mapping Project
``````````````````````````

    AMEC Environment & Infrastructure, 2013. Flood Risk Mapping Project - Corner Brook Stream and Petrie's Brook. Report prepared for Government of Newfoundland and Labrador Department of Environment and Conservation, Water Resources Management Division. pp. 2-12 - 2-15. Accessed from https://www.gov.nl.ca/ecc/files/waterres-flooding-corner-brook-stream-cornerbrook-report.pdf

    **Short name:** amec_frmp_2013

|ds_searchtbl_return|

.. _amec_ssrba_wss:

South Saskatchewan River Basin in Alberta: Water Supply Study
`````````````````````````````````````````````````````````````

    AMEC Earth & Environmental, 2009. South Saskatchewan River Basin in Alberta: Water Supply Study. Report prepared for Alberta Agriculture and Rural Development. pp. 20. Accessed May 6, 2022, from https://www1.agric.gov.ab.ca/$Department/deptdocs.nsf/all/irr13053/$FILE/ssrb_main_report.pdf

    **Short name:** amec_ssrba_wss

|ds_searchtbl_return|

East Coast Aquatics Inc.
++++++++++++++++++++++++

.. _eca_bio_assess:

Biological Assessment for Proposed Liverpool Wind Farm
``````````````````````````````````````````````````````

    East Coast Aquatics Inc., 2014. Biological Assessment for Proposed Liverpool Wind Farm. Report prepared for Eon Wind Electric. pp. 17; Table 3. Accessed from https://novascotia.ca/nse/ea/liverpool-wind-farm/Appendix_H-K.pdf

    **Short name:** eca_bio_assess

|ds_searchtbl_return|

Golder Associates Inc.
++++++++++++++++++++++

.. _golder_genesee_2013:

Genesee Cooling Pond Thermal and Water Quality Modelling Study
``````````````````````````````````````````````````````````````

    Golder Associates, 2013. Genesee Cooling Pond Thermal and Water Quality Modelling Study. Report prepared for Capital Power Corporation. pp. 1. Accessed May 6, 2022, from https://www.capitalpower.com/wp-content/uploads/2019/06/Appendix_F_Genesee_Cooling_Pond_Modelling_Study.pdf 

    **Short name:** golder_genesee_2013

|ds_searchtbl_return|

.. _golder_inv_nl_2016:

Inventory and Assessment of Dams in Eastern Newfoundland
````````````````````````````````````````````````````````

    Golder Associates Inc., 2016. Inventory and Assessment of Dams in Eastern Newfoundland. Report Prepared for Government of Newfoundland and Labrador Department of Environment and Conservation, Water Resources Management Division. pp. 5-42. Accessed from https://www.gov.nl.ca/ecc/files/waterres-reports-dam-safety-1533903-01-rev1-east-nl-dam-inv-report.pdf

    **Short name:** golder_inv_nl_2016

|ds_searchtbl_return|

.. _golder_inv_nl_2019:

Inventory and Assessment of Dams in Newfoundland and Labrador Year Three
````````````````````````````````````````````````````````````````````````

    Golder Associates Inc., 2019. Inventory and Assessment of Dams in Newfoundland and Labrador Year Three. Report Prepared for Government of Newfoundland and Labrador Department of Municipal Affairs and Environment, Water Resources Management Division. pp. 11-37. Accessed from https://www.gov.nl.ca/ecc/files/waterres-reports-dam-safety-nl-dam-inventory-year-3-report.pdf

    **Short name:** golder_inv_nl_2019

|ds_searchtbl_return|

.. _golder_inv_nl_2017:

Inventory and Assessment of Dams in Newfoundland and Labrador Year Two
``````````````````````````````````````````````````````````````````````

    Golder Associates Inc., 2017. Inventory and Assessment of Dams in Newfoundland and Labrador Year Two. Report Prepared for Government of Newfoundland and Labrador Department of Municipal Affairs and Environment, Water Resources Management Division. pp. 12-40. Accessed from https://www.gov.nl.ca/ecc/files/waterres-reports-dam-safety-nl-dam-inventory-year-2-final-report.pdf

    **Short name:** golder_inv_nl_2017

|ds_searchtbl_return|

MPE Engineering Ltd.
++++++++++++++++++++

.. _mpe_aep_prov_inventory:

Provincial Inventory of Potential Water Storage Sites and Diversion Scenarios
`````````````````````````````````````````````````````````````````````````````

    MPE Engineering Ltd., 2005. Provincial Inventory of Potential Water Storage Sites and Diversion Scenarios. Report prepared for Alberta Environment. Accessed from https://open.alberta.ca/dataset/9b95703a-13ca-4645-87a7-ee33e99508ca/resource/2f28e7ed-0c72-427d-bfe2-3b1ddfb00bbf/download/aenv-water-for-life-reliable-quality-water-supplies-for-a-sustainable-economy-7750.pdf

    **Short name:** mpe_aep_prov_inventory

|ds_searchtbl_return|

Power Advisory LLC
++++++++++++++++++

.. _pallc_nl_elec:

Review of the Newfoundland and Labrador Electricity System
``````````````````````````````````````````````````````````

    Power Advisory LLC, 2015. Review of the Newfoundland and Labrador Electricity System. Report prepared for Government of Newfoundland and Labrador Department of Natural Resources. pp. 40, 45, 47, 52-53, 76. Accessed from https://www.muskratfallsinquiry.ca/files/P-00110.pdf

    **Short name:** pallc_nl_elec

|ds_searchtbl_return|

SNC-Lavalin Group Inc.
++++++++++++++++++++++

.. _sncl_lower_churchill:

Lower Churchill Project Design Criteria
```````````````````````````````````````

    SNC-Lavalin Group Inc., 2013. Lower Churchill Project Design Criteria - Civil. Report prepared for Nalcor Energy. pp. 34, 44-45. Accessed from https://muskratfalls.nalcorenergy.com/wp-content/uploads/2013/03/Muskrat-Falls_Civil-Design-Criteria_Feb2013_Web.pdf

    **Short name:** sncl_lower_churchill

|ds_searchtbl_return|

Peer-Reviewed Articles
~~~~~~~~~~~~~~~~~~~~~~

.. _alrs_spray_lakes:

Alberta Law Review
++++++++++++++++++

    Nykolaishen, S. & Bankes, N., 2012. Sacrificing Fish for Power: A Legal History of the Spray Lakes Development. Alberta Law Review 50(1), pp. 6. https://doi.org/10.29173/alr266

    **Short name:** alrs_spray_lakes

|ds_searchtbl_return|

.. _cgj_williams_etal_1983:

Canadian Geotechnical Journal
+++++++++++++++++++++++++++++

    Williams, D. R., Balanko, L. A., & Martin, R. L., 1983. Monitoring and performance of an earth-fill dam in central Alberta. Canadian Geotechnical Journal, 20(4), pp. 570–586. https://doi.org/10.1139/t83-068

    **Short name:** cgj_williams_etal_1983

|ds_searchtbl_return|

Miscellaneous Online Sources
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Wikipedia
+++++++++

.. _wiki_dickson_dam:

Dickson Dam
```````````

    Wikipedia contributors, 2022. Dickson Dam. Wikipedia. Accessed May 6, 2022, from https://en.wikipedia.org/wiki/Dickson_Dam

    **Short name:** wiki_dickson_dam

|ds_searchtbl_return|

.. _wiki_cdn_wfs:

List of Canadian Waterfalls
```````````````````````````

    Wikipedia contributors, 2020. List of waterfalls of Canada. Wikipedia. Accessed February 14, 2020, from https://en.wikipedia.org/wiki/List_of_waterfalls_of_Canada

    **Short name:** wiki_cdn_wfs

|ds_searchtbl_return|

.. _wiki_gs_bc:

List of Generating Stations in British Columbia
```````````````````````````````````````````````

    Wikipedia contributors, 2020. List of generating stations in British Columbia. Wikipedia. Accessed April 28, 2020, from https://en.wikipedia.org/wiki/List_of_generating_stations_in_British_Columbia

    **Short name:** wiki_gs_bc

|ds_searchtbl_return|

.. _wiki_nb_hydro: 

List of Generating Stations in New Brunswick
````````````````````````````````````````````

    Wikipedia contributors, 2021. List of generating stations in New Brunswick. Wikipedia. Accessed February 8, 2022, from https://en.wikipedia.org/wiki/List_of_generating_stations_in_New_Brunswick

    **Short name:** wiki_nb_hydro

|ds_searchtbl_return|

.. _wiki_lbr: 

Little Bow Lake Reservoir
`````````````````````````

    Wikipedia contributors, 2020. Little Bow Lake Reservoir. Wikipedia. Accessed from https://en.wikipedia.org/wiki/Little_Bow_Lake_Reservoir

    **Short name:** wiki_lbr


|ds_searchtbl_return|

.. toctree::
   :hidden:

   docs_user_data_sources/docs_user_data_sources_csv_download.rst