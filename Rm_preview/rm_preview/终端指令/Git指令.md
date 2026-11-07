#Git指令
##一、设置类
- `git config --global user.name`:设置用户名。
- `git config --global user.email`：设置邮箱地址
- `git config --list`:查看当前所有git的配置
##二、仓库工作类
- `git init`：在当前目录初始化一个新的本地Git仓库
- `git clone `<仓库地址>：把远程仓库完整下到本地。
- `git status`:查看当前工作区和暂存区的状态。可以查看当前哪些文件被修改了，哪些文件已经准备提交。
- `git add`:把当前目录下的所有修改、新建的文件添加到暂存区。
- `git commit -m`:提交暂存区的内容到本地仓库，形成记录。
- `git remote -v`:查看当前关联的远程仓库地址
- `git push`:把本地仓库的提交推送到远程仓库
- `git pull`:把远程仓库的最新代码拉取下来
- `git fetch`:只拉取信息，但不自动合并
##三、分支管理类
- `git branch`:查看本地所有分支（*号跟着当前分支）
- `git branch <分支名>`:创建新分支
- `git checkout <分支名>:`与`git switch <分支>`：切换到指定分路
- `git switch -c <分支>`:创建并切换
- `git checkout -b <分支名>`:创建并切换
- `git merge <分支>`:把指定的分支合并到当前所在分支
##四、查看历史与差异
- `git log`:查看历史提交记录（按q退出）
- `git diff`:查看工作区和暂存区文件的具体代码差异
##五、撤销与回退
- `git restore<文件名>`:放弃工作区中某个文件的修改。
- `git restore --staged<文件名>`:从暂存区退回到工作区。
- `git reset --hard <commit-id>`:把本地仓库回退到某个历史版本。
#Git工作流
先创建一个分支，再切换到新分支上，写完再提交到主路并删除支路。
