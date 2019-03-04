---
title: Win32 Console指令之工作管理篇
tags:
  - Command line
  - Windows 相關
  - 軟体應用相關
date: 2011-01-10 19:12:00
---

想管理電腦正在執行的程式，用Ctrl+Alt+Del呼叫Windows工作管理員很直覺，但如果要寫個簡單的batch或script自動化，GUI反而無用武之地。

在命令提示字元試試以下的指令：**tasklist**
**
**
這道指令用來查詢有哪些程式正在執行(list processes)。
再來打開記事本小程式，
然後執行：**taskkill /f /im notepad.exe**
**
**
就可以關掉執行中的記事本。

用法很簡單，加上/?參數可以查詢完整用法。<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>