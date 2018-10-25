---
title: hexo多设备同步与版本控制实现
date: 2018-10-26 00:34:07
tags:
---

##hexo多设备同步与版本控制实现

我们知道，hexo是一个静态网页个人博客，所有的资源和文件都是储存在本地的，但这样不利于实现网页的版本控制和随时随地发表博客，因此Google了一下hexo多设备同步的问题。 
##环境要求
已经能正常使用和deploy的hexo仓库，一个GitHub账号，对Git使用较为熟悉。

##使用网盘同步
最简单的方式其实就是直接把你博客的文件夹保存在网盘中，可自动实现同步。推荐使用OneDrive或者Google Drive。当需要使用新设备写作时，可直接复制这个文件夹，然后安装node.js和hexo即可。 
这种方法的好处当然是简单直观，但无法做到版本同步，作为计算机的学生，怎么能不使用GitHub进行同步呢~

##使用GitHub进行同步
使用分支搭建博客
其实，Hexo生成的网站文件中有.gitignore文件，因此它的本意也是想我们将Hexo生成的网站文件存放到GitHub上进行管理。

##博客搭建流程：
```
1. 创建仓库，youraccount.github.io 
2. 创建两个分支：master 与 hexo 
3. 设置hexo为默认分支（因为我们只需要手动管理这个分支上的Hexo网站文件，master分支为hexo deploy自动生成和管理） 
4. 使用git clone git@github.com:youraccount/youraccount.github.io.git拷贝仓库 
5. 在本地youraccount.github.io文件夹下通过Git bash依次执行npm install hexo、hexo init、npm install 和 npm install hexo-deployer-git（此时当前分支应显示为hexo） 
6. 修改_config.yml中的deploy参数，分支应为master 
7. 依次执行git add .、git commit -m “…”、git push origin hexo提交网站相关的文件 
8. 执行hexo generate -d生成网站并部署到GitHub上
```

这样一来，在GitHub上的youraccount.github.io仓库就有两个分支，一个hexo分支用来存放网站的原始文件，一个master分支用来存放生成的静态网页

##在新设备中安装node.js和Git
无需多说，直接安装：node.js，Git。

##给新设备添加SSH KEYS
在Git Bash中输入：

```
ssh-keygen -t rsa -C “你的邮箱地址”
```

按三次回车（密码为空），生成密匙。 
在C:\Users\Administrator.ssh中（Administrator为自己对应的管理员账号），得到两个文件，分别为id_rsa和id_rsa.pub。 
打开id_rsa.pub，复制全文。进入GitHub中的SSH设置 ，Add SSH key，粘贴进去。

##新设备同步
使用
```
git clone git@github.com:youraccount/youraccount.github.io.git
```
拷贝仓库（默认分支为hexo） 
在本地得到的youraccount.github.io文件夹下通过Git bash依次执行下列指令： 
```
npm install -g hexo
```
```
npm install
```
```
npm install hexo-deployer-git
```
即可将最新的博客文件全部同步。
##日常维护
在本地对博客进行修改（添加新博文、修改样式等等）后，通过下面的流程进行管理： 
1. 依次执行git add .、git commit -m “…”、git push origin hexo指令将改动推送到GitHub（此时当前分支应为hexo） 
2. 执行hexo generate -d发布网站到master分支上