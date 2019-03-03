---
title: 'Django 的虛擬環境 VENV, 使用的基本指令'
tags:
  - Django
  - Mac
  - Python
date: 2015-10-19 12:14:43
---

VENV是簡稱，全名是Virtualenv
進入VENV環境
**Windows**
C:\Users\YOUR_NAME\djangogirls&gt; VENV\Scripts\activate 
**Linux / OS X**
~/djangogirls$ . VENV/bin/activate 
<table css="tb"><thead><tr><th style="width: 50%;">指令</th><th style="width: 50%;">說明</th></tr></thead><tbody><tr><td>django-admin.py **startproject** _`&lt;project_name&gt;`_</td><td>建立 django 專案</td></tr><tr><td>python manage.py **-h** _`&lt;command_name&gt;`_</td><td>查看 django command 的使用方法</td></tr><tr><td>python manage.py **runserver**</td><td>啟動開發伺服器</td></tr><tr><td>python manage.py **startapp** _`&lt;app_name&gt;`_</td><td>新增 django app</td></tr><tr> </tr><tr><td>python manage.py **migrate**</td><td>migrate 指令會根據INSTALLED_APPS的設定，按照 app 順序建立或更新資料表，將你在 models.py 裡的更新跟資料庫同步。 </td></tr><tr><td>python manage.py **makemigrations**</td><td>如果你不是第一次執行migrate，在此之前需要先執行 makemigrations： 這個指令會根據你對 Model 的修改刪除建立一個新的 migration 檔案，讓migrate指令執行時，可以照著這份紀錄更新資料庫。 </td></tr><tr><td>python manage.py **shell**</td><td>使用 shell 指令，進入 Django Shell， 這個 shell 和我們之前輸入 python 執行的 shell 長得一樣，只是它會預先為我們設定 Django 需要的環境，方便我們執行 Django 相關的程式。 </td></tr><tr><td>python manage.py **createsuperuser**</td><td>建立Django 的管理後台的 superuser 確認 you_project/urls.py 中的 urlpatterns 包含下面這行 url(r'^admin/', include(admin.site.urls)), </td></tr></tbody></table><style>.tb{ width:100%; border: 1px solid #cccccc; } th{ border: 1px solid #cccccc; } td{ height:30px; padding:7px; } </style><div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>