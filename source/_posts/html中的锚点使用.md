---
title: " html中的锚点使用\t\t"
tags:
  - 其他
id: '99'
date: 2019-03-20 16:08:00
---

锚点是网页制作中超级链接的一种，又叫[命名锚记](http://baike.baidu.com/view/1153353.htm)。命名锚记像一个迅速[定位器](https://www.baidu.com/s?wd=%E5%AE%9A%E4%BD%8D%E5%99%A8&tn=24004469_oem_dg&rsv_dl=gh_pl_sl_csd)一样是一种页面内的超级链接，运用相当普遍。

在HTML页面中适当位置定义如下的锚点：  
<a name="top">这里是TOP部分</a>  
<a name="content">这里是CONTENT部分</a>  
<a name="foot">这里是FOOT部分</a>  
（也可以使用 id 属性来替代 name 属性，命名锚同样有效）  
对于如上锚点的访问有两种方法：  
一种是利用超链接标签<a></a>制作锚点链接，主要用于页面内的锚点访问  
<a href="#top">点击我链接到TOP</a>  
<a href="#content">点击我链接到CONTENT</a>  
<a href="#foot">点击我链接到FOOT</a>  
另一种方式是直接在页面地址后面加锚点标记，主要用于不同页面之间的锚点访问  
假如本页面的地址是http://文件路径/index.html，要访问foot锚点只要访问如下链接即可  
http://文件路径/index.html#foot

代码：  
<a href="#001">跳到001</a>  
...文字省略  
<a name="001" id="001" ></a>  
...文字省略

其实锚点只需name就可以了，加id是为了让它兼容性更好.  
href的值要跟name \\ i d 一致，前面必须加"#"，以上代码在ie6/7,ff中都可以兼容，但在ie8中就不行。  
因为我们锚点的<a></a>值为空，为不影响美观我们加个空格就行了,

如以下代码，就可以兼容ie8  
<a href="#001">跳到001</a>  
...文字省略  
<a name="001" id="001" > & n b s p  </a>  
...文字省略

另一问题，想显示某页面(如：123.html)的某锚点内容呢？

代码如下  
<a href="123.html#001">跳到001</a>  
...文字省略  
<a name="001" id="001" > & n b s p </a>  
...文字省略

示例代码：  
<html>  
<body>  
<p>  
<a href="#method1">页面锚点方法一</a>  
</p>  
<p>  
<a href="#method2">页面锚点方法二</a>  
</p>  
<h2><a name="method1">方法一</a></h2>  
<p>使用锚标签的 href 和 name 属性</p>  
<h2 id="method2">方法二</h2>  
<p>使用锚标签和 id 属性</p>  
</body>  
</html>