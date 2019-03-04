---
title: JSON (javascript object notation)
tags:
  - javascript
date: 2010-11-18 16:52:00
---

**JSON**（**J**ava**s**cript **O**bject **N**otation）是一種輕量級的資料交換語言，以文字為基礎，且易於讓人閱讀。儘管JSON是在Javascript的一個子集，但JSON是獨立於語言的文本格式，並且採用了類似於C語言家族的一些習慣。

下列 javascript code是生成JSON的資料結構方式

Ex1:
<pre class="brush: js;">var mailingAddress = { 
     "Address"    :   "123 Anywhere St.", 
     "City"       :   "Springfield", 
     "PostalCode" :   99999
};

alert("The package will be shipped to postal code " + mailingAddress.PostalCode);

};

</pre>
Ex2:
<pre class="brush: js;">var contact = {
     "Name": "John Doe",
     "PermissionToCall": true,
     "PhoneNumbers": [ 
       {
           "Location": "Home",
           "Number": "555-555-1234"
       },
       {
           "Location": "Work",
           "Number": "555-555-9999 Ext. 123"
       }
     ]
};
if (contact.PermissionToCall)
{
  alert("Call " + contact.Name + " at " + contact.PhoneNumbers[0].Number);
}

</pre>
下方幾個引用位置是不錯的學習地方 , 在此就不做範例過程

JSON in javascript
[http://www.json.org/js.html](http://www.json.org/js.html)

JSON + jQuery +Asp.Net C# 使用心得
[http://chrisbalboa.pixnet.net/blog/post/30161616](http://chrisbalboa.pixnet.net/blog/post/30161616)

An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET
[http://msdn.microsoft.com/en-us/library/bb299886.aspx](http://msdn.microsoft.com/en-us/library/bb299886.aspx)

jQuery.getJSON()
[http://api.jquery.com/jQuery.getJSON/#urldatacallback](http://api.jquery.com/jQuery.getJSON/#urldatacallback)

ASP.NET的JSON日期轉換
[http://blog.darkthread.net/blogs/darkthreadtw/archive/2010/04/21/asp-net-json.aspx](http://blog.darkthread.net/blogs/darkthreadtw/archive/2010/04/21/asp-net-json.aspx)<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>