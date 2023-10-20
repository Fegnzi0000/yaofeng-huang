# 作业
## [作业链接](https://github.com/liyixin135/git_2023/blob/master/_2023-finalproject/README.md)
https://github.com/liyixin135/git_2023/blob/master/_2023-finalproject/README.md
# git学习

## 一、为什么要学git

### <font color=#008000>简答：方便团队合作、对历史修改进行跟踪等</font>

## 二、git是什么

### <font color=#008000>版本控制系统</font>

##### 备注：什么是版本控制？

##### 版本控制是一种<font color=#008000>记录</font>一个或若干文件<font color=#008000>内容变化</font>，以便将来查阅特定版本修订情况的系统。

## 三、git原理

### 1. 底层实现原理，具体看以下链接：

#### [git底层原理（点击）](http://chuquan.me/2022/05/21/understand-principle-of-git/)
备注：这个不讲，将进行简单讲解，方便理解，有兴趣深入了解的可以自行学习
### 2.简单理解
#### <1> 简单概念认识

##### git基本组成框架：Workspace(工作区)、Index / Stage(缓存区)、Repository(本地仓库)、Remote(远程仓库)

* * *

##### Workspace(工作区)：你当前的工作目录

---

##### Index / Stage(缓存区)：存在git add命令提交的文件描述信息，位于.git（隐藏目录）的index文件中

---

##### Repository(本地仓库)：一般理解为在自己电脑上被git管理的文件

---

##### Remote(远程仓库)：一般理解为github上的仓库

---

##### 主支为master或者main

* * *

##### git分支类型：<br>本地分支<br>本地远程分支<br>远程分支

### 3. 初次使用git

#### <1>下载git

```
sudo apt install git
```

备注：找不到可按tab键补齐

#### <2>配置git环境（将本地与远程进行搭建）

##### 初次使用git需要设置你的用户名以及邮箱，有两种方法。

方法一：直接配置

用户名配置

```
git config --global user.name "你的github用户名"
```

邮箱配置

```
git config --global user.email "你github注册时使用的邮箱"
```

方法二：被动设置（我自己取的名字

当你在本地clone其他仓库时，本地终端会要求你手动输入用户名、邮箱和密码，输入完成后也可以完成设置。

### 4. git简单命令

#### <1>创建本地空仓库

```
mkdir test
cd test
git init
```

备注：此时可用ls -ah查看隐藏目录

#### <2>查看文件是否做了改动

```
git status
```

备注：status查看当前仓库状态

#### <3>新建文件添加到本地仓库(跟在<1>后面)

```
cd test
touch test.md
git status
git add test.md
git status
git commit -m "Add new file."
```

解释：

```
add:将文件添加到缓存区
commit：提交到本地仓库
```
##### 拓展：
将所有改动文件添加到缓存区
```
git add --all
```
注意事项：git commit -m ""：""中为 对新版本做出的修改做出简单的描述，队内要求为1首字母大写，2英文描述，3要有句号。

不小心写错描述如何修改：

```
git commit --amend
```

（自行摸索用法

#### <4>查看历史提交日志

```
git log
```

（自行操作去看

---

#### 查看提交历史

```
git reflog
```

可以查看当前版本库的提交历史，凡是对仓库版本进行迭代的都会出现在这个里面

#### <5>各种回退
先git flog查看版本，选择要回退的版本
```
git reset --hard 要回滚版本
```
回到所在分支的上次版本
```
git reset --hard HEAD^
```
回到所在分支的前n次版本，例如前三次
```
git reset --hard HEAD~3
```
#### <6>建立和切换分支
创建新分支
```
git branch 分支名
```
备注：可用git branch查看分支<br>
切换分支
```
git checkout 分支名
```
创建并切换新分支
```
git checkout -b 分支名
```
注意事项：若切换分支前，所在分支存在未commit的内容，会把这部分未commit内容连带到所切分支上
##### 解决方案，保存当前工作切换分支：
```
git stash
```
此时就不需要担心未commit内容连带到所切分支上
查看当前存储了多少工作状态
```
git stash list
```
切换会原来的分支，将状态恢复
```
git stash pop
```
备注：git stash还会别的命令（自行搜索理解）。<br>准确来说，git stash的作用就是为了解决git不提交代码不能切换分支的问题。
#### <7>从github拉取git仓库
```
git clone [url]
```
##### 我们统一使用ssh协议
首次使用要配置ssh key，在网上随便找个教程看看吧（我写不动了
##### 为什么要使用ssh协议？
配了ssh才能实现push代码的时候不需要反复输入自己的github账号密码，更方便。配置的时候是把当前主机的公钥放到了你的github账号下，相当于当前主机和你的github账号做了一个关联，你在这台主机上已经登录了你的账号，此时此刻github认为是该账号主人在操作这台主机，在配置ssh后就信任该主机了。
#### <8>合并分支
```
git merge 分支
```
## 四、实操
### 1.从github拉取代码
### 2.开pr（pull request）
### 3.clion简单使用
