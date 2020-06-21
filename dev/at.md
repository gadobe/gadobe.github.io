---
title: "at"
permalink: /dev/at
search: false
layout: dev001
---
<script>
adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "at2testing300x2501",
          parameters: {
            category: "drinks",
            subcategory: "coffee"
          }
        },
        {
          index: 1,
          name: "at2testing300x2502",
          parameters: {
            category: "drinks",
            subcategory: "tea"
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
<p>ad tag returned in AT mbox</p>
<div id="container1" style="height:250px;width:300px;background-color:powderblue;">
  default mbox 1
</div>
<p>ad tag as default html in AT div</p>
<div id="container2">
<ins class='dcmads' style='display:inline-block;width:300px;height:250px'
    data-dcm-placement='N1262025.3421124ADOBEADCLOUD-DI/B24071122.273149705'
    data-dcm-rendering-mode='iframe'
    data-dcm-https-only
    data-dcm-resettable-device-id=''
    data-dcm-app-id='' data-dcm-click-tracker='${TM_CLICK_URL}' >
  <script src='https://www.googletagservices.com/dcm/dcmads.js'></script>
</ins>
</div>