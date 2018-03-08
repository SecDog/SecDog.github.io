---
title: hexo tips
tags:
---


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

