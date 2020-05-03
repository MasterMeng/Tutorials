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

Python的解释器可以像一个简单的计算器一样：你可以在里面输入一个表达式，之后它会写出答案：   

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
>>> 5 ** 2  # **表示计算幂运算
25
```  

#### String  

Python中的字符串用单引号`'`或者双引号`"`引起来，使用反斜杠`\`转义特殊字符：  

```python
>>> 'hello' # 等价于 "hello"
'hello'
>>> 'doesn\'t'
"doesn't"
>>> '"Yes," they said.'
'"Yes," they said.'
>>> "\"Yes,\" they said."
'"Yes," they said.'
```  

当然，如果你不想使用`\`来转义特殊字符，可以在引号前加`r`来表示使用原始字符串输出：  

```python
>>> r'C:\some\name'
C:\\some\\name
```  

当你想输入一行比较长的字符串时，可以使用`"""..."""`或`'''...'''`，也可以在行尾使用`\`忽略字符串中包含的换行符：  

```python
print('''\
Usage: thingy [OPTIONS]
    -h
    -H hostname
''')
```  

输出如下，最开始的空行并没有包含进来：  

```bash
Usage: thingy [OPTIONS]
    -h
    -H hostname
```  

字符串可以使用`+`来进行拼接，也可以使用`*`进行重复：  

```python
>>> 3 * 'un' + 'ium'
'unununium'
```  

字符串可以被*索引*，即通过下标访问，索引值从0开始。  

```python
>>> word = 'Python'
>>> word[0]
'P'
>>> word[5]
'n'
```  

索引值也可以是负的，表示从右开始索引：  

```python
>>> word[-1]
'n'
>>> word[-2]
'o'
>>> word[-6]
'P'
```  

字符串不仅能被索引，还支持*切片*。索引得到的是单个字符，切片得到的是字符串的子串：  

```python
>>> word[0:2]   # 前闭后开
'Py'
>>> word[2:5]
'tho'  
```  

如果索引值过大时，会产生一个错误：  

```python
>>> word[42]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: string index out of range
```  

但切片的越界索引会被自动处理：  

```python
>>> word[4:42]
'on'
>>> word[42:]
''
```  

当想知道一个字符串的大小时，可以使用内建的函数`len()`来计算：  

```python
>>> len(word)
6
```  

#### 列表  

在Python中除了前面介绍的三种基础类型之外，还有多种*复合数据类型*，其中最常用的就是*列表*，它是一组由方括号扩起、逗号分隔的一组元素组成。一个列表中可以包含不同数据类型的元素，不过使用时通常使用的各个元素类型相同：  

```python
>>> squares = [1, 3, 4, 5, 0]
>>> squares
[1, 3, 4, 5, 0]
```  

跟字符串一样，列表也支持索引和切片：  

```python
>>> squares[0]
1
>>> squares[-1]
0
>>> squares[-3:]
[4, 5, 0]
```  

列表也支持拼接操作：  

```python
>>> squares + [2, 4, 5, 54, 65]
[1, 3, 4, 5, 0, 2, 4, 5, 54, 65]
```  

你也可以通过`append()`方法来在列表的末尾添加一个新的元素：  

```python
>>> squares.append(9)
[1, 3, 4, 5, 0, 9]
```

也可以使用`len()`来获取列表的长度：  

```python
>>> letters = ['a', 'b', 'c', 'd']
>>> len(letters)
4
```  

#### 元组  

元组是由多个被逗号分隔的值组成的（注意，这里没有说用方括号括起来），比如：  

```python
>>> t = 12345, 54321, 'hello!'
>>> t[0]
12345
>>> t
(12345, 54321, 'hello!')
>>> # Tuples may be nested:
... u = t, (1, 2, 3, 4, 5)
>>> u
((12345, 54321, 'hello!'), (1, 2, 3, 4, 5))
>>> # Tuples are immutable:
... t[0] = 88888
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
>>> # but they can contain mutable objects:
... v = ([1, 2, 3], [3, 2, 1])
>>> v
([1, 2, 3], [3, 2, 1])
```  
如你所见，元组在输出的时候总是被小括号括起来，以便正确表示嵌套元组。输入时的小括号虽然可有可无，但最好还是加上。  

#### 集合  

Python中也包含*集合*类型。集合是由不重复元素组成的无序的集。它的基本用法包括成员检测和消除重复元素。集合对象也支持像 联合，交集，差集，对称差分等数学运算。  

花括号或`set()`函数可以用来创建集合。注意，要创建一个空集合，只能使用`set()`，不能用`{}`，因为`{}`是创建一个空的字典。  

下面是集合的一些简单示例：  

```python
>>> basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
>>> print(basket)                      # show that duplicates have been removed
{'orange', 'banana', 'pear', 'apple'}
>>> 'orange' in basket                 # fast membership testing
True
>>> 'crabgrass' in basket
False

