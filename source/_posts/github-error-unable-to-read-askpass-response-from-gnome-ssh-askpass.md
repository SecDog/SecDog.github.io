---
title: 'github error: unable to read askpass response from gnome-ssh-askpass'
date: 2018-02-02 20:54:43
tags:
---






```
$cat /etc/profile.d/gnome-ssh-askpass.sh
SSH_ASKPASS=/usr/libexec/openssh/gnome-ssh-askpass 
```


# Fixed

>$unset SSH_ASKPASS

then

>$git push origin maste




