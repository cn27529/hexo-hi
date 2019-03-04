---
title: MS-SQL 指令、語法與管理
tags:
  - MS-SQL
  - Windows 相關
  - 軟体應用相關
date: 2012-02-22 13:48:00
---

<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">很多時候，都需要使用到指令、語法來管理MS SQL資料庫，但通常都是記不住的，寫下來便於使用，至於管理，towns是很遜的，很多時候都是土法鍊鋼，一點一點做 ^^"</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">1\. 指令管理資料庫關閉與啟動
net stop mssqlserver /y&nbsp; &lt;==使用net 指令停止mssqlserver服務，並同時同意停止其他相關服務
net start sqlserveragent &lt;==使用net 指令啟動sqlserveragent服務，系統會自動將mssqlserver 啟動
net stop 及 start 主要是用來停止與啟動系統中的服務，所有的服務都可以透過這樣的方式來管理，另一個towns常用的是IIS的管理。</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">注意：後面加的服務名稱並不是在“服務”中的“顯示名稱”，而是“服務名稱”</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">2\. 列出abc所有的table
sp_tables @table_name = '%',@table_owner = 'dbo',@table_qualifier = 'abc'</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">3\. 選擇所有欄位從 abcd 資料表中找出 cdef 欄，並找有towns完全相同的字串（單一條件絕對搜尋，顯示所有欄位）
select&nbsp; * &nbsp;from&nbsp;abcd where cdef = 'towns'

