## 常用git命令

```
git init
git add <file>
git commit -m 'add a file'
git status
git diff
git reset --hard^
git reset --hard <commit_id>
git log
git log pretty=oneline
git reflog
git diff HEAD -- <file>
git checkout -- file
git reset HEAD file

git checkout -b dev  <=> git branch dev; git checkout dev;
git merge dev
git branch -d <dev>
###
git branch
git branch <name>
git checkout <branch_name> / git switch <name>
git checkout -b <name> / git switch -c <name>
git merge <name>
git branch -d <name>



```





## 总结

工作区域分为 工作区 版本库 暂存区

git commit 提交的只是暂存区的内容



## 创建、关联远程库

```
# 1.在github创建远程仓库，在本地创建本地仓库 最好保持一个名字
# 关联远程仓库前，可以先删除以防其他的远程链接占用
git remote rm origin
# 2.关联远程仓库命令：
git remote add origin git@server-name:path/repo-name.git
# 3.通过如下命令和远程代码进行合并 
git pull --rebase origin master
# 第一次推送master分支的所有内容
git push -u origin master
# 之前已经推送过了
git push origin master

```





