---
title: close default net share in win10
date: 2018-02-07 06:56:53
tags:
    - win10
    - net share
    - windows service
    - regedit
---


- tpye `net share` in command window to check it


**fix**  

1.Open the registry editor.(`regedit`)

2.Navigate all the way to 
>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System.

3.Right-click in the pane on the right side and add a new `DWORD` (32-bit).

4.Give the new setting the name `LocalAccountTokenFilterPolicy`.

5.Double click on that setting and give it a value of 1.