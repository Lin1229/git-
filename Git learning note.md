# GIT 学习笔记
------
## 1. git安装及版本库

> 1. Windows可以从Git[官网](https://git-scm.com/downloads)下载安装程序，按照默认选项安装即可
> 2. 安装完成后打开Git Bash，在命令行输入
>  ```
> git config --global user.name "Your Name" 
> git config --global user.email "email@example.com" 
>  ```
> 3. 使用 `mkdir learngit`创建一个名为learngit的文件夹`cd learngit`进入文件夹
> 4. 在文件夹内通过`git init`把这个目录变为git管理的仓库（repo），版本库建立完成
> #### 本章代码总结
> > 1. mkdir <filename>     创建文件夹
> > 2. cd <filename>         切换到目标文件夹
> > 3. pdw                              显示当前目录
> > 4. cat <filename>         查看目标文件
> > 5.  ls                                  显示当前文件夹内容

## 2. 版本回退

> 1. 将文件加入版本库
> ```
> 1. git add <filename1><filename2>  将目标文件添加到缓存区(若文件名带有空格，则加上引号git add "learn git.txt")
> 2. git status               查看缓存区状态
> 3. git diff                  查看修改内容
> 4. git commit -m"message"  将缓存区中的文件提交到版本库中，并提交说明
> ```
> 2. 版本回退
> ```
> 1.使用git log 查看提交日志(git log --pretty=oneline可以显示简洁信息)(git log --graph可以查看分支合并图)(按Q键退出)
> 2.git reset --hard commit_id 回退到指定版本 (HEAD表示当前版本，HEAD^表示前一版本，HEAD~100表示前一百个版本)
> ```
> #### 本章代码总结
> > 1. mkdir <filename>     创建文件夹
> > 2. cd <filename>         切换到目标文件夹
> > 3. pdw                              显示当前目录
> > 4. cat <filename>         查看目标文件
> > 5.  ls                                  显示当前文件夹内容


