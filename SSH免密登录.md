**本地获取：**  
cd~进入家目录  
rm -r .ssh/ 删掉  
ssh-keygen -t rsa -C 邮箱地址  
cd .ssh/ 进入  
ls -l 去扫盘  
之后  
cat id_rsa.pub
 
**远程接入SS****H****：**  
SSH密钥  
放到自己github用户SSH and GPG上面
   

**本地获取远程连接：**  
git remote add origin_ssh
 
SSH仓库地址可以增加一个ssh的仓库别名
 
然后push操作 git push origin_ssh master 即可