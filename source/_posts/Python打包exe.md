---
title: Python打包exe
description: pyinstaller使用
date: 2023-05-9 16:10:00
updated: 2023-05-9 16:10:00
tags:
  - Python
categories:
  - 开发
swiper_index: 1
---

## 使用pyinstaller打包

在pycharm中点击**新建环境**

![image-20230509165923855](https://cdn.staticaly.com/gh/Wang-weijun/pic_bed@main/img/image-20230509165923855.png)

进入文件后，会有一个文件夹`venv`，用来存放管理的库文件

### 创建requirements.txt

~~~shell
pip install requests
~~~

~~~shell
pip freeze > requirements.txt
~~~

![image-20230509170609691](https://cdn.staticaly.com/gh/Wang-weijun/pic_bed@main/img/image-20230509170609691.png)

可以看到虚拟环境下安装的包



## 安装pyinstaller

~~~shell
pip install pyinstaller
~~~

安装完成后将终端关闭，**重新打开**

我们输入`pyinstaller`，当出现一下结果，说明安装成功

![image-20230509171248558](https://cdn.staticaly.com/gh/Wang-weijun/pic_bed@main/img/image-20230509171248558.png)



### 单文件打包

~~~shell
pyinstaller -D app.py
~~~

开始打包

![image-20230509171708499](https://cdn.staticaly.com/gh/Wang-weijun/pic_bed@main/img/image-20230509171708499.png)

之后在当前文件夹会出现三个文件

+ **build**：中间编译时，产出的文件
+ **dist**：打包生成后的文件目录
+ **xxx.spec**：打包的配置文件

在`dist`中可以看到有我们上面起的名字`app`，只需将**app文件夹**发给他人，打开里面的**app.exe**文件，即可使用













