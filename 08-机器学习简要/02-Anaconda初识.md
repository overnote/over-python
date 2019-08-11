## 一 Anaconda简介

 Anaconda（水蟒）：是一个科学计算软件发行版，集成了大量常用扩展包的环境，包含了 conda、Python 等 180 多个科学计算包及其依赖项，并且支持所有操作系统平台。  
 
下载地址：https://www.continuum.io/downloads

常用软件：  
（1）Jupyter Notebook：唤起命令为`jupyter notebook`
     1.Anaconda自带，无需单独安装
     2.实时查看运行过程
     3.基本的web编辑器（本地）
     4..ipynb 文件分享
     5.可交互式 
     6.记录历史运行结果 

需要修改jupyter显示的文件路径：通过jupyter notebook --generate-config命令创建配置文件，之后在进入用户文件夹下面查看.jupyter隐藏文件夹，修改其中文件jupyter_notebook_config.py的202行为计算机本地存在的路径。  

（2）IPython：唤起命令`ipython`
     1.Anaconda自带，无需单独安装 
     2.Python的交互式命令行 Shell
     3.可交互式 
     4.记录历史运行结果 
     5.及时验证想法  

(3)Spyder：唤起命令`spyder`
     1.Anaconda自带，无需单独安装 
     2.完全免费，适合熟悉Matlab的用户
     3.功能强大，使用简单的图形界面开发环境


## 二 conda包使用

conda和pip类似均为安装、卸载或管理Python第三方包：
- conda install 包名   pip install 包名
- conda uninstall 包名   pip uninstall 包名
- conda install -U 包名   pip install -U 包名

## 三 conda管理数据科学环境

步骤:
```
# 打开Anaconda Prompt窗口，执行：
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --set show_channel_urls yes

# 在用户目录下找到.condarc文件，删除第3行 -defaults 
```

