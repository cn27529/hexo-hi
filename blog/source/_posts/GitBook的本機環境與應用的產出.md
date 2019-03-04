---
title: GitBook的本機環境與應用的產出
tags:
  - Git
  - GitBook
  - GitHub
date: 2017-05-05 10:37:00
---

線上文件是一種顛覆本機工作的產物，哈！今天來玩玩GitBook的文件產出ＸＤ
這篇不是新手文章，是新手的請確認你己會使用gitbook
直接進主題:

確定己經安裝了gitbook-cli還沒裝的快去裝XD, 這個套件可以讓我們的gitbook文件產出
HTML 文件
ePub 電子書
Kindle 電子書
製作 PDF 電子書

今天的例子是HTML文件
先切換像到你的gitbook目錄位置, 執行終端指令
開啟.gitignore檔查看

# Node rules:
## Grunt intermediate storage (http://gruntjs.com/creating-plugins#storing-task-files)
.grunt

## Dependency directory
## Commenting this out is preferred by some people, see
## https://docs.npmjs.com/misc/faq#should-i-check-my-node_modules-folder-into-git
node_modules

# Book build output
_book

# eBook build output
*.epub
*.mobi
*.pdf

如果沒有上面這段就自己打吧XD

若在本地看gitbook命令列輸入:
gitbook serve
它預設會開啟 localhost:4000

若要產生html靜態檔案, 命令列輸入:
gitbook fulid --output=/site/mybook

<div class="separator" style="clear: both; text-align: center;">[![](https://1.bp.blogspot.com/-JM_aAmlMknY/WQvh5R4et4I/AAAAAAAAOY8/tKdrJ22Ie0gzRUkkWoc_GqGdj6f42JP-wCLcB/s400/2017-05-05_102205.png)](https://1.bp.blogspot.com/-JM_aAmlMknY/WQvh5R4et4I/AAAAAAAAOY8/tKdrJ22Ie0gzRUkkWoc_GqGdj6f42JP-wCLcB/s1600/2017-05-05_102205.png)</div>
然後...
<div class="separator" style="clear: both; text-align: center;">[![](https://4.bp.blogspot.com/-CvwB2jQSOc0/WQvjQiL5AJI/AAAAAAAAOZI/2Wo8TgttkR4ycNoDz23On9iNGTVqTJ49gCLcB/s400/2017-05-05_102856.png)](https://4.bp.blogspot.com/-CvwB2jQSOc0/WQvjQiL5AJI/AAAAAAAAOZI/2Wo8TgttkR4ycNoDz23On9iNGTVqTJ49gCLcB/s1600/2017-05-05_102856.png)</div>
登登 success
來去目錄查看一下吧
<div class="separator" style="clear: both; text-align: center;">[![](https://4.bp.blogspot.com/-KfnggbsrQnY/WQvj1a3h8jI/AAAAAAAAOZQ/0HFjc3zcBc4h9R4JKj8ulEFb-zf5w2rcwCLcB/s320/2017-05-05_103120.png)](https://4.bp.blogspot.com/-KfnggbsrQnY/WQvj1a3h8jI/AAAAAAAAOZQ/0HFjc3zcBc4h9R4JKj8ulEFb-zf5w2rcwCLcB/s1600/2017-05-05_103120.png)</div>
有了之後, 直接去打開index.html吧GO~~
<div class="separator" style="clear: both; text-align: center;">[![](https://4.bp.blogspot.com/-dMYKTwbS0mo/WQvkrRk7OJI/AAAAAAAAOZg/YzPtNbcEN7g0HD3JAbmSAxuoeIoFuM52wCLcB/s640/2017-05-05_103450.png)](https://4.bp.blogspot.com/-dMYKTwbS0mo/WQvkrRk7OJI/AAAAAAAAOZg/YzPtNbcEN7g0HD3JAbmSAxuoeIoFuM52wCLcB/s1600/2017-05-05_103450.png)</div>
YA~有嘍~大功告成, 美觀又漂亮XD

收工! (握拳

<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>