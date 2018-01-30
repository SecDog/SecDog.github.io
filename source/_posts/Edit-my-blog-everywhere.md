---
title: Edit my blog everywhere
date: 2018-01-29 23:34:04
tags:
---
---
title: clone my blog everywhere
date: 2018-01-30 15:04:47
tags: hexo, github pages
---

# 做一个换电脑也能编写的hexo博客


## 原理

Github其实是分的。User Pages 是用来展示用户的，而 Project Pages 是用来展示项目的。

下面的实现直接用User Pages的Master和Hexo分支来分别储存生成的静态页面和Hexo代码。

其中Hexo是主要分支，当换电脑的时候直接pull下来进行编辑修改发布，推送到Master分支上。Master分支只管Blog展示。

[具体原理参考](http://crazymilk.github.io/2015/12/28/GitHub-Pages-Hexo搭建博客/#more)



## github端准备

- 1.到Github上创建`你的用户名.github.io`项目，即你的Blog仓库。 
- Github如何设置SSH等在这里就略过了。
- 2.git clone到本地。
- 3.在本地git bash里创建`你的用户名.github.io`项目分支`hexo`
     
    ```git
    git branch hexo
    git add .
    git commit -m "newbranch hexo"
    git push origin master
    ```
      
- 4.在github里如图操作，将默认分支改成"hexo"，其实我觉得不改问题也不大，编辑的时候记得切换就好了。不过为了方便起见，我就改了。

![如图](/Edit-my-blog-everywhere/branchswtich.jpg)




## 平台端准备

### Win10准备

### Fedora准备

