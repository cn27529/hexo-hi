---
title: 讓你的筆記本工具，在另存檔案時預設使用utf-8編碼
tags:
  - Windows 相關
  - 軟体應用相關
  - 軟工文件工具
date: 2012-10-15 22:32:00
---

Windows Notepad default save as utf-8
介紹如何讓windows notepad，能夠在另存檔案時預設使用為utf-8編碼。
<div>
</div><div>1\. 建立一個名為TXTUTF-8.txt文檔</div><div>
</div><div>2\. 打開TXTUTF-8.txt文檔，選擇"檔案" &gt; "另存" 為utf-8格式</div><div>
</div><div>3\. 移置C:\Windows\SHELLNEW，將TXTUTF-8.txt拷貝至此C:\Windows\SHELLNEW路徑下</div><div>
</div><div>3\. 執行cmd命令，鍵入regedit命令</div><div>
</div><div>4\. 選擇HKEY_CLASSES_ROOT找到.txt節點，在.txt下找到ShellNew。</div><div>
</div><div>5.&nbsp;點選ShellNew，在右邊的視窗中空白處，點右鍵&nbsp;新增 &gt; 字串值&nbsp;項目，將字串值的名稱命名為FileName，點選FileName按右鍵 &gt; 修改 ，填入TXTUTF-8.txt，按確定。</div><div>
</div><div>完成收工</div><div></div><div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>