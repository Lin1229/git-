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
>  4. cat <filename>         查看目标文件 cat -n或cat -b 给文件各项编号
>  5.  ls                                  显示当前文件夹内容 ls -l 列出文件详细信息 ls -a 查看所有文件包括隐藏文件
>  6. mv <filename_1>   <filename_2>
>  ```
>  1.若文件12都存在，则删除文件2，文件1重命名为文件2
>  2.若1存在2不存在，则将1重命名为2
>  3.若1为文件 2为文件夹，则将1移动到文件夹中
>  ```
> 7. touch  <filename> 创建文件 

## 3. 版本回退

> 1. 将文件加入版本库
> ```
> 1. git add <filename1><filename2>  将目标文件添加到缓存区(若文件名带有空格，则加上引号git add "learn git.txt")
> 2. git add -A 添加所有文件
> 3. git status               查看缓存区状态
> 4. git diff                  查看修改内容
> 5. git commit -m"message"  将缓存区中的文件提交到版本库中，并提交说明
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

>1. 本地仓库与远程仓库关联
>```
>1.登录github创建一个新的仓库
>2.在本地仓库中运行该指令 git remote add origin git@github.com:Yourname/reponame
>3.使用git push -u origin master 将本地库中所有内容推送到远程库中，-u是将本地库与远程库关联，下次使用push或pull时可以简化。
>4.关联成功后使用git push origin master 推送最新修改
>```
>2. 从远程库克隆
>
>```
>1.git clone git@github.com:Lin1229/gitskills.git从远程仓库中克隆
>2.默认情况下本地的克隆仓库中只有master分支
>3.若要查看其他分支则需要本地创建对应分支，使用 git checkout -b dev origin/dev 
>```

## 5. 分支管理

> 1. 创建合并分支
>
> ```
> 1.git checkout -b dev （等价于git branch dev和 git checkout dev）创建并切换到分支
> 2.也可以使用 git switch -c dev 创建并切换
> 3.git branch 查看当前分支
> 4.git merge dev 合并指定分支到当前分支
> 5.git branch -d dev 删除分支
> 6.git branch -D dev 强制删除
> ```
> 2. 分支冲突
>
> ```
> 1.若不同分支的同一文件有不同修改，则会发生冲突
> 2.此时需要手动修改文件内容，修改完成后再commit提交
> ```
>
> 3. 分支管理
>
> ```
> 1.合并分支时若使用Fast forward快速模式，删除分支后会丢失分支信息
> 2.若禁用快速模式合并时就会生成一个新的commit，则可以保留分支信息
> 3.git merge --no-ff -m"" dev 禁用快速模式合并，因为要创建新的commit所以要使用-m参数
> ```
>
> 4. 存储工作区
>
> ```
> 1.git stash 存储当前工作区状态
> 2.git stash list 查看存储列表
> 3.git stash apply 恢复工作区状态但不删除stash
> 4.git stash drop 删除stash
> 5.git stash pop   恢复并删除stash
> 6.git stash apply stash@{0} 多次stash后恢复指定内容
> 7.git chreey-pick <commit_id> 复制一个特定提交到当前分支
> ```
>
> 5. 多人协作
>
> ```
> 1.git remote 查看远程库信息 -v 显示详细信息
> 2.当有人已经push了对同一文件的修改，此时push会失败，需要使用git pull将最新分支抓取到本地，修改合并后再push
> 3.git branch --set-upstream-to=origin/dev dev 建立本地分支与远程分支的链接
> 4.若产生冲突，使用pull再push解决后，分支合并图会有很多分叉
> 5.解决方法是在push之前使用git rebase指令，将分支合并图顺成直线
> ```

## 6. 标签管理

> 1. 创建标签
> ```
> 1.git tag <name> 给当前分支最新commit打标签
> (git tag -a <name> -m" " <commit_id>  创建带有说明的标签)
> 2.git tag <name> <commit_id> 给历史提交的commit打标签
> 3.git tag 查看标签
> 4.git show <name> 查看标签信息
> 5.标签与commit关联，不同分支的同一commit会有相同标签
> ```
> 2. 标签管理
> ```
> 1.git tag -d <name> 删除标签
> 2.git push origin <name> 推送标签到远程库
> 3.git push origin --tags 推送所有标签
> 4.删除远程标签
>    1. git tag -d <name> 删除本地标签
>    2. git push origin ：refs/tags/<name> 删除远程标签
>    3.也可使用git push origin --delete <name>
> ```

## 7. 自定义

>让版本库忽略某个文件
>
>1.建立.gitignore文件（ 打开文本编辑器，保存时文件名输入“.gitignore”，保存类型选“所有文件”)
>
>\# 此为注释 – 将被 Git 忽略
>
>*.cs    # 忽略所有 .cs 结尾的文件   
>
> !ABC.cs  # 但 ABC.cs 除外   
> 
> /BLL    # 仅仅忽略项目根目录下的 BLL 文件，不包括 subdir/BLL   
> 
> build/   # 忽略 build/ 目录下的所有文件   
> 
> doc/*.txt # 会忽略 doc/notes.txt 但不包括 doc/server/arch.txt

