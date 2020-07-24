---
title: " CSS中 background属性\t\t"
tags:
  - 其他
id: '73'
date: 2018-06-06 11:52:56
---

****1.background-size:**** //规定背景图片的尺寸 例：background-size:80px 60px; background-size: 100% contain;

*   ****contain:****把图像图像扩展至最大尺寸，以使其宽度和高度完全适应内容区域。
*   ****length:**** __设置背景图像的高度和宽度.__ 第一个值设置宽度，第二个值设置高度。如果只设置一个值，则第二个值会被设置为 "auto"
*   ****percentage:****以父元素的百分比来设置背景图像的宽度和高度。第一个值设置宽度，第二个值设置高度。如果只设置一个值，则第二个值会被设置为 "auto"。
*   ****cover:****  把背景图像扩展至足够大，以使背景图像完全覆盖背景区域。背景图像的某些部分也许无法显示在背景定位区域中。

****2.background-position:**** //如何定位背景图像： 例：background-position: center 30%;

*   ****top left;**** top center; top right; center left;center center;center right;bottom left;bottom center;bottom right如果您仅规定了一个关键词，那么第二个值将是"center"。默认值：0% 0%。
*   ****x% y%:****第一个值是水平位置，第二个值是垂直位置。左上角是 0% 0%。右下角是 100% 100%。如果您仅规定了一个值，另一个值将是 50%
*   ****xpos ypos:****第一个值是水平位置，第二个值是垂直位置。左上角是 0 0。单位是像素 (0px 0px) 或任何其他的 CSS 单位。如果您仅规定了一个值，另一个值将是50%。您可以混合使用 % 和 position 值。

****3.background-repeat:**** //规定如何重复背景图像。 例：background-repeat: no-repeat;

*   ****repeat****:默认。背景图像将在垂直方向和水平方向重复。
*   ****repeat-x****:背景图像将在水平方向重复。
*   ****repeat-y:****背景图像将在垂直方向重复。
*   ****no-repeat:****背景图像将仅显示一次。
*   ****inherit:****规定应该从父元素继承 background-repeat 属性的设置。

****4.background-clip: border-box|padding-box|content-box;****

*   ****border-box:**** 背景被裁剪到边框盒。
*   ****padding-box:**** 背景被裁剪到内边距框。
*   ****content-box:**** 背景被裁剪到内容框。

****5.background-origin: padding-box|border-box|content-box;****

*   ****border-box:**** 背景图像相对于内边距框来定位。
*   ****padding-box:**** 背景图像相对于边框盒来定位。
*   ****content-box:**** 背景图像相对于内容框来定位****。****

****6.background-attachment:  scroll|fixed|inherit;****

*   ****scroll:**** 默认值。背景图像会随着页面其余部分的滚动而移动。
*   ****fixed:**** 当页面的其余部分滚动时，背景图像不会移动****。****
*   ****inherit:**** 规定应该从父元素继承 background-attachment 属性的设置。

**7.background-image**：//规定要使用的背景图片