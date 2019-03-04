---
title: CollapsibleSectionExample 可折疊零件演示
tags:
  - javascript
date: 2009-03-17 23:45:00
---

&lt;html>
    &lt;head>
        &lt;title>Style Example&lt;/title>
        &lt;script type="text/javascript">
            function toggle(sDivId) {
                var oDiv = document.getElementById(sDivId);
                oDiv.style.display = (oDiv.style.display == "none") ? "block" : "none";
            }
        &lt;/script>
    &lt;/head>
    &lt;body>
        &lt;div style="background-color: blue; color: white; font-weight: bold; padding: 10px; cursor: pointer"
             onclick="toggle('divContent1')" align="right">Click Here&lt;/div>
        &lt;div style="border: 3px solid blue; height: 100px; padding: 10px"
             id="divContent1" align="right">This is some content
        to show and hide.&lt;/div>
        &lt;p align="right">　&lt;/p>
        &lt;div style="background-color: blue; color: white; font-weight: bold; padding: 10px; cursor: pointer"
             onclick="toggle('divContent2')" align="right">Click Here&lt;/div>
        &lt;div style="border: 3px solid blue; height: 100px; padding: 10px"
             id="divContent2" align="right">This is some content
        to show and hide.&lt;/div>
    &lt;/body>
&lt;/html><div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>