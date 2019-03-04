---
title: JavaScript loading 效果使用 UpdatePanelAnimationExtender 控件
tags:
  - AJAXControlToolkit
  - ASP.NET
  - HTML
  - javascript
  - jQuery
date: 2010-11-21 00:44:00
---

前陣子同事分享了一個使用 ,&nbsp;JavaScript loading 效果使用 UpdatePanelAnimationExtender 控件
的文章 , 看了文章之後覺的還不錯趕快記下來 , 以後說不定也有可能運用上

 <pre class="prettyprint">
//在AJAX有個很讚的控制項(應該是說 在AJAX Control ToolKit裡面) 他就叫做 UpdatePanelAnimationExtender
//為什麼會使用它呢 ...!? jQuary的構成 ... 不外乎就是JavaScript
//使用 UpdatePanelAnimationExtender 的動畫效果(恩 可以用來呼叫javascript) 可以輕鬆的達到我們的目標呢
//現在 讓我們開始吧 ...
//對了 附帶一提 ... 其實我沒有在&lthead> 裡面引入jquery.js,jquery.blockUI.js 我用了另一種方法 ...

//在AJAX的ScriptManager 加入Scripts 如下(恩 這個其實是Control ToolKit裡面的控制項，跟ScriptManager有同樣效果) 

        &ltajaxToolkit:ToolkitScriptManager ID="ToolkitScriptManager" runat="server" EnableScriptGlobalization="True" EnablePageMethods="True"> 
            &ltScripts> 
                &ltasp:ScriptReference Path="js/jquery.js"> 
                &lt/asp:ScriptReference> 
                &ltasp:ScriptReference Path="js/jquery.blockUI.js"> 
                &lt/asp:ScriptReference> 
            &lt/Scripts> 
        &lt/ajaxToolkit:ToolkitScriptManager>

//首先 在&ltheade> &lt/head>之間 加入以下JavaScript 

1     &ltscript type="text/javascript"> 
2         function ajaxStart(){ $.blockUI({message: '&lth3>&lt/br>&ltimg src="img/loading/Loading2.gif" /> 資料載入中...&lt/h3>'}); } 
3         function ajaxStop(){ $.unblockUI(); } 
4     &lt/script>

//當然囉 ... 可以自己寫 ... 我這邊的範例 是做一個 有Loading圖片 和 資料載入中... 字樣的message，麻煩自由發揮 ...
//以下 是重點囉~~~
//在你有UpdatePanel的地方 都給他放上一個UpdatePanelAnimationExtender , TargetControlID 記得要設定你的UpdataPanel ... 不然沒有用的唷~
//然後 請看以下程式

01         &ltajaxToolkit:UpdatePanelAnimationExtender ID="UpdatePanelAnimationExtender" runat="server" TargetControlID="UpdatePanel1"> 
02                             &ltAnimations> 
03                     &ltOnUpdating> 
04                         &ltSequence> 
05                             &ltScriptAction script="ajaxStart();" /> 
06                         &lt/Sequence> 
07                     &lt/OnUpdating> 
08                     &ltOnUpdated> 
09                         &ltsequence> 
10                             &ltScriptAction script="ajaxStop();" /> 
11                         &lt/sequence> 
12                     &lt/OnUpdated> 
13                 &lt/Animations> 
14         &lt/ajaxToolkit:UpdatePanelAnimationExtender>

//大略說明一下好了 ... 在&ltAnimations>標籤 可以設定 你再非同步執行開始的時候 要做什麼事情&ltOnUpdating>，在非同步執行結束的時候要做什麼事情&ltOnUpdated>
//所以呢 ~ 我們就在這邊 呼叫剛剛寫在&lthead> 裡面的javascript
//這樣就大功告成了~~
//其實 這個方法蠻簡單的 ...當然 可以做的更花俏~畢竟UpdatePanelAnimationExtender不是吃素的
//假如 我希望在完成後 順便提示使用者 完成了 ... 我該怎麼做呢!?
//首先 在剛剛加入的javascript裡面 新增一個function

 function ajaxComplete(){  
   $.blockUI({message: '&lth3>&lt/br>&ltimg src="img/complete.gif" /> 資料載入完成&lt/h3>'});  
   }
//然後 在&ltOnUpdated>的地方 稍微增加一些東西 ...

1                     &ltOnUpdated>  
2                         &ltsequence>  
3                             &ltScriptAction script="ajaxStop();" />  
4                             &ltScriptAction script="ajaxComplete();" />  
5                             &ltScriptAction Duration="1" script="ajaxStop();" />  
6                         &lt/sequence>  
7                 &lt/OnUpdated>

//好了好了 完成了 ... 這邊意思是
//第三行 -在非同步執行完成後 先呼叫ajaxStop();
//第四行 -呼叫 剛剛加入的ajaxComplete(); 讓它顯示出 資料載入完成的字樣
//第五行 -1秒過後 (Duration) 呼叫ajaxStop(); 解除頁面Block ...
//至於其他變化型，請自由發揮囉 ~

</pre>
引自:&nbsp;[http://www.aspx2.com/a/ASP_NET/2010/0612/55692.html](http://www.aspx2.com/a/ASP_NET/2010/0612/55692.html)<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>