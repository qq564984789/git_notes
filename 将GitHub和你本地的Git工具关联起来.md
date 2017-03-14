## 将GitHub和本地的Git工具关联起来 ##

**前提**

- 注册一个GitHub账号



**方法**

 - 1、创建SSH Key。在用户主目录（~）下，看看有没有.ssh目录，如果有，再看看这个目录下有没有`id_rsa`和`id_rsa.pub`这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Git Bash，创建SSH Key：
`ssh-keygen -t rsa -C "15861884508@163.com"`

你需要把邮件地址换成你自己的邮件地址，然后一路回车，使用默认值即可，由于这个Key也不是用于军事目的，所以也无需设置密码。

- 2、登陆GitHub，打开“Settings”->“SSH and GPG Keys”页面：
然后，点“New SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容,点“Add Key”，你就应该看到已经添加的Key：

**注意**：

- GitHub允许你添加多个Key。假定你有若干电脑，你一会儿在公司提交，一会儿在家里提交，只要把每台电脑的Key都添加到GitHub，就可以在每台电脑上往GitHub推送了。
- 为什么GitHub需要SSH Key呢？因为GitHub需要识别出你推送的提交确实是你推送的，而不是别人冒充的，而Git支持SSH协议，所以，GitHub只要知道了你的公钥，就可以确认只有你自己才能推送。
