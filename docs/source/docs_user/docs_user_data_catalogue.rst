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
         
         if (kid.tagName.toLowerCase() == "section" && (kid.id.startsWith("ft_") || kid.id.startsWith("ftatt_"))){
            
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
               if (kid2.tagName.toLowerCase() == "section" && (kid.id.startsWith("ft_") || kid.id.startsWith("ftatt_"))){         
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
