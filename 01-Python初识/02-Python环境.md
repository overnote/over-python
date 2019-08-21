## 一 搭建编程环境

#### 1.0 Python环境的选择

Python拥有2个互不兼容的版本，Python2和Python3，当前推荐使用Python3。  

Python拥有下列两种常见的安装方式
- 官网下载安装：[网址](https://www.python.org/)，该方式适合python语法学习，web开发，爬虫开发，运维开发等场景
- 科学环境安装：[安装科学集成环境Anaconda](https://www.continuum.io/downloads)，该环境内置了python以及其他科学运算包，适合人工智能领域使用

本章介绍Python官网方式安装。

#### 1.1 Win安装Python

前往[官网](https://www.python.org/)下载对应操作系统的python安装包后，下一步下一步即可。  

注意：
- 安装目录建立使用无空格的英文目录
- win7系统需要预先安装Service Pack 1补丁包
- win7安装时，建议勾选`Add Python 3 to PATH`，并在`Optional Features`界面勾选`“pip”、“tcl/tk”、“Python test suite”`
- 安装完成会看到“Setup was successful”的提示，但是在启动Python环境时可能会因为缺失一些动态链接库文件而导致Python解释器无法运行，常见的问题主要是api-ms-win-crt*.dll缺失以及更新DirectX之后导致某些动态链接库文件缺失，前者可以参照《api-ms-win-crt*.dll缺失原因分析和解决方法》一文讲解的方法进行处理或者直接在微软官网下载Visual C++ Redistributable for Visual Studio 2015文件进行修复，后者可以下载一个DirectX修复工具进行修复。

#### 1.2 Mac安装Python

Mac自带了Python2版本，打开命令行工具输入：
```
python          # 此时即可进入python2环境
```

当然Mac也可以额外安装Python3，让Python2和Python3共存。下载[官网](https://www.python.org/)的3.x版本pkg安装包即可，输入如下命令：
```
python3         # 此时可进入python3环境
```

#### 2.2 CentOS环境

Linux环境自带Python 2.x版本，输入如下命令查看：
```
python          # 此时即可进入python2环境
```

CentOS安装Python3需要使用源码编译方式安装，先安装依赖环境：
```
yum -y install wget gcc zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel libffi-devel
```

Python3安装：
```
# 下载Python3
wget https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz
xz -d Python-3.7.4.tar.xz
tar -xvf Python-3.7.4.tar

# 安装Python3
cd Python-3.7.4
./configure --prefix=/usr/local/python3 --enable-optimizations
make && make install

# 配置环境变量
vim ~/.bash_profile
export PATH=$PATH:/usr/local/python3/bin
source ~/.bash_profile
```

测试python3环境：
```
python3
```

## 二 HelloWorld

新建一个文件夹test，在文件夹内新建文件：hello.py，内容如下：
```
print('hello, world!')         
```

运行hello.py：
```
cd test
python3 hello.py                # 注意：如果使用命令为 python，则启用python2解释器
```

输出：`hello, world!`

## 三 常见Python解析器

编程语言语言只是符号、语法、语义定义及使用规则的集合，使用这些规则编写的程序（就是Python程序）并不能被计算机直接执行。  

解析执行Python源程序的程序叫做Python解析器（Interpreter）。  

HelloWorld程序能够运行依靠的就是安装Python时候默认的内置解释器：CPython。  

Python解析器有多种：
- CPython：官方提供默认解析器，由于使用C语言实现，所以称之为CPython。
- JPython：使用Java语言实现的Python解析器，将Python代码编程成Java字节码执行。
- IronPython：是运行在微软Net平台上的Python解析器，直接把Python代码编译成Net字节码。
- PyPy：使用Python语言实现的Python解析器。

输入如下命令，可以查看当前使用的python解释器
```
which python        
```

## 四 开发工具

推荐的开发工具有：Pycharm（或IDEA+py插件），VSCode。  

贴士：Pycharm打开上述test文件夹后，是不识别pythonSDK（包含解释器）的，点击File-Project Structure-设置SDK，也可以新建自定义SDK目录。  

以mac为示例：  

![](../images/python/01-01.png)  

SDK设置完毕后，需要设置当前项目启用该SDK：  

![](../images/python/01-03.png)

