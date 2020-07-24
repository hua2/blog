---
title: " API Mocker\t\t"
tags:
  - 其他
id: '120'
date: 2019-05-27 15:49:39
---

### 服务端配置

初次启动项目，需要手动添加配置文件 `./server/config/core.js` 和 `./server/config/manager.js`

分别通过复制 `./server/config/default.core.js` 和 `./server/config/default.manager.js` 进行添加

注意：core.js 为配置 mongo 数据库，md5 key，邮件服务；manager.js 为初始化新建超级管理员账户。

 **core.js**   
  mongoose: {  
   url: 'mongodb://127.0.0.1/api-mock' //配置安装mongo的服务器地址  
 },

#### Client

*   `cd client && npm install && npm run dev`

#### [](https://github.com/DXY-F2E/api-mocker#server-1)Server

*   `cd server && npm install && npm run dev`

### [](https://github.com/DXY-F2E/api-mocker#%E5%8F%91%E5%B8%83%E5%90%AF%E5%8A%A8prods)发布启动(prods)

#### [](https://github.com/DXY-F2E/api-mocker#client-2)Client

*   `cd client && npm install && npm run build`

#### [](https://github.com/DXY-F2E/api-mocker#server-2)Server

*   `cd server && npm install && npm start`

默认端口号为7001

**注意：**

若npm依赖安装失败，用nrm切换源

全局安装： npm install -g nrm ；

查看当前源：nrm ls；

切换源：nrm use cnpm；

[参考链接：https://github.com/DXY-F2E/api-mocker.git](https://github.com/DXY-F2E/api-mocker.git)