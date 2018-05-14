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

```
$ git reset --hard HEAD^
$ git reset --hard 版本号
```



