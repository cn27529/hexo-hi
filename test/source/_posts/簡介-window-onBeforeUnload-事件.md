---
title: 簡介 window.onBeforeUnload 事件
tags:
  - HTML
  - javascript
date: 2009-05-18 20:47:00
---

在 Gmail 中如果採用<span style="color:#ff6666;">另開視窗模式</span>撰寫信件時，在隨意填寫一些文字後按下視窗右上角的關閉按鈕，會先出現以下警告視窗： 這是利用 onBeforeUnload 事件來完成的，目的在避免使用者操作錯誤時，使得他所輸入的文字付諸流水。
以下是模擬的方式：

&lt;!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
&lt;html xmlns="http://www.w3.org/1999/xhtml">
&lt;head>
&lt;meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
&lt;title>TEST&lt;/title>
&lt;/head>
&lt;body>
&lt;script type="text/javascript">
window.onbeforeunload = function () {
if (!confirm('您的郵件尚未寄出，\n您要捨棄此郵件嗎？')) {
return '按一下「取消」停留在此頁。';
}
}
&lt;/script>
&lt;/body>
&lt;/html>

目前只有 Firefox 和 IE 支援 onBeforeUnload 事件， Opera 到 9.20 版為止都尚無支援。觸發的時機如下：

*   關閉瀏覽器視窗。
*   通過網址列或書籤 (我的最愛) 導向其他頁面。
*   點選上一頁、下一頁，重新整理，首頁等其中一個功能。
*   點選一個前往其他頁面的 URL 連結。
*   觸發或呼叫以下任意一個事件：

    *   onclick
    *   document.write()
    *   document.open()
    *   document.close()
    *   window.close()
    *   window.navigate()
    *   window.NavigateAndFind()
    *   location.replace()
    *   location.reload()
    *   form.submit()

*   利用 window.open() 打開一個頁面，並把本頁的 window 的名字傳給要打開的頁面。
*   重新賦予 location.href 的值。
*   透過 input type=&quot;submit&quot; 按鈕提交一個具有指定 action 的表單的時候。

註：以上改自[陳澤|SurfChen::onbeforeunload 事件](http://www.surfchen.org/?p=54)。
<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>