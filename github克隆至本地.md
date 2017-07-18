## 从GitHub上克隆远程库到本地  ##

**前提**

- 要克隆的远程库不能为空，至少要有一个readme文件
- 既可以克隆GitHub上自己的远程库，也可以克隆GitHub上别人的远程库


**方法**

 - 使用指令`git clone git@github.com:qq564984789/gitskills.git` 或`git clone https://github.com/qq564984789/gitskills.git` 

其中，`qq564984789`是你要克隆远程库所在位置的github用户名，`gitskills`是远程库的名称。

**注意**：

- 如果是使用git第一次克隆远程库，会出现如下提示：
`Are you sure you want to continue connecting (yes/no)?`直接输入` yes`即可。
- 在任意文件路径下输入克隆指令就可以克隆远程库，无需先在本地创建git版本库
- 可以直接复制远程版本库页面的`Clone or Download`下的git指令（其实就是方法中的指令，不过帮你写好了），然后使用键盘的insert按键将指令粘贴到git bash里。

