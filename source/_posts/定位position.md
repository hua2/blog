---
title: " Position的属性值\t\t"
tags:
  - 其他
id: '44'
date: 2018-05-08 17:55:46
---

**1.fixed 定位：**

*   实现原理就是header和footer部分都为fixed定位。内容页面可以使用`-webkit-overflow-scrolling:touch`来进行滚动，当然，对于不支持的，也可以使用[iscroll](https://github.com/cubiq/iscroll)来兼容。
*   生成绝对定位的元素，相对于浏览器窗口进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。
*   元素框正常生成。块级元素生成一个矩形框，作为文档流的一部分，行内元素则会创建一个或多个行框，置于其父元素中。

**2.absolute是指绝对定位：**

*   生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。
*   元素框从文档流完全删除，并相对于其包含块定位。包含块可能是文档中的另一个元素或者是初始包含块。
*   元素原先在正常文档流中所占的空间会关闭，就好像元素原来不存在一样。元素定位后生成一个块级框，而不论原来它在正常流中生成何种类型的框。

**3.relative是指相对定位：** 生成相对定位的元素，相对于其正常位置进行定位；元素框偏移某个距离。元素仍保持其未定位前的形状，它原本所占的空间仍保留。因此，"left:20" 会向元素的 LEFT 位置添加 20 像素。 **4.static定位：**

*   默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right 或者 z-index 声明）。
*   元素框正常生成。块级元素生成一个矩形框，作为文档流的一部分，行内元素则会创建一个或多个行框，置于其父元素中。

**5\. inherit定位**：规定应该从父元素继承 position 属性的值。 ** flex布局：**设为 Flex 布局以后，子元素的`float`、`clear`和`vertical-align`属性将失效。

*   flex-direction（项目的排列方向）：`flex-direction: row | row-reverse | column | column-reverse;`
*   flex-wrap（换行方式）：`flex-wrap: nowrap | wrap | wrap-reverse;`
*   flex-flow：`flex-flow: <flex-direction> || <flex-wrap>;`
*   justify-content（在主轴上的对齐方式）：`justify-content: flex-start | flex-end | center | space-between | space-around;`
*   align-items（在交叉轴上如何对齐）：`align-items: flex-start | flex-end | center | baseline | stretch;`
*   align-content（多根轴线的对齐方式）：`align-content: flex-start | flex-end | center | space-between | space-around | stretch;`

Webkit 内核的浏览器，必须加上`-webkit`前缀。

    .box{
      display: -webkit-flex; /* Safari */
      display: flex;
    }