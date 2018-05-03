---
title: ALL About Fedora in Hyper-V
date: 2018-05-04 00:58:50
tags:
---


# 关于Fedora的一切



### 更改hyper-v上的分辨率

[引用链接](https://stackoverflow.com/questions/18172319/windows-8-fedora-19-os-hyper-v-virtual-machine)

- Open a Terminal (Ctrl-Alt-T) 打开终端

- Run

  ```
  sudo vi /etc/default/grub
  ```

- Find the line starting with GRUB_CMDLINE_LINUX（*这个名字可能每个人的不同*）, and add

  ```
  video=hyperv_fb:[the resolution you want]
  ```

  If the resolution I want is 1280×720 then my line ends up looking like this:

  ```
  GRUB_CMDLINE_LINUX="… quiet splash video=hyperv_fb:1280×720"
  ```

- Write the changes and quit vi by hitting ESC and typing

  ```
  :wq
  ```

- Run:

  ```
  sudo grub2-mkconfig -o /boot/grub2/grub.cfg
  ```

- Reboot the virtual machine






### 用win10自带的ssh连接Fedora

- 检查Fedora端的ssh状态:

  ```
   /sbin/service sshd status
  ```

   如果运行了，则会回显:

   ```
   sshd (pid xxx) is running...
   ```

  如果没安装，则用下面的命令:

  ```
  su -
  yum install openssh-server
  ```

  如果安装了，但是Active显示为Dead，则开启:

  ```
  /sbin/service sshd start
  ```

- 防火墙的开启：

  通过软件商店，安装系统自带防火墙，安装完会自动勾选ssh（port22）端口。


- 文件传送命令：

  文件拖取：在win10打开powshell，键入命令，
  ```
  scp username@192.168.2.21:/home/demo/myfile.txt .
  ```

  文件传送：在win10打开powshell，键入命令，

  ```
  scp myfile.txt username@192.168.2.21:/home/demo/ 
  ```

  其中，192.168.2.21为Fedora端的IP地址

  

- 设置随机启动

  通过ntsysv 选中sshd服务
