---
title: 無法寫入輸出檔  Temporary ASP.NET Files
tags:
  - ASP.NET
  - IIS
date: 2015-08-26 10:31:00
---

此症頭常出現在WIN7

解法

C:\WINDOWS\TEMP 目錄

加入讀寫權限：
NETWORK SERVICE用户
IUSER用户
IIS_USER用户

C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Temporary ASP.NET Files 目錄

加入讀寫權限：
NETWORK SERVICE用户
IUSER用户
IIS_USER用户

停用IIS
<div class="separator" style="clear: both; text-align: center;">[![](https://2.bp.blogspot.com/-Pg7-yrnYtjE/ViRVdtmD2MI/AAAAAAAAIs4/W9pFhDanxv0/s1600/img_16%2B20151019%2B10.23.jpg)](http://2.bp.blogspot.com/-Pg7-yrnYtjE/ViRVdtmD2MI/AAAAAAAAIs4/W9pFhDanxv0/s1600/img_16%2B20151019%2B10.23.jpg)</div>

移除 Temporary ASP.NET Files 目錄內所有檔案

重啟IIS
<div class="separator" style="clear: both; text-align: center;">[![](https://4.bp.blogspot.com/-4G_SPlxGcYQ/ViRVhMY46-I/AAAAAAAAItE/IJmnXEj6Uwo/s1600/img_17%2B20151019%2B10.27.jpg)](http://4.bp.blogspot.com/-4G_SPlxGcYQ/ViRVhMY46-I/AAAAAAAAItE/IJmnXEj6Uwo/s1600/img_17%2B20151019%2B10.27.jpg)</div>

若還是不能解，開啟IIS管理員，執行下面改成True
<div class="separator" style="clear: both; text-align: center;">[![](https://3.bp.blogspot.com/-reth3x9GjBE/ViRVjBfb8hI/AAAAAAAAItM/K5cqQ89H3SQ/s1600/img_15%2B20151019%2B10.15.jpg)](http://3.bp.blogspot.com/-reth3x9GjBE/ViRVjBfb8hI/AAAAAAAAItM/K5cqQ89H3SQ/s1600/img_15%2B20151019%2B10.15.jpg)</div>
收工。

<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>