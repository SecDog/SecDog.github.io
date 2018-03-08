---
layout: post-toc
title: hexo-tips
date: 2018-03-08 03:29:11
tags:
---







### 1. _config.yml

####  could not read Username

**Bug:**

```
hexo d ：give me fatal: could not read Username for 'https://github.com': No error  
```

**Fix:**  

{% blockquote %}
    gvim _config.yml
{% endblockquote %}

Replace *https://github.com/YourUsrName/YourUsrName.github.io.git*   
with *git@github.com:YourUsrName/YourUsrName.github.io.git*  

***

### 2. 文章详情页面的设置

#### Toc目录的添加

1. 到*theme*文件夹下找到`layout/post.ejs`
2. 在`partial('casper/post', {post: page})`里发现调用的是`casper/post`
3. 到`layout/casper/post.ejs`里添加

{% blockquote %}
    <%- toc(page.content) %>
{% endblockquote %}

