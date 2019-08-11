## 一 从终端运行Python程序

#### 1.1 确认Python的版本

在终端或命令行提示符中键入下面的命令。

    python --version

当然也可以先输入python进入交互式环境，再执行以下的代码检查Python的版本。

    import sys
    print(sys.version_info)
    print(sys.version)

#### 1.2 编写Python源代码

可以用文本编辑工具（推荐使用Sublime、Atom、TextMate、VSCode等高级文本编辑工具）编写Python源代码并将其命名为hello.py保存起来，代码内容如下所示。

    print('hello, world!')

#### 1.3 运行程序

切换到源代码所在的目录并执行下面的命令，看看屏幕上是否输出了"hello, world!"。

    python hello.py

#### 1.4 IPython - 更好的交互式编程工具

IPython是一种基于Python的交互式解释器。相较于原生的Python Shell，IPython提供了更为强大的编辑和交互功能。可以通过Python的包管理工具pip安装IPython和Jupyter，具体的操作如下所示。

    pip install ipython jupyter

或者

    python -m pip install ipython jupyter

#### 1.5 Anaconda - 一站式的数据科学神器

Anaconda是专注于数据科学的Python发行版本，其包含了conda、Python等190多个科学包及其依赖项。因为包含的内容较多，Anaconda的下载文件比较大，如果只需要其中一部分的包，或者需要节省带宽或存储空间，也可以使用Miniconda这个较小的发行版（仅包含conda和 Python）。对于学习数据科学的人来说，Anaconda是绝对的神器，有兴趣的读者可以阅读《致Python初学者们 - Anaconda入门使用指南》一文进行了解。


## 二 常见Python解析器

编程语言语言只是符号、语法、语义定义及使用规则的集合，使用这些规则编写的程序（就是Python程序）并不能被计算机直接执行。  

解析执行Python源程序的程序叫做Python解析器（Interpreter），而由解析器解析执行的过程就是Python的实现。

Python解析器有几种：
- CPython：官方提供的解析器就是C语言实现的，所以称之为CPython，也是最常用的Python实现，课程中使用的就是CPython作为解析器。
- JPython：使用Java语言实现的Python解析器，将Python代码编程成Java字节码执行。
- IronPython：是运行在微软Net平台上的Python解析器，直接把Python代码编译成Net字节码。
- PyPy：使用Python语言实现的Python解析器。

## 三 python2与python3

Python 2 or Python 3：
- Python 2.x 是早期版本，Python 3.x是当前版本，Python 2.7 (2.x的最终版)于2010年发布后很少有大的更新
- Python 2.x 比 Python3.x 拥有更多的工具库
- 大多数Linux系统默认安装的仍是 Python 2.x
- 版本选择取决于要解决的问题

建议选择 Python 2.x 的情况：
- 部署环境不可控，Python版本不能自行选择
- 某些工具库还没有提供支持 Python 3.x。
- 如果选择使用 Python 3.x，需要确定要用的工具库支持新版本。
    
常见区别如下：  

（1）脚本语言的第一行`#!/usr/bin/python`，只对Linux/Unix用户适用，用来指定本脚本用什么interperter来执行（调用/usr/bin下的python解释器）。有这句后加上执行权限后，可以直接用./执行，不然会出错，因为找不到python解释器。`#!/usr/bin/env` python这种用法是为了防止操作系统用户没有将python装在默认的/usr/bin路径里。当系统看到这一行的时候，首先会到env设置里查找python的安装路径，再调用对应路径下的解释器程序完成操作，该写法可以增强代码的可移植性，推荐这种写法。

（2）`# -*- coding:utf-8 -*-` `#coding=utf-8` 。如果要在python2的py文件里面写中文，则必须要添加一行声明文件编码的注释，否则python2会默认使用ASCII编码。查看编码方式:
```
import sys
print(sys.getdefaultencoding())
```
Python3 最重要的一项改进之一就是解决了 Python2 中字符串与字符编码遗留下来的这个大坑。

(3)Python2 字符串设计上的一些缺陷：
- 1.使用 ASCII 码作为默认编码方式，对中文处理很不友好。
- 2.把字符串的牵强地分为 unicode 和 str 两种类型，误导开发者

(4)Python3 改进:
- Python3 把系统默认编码设置为 UTF-8
- 文本字符和二进制数据区分得更清晰，分别用 str 和 bytes 表示。文本字符全部用 str 类型表示，str 能表示 Unicode 字符集中所有字符，而二进制字节数据用一种全新的数据类型，用 bytes 来表示
- Python3 中，在字符引号前加‘b'，明确表示这是一个 bytes 类型的对象，实际上它就是一组二进制字节序列组成的数据
- encode 负责字符（unicode）到字节（byte）的编码转换。默认使用 UTF-8 编码准换。

注意区分：Unicode和UTF-8的区别（utf-8是为传送unicode字符的一种再编码的方式）
