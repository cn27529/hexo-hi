---
title: 'ALTER TABLE on ADD, ALTER, DROP column_name'
tags:
  - Database
  - MS-SQL
date: 2016-03-25 13:42:57
---

常用的表格欄位新增異動語法 MS SQL 
<pre class="prettyprint">--加欄位ADD column
ALTER TABLE my_table_name ADD my_column_name nvarchar(50)

--異動資料類型ALTER COLUMN
ALTER TABLE my_table_name ALTER COLUMN my_column_name nvarchar(50)

--移除欄位DROP COLUMN
ALTER TABLE my_table_name DROP COLUMN my_column_name

</pre><div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>