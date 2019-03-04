---
title: 玩玩 jsbin.com
tags:
  - CSS3
  - HTML
  - javascript
  - jQuery
  - JSON
  - 線上工具
  - 隨便寫寫
date: 2016-03-25 13:54:00
---

好用的jsbin，[http://jsbin.com](http://jsbin.com/)是一套前端的編輯工具線上，可在撰寫前端程式碼，然後可即時反應，也不用自己F5，XD

開始玩一下吧
<div class="separator" style="clear: both; text-align: center;"></div><div class="separator" style="clear: both; text-align: center;">[![](https://3.bp.blogspot.com/-2iv8TmW-cH0/VvSqLMkfAQI/AAAAAAAAJyg/yry1PNfjGiUXdIbqKnLcqDc141cO7k44w/s1600/new-jsbin.png)](https://3.bp.blogspot.com/-2iv8TmW-cH0/VvSqLMkfAQI/AAAAAAAAJyg/yry1PNfjGiUXdIbqKnLcqDc141cO7k44w/s1600/new-jsbin.png)</div>

在JavaScript區塊中來個JSON如下，完成JSON後，再按CTRL+S，進行存檔
<pre class="prettyprint">{ 

  "name": "jsbin",
  "age": 99,
  "birthday": "1988/02/02",
  "mails": {"home": "hotmail@mail.com", "work": "yahoo@mail.com"},
  "phones": {"mobile": "0923456789", "home": "048353868" }

}

</pre>

將網址列的URL記下來，等一下會用到
<div class="separator" style="clear: both; text-align: center;">[![](https://4.bp.blogspot.com/-3pJy7E5g_7Y/VvTQPWBzHVI/AAAAAAAAJy4/ViRK9v2Qyj4_iMd1We6c07TbXENZB1bDQ/s1600/jsbin-url.png)](https://4.bp.blogspot.com/-3pJy7E5g_7Y/VvTQPWBzHVI/AAAAAAAAJy4/ViRK9v2Qyj4_iMd1We6c07TbXENZB1bDQ/s1600/jsbin-url.png)</div>

再開一個新的jsbin，在JavaScript區塊中來個一段如下

<pre class="prettyprint">$.ajax({
  url: 'http://jsbin.com/dijeyodote/2/edit?js',
  dataType: 'json',
  success: function(data) {

    var json_str=JSON.stringify(data);
    var json = JSON.parse(json_str);
    alert(json.phones.mobile);   

  }

});

</pre>
完成，顯示JSON的mobile值
<div class="separator" style="clear: both; text-align: center;">[![](https://4.bp.blogspot.com/-iTSqPYYtKz8/VvTSe8Y-3kI/AAAAAAAAJzE/kki6eE-rijAHUMXyxhRZoGOTh1Wuund4g/s1600/jsbin-alert-json.png)](https://4.bp.blogspot.com/-iTSqPYYtKz8/VvTSe8Y-3kI/AAAAAAAAJzE/kki6eE-rijAHUMXyxhRZoGOTh1Wuund4g/s1600/jsbin-alert-json.png)</div>

好，收工 XD

<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>