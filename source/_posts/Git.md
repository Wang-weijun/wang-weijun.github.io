---
title: Git
description: Git学习
date: 2023-05-12 1:0:00
updated: 2023-05-12 1:0:00
tags:
  - Git
categories:
  - 技术栈
swiper_index: 1 # 置顶权重
---

> git config --global user.name #name	设置用户签名

> git config --global user.email #email	设置用户邮箱

---

> git init	初始化本地库

> git status	本地库状态

~~~shell
$ git status	本地库状态
On branch master

No commits yet	

nothing to commit (create/copy files and use "git add" to track)	# 还没有文件

$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test.txt

nothing added to commit but untracked files present (use "git add" to track)
~~~

> git add #filename

~~~
~~~



> git config --list    #查看git配置信息

![image-20230512200827202](https://cdn.staticaly.com/gh/Wang-weijun/pic_bed@main/img/image-20230512200827202.png)



查看用户名，密码和邮箱命令：

~~~bash
git config user.name 
git config user.password 
git config user.email 
~~~

设置或修改用户名，密码和邮箱命令：

~~~bash
git config --global user.name "freedom"
git config --global user.password "123456"
git config --global user.email "12345678@qq.com"
~~~













## Git分支 

> 切换分支

```Shell
git checkout branchName
```

> 查看分支

```Shell
git branch -a
```









## 使用码云

1. 注册登录，完善信息
2. 设置本机绑定SSH密钥，实现免密码登录

~~~bash
# 进入C:\Users\Admin\.ssh
# 生成公钥
ssh-keygen -t rsa
~~~

![image-20230512201232227](https://cdn.staticaly.com/gh/Wang-weijun/pic_bed@main/img/image-20230512201232227.png)

3. 添加密钥到码云

![image-20230512201245102](https://cdn.staticaly.com/gh/Wang-weijun/pic_bed@main/img/image-20230512201245102.png)

4. 使用码云创建自己的仓库

许可证：开源是否可以随意转载，开源但不能商业使用、不能转载，...限制



5. 克隆自己的仓库

![image-20230512201252646](https://cdn.staticaly.com/gh/Wang-weijun/pic_bed@main/img/image-20230512201252646.png)





















## Idea集成Git