>>> # Demonstrate set operations on unique letters from two words
...
>>> a = set('abracadabra')
>>> b = set('alacazam')
>>> a                                  # unique letters in a
{'a', 'r', 'b', 'c', 'd'}
>>> a - b                              # letters in a but not in b
{'r', 'd', 'b'}
>>> a | b                              # letters in a or b or both
{'a', 'c', 'r', 'd', 'b', 'm', 'z', 'l'}
>>> a & b                              # letters in both a and b
{'a', 'c'}
>>> a ^ b                              # letters in a or b but not both
{'r', 'd', 'b', 'm', 'z', 'l'}
```  

#### 字典  

*字典*是Python中非常有用的内置数据类型。与字符串、列表这些以连续整数为索引的序列不同，字典是一种以*key*为索引的数据结构，key的值可以是任意不可变的类型，通常是字符串或数字。  

字典可以看作是一个**key:value**的集合，key值必须是唯一的。一对空的大括号可以创建一个空字典：`{}`。常见的字典初始化方式是在一对大括号中放一些以逗号隔开的键值对，这也是字典的输出方式。  

字段主要的操作是使用关键字存储和解析值。也可以使用`del`来删除一个键值对。如果你使用一个已经存在的关键字来存储值，那么之前存储的值就会被舍弃。用一个不存在的键来取值则会报错。  

对一个字典执行`list(d)`将返回包含该字典中所有键的列表，按照插入顺序排序；要按照其它排序，使用`sorted(d)`。  

下面是一些字典的简单示例：  

```python
>>> tel = {'jack': 4098, 'sape': 4139}
>>> tel['guido'] = 4127
>>> tel
{'jack': 4098, 'sape': 4139, 'guido': 4127}
>>> tel['jack']
4098
>>> del tel['sape']
>>> tel['irv'] = 4127
>>> tel
{'jack': 4098, 'guido': 4127, 'irv': 4127}
>>> list(tel)
['jack', 'guido', 'irv']
>>> sorted(tel)
['guido', 'irv', 'jack']
>>> 'guido' in tel
True
>>> 'jack' not in tel
False
```  

`dict()`构造函数可以直接从键值对序列里创建字典：  

```python
>>> dict([('sape', 4139), ('guido', 4127), ('jack', 4098)])
{'sape': 4139, 'guido': 4127, 'jack': 4098}
```  

### Python 运算符  

#### 算数运算符  

| 运算符 |      描述      |
| :----: | :------------: |
|   +    |       加       |
|   -    |       减       |
|   *    |       乘       |
|   /    |       除       |
|   %    |  取模，即余数  |
|   **   |     幂运算     |
|   //   | 整除，向下取商 |


```python
>>> a, b = 21, 10
>>> a + b
31
>>> a - b
11
>>> a * b
210
>>> a / b
2.1
>>> a % b
1
>>> 2 ** 3
8
>>> a // b
2 
```  

#### 比较运算符

| 运算符 |   描述   |
| :----: | :------: |
|   ==   |   等于   |
|   !=   |  不等于  |
|   >    |   大于   |
|   <    |   小于   |
|   >=   | 大于等于 |
|   <=   | 小于等于 |

```python  
>>> a, b = 21, 10
>>> a == b
False
>>> a != b
True
>>> a > b
True
>>> a < b
False
>>> a >= b
False
>>> a <= b
>>> False
```  

#### 赋值运算符

| 运算符 |     描述     |
| :----: | :----------: |
|   =    |  简单的赋值  |
|   +=   | 加法赋值运算 |
|   -=   | 减法赋值运算 |
|   *=   | 乘法赋值运算 |
|   /=   | 除法赋值运算 |
|   %=   | 取模赋值运算 |
|  **=   |  幂赋值运算  |
|  //=   | 取整赋值运算 |

```python
>>> a, b = 21, 10
>>> c = a + b
>>> c
31
>>> c += a; print(c)
52
>>> c -= a; print(c)
31
>>> c *= a; print(c)
651
>>> c /= a; print(c)
31.0
>>> c %= a; print(c)
10.0
>>> c //= a; print(c)
0.0
>>> c = 2; c **= a; print(c)
2097152
```  

#### 成员运算符  

| 运算符 |                       描述                        |
| :----: | :-----------------------------------------------: |
|   in   |  如果在指定的序列中找到值返回True，否则返回False  |
| not in | 如果在指定的序列中找不到值返回True，否则返回False |

```python
>>> a = 10
>>> b = 2
>>> ls = [1, 2, 3, 4, 5]
>>> a in ls
False
>>> a not in ls
True
>>> b in ls
True
>>> b not in ls
False
```

### 条件控制  



本作品采用[知识共享署名-非商业性使用-禁止演绎 4.0 国际许可协议](https://creativecommons.org/licenses/by-nc-nd/4.0/)进行许可。