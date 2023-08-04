.. _data-catalogue:

==============
Data Catalogue
==============

The CABD data catalogue contains the the information you need to make sense of the attributes for each CABD feature type (dams, waterfalls, and fishways), including human-readable field names, breakdowns of allowable field values, and definitions. If you have questions about any of the information on this page, you can reach out to us at cabd@cwf-fcf.org.

Feature Types
-------------

.. raw:: html
  
    <div id="datasourcecontent">
    </div>
    
    <script>
    function loadDataSources() {
    
      let url = "https://cabd-web.azurewebsites.net/cabd-api/docs?options=types"
      let xhr = new XMLHttpRequest();
      // Making our connection 
       xhr.open("GET", url, true);
   
      // function execute after request is successful
      xhr.onreadystatechange = function () {
        if (this.readyState == 4 && this.status == 200) {
            let element = document.getElementById("datasourcecontent");
            element.innerHTML = this.responseText;      
            
            //make a data table out of the nhn watershed id field
            //across all feature types
            $("table[id^='datatable_attribute_nhn_watershed_id']").each(function(){
               $("#" + this.id).DataTable();
            });            
        }
      }
      // Sending our request
      xhr.send();
    }
    loadDataSources();
    </script>
  