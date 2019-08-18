---
layout: post
title: "My Blog"
date: 2019-07-29 23:33:27
categories: Travis
---
### 博客搭建笔记(●'◡'●)

#### 基本结构  
- [主页](https://lsq210.github.io/)  自己写了个简单的 html 作为个人主页，界面设计参考 [Archer](https://github.com/fi3ework/hexo-theme-archer) 主题。
- [生活流水账](https://lsq210.github.io/life/) 利用 Hexo 搭建，选取 [hollow](https://github.com/zchen9/hexo-theme-hollow) 主题，通过 [Travis CI](https://travis-ci.com/)实现了自动部署。
- [编程日记](https://lsq210.github.io/code/) 这个页面用了 [zchen9](https://github.com/zchen9) 的一个[仓库](https://github.com/zchen9/code)。

#### 一些笔记
##### 持续更新中...
- 网页无法向下滑动 原因：overflow-y: hidden   
   值|描述
   --|:--|
   visible|不裁剪内容，可能会显示在内容框之外
   hidden|裁剪内容，**不提供滚动机制**，不显示滚动条
   scroll|裁剪内容，**提供滚动机制**，显示滚动条
   auto|如果溢出框，则提供滚动机制，否则不显示
- 利用 v-for 对 a 标签进行循环时，相邻标签之间无换行也无空格。 
#### 感谢
💖 实在是太喜欢 [zchen9](https://github.com/zchen9) 小姐姐的博客风格了！！！于是就拿过来用了（如果有侵权啥的我立马换>< 在这里悄悄地表示感谢~  
😘 超级感谢为我解决千万 bug 的男朋友👉[一位不愿意透露姓名的前端大佬](https://github.com/CS-Tao)