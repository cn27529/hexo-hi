---
title: 'Python Dictionary, 字典的應用'
tags:
  - 'C#'
  - CSS3
  - HTML
  - javascript
  - Python
  - 線上工具
date: 2016-03-17 10:01:00
---

dictionary, 字典是指有一組以上的 key 與 value 所組成不多說, 直接展示吧... <pre class="prettyprint">
"""建立hi_dict的dictionary"""

hi_dict = {'name': '王小明', 'age': 25, 'mail': 'sample@gmail.com'}

"""取得某key的值"""

print hi_dict.get('name')
"""或"""
print hi_dict['name']

"""加入一組 key 與 value"""
add_dict = {'blog','http://myblog.com'}
hi_dict.update(add_dict)
"""或"""
hi_dict.update({'blog','http://myblog.com'})

"""移除一組 key 與 value"""
hi_dict.pop('blog') """若key 'blog' 不存在時會回傳, KeyError: 'bolg' 訊息"""

"""複製dict"""
hi_dict2=hi_dict.copy()

</pre><div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>