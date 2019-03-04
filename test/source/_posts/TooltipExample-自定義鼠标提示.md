---
title: TooltipExample 自定義鼠标提示
tags:
  - javascript
date: 2009-03-17 23:57:00
---

&lt;html>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;head>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;title>Style&nbsp;Example&lt;/title>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;script&nbsp;type="text/javascript">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;function&nbsp;showTip(oEvent)&nbsp;{
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var&nbsp;oDiv&nbsp;=&nbsp;document.getElementById("divTip1");
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;oDiv.style.visibility&nbsp;=&nbsp;"visible";
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;oDiv.style.left&nbsp;=&nbsp;oEvent.clientX&nbsp;+&nbsp;5;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;oDiv.style.top&nbsp;=&nbsp;oEvent.clientY&nbsp;+&nbsp;5;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;function&nbsp;hideTip(oEvent)&nbsp;{
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var&nbsp;oDiv&nbsp;=&nbsp;document.getElementById("divTip1");
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;oDiv.style.visibility&nbsp;=&nbsp;"hidden";
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/script>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/head>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;body>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;p>Move&nbsp;your&nbsp;mouse&nbsp;over&nbsp;the&nbsp;red&nbsp;square.&lt;/p>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&nbsp;id="div1"&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;style="background-color:&nbsp;red;&nbsp;height:&nbsp;50px;&nbsp;width:&nbsp;50px"
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;onmouseover="showTip(event)"&nbsp;onmouseout="hideTip(event)">&lt;/div>
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&nbsp;id="divTip1"&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;style="background-color:&nbsp;yellow;&nbsp;position:&nbsp;absolute;&nbsp;visibility:&nbsp;hidden;&nbsp;padding:&nbsp;5px">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;style="font-weight:&nbsp;bold">Custom&nbsp;Tooltip&lt;/span>&lt;br&nbsp;/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;More&nbsp;details&nbsp;can&nbsp;go&nbsp;here.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/body>
&lt;/html><div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>