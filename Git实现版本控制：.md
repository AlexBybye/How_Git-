

**git log 查看各个版本：**
 
tips：git log --pretty=oneline 可以显示为一行，想看指针可以去掉
 
git log --oneline仅显示修改操作
 
==git reflog==可以在oneline基础上显示到当前版本需要n次
 
HEAD@{n}
 
**多屏控制：**  
space 向下翻页 b 向上翻页 q 退出

**前进后退版本：**  
通过HEAD指针指向索引值git reset --hard 索引值（就是7位的识别码）
 
git reset HEAD~n (回退n步）
   

**git reset命令研究：**  
git reset --soft 7位哈希值 仅在本地库移动head
 
git reset --mixed 7位哈希值 在本地库移动head并重置暂存区
 
git reset --hard 7位哈希值 在本地库移动head、重置暂存区并重置工作区
 
**查看暂存堆栈****&****转战分支：****￼**==￼==git stash list  
单独 git stash 可以暂时停留住手头的东西转战其他分支  
想回来的时候回到分支后 git stash pop 就好了