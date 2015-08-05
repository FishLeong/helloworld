对于我来说，最开始使用github主要是为了使用它的[pages](https://pages.github.com/)功能展示demo，比如[这样](http://hanzichi.github.io/particle/1.html)。其实这些都是用[Github for Windows](https://windows.github.com/) push上去的，图形化界面的客户端使用确实简单，但是逼格不够，好吧其实是各种原因下不了客户端，正好给我一个探索terminal方式的机会。 


###1、github账号注册 & msysgit的安装###
---
言归正传，简单介绍下怎样利用git bash操作远端的github代码。首先得有git和github的基本概念，git是版本控制工具，而github相当于一个“免费”的服务器了。然后可以注册个[github](https://github.com/)的账号，很简单，分分钟注册完。其次，得在本地安装[git for windows](msysgit)，安装完后，你会发现多了git bash和git gui。 

###2、[获取密钥](https://help.github.com/articles/generating-ssh-keys/)###
GitHub选择的默认通信方式是SSH，所以要先在Git里面生成SHH Key。如果在当前用户的第一级文件夹下有`.ssh`文件夹，说明以前可能使用过git，把该文件夹删除。  

获得密钥：

    ssh-keygen -t rsa -C "abc@gmail.com" //填写email地址，然后一直“回车”ok

打开本地..\\.ssh\id_rsa.pub文件。此文件里面内容为刚才生成的密钥。然后把该密钥复制到github的[setting/ssh](https://github.com/settings/ssh)中，点击打开页面的add SSH key按钮，title任意，把key值复制进去。

经过上述配置，你的Git应该可以通过SSH连接GitHub服务器了，可以测试一把：

    ssh -T git@github.com
比如提示像我这样：Hi hanzichi! You've successfully authenticated, but GitHub does not provide shell access. 那就说明连接成功了。

###3、远程操作###
接着就可以用terminal来操作github了，