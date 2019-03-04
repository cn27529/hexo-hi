---
title: 'Django 使用 static (CSS, images)'
tags:
  - CSS3
  - Django
  - HTML
  - Python
date: 2015-10-14 17:57:00
---

1.開啟 settings.py

2.確認 INSTALL_APPS 的區塊已加入, 如下

INSTALLED_APPS = (
&nbsp; &nbsp; <span style="color: red;">'django.contrib.staticfiles',</span>
)

3.確認 settings.py 已加入, 如下

STATIC_URL = '/static/'
STATICFILES_DIRS = (
&nbsp; &nbsp; os.path.join(BASE_DIR, "static"),
)

4\. 在你的網頁中宣告與加入

<span style="color: red;">{% load staticfiles %}</span>
&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;
&nbsp; &nbsp; &lt;meta charset="UTF-8"&gt;
&nbsp; &nbsp; &lt;title&gt;&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
&nbsp; &nbsp; <span style="color: red;">&lt;img src="{% static "img/helloworld.jpg" %}" alt="My image"/&gt;</span>
&lt;/body&gt;
&lt;/html&gt;

5.執行
<div class="separator" style="clear: both; text-align: center;"></div><div class="separator" style="clear: both; text-align: center;">[![](https://1.bp.blogspot.com/-U5hWDLxjpf0/Vh4mChLCVsI/AAAAAAAAIrI/YV2CA6yXGTg/s400/img_35%2B20151014%2B17.51.jpg)](http://1.bp.blogspot.com/-U5hWDLxjpf0/Vh4mChLCVsI/AAAAAAAAIrI/YV2CA6yXGTg/s1600/img_35%2B20151014%2B17.51.jpg)</div>

6.收工

<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>