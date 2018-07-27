git：分布式版本控制系统

svn：集中式版本控制系统

Git本地仓库包含代码库还有历史库，在本地的环境开发就可以记录历史 而SVN的历史库存在于中央仓库，每次对比与提交代码都必须连接到中央仓库才能进行

这样的好处在于： 1、自己可以在脱机环境查看开发的版本历史 2、多人开发时如果充当中央仓库的Git仓库挂了，任何一个开发者的仓库都可以作为中央仓库进行服务

创建一个空文件夹

```
$ mkdir learngit  //创建文件夹
$ cd learngit    //打开文件
$ pwd   //显示当前目录
```

把这个目录变成Git可以管理的仓库

```
$ git init
```

第一步，用命令`git add`告诉Git，把文件添加到仓库

```
$ git add readme.txt    //添加文件
```

第二步，用命令`git commit`告诉Git，把文件提交到仓库

```
$ git commit -m "wrote a readme file"    //上传
```

运行`git status`命令看看结果

```
$ git status
# On branch master
# Changes not staged for commit:  //未提交的修改
```

要用`git diff`这个命令查看修改的内容

```
$ git diff readme.txt

git diff    #是工作区(work dict)和暂存区(stage)的比较
git diff --cached    #是暂存区(stage)和分支(master)的比较
```

要随时掌握工作区的状态，使用`git status`命令。

如果`git status`告诉你有文件被修改过，用`git diff`可以查看修改内容。

`git log`命令查看提交的历史记录

```
$ git log
```

```
$ git log --pretty=oneline   //只显示简单的记录
```

```
$ cat readme.txt     //查看文件内容
```

回退到哪个版本

既可以回退版本，也可以把暂存区的修改回退到工作区   $ git reset HEAD readme.txt

```
$ git reset --hard HEAD^
$ git reset --hard 版本号
```

把`readme.txt`文件在工作区的修改全部撤销

`git checkout -- readme.txt`

一种是`readme.txt`自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；

一种是`readme.txt`已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

删除工作区文件

```
$ rm test.txt    //删除工作区文件
$ git commit -m testme.txt     //上传
$ git checkout -- test.txt     //删错了
```

```
$ git push origin master   //push到版本库上
```

要关联一个远程库，使用命令`git remote add origin git@server-name:path/repo-name.git`；

关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容；

此后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改；

**增加分支**

1、我们创建`dev`分支，然后切换到`dev`分支：

```
$ git checkout -b dev
Switched to a new branch 'dev'
//相当于
$ git branch dev   //创建
$ git checkout dev   //分支切换到dev


//查看分支
$ git branch   //前面带 * 的是当前分支
//修改之后
$ git add readme.txt 
$ git commit -m "branch test"
//切换回master分支
$ git checkout master
//dev分支的工作成果合并到master分支上
$ git merge dev
//合并完成后，就可以放心地删除dev分支了
$ git branch -d dev
```

**解决冲突**

```
vi 文件名    //打开并编辑
大写两个ZZ    //保存并退出
:q         //强制退出
```

ls：查看在哪个文件夹

git clone 链接    克隆下代码

git branch  ：查看分支

在文件夹内 输入 git checkout -b 分支名字 创建分支

git add .   添加全部修改

git status  查看添加状态信息

git commit -m 'hometab'    提交到本地库

git push --set-upstream origin homemodel    提交到版本库

git branch   查看分支

git checkout master   切换到主分支

git branch  查看分支

git pull   首先在主分支上拉代码，

git checkout homemodel 切换到homemodel分支上

git rabase master    然后再从主分支上拉到  homemodel 分支上

git branch   查看分支



