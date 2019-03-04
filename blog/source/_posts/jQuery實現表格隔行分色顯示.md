---
title: jQuery實現表格隔行分色顯示
tags:
  - jQuery
date: 2009-03-17 23:28:00
---

<pre class="brush: html;">
&lt;html>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;head>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;title>New Document&lt;/title>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;script type="text/javascript" src="http://jqueryjs.googlecode.com/files/jquery-1.3.2.min.js">&lt;/script>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;script type="text/javascript">   
&nbsp;&nbsp;&nbsp;&nbsp;  $(document).ready(function(){   
&nbsp;&nbsp;&nbsp;&nbsp;    $('tr:odd').addClass('oddColor');   
&nbsp;&nbsp;&nbsp;&nbsp;    $('tr:even').addClass('evenColor');   
&nbsp;&nbsp;&nbsp;&nbsp;    $('td:contains("Christen")').addClass('highlight')   
&nbsp;&nbsp;&nbsp;&nbsp;});   
&nbsp;&nbsp;&nbsp;&nbsp;   
&nbsp;&nbsp;&nbsp;&nbsp;  &lt;/script>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;style type="text/css">   
&nbsp;&nbsp;&nbsp;&nbsp;&lt;!--   
&nbsp;&nbsp;&nbsp;&nbsp;.oddColor {   
&nbsp;&nbsp;&nbsp;&nbsp;background-color:#ffc;   
&nbsp;&nbsp;&nbsp;&nbsp;}   
&nbsp;&nbsp;&nbsp;&nbsp;.evenColor {   
&nbsp;&nbsp;&nbsp;&nbsp;background-color:#cef;   
&nbsp;&nbsp;&nbsp;&nbsp;}   
&nbsp;&nbsp;&nbsp;&nbsp;.highlight{   
&nbsp;&nbsp;&nbsp;&nbsp;font-weight:bold;   
&nbsp;&nbsp;&nbsp;&nbsp;color:#f00}   
&nbsp;&nbsp;&nbsp;&nbsp;-->   
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/style>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/head>
&nbsp;&nbsp;&nbsp;&nbsp;&lt;body>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;table>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;tr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是奇&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>Christen&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是奇&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是奇&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/tr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;tr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是偶&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>Pinkey&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是偶&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是偶&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/tr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;tr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是奇&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是奇&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>Maomao&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是奇&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/tr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;tr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是偶&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是偶&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是偶&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>我是偶&#25968;行&lt;/td>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/tr>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/table>&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/body>
&lt;/html>

</pre><div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>