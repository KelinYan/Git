# GIT


[话说Svn与Git的区别](http://www.jianshu.com/p/bfec042349ca)

[官方文档](https://git-scm.com/book/zh/v2)

[廖雪峰的git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
## 介绍
 - git是一个分布式管理工具，区别于svn，他拥有集中的服务器同时每个客户端都是一个仓库



 #### 常用的命令


 - git init
 - git add
 - git commit
 - git push
 - git stutas
 - git log
 - git diff


#### git分支的操作命令
 - git checkout -b
 - git branch
 - git merge
 - git log --graph


 #### 更改提交的操作
 - git reset
 - git commit -- amend
 - git rebase -i

 #### 提交到远程仓库
 - git remote add
 - git push
 - git pull
 - git fetch


 #### 从远程仓库获取
 - git clone
 - git fetch
 - git feature -D



#### pull request

gitlab github 配置ssh

git flow git多人协作及版本控制的流程



#### git submoudle



### git存储的介绍
git存储的是文件的快照
>关于指定数据集合的一个完全可用拷贝，该拷贝包括相应数据在某个时间点（拷贝开始的时间点）的映像


每次你提交更新，或在 Git 中保存项目状态时，它主要对当时的全部文件制作一个快照并保存这个快照的索引。 为了高效，如果文件没有修改，Git 不再重新存储该文件，而是只保留一个链接指向之前存储的文件。

 - 近乎于所有的操作都在本地进行，本地的仓库中保存了所有的历史数据，并且没有网络的时候也可以在本地进行提交。
 - Git 保证完整性
 - Git 一般只添加数据

### git的三种状态
>已提交（committed
已修改（modified）
已暂存（staged)


## git 命令行

- git config --list   查看个人配置的信息  
- git config user.name 配置用户名 改名称在每次提交的时候都会使用到


# git 使用流程

- 创建git仓库
  - git init
  - git add . (想要添加的文件，一般都使用。添加所有的文件)
  - git commit -m "commit message"

- 更改git配置
  - 配置个人信息
    > git config --global user.name xyz
  - 配置大小写敏感
    > git config core.ignorecase false
  - 设置别名
    > git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset-%C(yellow)%d%Creset%s%Cgreen(%cr)%C(bold blue)<%an>%Creset'
--abbrev-commit"

- 提交操作的修改
  - git commit -amend  （尝试重新提交）
  - git reset HEAD git.md （取消该文件的暂存）
  - git checkout -- git.md （撤销对该文件的修改）危险命令，会撤销所有的修改

- 从已经存在的仓库克隆项目
  - git clone git@github.com:KelinYan/Git.git
 
- 查看当前的状态
  - git status 查看当前文件存储的状态
  - git branch 查看分支状态
  - git branch -a 查看所有的分支

- 添加ignore文件

- 文件对比
  - git diff 使用该命令对比当前文件和暂存区域快照之间的差异，修改之后还没有暂存起来的内容
  - git diff --cached （--staged）查看已经暂存的将要添加到下次提交的内容

- 版本回退 时光倒流
  - git log 查看提交的日志，
  - git log -stat 查看每次提交的简略的统计信息
  - git reset --hard 版本信息  --根据生成的sha-1对应版本进行回退
  > HEAD 表示当前的版本，HEAD^表示上一个版本，以此类推，版本迭代太多的话可以使用HEAD~100

- 撤销版本回退 回到未来
  - git reflog 查看操作的日志
  - git reset --hard 版本信息  -- 还原到该操作时间点的版本


## git 打标签


## git分支 必杀特技

 ### 简介
 > 



## git版本库

- 工作区 
  >我们看到的文件夹就是一个工作区
- 暂存区  
  >我们git add 之后就会将修改存储在暂存区
- 分支
  >我们git commit之后提交到分支

    - git diff    是工作区(work dict)和暂存区(stage)的比较
    - git diff --cached    #是暂存区(stage)和分支(master)的比较

```flow
st=>start: 开始
e=>end: 结束
op=>operation: 我的操作
cond=>condition: 确认？
st->op->cond
cond(yes)->e
cond(no)->op
```











 
