---
title: 'JSON.stringify(), JSON資料轉字串'
tags:
  - javascript
  - jQuery
  - JSON
date: 2016-03-22 11:33:44
---

JSON.stringify(), JSON資料轉字串  <pre class="prettyprint">

//JSON資料
var data = { 
  "name": "jsbin",
  "age": 99,
  "birthday": "1988/02/02",
  "mails": {"home": "hotmail@mail.com", "work": "yahoo@mail.com"},
  "phones": {"mobile": "0923456789", "home": "048353868" }
}

//轉字串
var json_str = JSON.stringify(data);
alert(json_str);

</pre>  JSON.parse(), 將字串JSON物件 <pre class="prettyprint">

//JSON string 
var json_str = '{"name":"jsbin","age":99,"birthday":"1988/02/02"';
json_str.concat(',"mails":{"home":"hotmail@mail.com","work":"yahoo@mail.com"}');
json_str.concat(',"phones":{"mobile":"0923456789","home":"048353868"}}');

//轉JSON物件
var json = JSON.parse(json_str);
alert(json.mails.home);

</pre> 收工<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>