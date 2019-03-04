---
title: 'jQuery 外掛特輯 :Query String Object-GET參數的取得與設定'
tags:
  - jQuery
date: 2010-03-24 15:46:00
---

Sever side程式語言通常都會有用來處理Query String的類別或方法，像是PHP可以透過$_GET['key']取得對應的值。而C#也可以用Request.QueryString["key"]的方式取得對應的值。 

但是在Client端的javascript卻沒有如此方便的方法可以使用，所幸在jQuery流行的現在，我們可以從網路上找到一些jQuery外掛可以方便的處理Query String。以下我找到了三個外掛，分別是： 
[jqURL](http://www.oakcitygraphics.com/jquery/jqURL/jqURLdemo.html?var1=1&amp;var2=2&amp;var3=3) 
[getUrlParam](http://www.mathias-bank.de/2007/04/21/jquery-plugin-geturlparam-version-2/) 
[Query String Object](http://plugins.jquery.com/project/query-object) 

我選擇使用Query String Object，做為我的開發工具，因為從jQuery Plugin專案頁面上日期顯示，作者依然有持續在維護這個專案，最後一次release是在2009-10-16感覺似乎比較可靠(？)。 

接下來我簡單說明一下如何使用這個外掛取得網址的GET參數。 

如果現在有一串這樣的網址 
http://www.url.com/test.php?id=12&amp;num=20&amp;name=finalevil 
你可以透過下列語法取得對應的GET參數 

var str = $.query.get('id');

如此一來，取得的數值存入str變數中，所以str變數的值即為12 

除了取得GET參數，此外掛當然也可以用來設定GET參數，否則只能取得不能設定未免也太遜了吧XD 

var newUrl = $.query.set("id", 22).set("num", "100").toString();

這樣設定以後newUrl變數中的字串就是?id=22&amp;num=100 
另外，你可以呼叫Remove方法，移除GET參數中的某個數值，像這樣： 
如果現在有一串這樣的網址 http://www.url.com/test.php?id=12&amp;num=20&amp;name=finalevil 

var newUrl = $.query.REMOVE("id");

&nbsp;呼叫REMOVE方法，移除參數id，這個時候的newUrl為 
?num=20&amp;name=finalevil 
以上簡單介紹了這個外掛最重要的三個方法，get、set、REMOVE，供大家參考。

來源文章 [http://blog.finalevil.com/2009/10/jquery08query-string-object.html](http://blog.finalevil.com/2009/10/jquery08query-string-object.html)<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>