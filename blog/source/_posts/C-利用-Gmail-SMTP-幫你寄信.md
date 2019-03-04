---
title: 'C# - 利用 Gmail SMTP 幫你寄信'
tags:
  - ASP.NET
  - 'C#'
date: 2009-05-10 00:59:00
---

只要有 Gmail 個人帳號與密碼，透過 Gmail SMTP SSL 的認證，Gmail 就可以幫助你寄信囉！
該程式利用 [MailAddress](http://msdn2.microsoft.com/zh-tw/library/system.net.mail.mailaddress_members(VS.80).aspx "MailAddress") 建立收發信人的郵件位址，[MailMessage](http://msdn2.microsoft.com/zh-tw/library/system.net.mail.mailmessage_members(VS.80).aspx "MailMessage") 建立郵件相關內容，[SmtpClient](http://msdn2.microsoft.com/zh-tw/library/system.net.mail.smtpclient_members(VS.80).aspx "SmtpClient") 與 [NetworkCredential](http://msdn2.microsoft.com/zh-tw/library/system.net.networkcredential.networkcredential(vs.80).aspx "NetworkCredential") 建立 Smtp 連線認證與寄信功能。<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>