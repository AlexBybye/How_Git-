1. 使用Git Large File Storage（Git LFS）

Git LFS 是一个 Git 扩展，用于管理大文件。它允许你将大文件存储在远程服务器上，而不是直接存储在 Git 仓库中。以下是使用 Git LFS 的步骤：

安装Git LFS：  
git lfs install

配置Git LFS跟踪大文件：  
git lfs track "*.largefile"  
将 *.largefile 替换为你实际的大文件类型或路径。

提交和推送更改：  
git add .gitattributes  
git add path/to/largefile  
git commit -m "Add large file with Git LFS"  
git push origin master

2. 清理Git历史记录中的大文件

如果大文件已经在 Git 历史记录中，需要将其从历史记录中移除：

使用 git filter-branch 命令：  
git filter-branch --index-filter 'git rm -r --cached --ignore-unmatch <file/dir>' HEAD  
这个命令会从所有提交中删除指定的文件或目录。注意，这会改变提交的哈希值，可能会影响团队协作。

使用 git filter-repo（推荐）：  
git filter-repo --strip-blobs-bigger-than 100M  
这个命令会移除所有大于100MB的文件。

3. 调整Git配置

增加Git的HTTP缓冲区大小，以支持更大的推送：

git config --global http.postBuffer 524288000

4. 检查并删除未推送的大文件

如果大文件在本地仓库中但尚未推送，可以删除它们并重新提交：

git reset HEAD~1  
git rm --cached path/to/largefile  
git commit --amend  
git push origin master

5. 使用BFG Repo-Cleaner

BFG Repo-Cleaner 是一个更简单的工具，用于清理 Git 历史记录中的大文件：

java -jar bfg.jar --strip-blobs-bigger-than 100M my-repo.git

6. 迁移历史记录中的大文件到Git LFS

如果大文件已经在 Git 历史记录中，可以使用 git lfs migrate 命令将其迁移到 Git LFS：

git lfs migrate import --include="*.largefile"

7. 分步推送

如果推送的数据量过大，可以尝试分步推送：

git push origin master --no-thin

8. 检查远程仓库的限制

确保远程仓库（如GitHub、GitLab等）没有文件大小限制。例如，GitHub 的文件大小限制为100MB。

通过以上方法，你应该能够解决因大文件导致的 git push 错误。

来自 <[https://kimi.moonshot.cn/chat/cval46g52cevdu1297p0](https://kimi.moonshot.cn/chat/cval46g52cevdu1297p0)>

这里临时做个笔记，出处已声明。