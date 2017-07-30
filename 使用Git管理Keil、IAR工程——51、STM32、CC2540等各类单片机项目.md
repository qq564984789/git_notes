## 使用Git管理Keil、IAR工程——51、STM32、CC2540等各类单片机项目 ##

**前提**

- 在工程文件被Git管理之前，先在根目录下新建一个`.gitignore`文件：touch .gitignore。该文件主要用于过滤某些非源码文件，使其不被Git跟踪管理。
- `.gitignore`文件内容可以如下：
```
*.ewt        #所有.ewt文件都不被Git管理：内容有变化，不被跟踪
*.gitignore  #所有.gitignore文件都不被Git管理：内容有变化，不被跟踪
*.bat        #所有.bat文件都不被Git管理：内容有变化，不被跟踪
OBJ/*        #OBJ目录下的所有文件都不被跟踪
USER/UART.*  #USER目录下的所有以UART.开头的文件都不被跟踪
```

**方法**

 - 接下来使用指令`git init`,`git add .` 和`git commit - m "message"` 

其中，`git commit - m "message"`将所有项目文件(除了.gitignore文件中声明要过滤的文件)放入`.git`文件夹。

**注意**：

- 如果项目中的所有文件已经被Git管理起来了，怎么让某些文件不被继续管理呢?
  直接输入`git rm -r --cached .`这样，就会先把本地缓存删掉：也就是前面`git commit - m "message"`指令执行后被Git管理的文件都会重获自由——不被管理。
  这样，就回到了项目未被管理的一开始，继续前面的`前提+方法`。
