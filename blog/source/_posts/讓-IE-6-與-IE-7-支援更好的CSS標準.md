---
title: 讓 IE 6 與 IE 7 支援更好的CSS標準
tags:
  - CSS3
  - HTML
  - IE
date: 2009-10-26 05:10:00
---

長期以來，網頁設計師對於IE牛步更新對CSS的支援一直感到很無力，雖然IE8開始對於CSS支援有所進步，但是不可能要求每個使用者都去更新為IE8，也因此，這是寫程式的人一直感到很無力的地方。

幸好，在百書爭鳴的圖書館，發現一本「碼上就用CSS」，而在這本書中，讓海芋從中學到IE6支援比較新的CSS語法的方法了。

在 &lthead> 前加入以下程式碼。

&lt !-- if lt IE 8 -->
&ltscript src="http://ie7-js.googlecode.com/svn/version/2.0(beta3)/IE8.js" type="text/javascript" />
&lt !-- endif -->

原文連結：http://www.inote.tw/2007/09/goodbye-ie6goodbye-suck-css.html<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>