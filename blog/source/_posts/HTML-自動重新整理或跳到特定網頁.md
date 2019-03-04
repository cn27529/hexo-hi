---
title: HTML 自動重新整理或跳到特定網頁
tags:
  - HTML
  - IE
date: 2009-10-26 05:29:00
---

在 &lthead> 後，加入下列程式碼

<pre class="brush: html;">&ltmeta content='10' http-equiv='Refresh'/>
<!--數字是要隔幾秒後要重新整理，以本例來說，隔十秒就會讓網頁重新整理-->

&ltmeta content='10' URL='http://tw.yahoo.com' http-equiv='Refresh'/>
<!-- 隔十秒後，跳到指定的 http://tw.yahoo.com -->

</pre>
如果你是部落客，您必須要能編輯原始程式碼，如Google Blogger。<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>