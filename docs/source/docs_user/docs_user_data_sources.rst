.. _data-sources:


============
Data Sources
============

.. note::
    
    If you're visiting from the CABD web tool, and accidentally closed your tab, you can navigate back to the web tool `here <https://aquaticbarriers.ca>`_.


The CABD only exists due to all the painstaking work done by many groups and organizations who have compiled and maintained existing barrier inventories across North America, and either made them openly available or entered into data-sharing agreements with us. A special thank you to these groups! The CABD simply builds off this existing work, and we hope that our work to fill data gaps can benefit original data holders in return. If you are the maintainer of one of the data sources on this page, and would like to chat about how we can share some of our data updates back to you, please contact us at cabd@cwf-fcf.org.

A lot of the work done on the CABD involved de-duplicating and combining attributes for where two or more data sources have a point representing the same structure. This means that for a single point in the CABD, attribute information may be coming from multiple different sources, which makes data-source attribution a bit tricky! We've come up with a solution to map where each attribute in a CABD data point comes from, check out the :ref:`Feature Data Source Details Download <data-source-details>` page for more information.

.. attention::

    *Data in the CABD is made available through the* `CC BY-SA 4.0 <https://creativecommons.org/licenses/by-sa/4.0/>`_ *license. This license allows you to share and adapt this data, as long as you provide proper credit and distribute any derivative data under the same CC BY-SA 4.0 license.*

Data Source Table
-----------------


.. raw:: html
  
    <div id="datasourcecontent"/>
    
    <script>
    function loadDataSources() {
    
      let url = "https://cabd-web.azurewebsites.net/cabd-api/docs?options=ds"
      let xhr = new XMLHttpRequest();
      // Making our connection 
       xhr.open("GET", url, true);
   
      // function execute after request is successful
      xhr.onreadystatechange = function () {
        if (this.readyState == 4 && this.status == 200) {
            let element = document.getElementById("datasourcecontent");
            element.innerHTML = this.responseText;   
            //convert this into a dataTable
            $('#ds_dataTable').DataTable();
            
            let kids = $('nav[class*=\"page-toc\"]');
            for (kid of kids){
               createToC(element, kid);
             }
        }
      }
      // Sending our request
      xhr.send();
    } 
    
    function createToC(element, appendTo){
   
       for (let kid of element.children){
         
         if (kid.tagName.toLowerCase() == "section" && kid.id.startsWith("dsid_")){
            
            let ulchild = document.createElement("ul");
            ulchild.className = "visible nav section-nav flex-column";
            
            
            let child = document.createElement("li");
            child.className = "nav-item toc-entry toc-h2";
            
            let achild = document.createElement("a");
            achild.className="reference internal nav-link";
            achild.href = "#" + kid.id;
            achild.innerHTML = kid.children[0].innerHTML;
            
            child.appendChild(achild);
            ulchild.appendChild(child);
      
            appendTo.appendChild(ulchild);
            
            for (let kid2 of kid.children){
               if (kid2.tagName.toLowerCase() == "section" && kid2.id.startsWith("dsid_")){         
                  let ulchild = document.createElement("ul");
                  ulchild.className = "visible nav section-nav flex-column";
                  
                  
                  let child2 = document.createElement("li");
                  child2.className = "nav-item toc-entry toc-h3";
                  
                  let achild = document.createElement("a");
                  achild.className="reference internal nav-link";
                  achild.href = "#" + kid2.id;
                  //achild.innerHTML = kid2.innerHTML
                  achild.innerHTML = kid2.children[0].innerHTML;
                  
                  child2.appendChild(achild);
                  ulchild.appendChild(child2);
            
                  child.appendChild(ulchild);
               }
            }
          }    
      }
    }
    loadDataSources();
    </script>
  













