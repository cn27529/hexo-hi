---
title: 突破XP IIS連線數10的限制
tags:
  - ASP.NET
  - Windows 相關
  - 軟体應用相關
date: 2011-08-23 18:29:00
---

可以少量的增加連線數到達極限數40。
請在console模式中，切換到C:\Inetpub\AdminScripts\資料夾。
<span class="Apple-style-span" style="color: red;">CD C:\Inetpub\AdminScripts</span>

然後輸入以下指令來增加連數。
<span class="Apple-style-span" style="color: red;">cscript adsutil.vbs set w3svc/MaxConnections 40</span>

最後，我們可以下達以下指令來重新啟動IIS。
<span class="Apple-style-span" style="color: red;">iisreset</span>

可不可以把40改成更大的數目，以取得更多連線數？ 

答案是否定的！超過40，一律視為10；對，就是10而已！

引自: http://www.shunze.info/forum/thread.php?threadid=1324&amp;boardid=5&amp;sid=6d36c9b16d57d38a50cf27698afa96f0&amp;sid=6d36c9b16d57d38a50cf27698afa96f0<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>