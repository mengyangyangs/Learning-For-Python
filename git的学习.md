# Git之子(创建版本库) 
- git init

# Git的万金油
## 查看当前工作区和暂存区的状态 
- git status

## 将修改过的文件加入暂存区 
- git add <filename> or <path>

## 把暂存区的更改正式提交到本地Git仓库 
- git commit -m "提交说明"

## 查看提交的历史
- git log 

# 时光穿梭
## 查看文件内容的变化(两次提交之间的差异)
- git diff <commit1> <commit2>   or    git diff HEAD ***比较当前工作目录和最近一次提交（HEAD）的差异***

## 撤销提交或暂存的更改，重置 Git 的状态指针（慎用）
- git reset --hard or --sort or --mixed   ***--hard表示会回退到上个版本的已提交状态，--sort表示会回退到上个版本的未提交状态，--mixed会回退到上个版本未添加状态***

## 切换分支，或者恢复文件到某个指定的版本状态
- git checkout <commimt-id> -- <file> ***恢复文件***

## 恢复文件到某个版本，或撤销对工作区和暂存区文件的修改(代替 git checkout)
- git restore <file>  or  git restore --staged <file> ***从暂存区撤销文件到工作区***

## 从 Git 仓库中删除文件，并（默认）同时删除工作区中的对应文件 ***切记，使用git rm后，一定要执行git commit才会真正记录删除操作***
- git rm <file> or  git rm --cached <file> ***仅从暂存区删除文件(保留工作区文件)***

# 分支管理
## 查看分支
- git branch

## 创建分支
- git branch <name>

## 切换分支
- git checkout <name>  or  git switch <name>

## 创建并切换分支
- git checkout -b <name>  or  git switch -c <name>

## 合并某分支到当前分支
- git merge <name>

## 删除分支
- git branch -d <name>   or    git branch -D <name> ***强行删除***

## 查看分支合并图
- git log --graph

## 临时保存当前工作目录和暂存区的改动
- git stash  or  git stash push

## 查看当前的stash列表
- git stash list 

## 取出最近一个stash并删除它
- git stash pop

## 清除所有的stash
- git stash clear

## 查看远程仓库的信息
- git remote  or   git remote -v ***获取详细信息***

## 从本地推送分支
- git push origin branch-name ***如果推送失败，先 git pull 抓去远程最新的提交***

## 在本地创建和远程分支对应的分支
- git checkout -b branch-name origin/branch-name ***本地和远程分支的名称最好一致***

## 建立本地分支和远程分支的关联
- git branch --set-upstream branch-name origin/branch-name  ***在 git pull 提示 “no tracking information”时，则需要建立关联，建立后才可以git pull***

## 重新提交历史
- git rebase

# 标签管理
## 打标签（默认的打在最新的提交上，如果要在其他提交上打标签，则带上需要打标签的id即可）
- git tag <tagname>   or   git tag -a <tagname> -m "message" ***创建一个带说明的注释标签*** 

## 查看标签
- git tag

## 删标签
- git tag -d <tagname>

## 删除远程标签
- git push origin :refs/tags/<tagname>

## 推送一个本地标签
- git push origin <tagname>

## 推送本地全部标签
- git push origin --tags


