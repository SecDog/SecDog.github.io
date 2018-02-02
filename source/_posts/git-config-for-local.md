---
title: 为本地仓库分别设置独立的Git config
date: 2018-01-30 18:10:16
tags:
- git
- git config
---



有时候不只一个github账户，gitpages上博客都好几个，为了省去切换的麻烦，我采用的方式是在每一个blog文件夹里设置。

```
git config user.name "YourName"
git config user.email "YourEmail"
```

这里不使用`--global`是为了避免影响全局。


~PS: 更多的参数直接在bash里敲`git config`有详细说明。 
