---
title: Personal AutoHotkey Script
date: 2018-02-02 06:05:14
tags:
    - AutoHotkey
    - Personal
---




#### Run `sublime.exe` by `win`+`ctrl`+`s`

* Put the path of `sublime fold` into `enviroment variable` > `globe path`. Now you can simply type `subl` in `cmd` window to call `sublime.exe`.
* Edit `yourAutoHotkey.ahk', put the code into it.

```
#^s::
run, subl
return
```

`#`=`win`  

`^`=`ctrl`


--------------------------------------------------------------------------


#### Auto input my Email address by `m@`

* put `::m@:: abc@xxx.com` into `yourAutoHotkey.ahk'.

 *PS: change `abc` to `your email`*

* open notepad.exe and simply input `m@` then put down `space`.



--------------------------------------------------------------------------