選擇cdef,aaa欄位從 abcd 資料表中找出 cdef 欄，並找有towns完全相同的字串（單一條件絕對搜尋，只顯示兩欄位）
select&nbsp;cdef,aaa from abcd where cdef ='towns'</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">4\. 查尋資料庫版本
select @@version</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">5\. 刪除特定資料表
delete from abc &lt;==刪除abc資料表中的資料</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**6\. MSSQL 2005 資料庫 &lt;==&gt; MSSQL 2005 Express 資料庫**
&nbsp;MSSQL 2005 Express ==&gt; MSSQL 2005。直接附加即可
&nbsp;MSSQL 2005 ==&gt; MSSQL 2005 Express
&nbsp;1\. 由MSSQL 2005 匯出資料庫結構。在指定資料庫按滑鼠右鍵==&gt;工作==&gt;產生指令碼==&gt;下一步==&gt;確認是否為選擇的資料庫，下一步==&gt;在選擇指令碼選項中，不需做特別修改，下一步==&gt;選擇物件類型，僅選擇<span style="color: red;">資料表</span>及<span style="color: red;">檢視</span>，下一步==&gt;選擇資料表，全選，下一步==&gt;選擇檢視，全選，下一步==&gt;輸出選項，這裡依需求選擇，下一步（towns多選寫指令碼至檔案），下一步==&gt;設定檔名及路徑
，存檔，下一步==&gt;完成
&nbsp;註：對該資料庫需要有存取權限，如果只有讀取權限，匯出時會出現錯誤</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">&nbsp;2\. 將結構檔匯入&nbsp; MSSQL 2005 Express。開啟Managemant==&gt;檔案==&gt;開啟==&gt;檔案==&gt;選擇剛剛匯出的檔案==&gt;這時系統會要求打入帳密（確認連結的資料庫是否正確，帳密需有寫入權限）==&gt;此時結構語法已載入==&gt;點入語法，並<span style="color: red;">確認要載入的資料庫是否正確</span>（系統會預設載入為master）==&gt;執行==&gt;結構載入</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">&nbsp;3\. 將資料匯入&nbsp;MSSQL 2005 Express。
&nbsp; 3.1.連結資料庫匯入
&nbsp;&nbsp;&nbsp; 開啟Managemant==&gt;<span style="color: red;">選擇資料來源</span>（確認資料來源及登入資料，一般towns會使用ReadOnly 帳號，以避免錯誤）==&gt;<span style="color: red;">選擇目的地</span>（確認目的地及登入資料，這裡需有寫入權限）==&gt;指定資料表複製或查詢，towns通常是要複製，選從一或多個資料表或檢視複製資料，下一步==&gt;全選所有的資料表及檢示，編輯，選刪除資料表中的資料列，並取消檢視，下一步==&gt;立即執行==&gt;確認工作==&gt;完成
&nbsp; 3.2.可用匯出檔案方式，將資料再匯入。
&nbsp;&nbsp;&nbsp; 開啟Managemant==&gt;<span style="color: red;">選擇資料來源</span>（確認資料來源及登入資料，一般towns會使用ReadOnly 帳號，以避免錯誤）==&gt;<span style="color: red;">選擇目的地</span>（選擇excel）==&gt;選擇匯出路徑並打入檔案名稱==&gt;地區設定及字碼頁需依資料庫編碼決定 ==&gt;從一或多個資料表或檢視複製資料 ==&gt;下一步（這裡towns使用預設值）</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">注意事項：做匯出匯入的動作是非常危險的，方向一錯資料就不見了，建議在執行時，該備份的一定要先備份，不要嫌麻煩
技術指導：藍色小舖資深工程師 IZAN</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">補充說明：最近一次的測試，<span style="color: red;">是可以直接使用MSSQL 2005 ent 備份出來的檔案，直接還原到 MSSQL 2005 Express版 中</span>SQL Server Management Studio Express為 SP3版</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**7\. SQL2005 TCP/IP協定啟用**
&nbsp;到開始Microsoft SQL 2005==&gt;組態工具==&gt;進入 SQL Server組態管理員（有些會出現英文）==&gt;選擇 SQL Server 2005 網路組態==&gt; 這裡可能會出現SQL及SQLEXPRESS，看哪個要開就開哪個 ==&gt;選擇TCP/IP ==&gt;IP位址==&gt;確認IPALL中TCP通訊埠，是否有開起埠號（如預設值1433），在開啟後，要重新啟動SQL Server的服務，並使用netstat -an來檢查是否有開啟1433 port</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**8.&nbsp;加快資料庫讀取速度**，利用先將資料庫放到記憶體中，加快讀取速度
相關資料：[http://blog.miniasp.com/post/2009/11/SQL-Server-Performance-Tuning-Caching-commonly-used-tables.aspx](http://blog.miniasp.com/post/2009/11/SQL-Server-Performance-Tuning-Caching-commonly-used-tables.aspx)（感謝will大無私分享）</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**9\. 在MSSQL資料庫轉移時**，常常會遇到的問題
&nbsp;9.1\. 資料庫使用還原或附加後，因為使用者不存在而造成網站無法正確讀取資料庫（&nbsp;如圖[nouser](http://vip.blueshop.com.tw/towns/mssql/nouser.jpg)），此時需刪除並重建使用者
&nbsp;9.2\. 要刪除使用者，重建時，發生使用者無法刪除，導致無法重建該使用者。常見原因有
&nbsp; 9.2.1\. 在該資料庫==&gt;安全性==&gt;結構描述中，有該使用者的名稱
&nbsp;&nbsp;處理方式：到結構描述中，將該使用者刪除，如果無法刪除，就與下面兩點有關
&nbsp;&nbsp;9.2.2\. 在該資料庫==&gt;資料表==&gt;結構描述中，有該使用者的名稱（如圖[table](http://vip.blueshop.com.tw/towns/mssql/table.jpg)）
&nbsp; 9.2.3\. 在該資料庫==&gt;檢示==&gt;結構描述中，有該使用者的名稱（如圖[view](http://vip.blueshop.com.tw/towns/mssql/view.jpg)）

&nbsp; **SQL2000處理方式：手動將結構描述改為dbo**
&nbsp; 開啟SQL Server Enterprice&nbsp;Manager==&gt;選擇該資料庫==&gt;選擇資料表，其結構
&nbsp; 描述為使用者名稱的==&gt;到資料表上按滑鼠右鍵，選擇設計資料表==&gt;按左上方“資料表與索引屬
&nbsp; 性”（如圖[property](http://vip.blueshop.com.tw/towns/mssql/property.jpg)）==&gt;變更擁有者為dbo（如圖[property-1](http://vip.blueshop.com.tw/towns/mssql/property-1.jpg)），存檔==&gt;擁有者就改為dbo，就可
&nbsp; 刪除帳號即可

&nbsp; **SQL2005處理方式：手動將結構描述改為dbo**
&nbsp; 開啟Microsoft SQL Server&nbsp;Management Studio==&gt;選擇該資料庫==&gt;選擇資料表，其結構
&nbsp; 描述為使用者名稱的==&gt;到資料表上按滑鼠右鍵，選擇設計==&gt;在屬性中選結構描述==&gt;變更擁有者
&nbsp; 為dbo（如圖[2005property](http://vip.blueshop.com.tw/towns/mssql/2005property.jpg)），存檔==&gt;擁有者就改為dbo，就可刪除帳號即可

&nbsp; **SQL2008處理方式：手動將結構描述改為dbo**
&nbsp; 開啟Microsoft SQL Server&nbsp;Management Studio==&gt;選擇該資料庫==&gt;選擇資料表，其結構
&nbsp; 描述為使用者名稱的==&gt;到資料表上按滑鼠右鍵，選擇設計==&gt;在屬性中選結構描述==&gt;變更擁有者
&nbsp; 為dbo（如圖[2008property](http://vip.blueshop.com.tw/towns/mssql/2008property.jpg)），存檔==&gt;擁有者就改為dbo，就可刪除帳號即可
&nbsp;&nbsp;註：SQL Server Management Studio 預設並不開啟屬性視窗，按F4就可開啟

技術指導：藍色小舖資深工程師 IZAN</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">&nbsp;&nbsp;補充：使用者擁有預存程序（如圖[storedprocedure2](http://vip.blueshop.com.tw/towns/mssql/storedprocedure2.png)），這個也會造成無法刪除使用者的問題，這時必須重建預設程序才能解決該問題。在預存程序上按滑鼠右鍵==&gt;編寫預存程序指令碼為==&gt;CREATE至==&gt;產生指令碼，再將指令碼中的擁有者改為dbo，刪除該程序後重建這個預存程序。</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">技術指導：tina</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**10\. 當同台主機安裝了多個MSSQL**（如有有安裝2000、2005 Express、2005等）要注意
&nbsp;10.1.在進入SQL時，要選擇正確的版本
&nbsp;10.2.在新增帳號時，請使用2005來新增及指定資料庫，否則會發生帳號無法正常讀取的問題</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**11.&nbsp;從 abcd 資料表中cdef 欄**，找出有張及張*文的字串（兩條件模糊搜尋）
select * from abcd where&nbsp;(cdef LIKE '張%') OR (cdef LIKE '張%文')</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**12.&nbsp;查詢T-SQL語法**
&nbsp;sp_help</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**13.&nbsp;列出資料庫清單**，列出後再使用右鍵儲存結果為單一 CSV檔

&nbsp;13.1\. 列出資料庫所有狀態
sp_helpdb

&nbsp;13.2.&nbsp;僅列出資料庫名稱
USE master
SELECT dbid, DB_NAME(dbid) AS DB_NAME
FROM sysdatabases
ORDER BY dbid

&nbsp;資料來源：blues及tina口述</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**14\. 查看每一個SQL語法的使用記錄**
使用SQL Server Profiler 中新增追蹤，可以看到資料庫正在存取的情形
read ==&gt;讀取硬碟資料筆數
write ==&gt;寫入硬碟資料筆數
duration ==&gt;經過時間，時間太長就表示讀取/寫入硬碟資料時很長，這是造成資料庫回應緩慢的原因（1000=1秒）
技術指導：藍色小舖資深工程師 IZAN</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**15\. access 2007與資料庫連結（圖解）**
&nbsp;&nbsp;&nbsp;&nbsp; 1.&nbsp;匯入mssql 資料：外部資料==&gt;其他==&gt;ODBC資料庫（如圖[mdb1.jpg](http://vip.blueshop.com.tw/towns/access/mdb1.jpg)）
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2\. 選擇匯入方式，第一項為將資料cp一份到電腦中，第二項為連結同步，取得最新資料（如圖[mdb2.jpg](http://vip.blueshop.com.tw/towns/access/mdb2.jpg)）
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3\. 選擇資料來源，請新增一個 DSN資料來源（如圖[mdb3.jpg](http://vip.blueshop.com.tw/towns/access/mdb3.jpg)）
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4\. 選擇 SQL server 下一步（如圖[mdb4.jpg](http://vip.blueshop.com.tw/towns/access/mdb4.jpg)），將DSN指定存放位置及設定名稱 下一步（如圖[mdb5.jpg](http://vip.blueshop.com.tw/towns/access/mdb5.jpg)）
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;5.&nbsp;與伺服器建立連結，打入伺服器名稱或IP（如圖[mdb6.jpg](http://vip.blueshop.com.tw/towns/access/mdb6.jpg)）
&nbsp;&nbsp;&nbsp;&nbsp; 6\. 選擇連入帳戶，選擇第二項者，需打入帳號及密碼（如圖[mdb7.jpg](http://vip.blueshop.com.tw/towns/access/mdb7.jpg)）
&nbsp;&nbsp;&nbsp;&nbsp; 7\. 指定取得資料庫，勾選變更預設資料庫即可選擇（如圖[mdb8.jpg](http://vip.blueshop.com.tw/towns/access/mdb8.jpg)）
&nbsp;&nbsp;&nbsp;&nbsp; 8\. 這一塊使用預設值，不需變更（如圖[mdb9.jpg](http://vip.blueshop.com.tw/towns/access/mdb9.jpg)），summary（如圖[mdb10.jpg](http://vip.blueshop.com.tw/towns/access/mdb10.jpg)），完成後需打入帳密登入資料庫（如圖[mdb11.jpg](http://vip.blueshop.com.tw/towns/access/mdb11.jpg)）
&nbsp;&nbsp;&nbsp;&nbsp; 9\. 選擇要匯入的 table（如圖[mdb12.jpg](http://vip.blueshop.com.tw/towns/access/mdb12.jpg)），完成匯入</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">&nbsp;**16\. 關於資料庫 ldf 檔非常大，但卻無法壓縮的問題**
towns管理的伺服器中，有些資料庫的Log檔，實在是大的離譜，但在執行備份壓縮後，卻不見Log檔變小（如圖[mssqlLog2.jpg](http://vip.blueshop.com.tw/towns/mssql/mssqlLog2.jpg)），雖然說可用空間明顯加大（如圖[mssqlLog.jpg](http://vip.blueshop.com.tw/towns/mssql/mssqlLog.jpg)），但檔案事實上是沒變小的，目前towns 將自動壓縮功能啟用（如圖[mssqlLog3.jpg](http://vip.blueshop.com.tw/towns/mssql/mssqlLog3.jpg)）並執行排程備份壓縮，是否能成功將 ldf 檔變小，今天晚上就可以知道了。
很可惜，ldf 檔並沒有變小，看來在動作中的資料庫，要壓縮是個問題呢
&nbsp;16.1.經過IZAN指導，要連續兩次壓縮，才能將ldf 檔變小，而且必需使用維護計畫來執行才能有效壓縮，可以先做一次手動備份LDF檔，再用計畫做備份壓縮，也可以有效處理
&nbsp;16.2.不需要設定自動壓縮功能（如圖[mssqlLog3.jpg](http://vip.blueshop.com.tw/towns/mssql/mssqlLog3.jpg)），也能有效壓縮
技術指導：藍色小舖資深工程師 IZAN
相關資料：[http://ithelp.ithome.com.tw/question/10028911](http://ithelp.ithome.com.tw/question/10028911)</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">補充：LDF 檔有多大，就需要給他一個多大的空間來備份，如LDF約10GB，硬碟空間就要 &gt; 10GB</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**17\. 從 abcd 資料表中所有的欄位找出 cdef 欄，並找有 1 或 2 字串的資料（同時搜尋兩條件）**
SELECT * FROM&nbsp; abcd&nbsp; WHERE (cdef = '1') OR (cdef = '2')</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**18\. 從 abcd 資料表中所有的欄位找出 cdef 欄，去除有 1 或 2 字串的資料（同時去除兩條件）**
SELECT * FROM&nbsp; abcd&nbsp; WHERE not(cdef = '1'&nbsp; OR&nbsp; cdef = '2')
SELECT * FROM&nbsp; abcd where cdef not in ('1','2')
資料來源：IZAN 及 TINA</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">
</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">**19\. 從 abcd 資料表中所有的欄位找出 cdef 欄為空值的資料**
SELECT * FROM&nbsp;abcd WHERE (cdef = '')</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">20\. 統計abcd 資料表筆數
select count(*) from abcd
資料來源：Blues</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">21\. 從abcd 資料表中列出前 N 筆 cdef 欄 資料（僅顯示cdef 欄資料）
select top ( N ) cdef from abcd
從abcd 資料表中列出前 N 筆資料
select top ( N )&nbsp;* from abcd
資料來源：Blues</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">22\. 從abcd 資料表中抓取 cdef 欄及ghij 資料
select cdef,ghij from abcd&nbsp;</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">23\. 索引片段過多會導致資料庫讀取該table效能變差
查看索引片段情形與頁面使用飽和度
進入資料庫==&gt;選定特定資料庫==&gt;資料表==&gt;選定特定資料表==&gt;索引==&gt;點開看該叢集==&gt;滑鼠右鍵點屬性==&gt;選擇片段==&gt;這裡就可以看到片段總計及頁面飽和度</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">24\. T-SQL指令變更資料型別
ALTER TABLE abc
ALTER COLUMN&nbsp;abcuid Varchar (20) NOT NULL;
變更資料表 abc中的資料欄 abcuid 的欄位長度為 20
技術提供：blues</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">25\. 清空特定資料庫語法。這個語法會特定資料庫中的資料完全清除
TRUNCATE TABLE&nbsp; table_name</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">26\. MS-SQL 語法教學站台
[http://www.1keydata.com/tw/sql/sql.html](http://www.1keydata.com/tw/sql/sql.html)</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">27\. MS-SQL 2000 問題
當使用windws 2003 server 安裝 MS-SQL 2000，SQL 版本為 SP2或更舊，這時會造成 TCP/IP 通訊協定無法開啟的問題，這時請將SQL 2000更新到 SP4版，這個問題就會解決，詳細資料可見事件檢視器==&gt;應用程式</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">28\. MS-SQL 2008 無法直接編輯資料的修改方式
2k8基於安全性考量，management studio預設的編輯功能為唯讀，導致無法編輯欄位內容、欄位格式等等，需到工具 ==&gt;選項 ==&gt;Desigeners ==&gt;資料表和資料庫設計工具 ==&gt;取消“防止存儲需要資料表重建的變更”，這樣就可以編輯了
資料來源：小舖工程師 jainkai</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">29\. MS-SQL 2000的查詢頁面
ms-sql 2000中並沒有新增查詢的項目，以提供語法寫入，需要到 工具 ==&gt; sql query analyzer 才會開啟語法寫入頁面
註：要指定資料庫</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">30\. 帳號權限管理
&nbsp;30.1\. 限制讀取指定資料表（table）
建立帳號test ==&gt;在指定資料庫（abcd），安全性中加入使用者test ==&gt;但不提供“資料庫角色成員資格”==&gt;到指定table（tbAabc）上按滑鼠右鍵==&gt;屬性 ==&gt;權限 ==&gt;點下 搜尋 ==&gt;瀏覽 ==&gt;勾選指定帳號（test）==&gt;到下表中勾選test的權限，這裡依需求勾選，towns只勾授與“選取”。設定完成後，test帳號就只能看到這個table 並對這個table執行選取的指令了
刪除方式：直接於指定資料庫安全性中刪除該使用者</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">31\. 主機名稱與MSSQL問題
當我們在安裝完MSSQL後再變更主機名稱，會發生維護計畫無法使用的問題，因為MSSQL會抓取舊主機名稱，造成執行權限不正確，導致維護計畫無法使用，這個問題可以在事件檢視器中看到。
處理方式：還在找</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">32\. 建立資料庫
與ACCESS、Excel表很類似，不過通常需要加上主索引
主索引 自行設定名稱 類型 bigint，自動編號 請將識別規格改為 是
資料行 自行設定名稱 類型 nchar，並設定字數</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">33\. 單一table大小可以在該table上面按滑鼠右鍵==&gt;屬性==&gt;儲存體，這裡就可以看到他使用的索引空間大小，資料空間大小</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">34\. 取出大於等於1000的數值資料
select * from abcd where&nbsp;defg &gt;= 1000
註：defg欄位必需為數值資料</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">35\. MSSQL 2008 安裝失敗
系統：windows 2008 R2 std sp1
MSSQL：MSSQL 2008 R2 ent
在安裝過程中出現了“效能計數器登入區一致性：失敗”
![](http://vip2.blueshop.com.tw/towns//mssql/processcont.jpg)</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">點選失敗後，會請我們到指定網站參考微軟的說明
![](http://vip2.blueshop.com.tw/towns//mssql/processcont2.jpg)</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">連到官網後，看了一下資料，說真的以towns的資質，實在是看不懂這個文章在寫什麼，更不知道怎麼下手處理問題，但towns有在伺服器廠商安裝系統時，有發現他們使用的是英文版OS，這個也造成了系統的區域資料異常。towns 試著到 控制台==&gt;時鐘、語言和區域中查看，發覺在 系統管理==&gt;非Unicode程式的語言，這裡寫的是“<span style="color: red;">英文（美國</span>）”，這個資訊顯然是錯誤的，towns 將他改為“<span style="color: red;">中文（繁體、台灣）</span>後，就可以正常安裝mssql了，還好這樣就可以了，官網資料實在是太難懂了= =</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">發覺這個問題，是因為在cmd模式下，會出現亂碼</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">36\. MSSQL 語法，選取時間格式
方法一
SELECT&nbsp;&nbsp;&nbsp; *
FROM&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; abc
WHERE
&nbsp;&nbsp;&nbsp; DATEPART(yy, d_date) = 2010
AND DATEPART(mm, d_date) = 12
AND DATEPART(dd, d_date) = 31</div><div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">方法二
SELECT *
FROM abc
WHERE
&nbsp;&nbsp;&nbsp; d_date BETWEEN '2010-12-31 00:00:00' AND '2010-12-31 23:59:59'

資料來源：blues大師口述</div>

* * *
<div style="color: #423a00; font-size: 15px; line-height: 25px; text-align: left;">37\. 關於LDF檔異常長大的原因
使用索引重建，會造成LDF檔變大，如果有需要重建，建議先看看LDF檔是否很大了，如果很大，要先壓縮後再執行</div>引用自:[http://itgroup.blueshop.com.tw/towns/hc?n=wodvew&amp;i=385](http://itgroup.blueshop.com.tw/towns/hc?n=wodvew&amp;i=385)<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>