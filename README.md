# git-upload
#linux本地上传GitHub

一 创建本地RSA
& cd ~/.ssh
& ll #查看是否有RSA
& ssh-keygen -t rsa -C "github注册邮箱"  #若无则创建，若有则更新，公钥在id_rsa.pub
$ eval "$(ssh-agent -s)" #如果git clone 网址出错，需要执行这两步
& ssh-add
& cat id_rsa.pub   #查看内容，全部复制内容

二 复制公钥到GitHub
在GitHub中Settings菜单，点击SSH and GPG keys,点击New SSH key,写标识，粘贴id_rsa.pub内容，点击Add SSH key.

三 创建远程仓库
点击New，填写repository name ，勾选Initialize this repository with a README后，就可以下一步了

四 测试
& mkdir php   #在任意目录创建
& cd php
& cp   ... ....   #把需要上传内容复制到php文件夹下
& git config --global user.email "github注册邮箱"  登陆GitHub
& git config --global user.name "github用户名"
& git clone git@github.com:用户名/php   #用户名，仓库名
& git init
& git add *
& git commit -m "test"  #引号内为添加的注释内容，不能
& git push https://用户名@github.com/用户名/仓库名.git     #弹出框输入GitHub登陆密码，提交成功
& git branch -a
