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

## 2.git 基础操作

> 1. mkdir <filename>     创建文件夹
> 2. cd <filename>         切换到目标文件夹
>  3. pdw                              显示当前目录
>  4. cat <filename>         查看目标文件
>  5.  ls                                  显示当前文件夹内容

## 3. 版本回退

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
> 3.git reflog 查看操作纪录
> 4.git diff 查看工作区与版本库内最新版本区别
> ```
> 3.撤销修改
>
> ```
> 1.git checkout -- readme.txt 撤销工作区中readme.txt文件的修改
> （若未递交到暂存区，则退回到与版本库中相同，若提交到暂存区后又进行修改，则退回到添加到暂存区后代状态）
> 2.git reset HEAD readme.txt 撤销暂存区的修改，回退到工作区
> ```
> 4.删除文件
> ```
> 1.rm test.txt 删除文件
> 2.git rm test.txt 提交删除文件请求到暂存区，再使用git commit -m"" 命令删除版本库中文件
> 3.误删除可以使用git checkout -- test.txt 恢复
> ```

## 4. 远程仓库  

>1.本地仓库与远程仓库关联
>```
>1.登录github创建一个新的仓库
>2.在本地仓库中运行该指令 git remote add origin git@github.com:Yourname/reponame
>3.使用git push -u origin master 将本地库中所有内容推送到远程库中，-u是将本地库与远程库关联，下次使用push或pull时可以简化。
>4.关联成功后使用git push origin master 推送最新修改
>```
>2.从远程库克隆
>```
>1.git clone git@github.com:Lin1229/gitskills.git从远程仓库中克隆
>```

## 5.分支管理

> 1.创建合并分支
> ```
> 1.git checkout -b dev （等价于git branch dev和 git checkout dev）创建并切换到分支
> 2.也可以使用 git switch -c dev 创建并切换
> 3.git branch 查看当前分支
> 4.git merge dev 合并指定分支到当前分支
> 5.git branch -d dev 删除分支
> 6.git branch -D dev 强制删除
> ```
> 2.分支冲突
>
> ```
> 1.若不同分支的同一文件有不同修改，则会发生冲突
> 2.此时需要手动修改文件内容，修改完成后再commit提交
> ```
>
> 3.分支管理
> ```
> 1.合并分支时若使用Fast forward快速模式，删除分支后会丢失分支信息
> 2.若禁用快速模式合并时就会生成一个新的commit，则可以保留分支信息
> 3.git merge --no-ff -m"" dev 禁用快速模式合并，因为要创建新的commit所以要使用-m参数
> 
> ```




