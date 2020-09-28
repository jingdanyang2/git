



### 添加到暂存区
git add  
添加新文件 touch a(文件名)  
删除文件  git rm a（文件名） // rm a  
编辑文件  echo 1111 >> a  
文件改名   git mv  a   b  
文件移动  git mv b  ./demos/  
文件夹操作   git add .

一个文件多个提交  git add -p  a(文件名)

### 提交到工作区
git commit -m "message"  
git commit –a –m "message"

### 信息查看
以图形的方式打印 Git 提交日志  (git hi -5)
#### 设置别名
git config --global alias.hi "log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short"  
查看某个提交
git show HEAD  
查看文件修改历史
git blame <file name>
### 不同位置文件的不同
git diff 工作区和暂存区的不同  
git diff HEAD 工作区和仓库的不同  
git diff  --cached 仓库和暂存区的不同  
git diff HEAD~1 HEAD~3 仓库中提交的不同  


### 回撤操作
回撤暂存区到工作目录  
git reset HEAD  
回撤提交到暂存区  
git reset HEAD --soft  
回撤提交，放弃变更(暂存区和当前工作目录中的文件都就没有了，恢复到仓库的某个位置)  
git reset HEAD --hard
变基操作，改写历史提交  
git rebase -i HEAD~3


### 标签操作
在当前提交之前的第4个版本上，打标签foo 并给message信息注释
```  
git tag foo HEAD~4 -m "message"
```  
删除标签
```  
git tag -d foo
```  
列出所有标签
```  
git tag
```  
把标签推送到远程仓库  
```
git push origin --tags
```  
把v0.1标签推送到远程仓库  
```
git push origin v0.1
```  
本地仓库和远程标签同步， 删除远程仓库标签  
``` 
git  push origin :refs/tags/v0.0  
```

### 分支操作
创建分支  
git branch foo  
切换分支  
git checkout foo  
删除分支  
git branch -d foo  
合并分支  
git merge <branch name>  

保持进度  
git stash
弹出进度  
git stash pop  
查看stash列表  
git stash list  
删除stash列表  
git stash clear

