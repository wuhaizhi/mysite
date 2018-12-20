# mysite
@[TOC](Git 入门教程)
# Git 入门教程
> `定义` Git是一个免费的版本系统，其特点有最优的存储能力、高效性能、开源、支持离线操作。

## Git 安装

### windows 安装

 先到[Git官网](https://git-scm.com/)下载Git安装程序：https://git-scm.com/download/win
 下载后直接点击安装就可以非常简单。
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20181216060908909.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)


### 在 Linux 上安装
如果你想在 Linux 上用二进制安装程序来安装 Git，可以使用发行版包含的基础软件包管理工具来安装。 如果以 Fedora 上为例，你可以使用 yum：

  `$ sudo yum install git`
如果你在基于 Debian 的发行版上，请尝试用 apt-get：

  `$ sudo apt-get install git`
要了解更多选择，Git 官方网站上有在各种 Unix 风格的系统上安装步骤，网址为 http://git-scm.com/download/linux。

### 在 Mac 上安装
在 Mac 上安装 Git 有多种方式。 最简单的方法是安装 Xcode Command Line Tools。 Mavericks （10.9） 或更高版本的系统中，在 Terminal 里尝试首次运行 git 命令即可。 如果没有安装过命令行开发者工具，将会提示你安装。

如果你想安装更新的版本，可以使用二进制安装程序。 官方维护的 OSX Git 安装程序可以在 Git 官方网站下载，网址为 http://git-scm.com/download/mac。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181216062103106.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)
Git OS X 安装程序。
Figure 7. Git OS X 安装程序.
你也可以将它作为 GitHub for Mac 的一部分来安装。 它们的图形化 Git 工具有一个安装命令行工具的选项。 你可以从 GitHub for Mac 网站下载该工具，网址为 http://mac.github.com。

## 简单配置
### 配置用户（user）信息
> 作提交的时候会显示当前配置的用户信息
* global 配置
```shell
git config --global user.name 'you name'
git config --global user.email 'you_email@XXX.com'
```

* local 配置
```shell
git config --local user.name 'you name'
git config --local user.email 'you_email@XXX.com'
```

* 区别
global是做用于全局的，如果某一个工作区设置了local会优先选用local信息。

* 查看配置
```shell
git config --list --global
git config --list --local
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20181216063803202.png)

## 创建Git仓库
```shell
# 新文件夹
mkdir lorl_project 

# 进入文件夹中
cd lorl_project

# 输入git init
git init

# 可以直接使用 git init lorl_porject 会自动创建文件夹
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181216064409566.png)

## Git常用的命令
> 以一个简单的Django项目为例

### Git中status查看工作区状态

我在工作区中添加一个 index.html文件
```shell
# 查看工作状态
git status
```
如下图：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181216191209843.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)

### 把文件添加到张缓存区 `git add` 后面可加多个文件或文件夹

```shell
git add db.sqlite3 lorl_porject/ manage.py
# 也可以使用 git add * 正则表达式来做批量提交，不推荐使用
```
查看状态 `git status` 文件已经放入暂存区：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181216191354600.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)

### 提交所有更改文件`git commit `

```shell
git commit -m'add file list'
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181216191847127.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)

### 可用用 `git commit -am''`方式，直接把文件放到暂存区
只用于版本库中存在的文件

### 查看log 日志
#### git自带工具 `gitk`
```shell
gitk --all
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181218093303133.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)

* 设置gitk显示 `view\New view`，跟椐自己需要进行设置
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181218093407701.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)

#### 使用`git --log`进行查询，常用命令 
##### 常用方式 `git log`
```shell
git log
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181218091156343.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)
##### 单行显示log信息 `git log --oneline`
```shell
git log --oneline
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/2018121809123356.png)
##### 指定最近log信息，取所有log最近4条
```shell
git log -n2 #-n2 后边可以修改为任意数字 
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181218091305285.png)
##### 查看本地分支
```shell
git branch -v
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181218091526304.png)
##### 查看log图形化
```shell
git log --oneline --all --graph
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181218092845588.png)

### 撤消操作
#### 修改最近一次log信息

修改 `bo134bc`信息为 ‘2 change index’
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181217135743130.png)

```shell
git commit --amend
```
弹出编辑，直接修改就可以
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181217135938344.png)
修改完成
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181217140050826.png)

### 暂存区与HEAD的比较
1、生成polls脚本文件并添加到暂存区，查看 `git status`
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181218095826463.png)

2、使用`git diff --cached`
```shell
git diff --cached
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181218100037995.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)


### 暂存区恢复为HEAD
1. 取消所有
```shell
git reset HEAD
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181219085504556.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)

2. 按文件来取消 `git reset HEAD <文件名>`
```shell
git reset HEAD manage.py
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181219085814708.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)

### 把取消工作区修改
我现把我工作区中，修改两个文件， manage.py mysite/urls.py
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181219090315168.png)

使用 `git checkout -- <文件名|文件夹名/>`
```shell
git checkout --manage.py mysite/
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181219090618880.png)

总结 `git reset` 和 `get checkout --` 区别，reset 是取消暂存区的修改， checkout -- 是取消工作的修改

### 回滚到以前版本 
```shell 
# 恢复到头指针
git reset HEAD 
# 恢复到指定指针
git reset --hard 指针id
```

### 查看不同提交的差异
```shell
git diff 分支 分支 --文件
git diff 指针1 指针2 --文件 
```

例：比较 0e038a2 和 c74d2da 两个指针下面的 polls\views.py 差异
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181220092135272.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)

### 删除文件
```shell
git rm 文件名
```

### Git 不用管理的文件
`.gitignore` 配置文件放到根目录下即可与 `.git`文件同级, GitHub网站上有针对不同语言.gitignore文件如果需要自行下载 https://github.com/github/gitignore
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181220091553604.png)

## GitHub - 账户的创建和配置
> GitHub 是最大的 Git 版本库托管商，是成千上万的开发者和项目能够合作进行的中心。 大部分 Git 版本库都托管在 GitHub，很多开源项目使用 GitHub 实现 Git 托管、问题追踪、代码审查以及其它事情。 所以，尽管这不是 Git 开源项目的直接部分，但如果想要专业地使用 Git，你将不可避免地与 GitHub 打交道，所以这依然是一个绝好的学习机会
### 账户的创建和配置
到 https://github.com/ 申请账户，输入用户名以及一些其他信息进行申请。
![在这里插入图片描述](https://img-blog.csdnimg.cn/2018121810073878.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)

### 生成 SSH 公钥

```shell
ssh-keygen
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/2018121810220026.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)
查看公钥
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181218102423390.png)

### 设置SSH 访问
给你的要添加的公钥起一个名字，把上边生成的公钥copy到下面的key中。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181218102603864.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTk1NjMwOA==,size_16,color_FFFFFF,t_70)
# 未完持续更新中
