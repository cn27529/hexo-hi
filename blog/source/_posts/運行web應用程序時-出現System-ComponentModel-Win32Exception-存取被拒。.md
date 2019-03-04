---
title: '運行web應用程序時, 出現System.ComponentModel.Win32Exception: 存取被拒。'
tags:
  - ASP.NET
  - Windowns Service
  - Windows 相關
date: 2011-05-30 16:56:00
---

前幾天在撰寫一個web應用程序，而這個程序必需控制本地服務，當我在開發環境建置好之後，進行了初級測試，已確認沒有問題後，將它部署到伺服器，這時候該死的主機，給了我一個 System.ComponentModel.Win32Exception: 存取被拒 的訊息，拜訪G老師之後，有多項方法，有人說變更本地服務的登入方式：

**[解1]**
系統預設不允許從 IIS 執行 Windows應用程式，你可以從：系統管理工具 &gt; 服務 &gt; 找到 IIS Admin &gt; 內容 &gt; 登入 &gt; 勾選:允許服務與桌面互動 &gt; 動新啟動 IIS Admin，<span class="Apple-style-span" style="color: red;">對我來說是沒用的</span>。=_=(汗)

**[解2]**
1\. 設置一名為 asp.net.location 的使用者，設置密碼，給予它 administrators 群組。
2.在 web.config&nbsp;的 &lt;system.web&gt;&nbsp;區段，設置了
&lt;identity impersonate="true" userName="asp.net.location" password="你猜不到"/&gt;

它運行了，收工。

引自:&nbsp;http://tw.myblog.yahoo.com/jw!tDIPLkOYGRkpiFM3mV462TU-/article?mid=509&amp;next=475&amp;l=f&amp;fid=15<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>