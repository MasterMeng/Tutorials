# Python 入门教程  

[toc]

## 简介  

Python是一种跨平台的编程语言。它是一种解释型、面向对象、动态数据类型的高级编程语言，它是由Guido van Rossum于1989年开发出来，遵循GPL协议。在2020年1月1日，Python官方宣布停止Python 2的更新，所以本教程使用[Python 3.7.7](https://www.python.org/downloads/windows/python)。  

Python有什么特点呢？  

- **易于学习**：Python的关键字相对较少，结构简单
- **易于阅读**：Python的代码定义清晰，可读性性高
- **广泛的标准库**：Python拥有丰富的库，跨平台，可以说，你能想到的功能，Python都有现成的库可供使用

那么Python可以做什么呢？  

- 日常任务，比如定期备份资料；
- 做网站，国内的豆瓣，Google的Youtube，都是用Python写的；
- 也可以做网络游戏的后台；
- 等等  

那么本教程适合哪些人群学习呢？  

- 会使用电脑，但是从没写过程序；
- 想通过编程简化部分日常工作
- 每天可以抽出半小时左右时间学习

> 注：目前Python的最新版为3.8.2  

## 环境搭建  

本章节我们介绍如何搭建Python的开发环境。  

考虑到本教程是面向编程基础为0的用户，所以这里就以Windows系统为例来搭建开发环境。  

### Python下载  

有关Python的最新源码、二进制文件、文档等资讯都可以从[Python官网](https://www.python.org/)获取。  

本教程使用的Python3.7.7，可以从[这里](https://www.python.org/downloads/release/python-377/)获取。  

![download.png](../pics/download.png)

### Python安装   

Windows版的Python，遵循Windows系统一贯的傻瓜式的“Next”安装方式，安装步骤如下：  

![install_00](../pics/install_00.jpg)  

![install_01](../pics/install_01.png)  

![install_02](../pics/install_02.png)  

![install_03](../pics/install_03.png)  

### 第一个Python程序  

在Windows的左下角的搜索框中输入`powershell`，如下图：  

![first_00](../pics/first_00.png)  

回车之后会打开一个黑窗口，在其中输入`python`，结果如下图：  

![first_01](../pics/first_01.png)  

之后输入如下内容：  

```python
print('hello world')
```  

得到下面的图：  

![first_02](../pics/first_02.png)  

### 选择合适的编辑器  

对于编程而言，一个适合自己的编辑器能起到事半功倍的效果。这里推荐微软推出的跨平台的文本编辑器**VSCode**。  

vscode可以从[这里](https://code.visualstudio.com/Download)下载，选择如下：  

![download_vscode](../pics/download_vscode.png)  

下载完成后双击安装即可。  

### 配置vscode  

安装完成后，打开vscode，操作如下：  

![config vscode](../pics/config_vscode.png)  

汉化vscode：  

![chinese vscode](../pics/chinese_vscode.png)  

## Python基础  

Python作为一门计算机编程语言，它于我们日常使用的自然语言有所不同，最大的不同之处在于，自然语言在不同的语境中可以有不同的解释；但对于编程语言，计算机需要根据给定的编程语言执行相应的任务，这就必须保证编程语言所写的程序不能有歧义。所以每种编程语言都有自己的一套语法，编译器或解释器把符合语法规范的代码转换成CPU能够执行的二进制程序。  

Python也有自己的语法，不过它的语法相对比较简单，采用缩进的方式作为语法规则，写出的代码格式就想下面的例子：  

```python
# 输出字符串 a 或者 b
a = '123'
b = '456'
if a != b:
    print(a)
else:
    print(b)
```  

以`#`开头的语句为注释，是为了给人看的，可以是对接下来的代码的注释，也可以是一些调侃的话，代码执行的时候解释器会自动忽略掉这行的内容，所以`#`之后可以是任何内容。之后的每一行都是一个语句；当语句以`:`结尾时，下一行的语句必须进行缩进，这是一个代码块。按照约定俗称的惯例，缩进使用**4个空格**。最后，Python程序**大小写敏感**，即大小写代表不同的内容。  

### Python基本的数据类型  

在Python中，变量不需要声明，但在使用之前必须进行赋值，变量赋值以后该变量才会被创建。  

在Python中，变量赋值使用的是`=`，它表示把`=`右边的值赋值给左边的变量，而不是表示`=`左右两边相等。在编程语言中，通常用`==`来判断等号两边的变量是否相等。  

在Python3中，有6个标准的数据类型：  

- Number（数字）
- String（字符串）
- List（列表）
- Tuple（元组）
- Set（集合）
- Dictionary（字典）  

#### Number  

Python3支持**int**、**float**、**bool**、**complex（复数）**。跟其它的编程语言一样，数值类型的赋值和计算都是非常直观的。可以使用内置的`type()`来查询变量所指向的内容的数据类型。  

```python
>>> a,b = 100,200
>>> print(a,type(a),b,type(b))
100 <class 'int'> 200 <class 'int'>
```  

数值运算：  

```python
>>> 5 + 4   #加法
9
>>> 5 * 4   #乘法
20
>>> 5 / 4   #除法，得到一个浮点数
1.25
>>> 5 / 4   #除法，得到一个整数
1
>>> 5 - 4   #减法
1
```  

#### String  

Python中的字符串用单引号`'`或者双引号`"`引起来，使用反斜杠`\`转义特殊字符：  

```python
value = 'hello' # 等价于 value = "hello"
```


本作品采用[知识共享署名-非商业性使用-禁止演绎 4.0 国际许可协议](https://creativecommons.org/licenses/by-nc-nd/4.0/)进行许可。