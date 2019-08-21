## 说明

本章主要用于配置机器学习环境，在前期语法、框架、web开发、爬虫学习阶段无需配置。

## 一 Anaconda

Anaconda是当前流行的Python科学环境，即专门为数据分析、机器学习等人工智能领域使用的科学计算包。   

Anaconda本身集成了大量常用扩展包的环境，包含了 conda命令、Python等 180 多个科学计算包及其依赖项，并且支持所有操作系统平台。  

Anaconda官网与下载地址：https://www.continuum.io/downloads    

安装完毕后创建环境：
```
# 创建环境
conda create --name python3 python=3

# win切换环境
conda activate python3

# mac/linux切换环境
source activate python3
```

测试，输入如下命令即可查看当前python环境是否已经切换到conda环境：
```
which python
```

pycharm开发环境配置：点击File-Project Structure-设置SDK，选择：`System Interpreter`，添加的SDK如图：  

![](../images/python/01-04.png)

SDK设置完毕后，需要设置当前项目启用该SDK：  

![](../images/python/01-03.png)

## 二 Anaconda自带的软件

安装Anaconda后，将会自带下列软件：
- Python：依据选择的Anaconda，决定python的版本
- Jupyter：一款编程/文档/展示软件，启动命令：`jupyter notebook`，可以实时查看运行过程，记录历史运行结果
- Sypder：适合熟悉Matlab的用户，使用简单的图形界面开发环境
- IPython：交互式命令行 Shell，唤起命令`ipython`

## 三 conda包使用

conda和pip类似均为安装、卸载或管理Python第三方包：
- conda install 包名   pip install 包名
- conda uninstall 包名   pip uninstall 包名
- conda install -U 包名   pip install -U 包名

## 四 conda管理数据科学环境

步骤:
```
# 打开Anaconda Prompt窗口，执行：
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --set show_channel_urls yes

# 在用户目录下找到.condarc文件，删除第3行 -defaults 
```

