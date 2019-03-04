---
title: jquery.SerialScroll plugin 滚动图片
tags: []
date: 2009-02-10 14:54:00
---

Demo : [http://demos.flesler.com/jquery/serialScroll/](http://demos.flesler.com/jquery/serialScroll/)

Example code here :

<div class="postbody">

&lt;%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="ScrollJquery._Default" %&gt; <p>&lt;!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "[http://www.blogger.com/](http://www.blogger.com/)&gt;
&lt;html xmlns="[http://www.blogger.com/](http://www.blogger.com/)&gt;
&lt;head runat="server"&gt;
&lt;title&gt;Jquery Scroll&lt;/title&gt; <p>&lt;script type='text/javascript' src='jquery-1.2.6.min.js'&gt;&lt;/script&gt; <p>&lt;script type="text/javascript" src="jquery.scrollTo-min.js"&gt;&lt;/script&gt; <p>&lt;script type="text/javascript" src="jquery.serialScroll-min.js"&gt;&lt;/script&gt; <p>&lt;script type="text/javascript"&gt;
jQuery.easing.easeOutQuart = function (x, t, b, c, d) {
return -c * ((t=t/d-1)*t*t*t - 1) + b;
};
jQuery(function(){
$('#slideshow').serialScroll({
items:'li',
prev:'#screen2 a.prev',
next:'#screen2 a.next',
start:0, //as we are centering it, start at the 2nd
duration:2000, //auto timer , changed the image it to next image
force:true,
interval:1,
cycle:true, //don't pull back once you reach the end
jump:true,
interval:5000
});
}
);
&lt;/script&gt; <p>&lt;style type="text/css"&gt;
#screen2
{
position: relative;
width: 300px;
margin: 20px;
}
#screen2 #buttons
{
border: 1px solid #777;
margin-bottom: 5px;
width: 300px;
}
#screen2 #buttons a
{
margin: 10px 10px;
color: #69C;
}
#screen2 .prev
{
float: left;
}
#screen2 .next
{
float: right;
}
#slideshow
{
overflow: hidden;
width: 300px;
border: 1px solid #777;
}
#slideshow ul
{
width: 900px;
padding-left: 0px;
margin: 0px;
}
#slideshow li
{
float: left;
cursor: pointer;
}
&lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;form id="form1" runat="server"&gt;
&lt;div id="screen2"&gt;
&lt;div id="buttons"&gt;
&lt;a class="prev" href="#"&gt;Previous&lt;/a&gt; &lt;a class="next" href="#"&gt;Next&lt;/a&gt;
&lt;/div&gt;
&lt;div id="slideshow"&gt;
&lt;ul&gt;
&lt;li&gt;
&lt;img width="300" height="500" src="abstract_colors_Galeor.jpg" /&gt;
&lt;/li&gt;
&lt;li&gt;
&lt;img width="300" height="500" src="Palawan Island Philippines.jpg" /&gt;
&lt;/li&gt;
&lt;li&gt;
&lt;img width="300" height="500" src="Peaceful Getaway Maldives.jpg" /&gt;
&lt;/li&gt;
&lt;/ul&gt;
&lt;/div&gt;
&lt;/div&gt;
&lt;/form&gt;
&lt;/body&gt;
&lt;/html&gt;
</div><div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>