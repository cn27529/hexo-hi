---
title: 在 Frameset 中 Session 遺失
tags:
  - ASP.NET
  - IIS
  - Windows 相關
  - 瀏覽器
date: 2012-04-20 18:35:00
---

今天的問題是
1\. 我有一個A網站, 及B網站
2\. 在A站裡頭有個A網頁使用 Frameset, 連結了B站的B網頁
3\. 透過A站的A頁的Frameset連結B站的B頁
4\. B頁進行了Session的儲存
5\. B頁執行轉向到B站的C頁時, 發現C頁取不到Session值了

苦惱, 爬了一下文發現了 <span style="color: red;">P3P: CP="CAO PSA OUR"</span> 這個東西, 不知這東西是什麼鬼
加了這東西, 竟然好了, 趕快記下來

<span style="background-color: white; color: blue;">症頭</span>
在IE瀏覽器內無法正常取得Session值，但在Firefox內卻可以正常的取出該Session值。

<span style="color: blue;">處理參考一</span> ( 在ASP程式內標頭加入下面語法 )
response.expires = 0
response.expiresabsolute = Now() - 1
response.addHeader "pragma","no-cache"
response.addHeader "cache-control","private"
response.addHeader "P3P","CP='CAO PSA OUR'"
response.CacheControl = "no-cache"

<span style="color: blue;">處理參考二</span> ( 在IIS內設定 [HTTP表頭] )
1\. 按一下 [ 開始 ]、 按一下 [ 執行 ]，然後再輸入 inetmgr ]。
2\. 在 [左邊的瀏覽] 頁面按一下 [適當的檔案或目錄，在您想要新增標頭，以滑鼠右鍵按一下的檔案，然後按一下 [ 內容 您網站上]。
3\. 按一下 [ HTTP 表頭 ] 索引標籤。
4\. 在 [ 自訂 HTTP 表頭 ] 群組方塊中，按一下 [ 新增 ]。
5\. 輸入 自訂標頭名稱(C):， P3P ，然後輸入 自訂標頭值(U):， CP="CAO PSA OUR"。

引自[http://cp0501.blogspot.com/2009/11/asp-iesession.html](http://cp0501.blogspot.com/2009/11/asp-iesession.html)<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>