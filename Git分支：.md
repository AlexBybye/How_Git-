**分支就是多个方向去开发，互不干扰。**
 
创建分支  
git branch 分支名   
切换分支  
git checkout 分支名   
创建并切换到分支  
git checkout -b 分支名   
查看分支  
git branch -v ：
基本格式，用于查看本地分支及其最新提交。   
上传分支：  
`git push -u origin <branch-name> `
合并分支  
git merge 分支名  
先切换到一个想合并的分支，然后写另一个分支的名字  
当出现同时修改时，会变成手动合并，手动编辑后git add此文件

## 删除分支
 
项目主人可以顺利删除远程分支，而普通贡献者则需要遵循团队的权限管理规则。
 
删除本地分支 ：git branch -d 分支名 ，例如 git branch -d feature-login，会删除 “feature-login” 分支。如果分支还没有合并，Git 会提示你，此时可以用 git branch -D 分支名 强制删除。
 
删除远程分支 ：git push origin --delete 分支名 ，比如 git push origin --delete feature-login-remote，会删除远程仓库中的 “feature-login-remote” 分支。   重命名分支 ：git branch -m 旧分支名 新分支名