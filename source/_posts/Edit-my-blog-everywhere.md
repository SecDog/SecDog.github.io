---
title: Edit my blog everywhere
date: 2018-01-29 23:34:04
tags: 
    - hexo
    - github pages
---



# 做一个换电脑也能编写的hexo博客

折腾了一个新的github pages，因为日常经常换电脑，也很烦云备份，所以参考了一下[这篇文字](http://crazymilk.github.io/2015/12/28/GitHub-Pages-Hexo搭建博客/#more)进行了配置，做了一些修改。


## 原理

Github其实是分的。User Pages 是用来展示用户的，而 Project Pages 是用来展示项目的。

下面的实现直接用User Pages的Master和Hexo分支来分别储存生成的静态页面和Hexo代码。

其中Hexo是主要分支，当换电脑的时候直接pull下来进行编辑修改发布，推送到Master分支上。Master分支只管Blog展示。


-----------------------





## github端

1.到Github上创建`你的用户名.github.io`项目，即你的Blog仓库。 
    Github如何设置SSH等在这里就略过了。
2.git clone到本地。
3.在本地git bash里创建`你的用户名.github.io`项目分支`hexo`
     
    ```git
    git branch hexo
    git add .
    git commit -m "newbranch hexo"
    git push origin master
    ```
      

4.在github里如图操作，将默认分支改成"hexo"，其实我觉得不改问题也不大，编辑的时候记得切换就好了。不过为了方便起见，我就改了。

![如图](/Edit-my-blog-everywhere/branchswtich.jpg)

下面跳到平台端


## 平台端

### Win10

1. 安装[git](https://git-scm.com),[node](http://nodejs.org/)。这里注意的是，直接去node网站下一个安装器就好了，别在命令行折腾，大坑。

2. 在刚才clone下来的`你的用户名.github.io`文件夹里新建一个hexo。
    一定要新建，否则等下'hexo init'会报错。因为目录里面有一个`.git`隐藏文件了。
    所以需要先到hexo目录下建好再拷贝出来。

3. 在`你的用户名.github.io`文件夹里打开git bash
4. 依次输入以下命令。
    
```git
git checkout hexo
npm install -g hexo-cli
hexo init hexo
cd hexo
npm install
```

5. 将hexo文件夹里的所有内容拷贝到`你的用户名.github.io`里。删除`hexo`
6. 修改`_config.yml`文件,将里面的`deploy`部分修改如下。
```
deploy:
  type: git
  repo: https://github.com/你的用户名/你的用户名.github.io
  branch: master
```

7. 测试,在`你的用户名.github.io`文件夹里打开git bash

```git
 npm install hexo-deployer-git --save
 hexo generate
 hexo server

```

然后去浏览器打开`localhost:4000`，看看是否成功。

8. 推送到hexo分支
```git
git add .
git commit -m 'hexo init'
git push origin hexo
```

9.接下来就是hexo的建站过程，写博文过程，略。
10.执行`hexo generate -d`生成网站并部署到GitHub上。







### Fedora准备

----------------------------------------------------------
## 日常操作

在本地对博客进行修改（添加新博文、修改样式等等）后，通过下面的流程进行管理：

1.依次执行git add .、git commit -m “…”、git push origin hexo指令将改动推送到GitHub（此时当前分支应为hexo）；
2.然后才执行hexo generate -d发布网站到master分支上。

虽然两个过程顺序调转一般不会有问题，不过逻辑上这样的顺序是绝对没问题的（例如突然死机要重装了，悲催….的情况，调转顺序就有问题了）。