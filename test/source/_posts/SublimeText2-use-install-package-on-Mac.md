---
title: SublimeText2 use install package on Mac
tags:
  - Mac
  - SublimeText
  - 軟体應用相關
date: 2015-03-23 19:42:00
---

<div class="separator" style="clear: both; text-align: center;"></div>在mac下，沒有notepad++可用怎辦？用sublime text 2吧，好用的sublime text 2有著強大的外掛，也不輸notepad++，如何使用外掛呢？趕快記錄下來以後用的上。

1.安裝好sublime text 2後，開啟show console，如圖
<div class="separator" style="clear: both; text-align: center;">[![](http://1.bp.blogspot.com/-1LQNvcyM1y0/VQ_vrayVcuI/AAAAAAAAHyg/-owKiFpjp8M/s1600/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%2B2015-03-23%2B18.47.02.png)](http://1.bp.blogspot.com/-1LQNvcyM1y0/VQ_vrayVcuI/AAAAAAAAHyg/-owKiFpjp8M/s1600/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%2B2015-03-23%2B18.47.02.png)</div>
2.出現console命令列，如圖
<div class="separator" style="clear: both; text-align: center;">[![](http://4.bp.blogspot.com/-C-WpNVx-rPM/VQ_w4U8vgyI/AAAAAAAAHys/Oj1pgagLLYs/s1600/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%2B2015-03-23%2B18.52.35.png)](http://4.bp.blogspot.com/-C-WpNVx-rPM/VQ_w4U8vgyI/AAAAAAAAHys/Oj1pgagLLYs/s1600/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%2B2015-03-23%2B18.52.35.png)</div>
3.在console輸入框處，貼上下文

<span style="background-color: #f4f5f7; color: #5f676a; font-family: Helvetica, Arial, 微軟正黑體, sans-serif; font-size: 12px; line-height: 21.6000003814697px;">import urllib2,os; pf='Package Control.sublime-package'; ipp=sublime.installed_packages_path(); os.makedirs(ipp) if not os.path.exists(ipp) else None; urllib2.install_opener(urllib2.build_opener(urllib2.ProxyHandler())); open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read()); print 'Please restart Sublime Text to finish installation'</span>
<span style="background-color: #f4f5f7; color: #5f676a; font-family: Helvetica, Arial, 微軟正黑體, sans-serif; font-size: 12px; line-height: 21.6000003814697px;">
</span><span style="background-color: #f4f5f7; color: #5f676a; font-family: Helvetica, Arial, 微軟正黑體, sans-serif; font-size: 12px; line-height: 21.6000003814697px;">4.完成後，會要求你關閉並重開sublime text 2，如圖</span>
<div class="separator" style="clear: both; text-align: center;">[![](http://2.bp.blogspot.com/-mgwoSRTq2cg/VQ_3nW-WduI/AAAAAAAAHzE/9TVLRTGPK8o/s1600/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%2B2015-03-23%2B18.56.52.png)](http://2.bp.blogspot.com/-mgwoSRTq2cg/VQ_3nW-WduI/AAAAAAAAHzE/9TVLRTGPK8o/s1600/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%2B2015-03-23%2B18.56.52.png)</div><div class="separator" style="clear: both; text-align: center;">
</div><span style="background-color: #f4f5f7; color: #5f676a; font-family: Helvetica, Arial, 微軟正黑體, sans-serif; font-size: 12px; line-height: 21.6000003814697px;">5.&nbsp;重開後就可以command+shift+P，使用install package命令，如圖</span>
<div class="separator" style="clear: both; text-align: center;">[![](http://1.bp.blogspot.com/-QpQsoAxAnMo/VQ_7VTCFWDI/AAAAAAAAHzQ/rbxXL3VkKbM/s1600/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%2B2015-03-23%2B19.02.18.png)](http://1.bp.blogspot.com/-QpQsoAxAnMo/VQ_7VTCFWDI/AAAAAAAAHzQ/rbxXL3VkKbM/s1600/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%2B2015-03-23%2B19.02.18.png)</div><span style="background-color: #f4f5f7; color: #5f676a; font-family: Helvetica, Arial, 微軟正黑體, sans-serif; font-size: 12px; line-height: 21.6000003814697px;">
</span><span style="background-color: #f4f5f7; color: #5f676a; font-family: Helvetica, Arial, 微軟正黑體, sans-serif; font-size: 12px; line-height: 21.6000003814697px;">6.鍵入install package後按enter，就可以進行尋找你要的外掛工具了，如圖</span>
<div class="separator" style="clear: both; text-align: center;">[![](http://1.bp.blogspot.com/-n2Gx6rH1e58/VRAEw30s4EI/AAAAAAAAHzg/qO03035HHo8/s1600/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%2B2015-03-23%2B19.01.23.png)](http://1.bp.blogspot.com/-n2Gx6rH1e58/VRAEw30s4EI/AAAAAAAAHzg/qO03035HHo8/s1600/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%2B2015-03-23%2B19.01.23.png)</div>
如果不行，就再試一次，或許是弄錯了XD

<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>