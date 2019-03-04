---
title: CSS 學習路之 img src 設置
tags:
  - CSS3
  - HTML
date: 2009-10-04 23:40:00
---

前幾天試驗一個css img 的配置時, 發覺 img 連結圖示除了以 src 配置之外, 是否也可以使用css 來配置呢, 當然也是可以使用js來達到統一設定, 因為js是在client端處理所以需要消耗client的資源, 說起來也不是那麼各師其職的, 為了不讓client的工作量變多, 上網拜了G神後找到了 img src 的 css 配置方式.

1.一般(傳統)的配置方式
&ltimg src="yourPath/yourImg.jpg" />

2.css配置方式
&ltimg class="yourImg" />

&lt style>
img&nbsp;&nbsp;.yourImg{
&nbsp;&nbsp;text:expression(src="yourPath/yourImg.jpg");
}
&lt/style>

套用css樣式後源碼也乾淨許多, 所以第2種配置方式較佳.哈哈哈~<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>