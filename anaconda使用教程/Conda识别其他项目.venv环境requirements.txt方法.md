**1.** **激活虚拟环境**  
首先，你需要激活这个虚拟环境，然后将其注册到 Anaconda 中。  
在 Windows 上，打开终端（如命令提示符或 PowerShell），导航到虚拟环境所在的目录，然后运行以下命令来激活环境：  
e.g.  
.venv\Scripts\activate

![preview](Exported%20image%2020250326194357-1.png)
**2.****将虚拟环境注册到 Anaconda**  
你可以将当前的虚拟环境注册到 Anaconda，这样可以在 Anaconda Navigator 中看到它。  
运行命令：conda init

**3.****在 Anaconda Navigator 中查看环境**  
打开 Anaconda Navigator，在左下角的环境选择框中，你应该能看到你的虚拟环境（.venv）。如果看不到，可能需要手动添加。  
**4****. 使用 pip 导出环境依赖** #important  
如果你希望在其他地方复现这个环境，可以导出它的依赖包列表：  
pip list --format=freeze > requirements.txt  
然后在其他环境中，可以通过以下命令安装这些依赖：  
pip install -r requirements.txt  
**5****. 在 Anaconda 中创建类似的环境** #important  
如果你希望在 Anaconda 中创建一个功能相似的环境，可以运行以下命令：  
conda create --name myenv python=3.10￼conda activate myenv￼pip install -r path\to\your\requirements.txt