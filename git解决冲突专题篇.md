

![Exported image](Exported%20image%2020250326194524-1.png)

每次记得先commit到自己本地库，然后去pull #important

- 之后进到冲突的文件：
- ![Exported image](Exported%20image%2020250326194525-2.png) 
======上面是本地的，下面是远程的，<<<<<<>>>>>>>>>>>内是冲突的部分  
zh
 
有时候可能会遇到没有共同祖先，这样子搞

![Exported image](Exported%20image%2020250326194526-3.png)

如果发现远程出错了，强制覆盖远程：git push origin master --force 即可

![Exported image](Exported%20image%2020250326194531-4.png)

之后可以退出自己的merge状态：git merge --abort

![Exported image](Exported%20image%2020250326194532-5.png)