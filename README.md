# 学习git

git学习

### linux常用命令：

`mkdir`：创建文件夹

`pwd`：当前在那个目录下

`ls`：显示当前文件夹

`ll`：详细显示文件夹或文件信息列表

`Ctr+l`：清屏

`rm -rf`：删除命令【慎重，这个命令很危险】

`touch`：新建文件

`mv`：改名称



### git全局配置

git config --global user.email "2363536014@qq.com"

git config --global user.name "woody_deng"



### 添加：

git add '文件名'/git add .

git status：查看状态

git commit -m '备注'：



### 版本库忽略文件配置

.gitignore

```php
*.txt // 所有.txt文件忽略
!a.txt //除了a.txt文件
```



### 删除：

git rm '文件名'：删除文件，同时删除本地和仓库

git rm --cached '文件名'：删除文件，把仓库删除，本地不删除



### 修改资料名称：

修改名称

git mv '原文件名' '新文件名'



### log日志查看

`git log`

`git log -p`：文件变动信息

`git log -p -1`：最近一次提交信息

`git log --oneline`

`git log --oneline -p`

`git log --name-only`

`git log --name-status`



### 修改最新一次提交名称

git commit --amend



### 分支branch基本管理操作

`git branch`：查看分支

`git branch ask`：创建ask分支

`git checkout ask`：切换到ask分支

`git checkout -b bbs`：创建bbs分支，并切换到bbs分支



### 分支合并与删除

`git merge ask`：合并ask分支【合并分支必须要做主分支master进行】

`git branch -d ask`：删除ask分支



### 处理分支冲突

需要人为进行处理



### merged与--no-merged及分支强制删除

`git branch --merged`：查看合并的分支

`git branch --no-merged`：查看没有合并的分支

`git branch -D test`：强制删除test分支【慎用大`D`参数】



### stash临时存储

`git stash`：临时存储

`git stash list `：查看暂存区列表

`git stash apply`或者`git stash apply stash@{0}`：恢复暂存区，不删除

`git stash drop stash@{0}`：删除暂存区

`git stash pop`：恢复暂存区，并删除



### TAG标签声明项目版本

`git tag`：查看版本标签

`git tag v1.0`：标记当前标签为V1.0版本

> 标签标记不可以随便标记，必须是项目是稳定才可以标记



### 生成ZIP代码发布压缩包

`git archive master --prefix='luocms/' --forma=zip > luocms.zip`



### 系统别名定义git全局指令

在 `~/ .bash_profile` 文件中定义

```
alias gs="git status"
alias gc="git commit -m "
alias gl="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit  "
alias gb="git branch"
alias ga="git add ."
alias go="git checkout"
```

 命令行直接使用 `gs` 即可以实现 `git status` 一样的效果

> windows 系统需要使用 git for window 中的 `Git Base` 软件



### rebase合理优化分支合并

`git rebase master` ：



### 本地与github进行关联

`git remote add origin 'github地址'`



### 额外知识

在git-bash中用sublime打开文件

配置方法

在git-bash的bin目录中`C:\Program Files\Git\bin` 【注意：这里是你本机安装git的bin目录】

在该目录下新建一个文件并以你想要的命令命名，如： `subl` 【注意不要带任何后缀】

代码如下：

```nginx
#!/bin/sh
"D:\Program Files\Sublime Text 3\sublime_text.exe" $1 &
```

`#!/bin/sh` : 这是个shell脚本

`"D:\Program Files\Sublime Text 3\sublime_text.exe"` ：这个是sublime安装的目录【根据自己本机安装的目录】

`$1` ：取的命令之后输入的参数

`$ `：此命令在后台打开，这样sublime打开之后，就不会阻塞您的git-bash

在此，git-bash利用sublime打开文件的配置就完成

`subl .gitignore`

