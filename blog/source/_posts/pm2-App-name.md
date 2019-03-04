---
title: 'pm2, App name'
tags:
  - Nodejs
  - pm2
  - vscode
date: 2018-05-22 18:21:00
---

具[官方文件](http://pm2.keymetrics.io/docs/usage/quick-start/#42-starts)是長這樣

    pm2 start app.js           <span class="c" style="box-sizing: border-box; color: #999988; font-style: italic;"># Start app.js</span>

    pm2 start app.js <span class="nt" style="box-sizing: border-box; color: navy;">--</span> <span class="nt" style="box-sizing: border-box; color: navy;">-a</span> 23  <span class="c" style="box-sizing: border-box; color: #999988; font-style: italic;"># Pass arguments '-a 23' argument to app.js script</span>

    pm2 start app.js <span class="nt" style="box-sizing: border-box; color: navy;">--name</span> serverone <span class="c" style="box-sizing: border-box; color: #999988; font-style: italic;"># Start a process and name it as serverone</span>
                                        <span class="c" style="box-sizing: border-box; color: #999988; font-style: italic;"># you can now stop the process by doing</span>
                                        <span class="c" style="box-sizing: border-box; color: #999988; font-style: italic;"># pm2 stop serverone</span>
別名其實是很方便的東西...

按官方指示, 在實際上使用時, 你會發現....
<div class="separator" style="clear: both; text-align: center;">[![](https://1.bp.blogspot.com/-ph3cB2mhYhs/WwPeDIkOgDI/AAAAAAAAaHE/3eFY0GR_RUEV6nk9tFM4fcfsfhKcSQXxQCLcBGAs/s640/pm2-set-App%2Bname-%25E5%2588%25A5%25E5%2590%258D%25E6%25B2%2592%25E8%25AE%258A%25E8%2580%25B6XD.jpg)](https://1.bp.blogspot.com/-ph3cB2mhYhs/WwPeDIkOgDI/AAAAAAAAaHE/3eFY0GR_RUEV6nk9tFM4fcfsfhKcSQXxQCLcBGAs/s1600/pm2-set-App%2Bname-%25E5%2588%25A5%25E5%2590%258D%25E6%25B2%2592%25E8%25AE%258A%25E8%2580%25B6XD.jpg)</div>

在**參數**搭配**別名**時會變成這樣..
<div class="separator" style="clear: both; text-align: center;">[![](https://4.bp.blogspot.com/-sZuS9EPBlyc/WwPefjKXbBI/AAAAAAAAaHM/NpsiVohEkTkDQHsm0sDvN7i11x4rYjZ-ACLcBGAs/s640/pm2-set-App%2Bname-%25E5%25B9%25B9%2521%25E5%258F%2583%25E6%2595%25B8%25E7%259A%2584%25E5%259C%25B0%25E6%2596%25B9%25E6%2598%25AF%25E6%25B2%2599%25E5%25B0%258F.jpg)](https://4.bp.blogspot.com/-sZuS9EPBlyc/WwPefjKXbBI/AAAAAAAAaHM/NpsiVohEkTkDQHsm0sDvN7i11x4rYjZ-ACLcBGAs/s1600/pm2-set-App%2Bname-%25E5%25B9%25B9%2521%25E5%258F%2583%25E6%2595%25B8%25E7%259A%2584%25E5%259C%25B0%25E6%2596%25B9%25E6%2598%25AF%25E6%25B2%2599%25E5%25B0%258F.jpg)</div>
原來是....別名在前, 參數在後
<div class="separator" style="clear: both; text-align: center;">[![](https://4.bp.blogspot.com/--Cxy83bXtVE/WwPuQ_QJ0rI/AAAAAAAAaHY/j2QehhARaRshoSSGFQxAiyG5l0xzzI8JACLcBGAs/s640/pm2-set-App%2Bname-%25E6%25AD%25A3%25E7%25A2%25BA%25E4%25BA%2586.jpg)](https://4.bp.blogspot.com/--Cxy83bXtVE/WwPuQ_QJ0rI/AAAAAAAAaHY/j2QehhARaRshoSSGFQxAiyG5l0xzzI8JACLcBGAs/s1600/pm2-set-App%2Bname-%25E6%25AD%25A3%25E7%25A2%25BA%25E4%25BA%2586.jpg)</div>
完工

<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>