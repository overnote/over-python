## 一 python2与python3简介

Python 2 or Python 3：
- Python 2.x 是早期版本，Python 3.x是当前版本，Python 2.7 (2.x的最终版)于2010年发布后很少有大的更新
- Python 2.x 比 Python3.x 拥有更多的工具库
- 大多数Linux系统默认安装的仍是 Python 2.x
- 版本选择取决于要解决的问题

建议选择 Python 2.x 的情况：
- 部署环境不可控，Python版本不能自行选择
- 某些工具库还没有提供支持 Python 3.x。
- 如果选择使用 Python 3.x，需要确定要用的工具库支持新版本。
    
## 二 python2与python3区别  

（1）脚本语言的第一行`#!/usr/bin/python`，只对Linux/Unix用户适用，用来指定本脚本用什么interperter来执行（调用/usr/bin下的python解释器）。有这句后加上执行权限后，可以直接用./执行，不然会出错，因为找不到python解释器。`#!/usr/bin/env` python这种用法是为了防止操作系统用户没有将python装在默认的/usr/bin路径里。当系统看到这一行的时候，首先会到env设置里查找python的安装路径，再调用对应路径下的解释器程序完成操作，该写法可以增强代码的可移植性，推荐这种写法。  

（2）`# -*- coding:utf-8 -*-` `#coding=utf-8` 。如果要在python2的py文件里面写中文，则必须要添加一行声明文件编码的注释，否则python2会默认使用ASCII编码。查看编码方式:
```py
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