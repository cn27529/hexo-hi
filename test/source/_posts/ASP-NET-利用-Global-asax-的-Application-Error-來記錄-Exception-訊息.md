---
title: ASP.NET 利用 Global.asax 的 Application_Error 來記錄 Exception 訊息
tags:
  - ASP.NET
  - 'C#'
  - Windows 相關
date: 2009-11-09 17:29:00
---

利用 windows 的事件記錄器替我們做好記錄

錄網頁Exception訊息的方法有多種..在此介紹三種儲存方式...
1.記錄在事件檢視器裡
2.記錄在文字檔裡
3.用Email寄出訊息

1\. 於應用程式中建立 global.asax , 在 application_error 事件中加入下列 

void Application_Error(object sender, EventArgs e)
{

string Message = "";
Exception ex = Server.GetLastError();
Message = "發生錯誤的網頁:{0}錯誤訊息:{1}堆疊內容:{2}";
Message = String.Format(Message, Request.Path + Environment.NewLine, ex.GetBaseException().Message + Environment.NewLine, Environment.NewLine + ex.StackTrace);

//寫入事件撿視器,方法一
System.Diagnostics.EventLog.WriteEntry("WebAppError", Message, System.Diagnostics.EventLogEntryType.Error);

//寫入文字檔,方法二
System.IO.File.AppendAllText(Server.MapPath(string.Format("Log\\{0}.txt", DateTime.Now.Ticks.ToString())), Message);

//寄出Email,方法三
//此方法請參考System.Net.Mail.MailMessage

//清除Error
Server.ClearError();

Response.Write("系統錯誤,請聯絡系統管理員!!");

}

2\. 於一個新網頁中加入, 產生一個Null Exception 錯誤
protected void Page_Load(object sender, EventArgs e)
{
throw (new ArgumentNullException());
}

3\. 事件檢視器內容

<div class="separator" style="clear: both; text-align: center;">[![](http://3.bp.blogspot.com/_H5b1_vBT2Kw/SvfgJOm5lxI/AAAAAAAAA5s/dH7RQCaSw_w/s640/imgc01+2009.11.09+17.24.46.gif)](http://3.bp.blogspot.com/_H5b1_vBT2Kw/SvfgJOm5lxI/AAAAAAAAA5s/dH7RQCaSw_w/s1600-h/imgc01+2009.11.09+17.24.46.gif)
</div>

![](http://3.bp.blogspot.com/_H5b1_vBT2Kw/SvfgJOm5lxI/AAAAAAAAA5s/dH7RQCaSw_w/s640/imgc01+2009.11.09+17.24.46.gif)

4\. 文字內容

<div class="separator" style="clear: both; text-align: center;">[![](http://2.bp.blogspot.com/_H5b1_vBT2Kw/SvfgzKFoEcI/AAAAAAAAA50/uRyjPpz0X2E/s400/imgc02+2009.11.09+17.28.41.gif)](http://2.bp.blogspot.com/_H5b1_vBT2Kw/SvfgzKFoEcI/AAAAAAAAA50/uRyjPpz0X2E/s1600-h/imgc02+2009.11.09+17.28.41.gif)
</div>

5\. 完成了 , 收工~~*-*

參考來源 : 
http://www.dotblogs.com.tw/puma/archive/2008/08/31/5260.aspx
http://www.blueshop.com.tw/board/show.asp? subcde=BRD20080822113331G86&amp;fumcde=FUM20041006161839LRJ
http://support.microsoft.com/kb/306355/zh-tw<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>