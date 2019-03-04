---
title: 什麼是DOM (Document Object Model)
tags:
  - HTML
  - javascript
date: 2009-02-14 22:50:00
---

通过 JavaScript，您可以重構整个 HTML 文档。您可以添加、移除、改变或重排页 面上的项目。要改变页面的某个东西，JavaScript 就需要对 HTML 文档中所有元素进行访问的入口。 这个入口，连同对 HTML 元素进行添加、移动、改变或移除的方法和属性，都是通过文档对象模型来获 得的（DOM）。

在 1998 年，W3C 发布了第一级的 DOM 规範。这个规範允许访问和操作 HTML 页面中的每一个单独的元素。

所有的浏览器都执行了这个标准，因此，DOM 的相容性问题也幾乎难觅踪影了。

DOM 可被 JavaScript 用来读取、改变 HTML、XHTML 以及 XML 文 档。

### DOM 被分为不同的部分（核心、XML及HTML）和级别（DOM Level 1/2/3）：

<dl class="define">
<dt>Core DOM 定义了一套标准的针对任何结構化文档的对象 </dt><dt>[XML DOM](http://www.w3school.com.cn/xmldom/index.asp "XML DOM 教程") 定义了一套标准的针对 XML 文档的对象 </dt><dt>HTML DOM 定义了一套标准的针对 HTML 文档的对象。
</dt><dt>**HTML 文档中的每个成分都是一个节点。**</dt></dl>

## 节点

根據 DOM，HTML 文档中的每个成分都是一个节点。

DOM 是这样规定的：

*   整个文档是一个文档节点*   每个 HTML 标签是一个元素节点*   包含在 HTML 元素中的文本是文本节点*   每一个 HTML 属性是一个属性节点*   注释属於注释节点

## <span style="color:#ff0000;">Node 层次</span>

节点彼此都有等级关系。

HTML 文档中的所有节点组成了一个文档树（或节点树）。HTML 文档中的每个元素、 属性、文本等都代表着树中的一个节点。树起始于文档节点，並由此继续伸出枝条，直到处於这棵树
最低级别的所有文本节点为止。

下麵这个图片表示一个文档树（节点树）：

![HTML树结構](http://www.w3school.com.cn/i/ct_htmltree.gif)

**一棵节点树中的所有节点彼此都是有关系的。**

## 文档树（节点数）

请看下麵这个HTML文档：

<pre>&lt;html&gt;
  &lt;head&gt;
    &lt;title&gt;DOM Tutorial&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;DOM Lesson one&lt;/h1&gt;
    &lt;p&gt;Hello world!&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;</pre>

上面所有的节点彼此间都存在_关系_。

除文档节点之外的每个节点都有_父节点_。举例，&lt;head&gt; 和 &lt;body&gt; 的父节点是 &lt;html&gt; 节点，文本节点 "Hello
world!" 的父节点是 &lt;p&gt; 节点。

大部分元素节点都有_子节点_。比方说，&lt;head&gt; 节点有一个子节点 ：&lt;title&gt; 节点。&lt;title&gt; 节点也有一个子节点：文本节点
"DOM Tutorial"。

当节点分享同一个父节点时，它们就是_同辈（同级节点）_。比方说，&lt;h1&gt; 和 &lt;p&gt;是同辈，因为它们的父节点均是 &lt;body&gt; 节点。

节点也可以拥有_後代_，後代指某个节点的所有子节点，或者这些子节点的子 节点，以此类推。比方说，所有的文本节点都是 &lt;html&gt;节点的後代，而第一个文本节点是
&lt;head&gt; 节点的後代。

节点也可以拥有_先辈_。先辈是某个节点的父节点，或者父节点的父节点，以此 类推。比方说，所有的文本节点都可把 &lt;html&gt; 节点作为先辈节点。

**<span style="font-size:180%;color:#ff0000;">下麵 来看幾个简单的例子 我想一下子就明白了!</span>**

**通过 DOM，您可访问 HTML 文档中的每个节点。**

## 查找並访问节点

你可通过若干種方法来查找您希望操作的元素：

*   通过使用 getElementById() 和 getElementsByTagName() 方法*   通过使用一个元素节点的 parentNode、firstChild 以及 lastChild 属性

<span style="color:#800000;">getElementById() 和 getElementsByTagName()</span>

getElementById() 和 getElementsByTagName() 这两種方法，可查找整个 HTML 文档中的任何 HTML 元素。

这两種方法会忽略文档的结構。假如您希望查找文档中所有的 &lt;p&gt; 元素，getElementsByTagName() 会把它们全部找到，不管 &lt;p&gt;
元素处于文档中的哪个层次。同时，getElementById() 方法也会返回正確的元素，不论它被隐藏在文档结構中的什麼位置。

这两種方法会像您提供任何你所需要的 HTML 元素，不论它们在文档中所处的位置！

getElementById() 可通过指定的 ID 来返回元素：

### <span style="font-size:130%;color:#800080;">getElementById() 语法</span>
<pre>document.getElementById("ID");</pre><pre>注释：getElementById() 无法工作在 XML 中。在 XML 文档中，您必须通过拥有类型 id 的属性来进行搜索，而此类型必须在
XML DTD 中进行声明。</pre>

getElementsByTagName() 方法会使用指定的标签名返回所有的元素（作 为一个节点列表），这些元素是您在使用此方法时所处的元素的後代。

getElementsByTagName() 可被用於任何的 HTML 元素：

### <span style="font-size:130%;color:#800080;">getElementsByTagName() 语法</span>
<pre>document.getElementsByTagName("标签名称");</pre><pre>或者：</pre><pre>document.getElementById('ID').getElementsByTagName("标签名称");</pre>

### 實例1

下麵这个例子会返回文档中所有 &lt;p&gt; 元素的一个节点列表：

document.getElementsByTagName("p");

### 實例2

下麵这个例子会返回所有 &lt;p&gt; 元素的一个节点列表，且这些 &lt;p&gt; 元素必须是 id 为 "maindiv" 的元素的後代：

document.getElementById('maindiv').getElementsByTagName("p");

### 节点列表（nodeList）

当我们使用节点列表时，通常要把此列表保存在一个变量中，就像这样：
<pre>var x=document.getElementsByTagName("p");</pre>

现在，变量 x 包含着页面中所有 &lt;p&gt; 元素的一个列表，並且我们可以通过它们的索引 号来访问这些 &lt;p&gt; 元素。

注释：索引号从 0 开始。

您可以通过使用 length 属性来循环遍历节点列表：
<pre>var x=document.getElementsByTagName("p");
for (var i=0;i&lt;x.length;i++)
  {
  // do something with each paragraph
  }</pre>

您也可以通过索引号来访问某个具體的元素。

要访问第三个 &lt;p&gt; 元素，您可以这麼写：
<pre>var y=x[2];</pre>

## <span style="color:#800080;">parentNode、firstChild以及lastChild</span>

这三个属性 parentNode、firstChild 以及 lastChild 可遵循文档的结構，在文档中进行“短距離的旅行”。

请看下麵这个 HTML 片段：

<pre>&lt;table&gt;
  &lt;tr&gt;
    &lt;td&gt;John&lt;/td&gt;
    &lt;td&gt;Doe&lt;/td&gt;
    &lt;td&gt;Alaska&lt;/td&gt;
  &lt;/tr&gt;
&lt;/table&gt;</pre>

在上面的HTML代码中，第一个 &lt;td&gt; 是 &lt;tr&gt; 元素的首个子元素（firstChild），而最後一 个 &lt;td&gt; 是 &lt;tr&gt;元素的最後一个子元素（lastChild）。

此外，&lt;tr&gt; 是每个 &lt;td&gt;元 素的父节点（parentNode）。

对 firstChild 最普遍的用法是访问某个元素的文本：
<pre>var x=[a paragraph];
var text=x.firstChild.nodeValue;</pre><pre>parentNode 属性常被用来改变文档的结構。假设您希望从文档中删除带有 id 为 "maindiv" 的节点：</pre><pre>var x=document.getElementById("maindiv");
x.parentNode.removeChild(x);</pre>

首先，您需要找到带有指定 id 的节点，然後移至其父节点並执行 removeChild() 方法。

Link from : [http://hi.baidu.com/haomao/blog/item/4b8639c753bb3ad8d10060b0.html](http://hi.baidu.com/haomao/blog/item/4b8639c753bb3ad8d10060b0.html)<div class="blogger-post-footer">Copyright © 2018 helloworld4u.com All rights reserved.</div>