---
title: 'JSON.parse(), 將字串JSON物件'
tags:
  - javascript
  - jQuery
  - JSON
date: 2016-03-22 11:33:00
---

JSON.parse(), 將字串JSON物件 <pre class="prettyprint">

//JSON string 
var json_str = '{"name":"jsbin","age":99,"birthday":"1988/02/02"';
json_str.concat(',"mails":{"home":"hotmail@mail.com","work":"yahoo@mail.com"}');
json_str.concat(',"phones":{"mobile":"0923456789","home":"048353868"}}');

//轉JSON物件
var json = JSON.parse(json_str);
alert(json.mails.home);

</pre> 收工<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>