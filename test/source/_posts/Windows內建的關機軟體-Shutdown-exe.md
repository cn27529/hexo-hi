---
title: Windows內建的關機軟體(Shutdown.exe)
tags:
  - Command line
  - Windows 相關
date: 2010-11-16 18:28:00
---

找Windows用的關機軟體嗎？免下載，Windows XP之後的版本就有內建囉！
Shutdown是一支Windows內建的關機小程式，沒想到它除了命令列模式之外，也有圖形化界面。命令列模式的參數可以輸入 shutdown /? 來顯示。

**使用方式說明**: 
shutdown [-i | -l | -s | -r | -a] [-f] [-m \\computername] [-t xx]
&nbsp;[-c "comment"] [-d up:xx:yy]

&nbsp;&nbsp; &nbsp; &nbsp; &nbsp;沒有引數 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;顯示這個訊息 (和 -? 相同)
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp;-i &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;顯示 GUI 介面，必須是第一個選項
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp;-l &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;登出 (不能和 -m 選項一起使用)
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp;-s &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;電腦關機
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp;-r &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;關機並重新啟動電腦
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp;-a &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;中止系統關機
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp;-m \\\\computername &nbsp; &nbsp; 從遠端進行關機/重新啟動/中止
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp;-t xx &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 將關機等候時間設定成 xx 秒
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp;-c "comment" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;關機註解 (最多 127 個字元)
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp;-f &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;強制關閉執行中的應用程式，不顯示警告
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp;-d [u][p]:xx:yy &nbsp; &nbsp; &nbsp; &nbsp; 關機原因代碼
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;u 是使用者代碼
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;p 是預先計劃的關機代碼
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;xx 是主要原因代碼 (小於 256 的正整數)
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;yy 是次要原因代碼 (小於 65536 的正整數)

**範例**:

shutdown -c "AotoResetComputer" -r -f -t 5

1.關機註解: -c "AotoResetComputer"
2.關機並重新啟動電腦: -r
3.強制關閉執行中的應用程式，不顯示警告: -f
4.將關機等候時間設定成5秒: -t 5

引自:&nbsp;[http://blog.soft.idv.tw/?p=216](http://blog.soft.idv.tw/?p=216)<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>