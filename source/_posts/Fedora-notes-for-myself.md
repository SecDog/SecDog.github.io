---
title: Fedora notes for myself
date: 2018-02-02 06:23:12
tags:
---

### 1. Some tips

change to teminal without graphic

```
alt+ctrl+f3 
```


### 2.权限问题 

#### 2.1 普通用户无权限

##### Bug

想在普通用户中临时获得root权限时，却被提示:  “xxx 不在 sudoers 文件中。此事将被报告。” 

*PS：其中“xxx”为一个普通用户的用户名。*    

##### fix 

```shell
   su
```


之后输入root密码，切换到 **root** 用户

```shell

    visudo

```


*注：“vi”和“sudo”之间没有空格。*     

移动光标找到：

>“root    ALL=(ALL)       ALL” 1 “root    ALL=(ALL)       ALL”    

将光标停留在这一行，之后按下“o”键在这一行的下面插入一个空白行，输入：   

```shell
“xxx     ALL=(ALL)       ALL”   

```

*注：其中“xxx”为一个普通用户的用户名。*  

保存并退出。 

之后输入： 

```shell
sudo chmod 440 /etc/sudoers 1 sudo chmod 440 /etc/sudoers 
```


将“sudoers”的权限改为440.  至此该问题解决。
