---
title: 'github error: unable to read askpass response from gnome-ssh-askpass' 
date: 2018-02-02 20:54:43
tags:  
    - github
    - Fedaro
    - ssh
---



I was trying to push within Aptana but got the following error.

```
error: unable to read askpass response from gnome-ssh-askpass
```

> $cat /etc/profile.d/gnome-ssh-askpass.sh

It would be showed like this:

```
SSH_ASKPASS=/usr/libexec/openssh/gnome-ssh-askpass 
```


# Fixed

> $unset SSH_ASKPASS

then

>$git push origin maste







[Ref:](https://www.snip2code.com/Snippet/735288/github-error--unable-to-read-askpass-res/)
