---
layout:     post
title:      Jupyter notebook import package的问题
subtitle:   以及偶遇的sys.path
date:       2019-02-23
author:     Fernando
header-img: img/post-bg-re-vs-ng2.jpg
catalog: true
tags:
    - Python
---

#### 问题描述

由于Anaconda集成的包有限，需要用pip3安装sql相关的packege。但是本地的python3可以正常import，而Jupyter的解释器找不到该包。
于是在本地打开python3解释器后看了一下几个包import时的所在路径

![](https://ws4.sinaimg.cn/large/006tKfTcgy1g0nalhe2glj30vm0amdhp.jpg)

可以看到numpy的包在anaconda的site-packages里，而通过pip3安装的sql是在本地的python3的site-packages里。那说明Jupyter的python解释器和本地的python 解释器在import是搜索的路径不一样。


#### 解决办法
查了下博客园，貌似是sys.path这个东西在作怪。sys.path是python的搜索模块的路径集，是一个list。在本地查看的sys.path是这样的

![](https://ws4.sinaimg.cn/large/006tKfTcgy1g0nalkaz54j30vm06y0tx.jpg)

而在Jupyter输出的sys.path是少一个 `'/usr/local/lib/python3.7/site-packages'` 的, 所以没法importsql

###### 1. append()
既然sys.path是一个list，那最简单粗暴的方法就是往里面append你还想在import时候搜索的路径，在这里的话就是 `sys.path.append('/usr/local/lib/python3.7/site-packages')`. 但缺点显而易见，就是每一次重启Jupyter都得运行一遍这句话。

###### 2. PYTHONPATH
摘自博客园的一句话：
“使用PYTHONPATH环境变量，在这个环境变量中输入相关的路径，不同的路径之间用逗号（英文的！)分开，如果PYTHONPATH 变量还不存在，可以创建它！”
but 我试了下，并没有什么卵用，可能操作哦不是很得当（._.）

###### 3. **.pth**
使用.pth文件，在 site-packages 文件中创建.pth文件，将模块的路径写进去，一行一个路径，以下是我在`'/anaconda3/lib/python3.7/site-packages'`里创建的（.pth文件也可以使用注释）：

![](https://ws1.sinaimg.cn/large/006tKfTcgy1g0nbo12qa8j30vk04g74m.jpg)

#### 结果
重启了Jupyter以后， 一切正常o(^▽^)o
![](https://ws1.sinaimg.cn/large/006tKfTcgy1g0nbpxrjm7j31qa0jcq73.jpg)





