---
title: hexo d ：give me fatal: could not read Username for 'https://github.com': No error 
date: 2018-03-06 09:55:19
tags:
---

## Bug

> hexo -d

echo on the bash：

`give me fatal: could not read Username for 'https://github.com': No error `  

## Fix


- [ ] Open `_config.yml`  

- [ ] replace `https://github.com/zhangxiangqiang/zhangxiangqiang.github.io.git`whith `repo: git@github.com:zhangxiangqiang/zhangxiangqiang.github.io.git`