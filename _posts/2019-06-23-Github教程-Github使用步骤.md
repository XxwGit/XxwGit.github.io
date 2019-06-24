---
layout:     post
title:      "Github使用教程"
subtitle:   " 详细介绍如何合理的使用github "
date:       2019-06-23 
author:     "Xxw"
header-img: "img/post-bg-digital-native.jpg"
catalog: true
tags:
    - github
    - git
    - 远程
---

> 作为一名码农，对于github应该是相当的熟悉，那么，如何才能使用合理的使用github，下面我将会对githubb进行详细讲解
### Github介绍
Github是目前世界上最先进的分布式版本控制系统。
如果你不知道什么是版本控制，请继续看下去。
那么什么才是版本控制，举个栗子，比如说你在写一段代码，实现一个功能保存一次，如果你想在这个上面进行其他的修改，你首先需要备份，防止实验出现问题，也就是你在编写的过程中会出现很多的版本，0.1-0.2-0.3------0.n,如果你是一次次的进行备份，那么过程将会特别的复杂，github实现的就是对于这些版本的控制，比如你想回到原来的版本，那么你只需要在github上进行版本回退即可。
### Github命令行使用
#### 使用命令将文件上传github
1.进入目标文件夹的上一个目录
2.shift+鼠标右键选择Git Bash Here进入github的命令行模式
3.输入git init 初始化本地仓库
4.输入git add . 添加所有文件到git
5.输入 git commit -m"更新提示"  代码更新 ，其中引号内输入更新的内容介绍
6.输入 git remote add origin -----  连接远程仓库，其中----填写GitHub仓库地址
注意：如果出现fatal:远程origin已存在，，这时候只需要将远程仓库删除即可，使用get remote rm origin随后再一次执行第六步
7.输入git push -u oringin master  提交代码即可。
#### 使用命令更新Github代码步骤（团队项目，即多个用户）
> 如果是个人用户，从第五步开始即可
1.在对代码进行更改之后，需要对GitHub上的代码进行更新
2.输入 git fetch origin master:tmp //从远程仓库master分支获取最新，在本地建立tmp分支
3.输入git diff tmp //將當前分支和tmp进行对比
4.输入git merge tmp //合并tmp分支到当前分支
5.输入git status 查看当前文件状态
6.输入git add . 提交到本地仓库
7.输入git commit -m""  更新提示"  代码更新 ，其中引号内输入更新的内容介绍
8.输入git push提交代码
#### 使用命令回退版本
1.首先查看提交记录 输入git reflog
2.根据各个版本的提交记录和提交的版本号使用命令进行版本回退，输入git reset --hard 版本号
### 总结