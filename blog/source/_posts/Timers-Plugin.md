---
title: Timers Plugin
tags:
  - jQuery
date: 2009-05-19 23:56:00
---

一般的方式是使用Javascript的原生計時器函式clearInterval、clearTimeout、setInterval、setTimeout，不過原生函式在使用上不太直覺，而且無法快速的指定套用在某個特定的網頁元素，另外他的間隔單位是以毫秒去計算(1秒=1000毫秒)，嗯…我想要每5分鐘做一次，那我要設定…60*60*1000=3600000秒…對吧？還是360000秒？這時候快從哆啦B夢口袋拿出了JQuery Timers這個法寶就能解決這麻煩的問題。

JQuery Timers提供了三個函式

1\. everyTime(時間間隔, [計時器名稱], 函式名稱, [次數限制], [等待函式程序完成])
2\. oneTime(時間間隔, [計時器名稱], 呼叫的函式)
3\. stopTime ([計時器名稱], [函式名稱])

官方雖然有Demo，但是卻沒有列出使用的原始碼，即便右鍵檢視原始碼，裡面也沒有完整針對每一種情況寫出一組程式說明，所以我只好試著測試函式了。以下為測試程式報告：

/*************************************************************
* everyTime(時間間隔, [計時器名稱], 函式名稱, [次數限制], [等待函式程序完成])
*************************************************************/
//每1秒執行函式test()
function test(){
//do something...
}
$('body').everyTime('1s',test);

//每1秒執行
$('body').everyTime('1s',function(){
//do something...
});

//每1秒執行，並命名計時器名稱為A
$('body').everyTime('1s','A',function(){
//do something...
});

//每20秒執行，最多5次，並命名計時器名稱為B
$('body').everyTime('2das','B',function(){
//do something...
},5);

//每20秒執行，無限次，並命名計時器名稱為C
//若時間間隔抵到，但函式程序仍未完成則需等待執行函式完成後再繼續計時
$('body').everyTime('2das','C',function(){
//執行一個會超過20秒以上的程式
},0,true);

/***********************************************************
* oneTime(時間間隔, [計時器名稱], 呼叫的函式)
***********************************************************/
//倒數10秒後執行
$('body').oneTime('1das',function(){
//do something...
});

//倒數100秒後執行，並命名計時器名稱為D
$('body').oneTime('1hs','D',function(){
//do something...
});

/************************************************************
* stopTime ([計時器名稱], [函式名稱])
************************************************************/
//停止所有的在$('body')上計時器
$('body').stopTime ();

//停止$('body')上名稱為A的計時器
$('body').stopTime ('A');

//停止$('body')上所有呼叫test()的計時器
$('body').stopTime (test);

如果你試著打開他的原始碼，你可以發現下列這段程式碼，正是時間間隔的字串縮寫，所以我們也可以自訂自己所需要的縮寫字串，像是分，時之類的

// Yeah this is major overkill...
'ms': 1,
'cs': 10,
'ds': 100,
's': 1000,
'das': 10000,
'hs': 100000,
'ks': 1000000,
//自訂單位
'm': 60000,
'h': 360000

另外該作者也在網頁的開頭說明，他將程式碼移至jQuery區來做統一發佈管理，所以如果要下載該作者較新版的程式碼，請到http://plugins.jquery.com/project/timers 這邊下載，目前我所見到的是1.1.2版。

引用自 : [http://doublekai.org/blog/?p=774](http://doublekai.org/blog/?p=774)<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>