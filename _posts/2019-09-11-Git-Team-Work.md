---
layout: post
title: "Git Team Work"
date: 2019-09-07 23:56:00
categories: git
---
### Git 团队合作指南

> version 1.1

#### 下载项目

```bash
git clone https://github.com/lsq210/EasyPay.git
```

#### 从 develop 新建分支

- 方法一：先切换到 develop 分支，再新建

  ```bash
  git checkout develop
  git checkout -b <新分支名字如 add-header>
  ```

- 方法二：直接新建

  ```bash
  git checkout -b <新分支名字如 add-header> origin/develop
  ```

#### 添加新功能的部分代码

- bug1
- bug2
- feature1/4
- bug4
- fix bug1

#### 提交代码

1. 保存到暂存区

   ```bash
   # 暂存所有修改
   git add .
   # 或暂存指定文件
   git add <文件1名> <文件2名> ...
   ```

2. 将暂存区的修改提交到本地仓库

   ```bash
   git commit -m "这里输入本次提交的消息如 添加界面头部"
   ```

3. 提交代码到远程分支

   ```bash
   git push origin <分支名字如之前添加的 add-header>
   ```

#### 继续修改代码并提交代码

此处略去若干重复操作

#### 新功能添加完成后合并到 develop 分支并提交到远程

1. 更新本地的 develop 分支，使之和远程最新的 develop 分支保持一致

   ```bash
   git pull origin develop
   ```

2. 合并新分支到 develop 分支

   ```bash
   # 将新分支的所有提交移到 develop 分支的最前端，采用“变基”的方式
   git rebase develop

   # 将新分支合并到 develop 分支
   git checkout develop
   git merge --no-ff <分支名字如之前添加的 add-header>
   ```

3. 将 develop 分支的新提交 push 到远程

   ```bash
   git push origin develop
   ```

#### 删除新功能分支

1. 删除本地分支

   ```bash
   git branch -m <新分支名字如 add-header>
   ```

2. 删除远程分支

   ```bash
   git push origin :<新分支名字(冒号后无空格)如 add-header>
   ```

#### 下一个功能...

1. 新建分支
2. 提交代码
3. 合并新分支到 develop
4. 更新远程
5. ...
6. ...

#### 发布新版本(组长操作)

1. 在 develop 分支上修改 package.json 中的 version 字段，改为新的版本号

2. 将 develop 分支合并到 master 分支

   ```bash
   git checkout master
   git merge --no-ff develop
   ```

3. 打新版本 tag

   ```bash
   # 以 v1.0.2 为例
   git tag v1.0.2
   ```

4. 更新远程 master 分支和新 tag

   ```bash
   git push origin master --tags
   ```

> 感谢 [@小陶老师](https://github.com/CS-Tao)