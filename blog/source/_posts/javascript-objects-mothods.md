---
title: javascript objects & mothods
tags:
  - javascript
date: 2009-02-16 16:49:00
---

alert(msg) //彈出 alert 對話框
confirm(msg) //彈出 confirm 對話框, 使用者按"OK"回傳true, 按"cancel"回傳false
prompt(msg, [defaultValue]) //彈出 prompt 字串輸入框

arguments //參數陣列
prototype //new 出來的物件可指定 prototype

parseInt() //轉型成整數
parseFloat() //轉型成浮點數

escape(string) //將字串轉成url編碼
unescape(string) //將url編碼轉回字串

String 物件:
toLowerCase() //字串轉為小寫
toUpperCase() //字串轉為大寫
charAt(i) //字串的第 i 個字元(由 0 開始)
charCodeAt(i) //字串的第 i 個字元(由 0 開始)的 Unicode 字碼
indexOf(string, i) //搜尋(第 i 個) string 字串的起始索引, 沒找到則傳回-1
lastIndexOf(string) //從最後面開始搜尋字串起始索引, 沒找到則傳回-1
match(string) //若字串包含該 string 則回傳, 若否則為 null (正規表示)
search(string) //同 indexOf(string) (正規表示)
replace(str1, str2) //將字串中所有的 str1 更換成 str2
split(string) //將字串以 string 為分割符號做切割, 回傳的是 Array
subStr(i , length) //從第 i 個字元擷取 length 個字做為字串回傳
subString(i1 , i2) //從第 i1 個字元擷取到(不含)第 i2 個字元做為字串回傳
concat(string) //字串相加, 需搭配 assignment

Array 物件:
join(separator) //將 array 輸出成字串並以 separator 分隔
reverse() //字串索引反轉
sort() //排序
concat(array) //合併

Math 物件:
常數屬性:
E / LN2 / LN10 / LOG2E / LOG10E / PI / SQRT1_2 / SQRT2
方法:
max(value1, value2) //傳回較大值
min(value1, value2) //傳回較小值
random() //0~1的亂數
round() //四捨五入
floor() //無條件捨去
ceil() //無條件進位
pow() //次方
sqrt() //平方根
abs() //絕對值
exp() //自然數指數 ex
log() //自然對數
sin() / cos() / tan() / asin() / acos() / atan() //三角函數

Date 物件:
getTimezoneOffset() //傳回本地時間與 GMT 時間差, 分為單位
toGMTString() //傳回轉成 GMT 時間的字串
toLocalString() //傳回轉成本地時間的字串
parse(Date) //傳回 1970年1月1日至本地時間 Date 的毫秒數(類別方法)
UTC(Date) //傳回 1970年1月1日至 GMT 時間 Date 的毫秒數(類別方法)
getDate() / setDate()
getDay() / setDay()
getMonth() / setMonth()
getFullYear() / setFullYear()
getYear() / setYear()
getHours() / setHours()
getMinutes() / setMinutes()
getSeconds() / setSeconds()
getMilliseconds() / setMilliseconds()
getTime() / setTime() //1970年1月1日至今的秒數<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>