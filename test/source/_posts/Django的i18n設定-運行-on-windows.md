---
title: 'Django的i18n設定, 運行 on windows'
tags:
  - Django
  - i18n
  - Python
  - Windows 相關
  - 軟体應用相關
date: 2015-09-07 14:48:00
---

來講一下多國語言i18n這個套件, 在Django的環境下如何運作與執行呢?
今天介紹的是在windows下的操作

在進行i18n項目前, 我們先來確認你的Django環境的幾件事情

1\. setting.py已設定了MIDDLEWARE_CLASSES
一定要有這兩行, 沒有就加上去吧
<div class="separator" style="clear: both; text-align: center;">[![](http://2.bp.blogspot.com/-wHLPwDqy0BQ/Ve01h7Lk2AI/AAAAAAAAIeE/xZu1GeH6cuY/s1600/img_18%2B20150907%2B14.55.jpg)](http://2.bp.blogspot.com/-wHLPwDqy0BQ/Ve01h7Lk2AI/AAAAAAAAIeE/xZu1GeH6cuY/s1600/img_18%2B20150907%2B14.55.jpg)</div>
2.USE_I18N, USE_L10N, USE_TZ 要設True
<div class="separator" style="clear: both; text-align: center;">[![](http://1.bp.blogspot.com/-UUyPYC5f-jw/Ve02TymAB6I/AAAAAAAAIeM/lSXrpNbJt4c/s1600/img_19%2B20150907%2B15.00.jpg)](http://1.bp.blogspot.com/-UUyPYC5f-jw/Ve02TymAB6I/AAAAAAAAIeM/lSXrpNbJt4c/s1600/img_19%2B20150907%2B15.00.jpg)</div>
3.加入locale設定
<div class="separator" style="clear: both; text-align: center;">[![](http://4.bp.blogspot.com/-0KOpDyMEZbs/Ve04UY9os1I/AAAAAAAAIeU/1U-GoLjXZi4/s1600/img_20%2B20150907%2B15.08.jpg)](http://4.bp.blogspot.com/-0KOpDyMEZbs/Ve04UY9os1I/AAAAAAAAIeU/1U-GoLjXZi4/s1600/img_20%2B20150907%2B15.08.jpg)</div>
接下來, 安裝需要的東西了

4\. 去[這裡下載](http://mlocati.github.io/gettext-iconv-windows/), 把裝起來
<div class="separator" style="clear: both; text-align: center;">[![](http://1.bp.blogspot.com/-RKR0ahYOKPQ/Ve05KZk0I4I/AAAAAAAAIec/KzKBw9Sljsg/s1600/img_21%2B20150907%2B15.12.jpg)](http://1.bp.blogspot.com/-RKR0ahYOKPQ/Ve05KZk0I4I/AAAAAAAAIec/KzKBw9Sljsg/s1600/img_21%2B20150907%2B15.12.jpg)</div>

5.設定gettext &amp; iconv環境變數, 這是之後下指命時會使用到
<div class="separator" style="clear: both; text-align: center;">[![](http://2.bp.blogspot.com/-w44XcJyFBKQ/Ve05xBojxTI/AAAAAAAAIek/UHIlVSmnDGo/s1600/img_22%2B20150907%2B15.14.jpg)](http://2.bp.blogspot.com/-w44XcJyFBKQ/Ve05xBojxTI/AAAAAAAAIek/UHIlVSmnDGo/s1600/img_22%2B20150907%2B15.14.jpg)</div>

6.在你的Django工作區建立locale資料夾, 這是存放語言檔案用的地方, 是建立在manage.py同一層目錄中.
<div class="separator" style="clear: both; text-align: center;">[![](http://2.bp.blogspot.com/-pGyCSNaiqV8/Ve06rV_SotI/AAAAAAAAIew/5V1uH-qYqjY/s1600/img_23%2B20150907%2B15.18.jpg)](http://2.bp.blogspot.com/-pGyCSNaiqV8/Ve06rV_SotI/AAAAAAAAIew/5V1uH-qYqjY/s1600/img_23%2B20150907%2B15.18.jpg)</div>

7.在你templates的檔案加入{% load i18n %}的宣告
7-1在你templates的檔案需要被翻譯文字的地方加入{% trans "Hello World" %}

<div class="separator" style="clear: both; text-align: center;">[![](http://1.bp.blogspot.com/-fw316Buc9Oc/Ve07mTJuMSI/AAAAAAAAIe8/f9ChIVG8H3I/s1600/img_24%2B20150907%2B15.21.jpg)](http://1.bp.blogspot.com/-fw316Buc9Oc/Ve07mTJuMSI/AAAAAAAAIe8/f9ChIVG8H3I/s1600/img_24%2B20150907%2B15.21.jpg)</div>

8.上面1~7都沒問題後, 執行命令, 產生多國語言的django.po檔案
我這裡是泰文 是使用th為代碼
<div class="separator" style="clear: both; text-align: center;">[![](http://4.bp.blogspot.com/-1VbUeQLz1xM/Ve09d0RTjPI/AAAAAAAAIfI/G_48cA9IupE/s1600/img_25%2B20150907%2B15.30.jpg)](http://4.bp.blogspot.com/-1VbUeQLz1xM/Ve09d0RTjPI/AAAAAAAAIfI/G_48cA9IupE/s1600/img_25%2B20150907%2B15.30.jpg)</div>

9.來編輯這個th的django.po的檔案, msgstr的值填上
<div class="separator" style="clear: both; text-align: center;">[![](http://1.bp.blogspot.com/-gAhtpXAyG6M/Ve09-aukikI/AAAAAAAAIfQ/nnxIFdEeGX0/s1600/img_26%2B20150907%2B15.32.jpg)](http://1.bp.blogspot.com/-gAhtpXAyG6M/Ve09-aukikI/AAAAAAAAIfQ/nnxIFdEeGX0/s1600/img_26%2B20150907%2B15.32.jpg)</div>

10.執行命令, 將django.po的檔案, 轉成二進位
我使用了中, 日, 英, 韓, 泰, 五種語言
<div class="separator" style="clear: both; text-align: center;">[![](http://2.bp.blogspot.com/-7x5GuDkPm5I/Ve0-8Asf8KI/AAAAAAAAIfc/y3THHn8uiT0/s1600/img_27%2B20150907%2B15.37.jpg)](http://2.bp.blogspot.com/-7x5GuDkPm5I/Ve0-8Asf8KI/AAAAAAAAIfc/y3THHn8uiT0/s1600/img_27%2B20150907%2B15.37.jpg)</div>

11.啟動django web server
<div class="separator" style="clear: both; text-align: center;">[![](http://2.bp.blogspot.com/-DkNoh5I5U8M/Ve0_uCnD4oI/AAAAAAAAIfk/gs_GF_oHkPM/s1600/img_28%2B20150907%2B15.39.jpg)](http://2.bp.blogspot.com/-DkNoh5I5U8M/Ve0_uCnD4oI/AAAAAAAAIfk/gs_GF_oHkPM/s1600/img_28%2B20150907%2B15.39.jpg)</div>

12.檢視一下成果
日文
<div class="separator" style="clear: both; text-align: center;">[![](http://1.bp.blogspot.com/-4zBGY_tAeJs/Ve1AndLVLlI/AAAAAAAAIfs/aK6UBDbhHyM/s640/img_29%2B20150907%2B15.44.jpg)](http://1.bp.blogspot.com/-4zBGY_tAeJs/Ve1AndLVLlI/AAAAAAAAIfs/aK6UBDbhHyM/s1600/img_29%2B20150907%2B15.44.jpg)</div>
英文
<div class="separator" style="clear: both; text-align: center;">[![](http://4.bp.blogspot.com/-nE2PAylIZEU/Ve1A-Zat6oI/AAAAAAAAIf0/kP_D_wxlhk8/s640/img_30%2B20150907%2B15.45.jpg)](http://4.bp.blogspot.com/-nE2PAylIZEU/Ve1A-Zat6oI/AAAAAAAAIf0/kP_D_wxlhk8/s1600/img_30%2B20150907%2B15.45.jpg)</div>
韓文
<div class="separator" style="clear: both; text-align: center;">[![](http://4.bp.blogspot.com/-1BdQmlmzdfQ/Ve1BSMwWroI/AAAAAAAAIf8/iUkyanKIbL8/s640/img_31%2B20150907%2B15.46.jpg)](http://4.bp.blogspot.com/-1BdQmlmzdfQ/Ve1BSMwWroI/AAAAAAAAIf8/iUkyanKIbL8/s1600/img_31%2B20150907%2B15.46.jpg)</div>
泰文
<div class="separator" style="clear: both; text-align: center;">[![](http://3.bp.blogspot.com/-FWB59pDnnT8/Ve1BW9zpLfI/AAAAAAAAIgE/yusdjJXSYYk/s640/img_32%2B20150907%2B15.47.jpg)](http://3.bp.blogspot.com/-FWB59pDnnT8/Ve1BW9zpLfI/AAAAAAAAIgE/yusdjJXSYYk/s1600/img_32%2B20150907%2B15.47.jpg)</div>

13.收工

<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>