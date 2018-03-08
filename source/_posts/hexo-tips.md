---
layout: post-toc
title: hexo-tips
date: 2018-03-08 03:29:11
tags:
---

# hexo

## All about `_config.yml` 

###  `could not read Username`

**Bug:**

>
hexo d ：give me fatal: could not read Username for 'https://github.com': No error  

**Fix:**  

>
gvim _config.yml


Replace *https://github.com/YourUsrName/YourUsrName.github.io.git*   
with *git@github.com:YourUsrName/YourUsrName.github.io.git*  

