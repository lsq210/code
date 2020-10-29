---
title: Linux 命令行笔记
date: 2020-01-07 18:48:00
categories: Linux
---
### 学就完事💻

#### 文件系统中跳转
- `pwd` — 打印出当前工作目录名
- `cd` — 更改目录
- `ls` — 列出目录内容
- `file` — 确定文件类型
- `less` — 浏览文件内容，`q` 退出  
##### 复制和粘贴小技巧  
鼠标移动到想要复制的文件名上双击左键，即复制，再在命令行里单机右键，即粘贴啦。

#### 操作文件和目录
- `cp` — 复制文件和目录
- `mv` — 移动/重命名文件和目录
- `mkdir` — 创建目录
- `rm` — 删除文件和目录
- `ln` — 创建硬链接和符号链接   
##### rm 实例

   命令             |运行结果
   -----------------|:------
   rm file1         |默默地删除文件
   rm -i file1      |除了在删除文件之前，提示用户确认信息之外，和上面的命令作用一样
   rm -r file1 dir1 |删除文件 file1, 目录 dir1，及 dir1 中的内容
   rm -rf file1 dir1|同上，除了如果文件 file1，或目录 dir1 不存在的话，rm 仍会继续执行

#### 一些好用的命令  
##### screen 关闭远程连接，程序继续运行
- `screen -ls` 查看所有 screen 会话
- `screen -S name` 新建 screen 会话
- `screen -r name` 进入 screen 会话
-  ctrl + a + d 退出
-  ctrl + a + k 终止 
- `screen -X -S 1234 quit` 杀死 screen 会话  

##### 换源
- `sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak` 备份原来的source.list文件
- `sudo vim /etc/apt/sources.list` 修改sources.list文件
- 添加镜像源

      # 中科大镜像源
      deb https://mirrors.ustc.edu.cn/ubuntu/ bionic main restricted universe multiverse
      deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic main restricted universe multiverse
      deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
      deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
      deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
      deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
      deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
      deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
      deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
      deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
      # 阿里镜像源
      deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
      deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
      deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
      deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
      deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
      deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
      deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
      deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
      deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
      deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse

> 推荐阅读：[《快乐的 Linux 命令行》](http://billie66.github.io/TLCL/book/)