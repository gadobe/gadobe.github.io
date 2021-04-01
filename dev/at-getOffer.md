---
title: "at-meta"
permalink: /dev/at-getOffer
search: false
layout: dev001
---

<script>
    function goDoSomething(d){
        alert(d.getAttribute("stitch-id"));
    }
</script>

<script>
adobe.target.getOffer({   
  "mbox": "ww-sm.web.search.banner",
  "params": {
     "SearchKeyword": "a2-milk",
     "at_property": "517215df-9ce4-b49c-557d-0fd48965740a"
  },
  "success": function(offer) {
        adobe.target.applyOffer( {  
           "mbox": "ww-sm.web.search.banner",
           "selector": "#container1",
           "offer": offer  
        } );
  },   
  "error": function(status, error) {           
      console.log('Error', status, error);
  }
});
</script>

<p>ww-sm.web.search.banner</p>
<div id="container1" style="height:250px;width:300px;background-color:powderblue;">
  default mbox 1
</div>

<p>ww-sm.web.search.contentcard</p>
<div id="container2" style="height:250px;width:300px;background-color:green;">
  default mbox 2
</div>
