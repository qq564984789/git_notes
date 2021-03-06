### 前提
- 本地内容已经包含git版本库
 (在本地路径下已使用过`git init`、`git add`和`git commit`命令)


### 方法步骤
1. 将本地仓库添加至远程库。
   ` git remote add origin git@github.com:qq564984789/Java.git`
> 其中Java.git是github上远程库的名称，origin是该远程库的别名（可以取其他名字）。
2. 将本地仓库内容推送至远程库。
    `git push -u origin master`
> 把本地库的内容推送到远程，用git push命令，实际上是把当前分支master推送到远程。由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。只需要使用`git push`即可。

### 注意：

1. 步骤1只有在第一次推送时使用，后面如果要推送，只要运行步骤2，且无需添加-u参数。即添加1次，就可以推送N次。
2. 如果远程库中本身有东西（和本地仓库内容不同），则需要先在本地仓库下运行：
   `git pull origin master`   
> 该指令是将远程库的内容先更新到本地。然后再运行
   `git push  origin master`
    将本地内容更新至远程库

3. 在步骤1执行后，可查看本地库是否添加成功，执行如下指令：
  `git remote -v`

4. 若要解除本地库和远程库的添加关系，执行如下指令：
  `git remote remove origin`
   其中origin是远程库的别名（根据步骤1中实际指定的别名来确定）
