

创建完仓库，HTTP在git中可以
 
git remote -v 就是遍览  
git remote add origin HTTP地址  
git remote -v
 
git remote remove origin 删除原有  
之后执行推送
 
git push origin master （--force：强制）
 
解释：origin 这里代表远程库地址别名 master 这里代表远程分支名   加入团队怎么搞？  
仓库collaborators里面去加人邀请链接接受就好。
 
克隆操作：  
git clone HTTP地址   之后做修改后正常去push，当然实际上是这样：
 
**工作流程**
 
修改文件：在工作区修改文件。  
添加更改：使用 git add 将更改添加到暂存区。  
提交更改：使用 git commit 将暂存区的更改提交到本地仓库。  
推送更改：使用 git push 将本地仓库的更改推送到远程仓库。   紧接着团队队长需要pull,包括fetch及merge  
git fetch origin master  
解释：origin 是远程库地址别名 merge 是远程分支名  
下载到本地了，但不修改本地源文件想看是什么怎么办？  
git checkout origin/master  
cat 文件名 查看内容  
之后 git checkout master  
git merge origin/master  
cat 文件名 查看内容   注意，同时修改，后推送的那个因为版本不同必须拉取网上的，然后去自己手动改。  
注意，别去clone，去pull，因为pull不修改本地文件  
git pull 之后 git log查看历史  
仅拉取远程的 README 文件（示例）  
git fetch origin master # 获取远程最新代码（但不合并）￼git checkout origin/master -- README.md # 将远程的 README 文件覆盖到本地  
假设你的 README 文件名是 README.md（根据实际名称调整）。  
这个操作会直接覆盖本地的 README 文件，但不会影响其他文件。  
2. 提交更新（示例）  
如果你希望记录这次更新：  
git add README.md￼git commit -m "Update README from remote"  
3. 验证结果  
查看文件内容是否更新：￼git diff HEAD~1 README.md # 确认与上一个版本的差异  
检查状态：￼git status # 确保只有 README 被修改  
跨团队就涉及到pull request merge 以及fork 了  
其他团队去github上去fork到自己的github  
clone到本地之后正常流程直至push到其他团队github  
之后在github 点 pull request 发信息即可  
本团队去仓库 审核