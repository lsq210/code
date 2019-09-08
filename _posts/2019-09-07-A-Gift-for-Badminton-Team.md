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
- [[fiddler]](https://www.telerik.com/fiddler) 对网页进行抓包，抢场主要分为三步：  
    1. 获取cookie，登陆账号  
    2. 查看当天是否开放抢场
    3. 如果是开放状态，预定场地
- [[electron-vue]](https://simulatedgreg.gitbooks.io/electron-vue/content/cn/) 利用 `vue-cli` 作为脚手架构造 `electron` 应用程序  

        // 安装 vue-cli 和 脚手架样板代码
        npm install -g vue-cli  
        vue init simulatedgreg/electron-vue my-project  

        // 安装依赖
        cd my-project  
        npm install // 或者yarn  

        // 本地运行
        npm run dev // 或者 yarn run dev  

        // 打包生成软件
        npm run build  

#### 模拟请求  
[axios](http://www.axios-js.com/) 是一个基于 promise 的 HTTP 库，可以用在浏览器和 node.js 中。  
以我的理解，就是一个用来向后台发送请求的工具。  
在vue构建的项目里，可用 `http` 代替 `axios`：
        
        Vue.http = Vue.prototype.$http = axios  

- 执行 GET 请求  

        this.$http.get(baseUrl)
            .then(function (response) {
            // handle success
            console.log(response)
            })
            .catch(function (error) {
            // handle error
            console.log(error)
            })

- 执行 POST 请求  

        this.$http.post(baseUrl, postContent)
            .then(function (response) {
            console.log(response)
            })
            .catch(function (error) {
            console.log(error)
            })

在`function createWindow ()`里添加每个请求访问的地址，特别要注意，`Header`里的内容一定要完全对应起来。  

#### 注意事项  
- 获取当前时间函数，**月份**是从 0 开始的。

        var time = new Date()
        var year = time.getFullYear()
        var month = time.getMonth() + 1
        var date = time.getDate()
        var hours = time.getHours()
        var minutes = time.getMinutes()
        var seconds = time.getSeconds()

- 函数的两种写法：

        // 普通函数
        function (parameter) {}  

        // 箭头函数
        (parameter) => {}  

#### 功能  
[x] 定时器
[ ] 自动获取 userId
[ ] 全自动抢场

##### 花絮
哈哈哈哈我觉得太中二了，还好这里没人💃

刚刚在写一个抢羽毛球场地的脚本。已经模拟了正常的预定场地功能，思考如何实现准点抢时——  
- 陶老师：你想想app显示的内容是从后台获取的。  
- 我：所以，不对后台发送请求就不能得到response？  
- 陶老师：是的，服务器一般不会主动发送。
- 我：哎，有点难过（叹气    
如果服务器不给我主动发送，我又怎么会知道。像爱一样，是想触碰又收回的手。

