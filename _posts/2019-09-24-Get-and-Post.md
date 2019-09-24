---
layout: post
title: "Get and Post"
date: 2019-09-24 17:36:00
categories: HTTP
---
### 两种请求对比

HTTP 定义了与服务器交互的不同方法，最基本的4种分别是`GET`、`POST`、`PUT`、`DELETE`。  
URL 全称是资源描述符，我们可以这样认为：  
一个 URL 地址，它用于描述一个网络上的资源，而 HTTP 中的`GET`，`POST`，`PUT`，`DELETE`就对应着对这个资源的`查`，`改`，`增`，`删`4个操作。  
<br>
也就是说`GET`一般用于获取/查询资源信息，而`POST`一般用于更新资源信息。  
所以`GET`在信息修改层面，`GET`比`POST`安全。`GET`请求一般不应产生副作用。它仅仅是获取资源信息，就像数据库查询一样，不会修改，增加数据，不会影响资源的状态。

#### Get
- GET 请求标准上是幂等的（用户应该认为请求是安全的-资源不会被修改，这里所以说应该是服务器端并不保证资源不会被修改）
- GET 请求可以被浏览器缓存；响应也可以被缓存（根据缓存头信息来处理）
- GET 请求可以保存在浏览器历史记录中，也可以作为链接分发或分享，可以收藏为书签
- GET请求的数据都在 URL 中，可以方便都从浏览器中获取数据（因此不能携带诸如密码的明文数据）
- GET 请求的长度会有限制
- GET 请求的数据只能包含 ASCII 字符
- GET 请求发送的参数通过`config.url`获得，但不能传数组等一些数据结构，可将要发送的数据转成字符串`toString()`发送

        function getUrlQuery (url) {
            var query = url.split('?')[1]
            var pairObject = {}
            query.split('&').forEach(item => {
                var pair = item.split('=')
                pairObject[pair[0]] = pair[1]
            })
            return pairObject
        }
        // variable 是存储参数的一个对象
        var variable = getUrlQuery(config.url)
#### Post
- POST 请求标准上不是幂等的（用户应该认为请求是有副作用的，可能会导致资源修改）
- POST 请求URL可以被浏览器缓存，但是 POST 数据不会被缓存；响应可以被缓存（根据缓存头信息来处理）
- POST 请求不便于分发或分享，因为 POST 数据会丢失，不能收藏为书签。
- POST 请求没有长度限制，可以用来处理“请求数据”很大的场景（只要不超过服务器端的处理能力）
- POST 请求的数据不限于 ASCII 字符，可以包含二进制数据
- POST 请求的数据通过`config.body`获得
> 参考  
[HTTP 规范](http://www.ietf.org/rfc/rfc2616.txt)  
[REST](http://zh.wikipedia.org/wiki/REST) 一套支持 HTTP 规范的 RESTful 架构