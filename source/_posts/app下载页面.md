---
title: " App下载页面\t\t"
tags:
  - 其他
id: '115'
date: 2019-05-24 16:07:12
---

*   移动终端浏览器版本信息

    var browser = {

*   判断当前是否是微信浏览器

 `if ([browser.versions.ios)](http://192.168.3.80:8090/pages/browser.versions.ios)) { //判断是否是iOS`  
`}`  
`if ([browser.versions.android)](http://192.168.3.80:8090/pages/browser.versions.android)) { //判断是否是Android`  
`}` 

*   判断当前客户端是iOS还是Android  
    

    if (browser.versions.weixin) {

*   自动下载应用  
    

 [window.location](http://192.168.3.80:8090/pages/window.location) = androidDownUrl; //android下载地址