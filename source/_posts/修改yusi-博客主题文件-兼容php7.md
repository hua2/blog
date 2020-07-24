---
title: " 修改Yusi 博客主题文件 兼容php7\t\t"
tags:
  - Blog
  - PHP
  - 博客
id: '17'
date: 2018-04-24 15:45:44
---

找到主题文件header.php

<?php echo str\_replace("</ul></div>", "", ereg\_replace("<div\[^>\]\*><ul\[^>\]\*>", "", wp\_nav\_menu(array('theme\_location' => 'nav', 'echo' => false)) )); ?>

更改为：

<?php echo str\_replace("</ul></div>", "", preg\_replace("{<div\[^>\]\*><ul\[^>\]\*>}", "", wp\_nav\_menu(array('theme\_location' => 'nav', 'echo' => false)) )); ?>

然后覆盖更新文件即可使用。