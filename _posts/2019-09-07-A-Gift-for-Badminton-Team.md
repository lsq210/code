---
layout: post
title: "A Gift for Badminton Team"
date: 2019-09-07 23:56:00
categories: adventure
---
### 独家抢场软件🏸

由于羽毛球场只能在网上预约，而永远是僧多粥少的局面。  
既然拼不过手速，就只能拼技术了。  
于是，就有了这份为球队准备的小礼物。   

### 开发笔记  
#### 前期准备
- [[fiddler]](https://www.telerik.com/fiddler) 对网页进行抓包  
- [[electron-vue]](https://simulatedgreg.gitbooks.io/electron-vue/content/cn/) 利用 `vue-cli` 作为脚手架构造 `electron` 应用程序  

        // 安装 vue-cli 和 脚手架样板代码
        npm install -g vue-cli
        vue init simulatedgreg/electron-vue my-project  

        // 安装依赖并运行你的程序
        cd my-project
        yarn // 或者 npm install
        yarn run dev // 或者 npm run dev

#### 花絮
哈哈哈哈我觉得太中二了，还好这里没人💃

刚刚在写一个抢羽毛球场地的脚本。已经模拟了正常的预定场地功能，思考如何实现准点抢时——  
- 陶老师：你想想app显示的内容是从后台获取的。  
- 我：所以，不对后台发送请求就不能得到response？  
- 陶老师：是的，服务器一般不会主动发送。
- 我：哎，有点难过（叹气    
如果服务器不给我主动发送，我又怎么会知道。像爱一样，是想触碰又收回的手。

