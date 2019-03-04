---
title: >-
  Install Django, create Django project and Django app.  安裝Django, 建立Django
  專案及建立 Django app
tags:
  - Django
  - MVC
  - Python
  - VM
date: 2015-07-29 14:41:00
---

已經裝好Python與設定環境變數後就可以安裝Django了，我是裝python3.4版本，如果還沒裝Python的話先去裝，這裡不說明，會直接進入Django的話題。

1.建立Python3內建的VM環境，提供Django使用，我使用的是D槽
<pre style="-webkit-font-smoothing: antialiased; -webkit-tap-highlight-color: transparent; background-color: #f7f7f7; border-radius: 3px; border: 0px; box-sizing: border-box; color: #333333; font-family: Consolas, 'Liberation Mono', Menlo, Courier, monospace; font-size: 13.6000003814697px; line-height: 1.45; margin-bottom: 16px; overflow: auto; padding: 16px; white-space: pre-wrap; word-wrap: normal;"><span style="color: black; font-family: 'Times New Roman'; font-size: small; line-height: normal; white-space: normal;">D:\Projects\Python&gt;python -m venv VM</span></pre>執行完後，python會在D:\Projects\Python&nbsp;下幫我建立一個叫VM的資料夾，這個夾是要執行python的VM用的，如圖
<div class="separator" style="clear: both; text-align: left;">[![](http://3.bp.blogspot.com/-Uy1aZThSrjA/VbhGMEtaNoI/AAAAAAAAH7I/kjFR_hYop_4/s400/img_01%2B2015-07-29%2B11.15.47.gif)](http://3.bp.blogspot.com/-Uy1aZThSrjA/VbhGMEtaNoI/AAAAAAAAH7I/kjFR_hYop_4/s1600/img_01%2B2015-07-29%2B11.15.47.gif)</div>

2.接下來，啟動VM
<pre style="-webkit-font-smoothing: antialiased; -webkit-tap-highlight-color: transparent; background-color: #f7f7f7; border-radius: 3px; border: 0px; box-sizing: border-box; color: #333333; font-family: Consolas, 'Liberation Mono', Menlo, Courier, monospace; font-size: 13.6000003814697px; line-height: 1.45; margin-bottom: 16px; overflow: auto; padding: 16px; white-space: pre-wrap; word-wrap: normal;"><span style="color: black; font-family: 'Times New Roman'; font-size: small; line-height: normal; white-space: normal;">d:\Projects\Python</span><span style="font-family: 'Times New Roman'; white-space: normal;">&gt;</span><span style="font-family: 'Times New Roman'; white-space: normal;">&nbsp;VM\Scripts\activate</span></pre>
3.<span style="background-color: white; color: #333333; font-family: 'Open Sans', 'Clear Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif; font-size: 16px; line-height: 25.6000003814697px;">如果看到前面多了</span>`(虛擬資料夾名稱)`<span style="background-color: white; color: #333333; font-family: 'Open Sans', 'Clear Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif; font-size: 16px; line-height: 25.6000003814697px;">，則表示已經成功切換至該虛擬環境</span>
<div class="separator" style="clear: both; text-align: left;">[![](http://2.bp.blogspot.com/-ovC96YMm0pI/VbhG2v9ZTtI/AAAAAAAAH7Q/Zndv7CGBcFQ/s400/img_02%2B2015-07-29%2B11.18.44.gif)](http://2.bp.blogspot.com/-ovC96YMm0pI/VbhG2v9ZTtI/AAAAAAAAH7Q/Zndv7CGBcFQ/s1600/img_02%2B2015-07-29%2B11.18.44.gif)</div>
4.接下來安裝Django
<div class="separator" style="clear: both; text-align: left;">[![](http://3.bp.blogspot.com/-o1AwA0sp2Fs/VbhHdjXSo3I/AAAAAAAAH7Y/kD5-cGEdEUg/s640/img_03%2B2015-07-29%2B11.20.35.gif)](http://3.bp.blogspot.com/-o1AwA0sp2Fs/VbhHdjXSo3I/AAAAAAAAH7Y/kD5-cGEdEUg/s1600/img_03%2B2015-07-29%2B11.20.35.gif)</div><div>Django裝好了XD</div><div>
</div>5.確認Django安裝有沒有成功，來測一下吧
<div><div class="separator" style="clear: both; text-align: left;">[![](http://1.bp.blogspot.com/-IIc7EsDrD-g/VbhKHBADgdI/AAAAAAAAH7k/PjEHzSBD8QE/s640/img_04%2B2015-07-29%2B11.32.28.gif)](http://1.bp.blogspot.com/-IIc7EsDrD-g/VbhKHBADgdI/AAAAAAAAH7k/PjEHzSBD8QE/s1600/img_04%2B2015-07-29%2B11.32.28.gif)</div><div>有回應是1.7.9的Django版本，XD
<div>
6.裝好需要的Django後，我們來建立一個Django的project
首先，使用 django-admin.py 來建立第一個 Django project名要 mysite
在VM的模式下鍵入 django-admin.py startproject mysite
<div class="separator" style="clear: both; text-align: left;">[![](http://2.bp.blogspot.com/-i7VtWW6Kq_Y/VbhOqjww_uI/AAAAAAAAH7w/HhYZaEea-SM/s640/img_06%2B2015-07-29%2B11.52.08.gif)](http://2.bp.blogspot.com/-i7VtWW6Kq_Y/VbhOqjww_uI/AAAAAAAAH7w/HhYZaEea-SM/s1600/img_06%2B2015-07-29%2B11.52.08.gif)</div>執行後如下圖，會多個mysite資料夾
<div class="separator" style="clear: both; text-align: left;">[![](http://3.bp.blogspot.com/-w23Tpuflc-U/VbhO-zrulmI/AAAAAAAAH74/grk1OCZGU0w/s400/img_05%2B2015-07-29%2B11.51.17.gif)](http://3.bp.blogspot.com/-w23Tpuflc-U/VbhO-zrulmI/AAAAAAAAH74/grk1OCZGU0w/s1600/img_05%2B2015-07-29%2B11.51.17.gif)</div><div class="separator" style="clear: both; text-align: left;">tree結構如下</div><div class="separator" style="clear: both; text-align: left;">[![](http://2.bp.blogspot.com/-6w0g3AZ5GV4/VbhQhCT29FI/AAAAAAAAH8E/ghvHDc_-GIc/s320/img_07%2B2015-07-29%2B11.58.13.gif)](http://2.bp.blogspot.com/-6w0g3AZ5GV4/VbhQhCT29FI/AAAAAAAAH8E/ghvHDc_-GIc/s1600/img_07%2B2015-07-29%2B11.58.13.gif)</div><div class="separator" style="clear: both; text-align: left;">
</div>第一層mysite的下層還會有個mysite，這是django建立專案的模式，這表示第一層mysite是專案的root區，先不管這

7.啟動需要開發Django的WEB伺服器，在VM模式下啟動

<div class="separator" style="clear: both; text-align: left;">[![](http://3.bp.blogspot.com/-gBFNKjz7Ub4/Vbhelh1C7XI/AAAAAAAAH8U/FNtIx_aO1Pg/s640/img_08%2B2015-07-29%2B12.57.51.gif)](http://3.bp.blogspot.com/-gBFNKjz7Ub4/Vbhelh1C7XI/AAAAAAAAH8U/FNtIx_aO1Pg/s1600/img_08%2B2015-07-29%2B12.57.51.gif)</div>
啟動完成後，會看到以下
<div class="separator" style="clear: both; text-align: left;">[![](http://1.bp.blogspot.com/-HQKql-GY3HA/VbhfZQp2jMI/AAAAAAAAH8c/iO8oN7qDqS0/s400/img_09%2B2015-07-29%2B13.03.28.gif)](http://1.bp.blogspot.com/-HQKql-GY3HA/VbhfZQp2jMI/AAAAAAAAH8c/iO8oN7qDqS0/s1600/img_09%2B2015-07-29%2B13.03.28.gif)</div>
web server已經開始運作了
如果無法看到成功畫面，或者瀏覽器上顯示錯誤訊息 - "A server error occurred. Please contact the administrator."，請輸入 &nbsp;python manage.py migrate
然後再次runserver啟動你的 web server，我們會在 Django Models 解釋migrate的作用。

8.建立 Django application (app)
我們可以按下 CTRL+C ，關閉 web server 回到命令列。
鍵入 python manage.py startapp trips
<div class="separator" style="clear: both; text-align: left;">[![](http://3.bp.blogspot.com/-ObdiwAjlMIg/Vbhg5GJxdgI/AAAAAAAAH8o/pNvWS_dW1eU/s640/img_10%2B2015-07-29%2B13.09.25.gif)](http://3.bp.blogspot.com/-ObdiwAjlMIg/Vbhg5GJxdgI/AAAAAAAAH8o/pNvWS_dW1eU/s1600/img_10%2B2015-07-29%2B13.09.25.gif)</div>
執行完後可見如下
<div class="separator" style="clear: both; text-align: left;">[![](http://2.bp.blogspot.com/-jhFwRHQNvho/VbhhprxbIXI/AAAAAAAAH8w/dEWuLitFdnk/s400/img_11%2B2015-07-29%2B13.12.48.gif)](http://2.bp.blogspot.com/-jhFwRHQNvho/VbhhprxbIXI/AAAAAAAAH8w/dEWuLitFdnk/s1600/img_11%2B2015-07-29%2B13.12.48.gif)</div>
名為trips的app已建立

9.將新增的 trips 的 Django app 加入設定檔
打開 mysite/settings.py，找到 INSTALLED_APPS區塊，加入'trips'，要讓 Django 知道要管理哪些 app ，請注意 app 之間有時候需要特定先後順序。在此，我們將自訂的trips加在最後面。如下

<div class="separator" style="clear: both; text-align: left;">[![](http://4.bp.blogspot.com/-1QJBkOfhwnA/Vbhiyp1kH6I/AAAAAAAAH88/4rnYjaNGb4w/s320/img_12%2B2015-07-29%2B13.17.04.gif)](http://4.bp.blogspot.com/-1QJBkOfhwnA/Vbhiyp1kH6I/AAAAAAAAH88/4rnYjaNGb4w/s1600/img_12%2B2015-07-29%2B13.17.04.gif)</div>

10.小結
到目前為止，我們使用 startproject 建立了一個名為 mysite 的 django 專案，和一個名為 trips 的 django app

最後，我們回顧一下本章學到的指令
django-admin.py startproject <project_name><span class="Apple-tab-span" style="white-space: pre;">	</span>建立 django 專案</project_name>
python manage.py -h <command_name><span class="Apple-tab-span" style="white-space: pre;">	</span>查看 django command 的使用方法</command_name>
python manage.py runserver<span class="Apple-tab-span" style="white-space: pre;">	</span>啟動開發伺服器
python manage.py startapp <app_name><span class="Apple-tab-span" style="white-space: pre;">	</span>新增 django app&nbsp;</app_name>

11.癈話不多說，還是要先來段hello world
首先建立一個名為 hello_world 的 View。在trips/views.py輸入下列程式碼

<div class="separator" style="clear: both; text-align: left;">[![](http://2.bp.blogspot.com/-MvixQ7eN6-s/Vbhl1mw74tI/AAAAAAAAH9I/jFNoKPsn8kI/s400/img_13%2B2015-07-29%2B13.30.57.gif)](http://2.bp.blogspot.com/-MvixQ7eN6-s/Vbhl1mw74tI/AAAAAAAAH9I/jFNoKPsn8kI/s1600/img_13%2B2015-07-29%2B13.30.57.gif)</div>
以上程式在做的事就是：
1從 django.http 模組中引用 HttpResponse 類別
2宣告 hello_world 這個 View
3當 hello_world 被呼叫時，回傳包含字串 Hello World! 的 HttpResponse 物件。

12.設定URL 與 View 的對應關係
有人瀏覽 http://127.0.0.1:8000/hello/ ，hello_world() 這個 view function 需要被執行。
而這個對應關係就是 URL conf (URL configuration)。
開啟&nbsp;mysite/urls.py 檔，填入
from trips.views import hello_world
url(r'^hello/$', hello_world),
<div class="separator" style="clear: both; text-align: left;">[![](http://2.bp.blogspot.com/-pxY4MA7y3iE/VbhvPHgFkBI/AAAAAAAAH9g/Hhs9KZT6P5I/s400/img_16%2B2015-07-29%2B14.11.04.gif)](http://2.bp.blogspot.com/-pxY4MA7y3iE/VbhvPHgFkBI/AAAAAAAAH9g/Hhs9KZT6P5I/s1600/img_16%2B2015-07-29%2B14.11.04.gif)</div>
這樣就設定好了 URL 與 View 的對應關係

13.測試 Hello World
現在，啟動你的 web server。 (如果剛剛沒關閉的話，通常 Django 會在你修改程式碼後，自動重新啟動 web server)
[![](http://3.bp.blogspot.com/-gBFNKjz7Ub4/Vbhelh1C7XI/AAAAAAAAH8U/FNtIx_aO1Pg/s640/img_08%2B2015-07-29%2B12.57.51.gif)](http://3.bp.blogspot.com/-gBFNKjz7Ub4/Vbhelh1C7XI/AAAAAAAAH8U/FNtIx_aO1Pg/s1600/img_08%2B2015-07-29%2B12.57.51.gif)

重新整理 http://127.0.0.1:8000/hello/

<div class="separator" style="clear: both; text-align: left;">[![](http://3.bp.blogspot.com/-xRPiy5zMB9c/VbhznNgaw7I/AAAAAAAAH9s/7Zkq4mWdzxE/s400/img_17%2B2015-07-29%2B14.29.42.gif)](http://3.bp.blogspot.com/-xRPiy5zMB9c/VbhznNgaw7I/AAAAAAAAH9s/7Zkq4mWdzxE/s1600/img_17%2B2015-07-29%2B14.29.42.gif)</div>
14\. hello world 完成，收工。

引自[Django Girls 學習指南](http://djangogirlstaipei.gitbooks.io/django-girls-taipei-tutorial/content/index.html)

<!--1--><!--1--></div></div></div><div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>