---
layout: post
title: "Puzzlement about Travis"
date: 2019-07-29 23:33:27
categories: Travis
abstract: 激活的仓库为何消失？下午从未失手的部署晚上为何频频失败？究竟是程序猿的过失还是网站的bug，让我们走进今日迷惑之travis
---
😀我还能心平气和地敲下摘要，是因为谜团终于解开了，我，终于可以安心地睡觉了  

然而，就在十分钟前，我还处于😡👿🤬的状态。

事情是这样的。下午折腾好久将github仓库和travis连好了，本以为以后就可以靠着travis过上懒人博主的生活。结果！晚上就给我一个暴击！

开心地push到github上之后，博客却迟迟没有更新，点进travis官网，发现我的仓库竟然没有激活，我？？？？一脸懵逼，搞不清状况，然后又重新生成token，把下午的操作重来了一遍，依然无尽的failed。就在查找错误原因的过程，看见有人说travis有两个网站....  
我一看，下午进的是travis.com，晚上进的是travis.org（我就说为啥晚上进又要重新登陆）
>https://travis-ci.com
>https://www.travis-ci.org/

敢情两个一模一样的网站竟然是不同的，我真的晕了Orz
虽然还没弄清楚这两个网站的关系，但我要睡觉了哈哈哈，一切留给明天吧~ good night🌙