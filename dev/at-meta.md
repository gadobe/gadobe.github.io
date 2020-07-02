---
title: "at-meta"
permalink: /dev/at-meta
search: false
layout: dev001
---
<script>
    function goDoSomething(d){
        alert(d.getAttribute("data-xf"));
    }
</script>
<script>
adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "ww-sm.web.search.banner",
          parameters: {
            SearchKeyword: "a2-milk"
          }
        },
        {
          index: 1,
          name: "ww-sm.web.search.contentcard",
          parameters: {
            SearchKeyword: "nomatch"
          }
        }
      ]
    }
  }
})
.then(response => {
  // get all mboxes from response
  const mboxes = response.prefetch.mboxes;
  let count = 1;
  mboxes.forEach(el => {
    adobe.target.applyOffers({
      selector: "#container" + count,
      response: {
        prefetch: {
          mboxes: [el]
        }
      }
    });
    count += 1;
  });
})
.then(() => console.log("All mboxes applied"));
</script>

<p>ww-sm.web.search.banner</p>
<div id="container1" style="height:250px;width:300px;background-color:powderblue;">
  default mbox 1
</div>

<p>ww-sm.web.search.contentcard</p>
<div id="container2" style="height:250px;width:300px;background-color:green;">
  default mbox 2
</div>
