Python基础
====
## Python简介

### 基于SymPy的代数计算

**1 Sympy简介**

SymPy 是用于符号数学的 Python 库，它旨在成为功能齐全的计算机代数系统。 SymPy 包括从基本符号算术到微积分，代数，离散数学和量子物理学的功能，使用符号计算体系可以完成多项式求值、求极限、解方程、求积分、微分方程、级数展开、矩阵运算等等计算问题，语法简单、易上手、有异常丰富的三方库生态。

与scipy基于数值计算不同，sympy是基于符号计算的工具包。数值计算的表达式、矩阵变量中不允许有未定义的自由变量 , 而符号计算可以含有未定义的符号变量。

数值计算和符号计算区别：

1) 数值运算会根据变量类型保留一定的有效位数，每一次数值运算有一定的截断误差，重复的多次数值运算就可能会造成很大的累积误差；符号运算不进行数值计算，无截断误差。

2) 符号运算可以得出完全的封闭解或任意精度的数值解。

3) 符号运算的时间较长，而数值运算速度快。

4) 数值运算中必须先对变量赋值；符号运算无须事先对变量赋值，但必须先定义，运算结果以标准的符号表达式形式给出。

**2 安装Sympy包**

步骤如下：

1.运行(Win+R)键，输入cmd打开命令行窗口；

2.输入命令```pip install sympy```，完成sympy包安装，出现下图所示内容即为安装成功。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/python%E7%AE%80%E4%BB%8B/image001.jpg)

sympy包安装完成后，在命令行中输入python以进入，通过以下命令可测试sympy库能否正常使用，出现下图所示结果即为测试成功。
```
import sympy as sym

sym.sin(sym.pi)

sym.cos(sym.pi)
```
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/python%E7%AE%80%E4%BB%8B/image002.png)

**3 Sympy函数简介**

Sympy可以实现的功能如下表

| 函数名              | 功能                           |
|---------------------|--------------------------------|
| Rational( )         | 有理数，可以表示为两个整数是商 |
| pprint( )           | 在控制台更好地打印输出         |
| sqrt( )             | 平方根                         |
| Symbol( )           | 定义符号                       |
| expand( )           | 扩展代数表达式                 |
| simplify( )         | 化简表达式                     |
| equals( )           | 比较表达式                     |
| solve()或solveset() | 求解方程                       |
| limit( )            | 求极限                         |
| sequence( )         | 序列                           |
| Matrix( )           | 矩阵                           |


**Sympy具体使用参考：**<https://blog.csdn.net/weixin_30670151/article/details/99021036>

<https://geek-docs.com/python/python-tutorial/python-sympy.html>

### 基于NumPy和SciPy的数值计算

**1 Numpy和Scipy简介**

NumPy（Numerical Python）是Python的一种开源的数值计算扩展。这种工具可用来存储和处理大型矩阵，比Python自身的嵌套列表（nested list structure)结构要高效的多（该结构也可以用来表示矩阵（matrix）），支持大量的维度数组与矩阵运算，此外也针对数组运算提供大量的数学函数库。

SciPy 是一个开源的 Python 算法库和数学工具包。Scipy 是基于 Numpy 的科学计算库，用于数学、科学、工程学等领域，很多有一些高阶抽象和物理模型需要使用 Scipy。SciPy 包含的模块有最优化、线性代数、积分、插值、特殊函数、快速傅里叶变换、信号处理和图像处理、常微分方程求解和其他科学与工程中常用的计算。

**2 安装Numpy包**

步骤如下：

1.运行(Win+R)键，输入cmd打开命令行窗口；

2.输入命令```pip install numpy```，完成numpy包安装；

3.若安装过程中出现下图所示Warning提醒，通过对pip进行更新可解决，更新命令为```python -m pip install --upgrade pip```。出现下图底部所示内容即为成功。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/python%E7%AE%80%E4%BB%8B/image003.png)

numpy包安装完成后，在命令行中输入python以进入，通过以下命令生成单位矩阵可测试numpy库能否正常使用，出现下图所示array即为测试成功。
```
from numpy import *

eye(4)
```
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/python%E7%AE%80%E4%BB%8B/image004.png)

**3 安装Scipy包**

步骤如下：

1. 运行(Win+R)键，输入cmd打开命令行窗口；

2.输入命令pip install scipy，完成scipy包安装，出现下图所示内容即为安装成功。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/python%E7%AE%80%E4%BB%8B/image005.jpg)

scipy包安装完成后，在命令行中输入python以进入，通过以下命令导入scipy中的常量模块constants可测试scipy库能否正常使用，出现下图所示结果即为测试成功。
```py
from scipy import constants

# 一英亩等于多少平方米

print(constants.acre)
```

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/python%E7%AE%80%E4%BB%8B/image006.png)

### 基于Matplotlib的数据可视化

Matplotlib是一个能够创建和修改静态、动态甚至交互式可视化内容的内容十分全面的Python库，在很多情况下，使用Python做出的可视化内容依托于该库，它有以下6个优点：

（1）创建出的可视化内容质量足够高，可以达到出版物的标准；

（2）部分可视化内容支持实时互动，比如缩放、平移和更新；

（3）界面风格和内容布局可以自己定制；

（4）可视化内容可以导出为多种格式；

（5）和某些平台能够充分整合，比如Jupyter Lab；

（6）拥有丰富且开源的第三方库。

Matplotlib安装起来十分简单，在已安装Python的情况下，输入命令行```pip install matplotlib```即可安装。

此外，由于Matplotlib是一个较为成熟的库，而且很好地顺应了科研的需求，一些平台在安装的时候就附带了该库，比如通过安装Anaconda可以实现Matplotlib的自动安装。

Matplotlib和Matlab绘图部分的功能各有所长、互不包含，但大部分绘制需求两者都能胜任。Matplotlib还非常贴心地准备了pyplot子库，使用其中的函数来编程，代码风格和Matlab十分贴近，给从Matlab转Python的使用者提供了很大的便利。

以下是一个使用matplotlib创建连续图、散点图、柱状图、茎叶图和阶梯图的例子，这个例子在后面的Matplotlib软件包使用部分还会进一步讲解。
```py
import matplotlib.pyplot as plt

x = [1,2,3,4,5,7.2];

y = [1,3,1,2,4,1];

# 连续图和散点图画在同一个图里

plt.subplot(321)

plt.plot(x,y)

plt.scatter(x,y)

plt.xlabel('x')

plt.ylabel('y')

plt.title('continuum and scatter')

# 柱状图

plt.subplot(222)

plt.bar(x,y)

# 茎叶图

plt.subplot(223)

plt.stem(x,y)

# 阶梯图

plt.subplot(224)

plt.step(x,y)

plt.show()
```
绘制出的图形如下图所示。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/python%E7%AE%80%E4%BB%8B/image007.png)

## 编程基础

Python是一门开源免费的脚本编程语言，它不仅简单易用，而且功能强大。

Python是一门推崇“极简主义”的编程语言，阅读优秀的 Python 程序就像阅读一段英文，非专业人士也可以使用 Python。

### 基础语法

Python 语言与 Perl，C 和 Java 等语言有许多相似之处。但是，也存在一些差异。

**1 交互式编程**

交互式编程不需要创建脚本文件，是通过 Python 解释器的交互模式进来编写代码。linux上你只需要在命令行中输入 Python 命令即可启动交互式编程。Window 上在安装 Python 时已经安装了交互式编程客户端。

**2 脚本式编程**

通过脚本参数调用解释器开始执行脚本，直到脚本执行完毕。当脚本执行完成后，解释器不再有效。所有 Python 文件将以 .py 为扩展名。

**3 Python 标识符**

在 Python 里，标识符由字母、数字、下划线组成。

在 Python 中，所有标识符可以包括英文、数字以及下划线(_)，但不能以数字开头。

Python 中的标识符是区分大小写的。

以下划线开头的标识符是有特殊意义的。以单下划线开头 _foo 的代表不能直接访问的类属性，需通过类提供的接口进行访问，不能用 ```from xxx import * ```而导入。

以双下划线开头的 \__foo 代表类的私有成员，以双下划线开头和结尾的 \__foo_\_ 代表 Python 里特殊方法专用的标识，如 \__init__() 代表类的构造函数。

Python 可以同一行显示多条语句，方法是用分号 ;

**4 Python 保留字符**

下面的列表显示了在Python中的保留字。这些保留字不能用作常数或变数，或任何其他标识符名称。

| and      | exec    | not    |
|----------|---------|--------|
| assert   | finally | or     |
| break    | for     | pass   |
| class    | from    | print  |
| continue | global  | raise  |
| def      | if      | return |
| del      | import  | try    |
| elif     | in      | while  |
| else     | is      | with   |
| except   | lambda  | yield  |


**5 行和缩进**

学习 Python 与其他语言最大的区别就是，Python 的代码块不使用大括号 {} 来控制类，函数以及其他逻辑判断。Python 最具特色的就是用缩进来写模块。

缩进的空白数量是可变的，但是所有代码块语句必须包含相同的缩进空白数量，这个必须严格执行。所有 Python 对格式要求非常严格。因此，在 Python 的代码块中必须使用相同数目的行首缩进空格数。建议在每个缩进层次使用单个制表符或两个空格或四个空格。注意不能混用。

**6 多行语句**

Python语句中一般以新行作为语句的结束符。但是我们可以使用斜杠（ \\）将一行的语句分为多行显示。语句中包含 [], {} 或 () 括号就不需要使用多行连接符。

**7 Python 引号**

Python 可以使用引号( ' )、双引号( " )、三引号( ''' 或 """ ) 来表示字符串，引号的开始与结束必须是相同类型的。其中三引号可以由多行组成，编写多行文本的快捷语法，常用于文档字符串，在文件的特定地点，被当做注释。

**8 Python注释**

Python中单行注释采用 # 开头。注释可以在语句或表达式行末。Python 中多行注释使用三个单引号(''')或三个双引号(""")。

**9 Python空行**

函数之间或类的方法之间用空行分隔，表示一段新的代码的开始。类和函数入口之间也用一行空行分隔，以突出函数入口的开始。

空行与代码缩进不同，空行并不是Python语法的一部分。书写时不插入空行，Python解释器运行也不会出错。但是空行的作用在于分隔两段不同功能或含义的代码，便于日后代码的维护或重构。空行也是程序代码的一部分。

**10 多个语句构成代码组**

缩进相同的一组语句构成一个代码块，我们称之代码组。像if、while、def和class这样的复合语句，首行以关键字开始，以冒号( : )结束，该行之后的一行或多行代码构成代码组。我们将首行及后面的代码组称为一个子句(clause)。

### 变量类型

变量存储在内存中的值，这就意味着在创建变量时会在内存中开辟一个空间。基于变量的数据类型，解释器会分配指定内存，并决定什么数据可以被存储在内存中。因此，变量可以指定不同的数据类型，这些变量可以存储整数，小数或字符。

**1 Python 数字**

数字数据类型用于存储数值。他们是不可改变的数据类型，这意味着改变数字数据类型会分配一个新的对象。当你指定一个值时，Number 对象就会被创建。

也可以使用del语句删除一些对象的引用。Python支持四种不同的数字类型：

int（有符号整型）long（长整型，也可以代表八进制和十六进制）float（浮点型）complex（复数）。复数由实数部分和虚数部分构成，可以用 a + bj,或者 complex(a,b) 表示， 复数的实部 a 和虚部 b 都是浮点型。

**2 Python字符串**

字符串或串(String)是由数字、字母、下划线组成的一串字符。它是编程语言中表示文本的数据类型。Python的字串列表有2种取值顺序:

从左到右索引默认0开始的，最大范围是字符串长度少1。

从右到左索引默认-1开始的，最大范围是字符串开头。

如果要实现从字符串中获取一段子字符串的话，可以使用 [头下标:尾下标] 来截取相应的字符串，其中下标是从 0 开始算起，可以是正数或负数，下标可以为空表示取到头或尾。[头下标:尾下标] 获取的子字符串包含头下标的字符，但不包含尾下标的字符。加号（+）是字符串连接运算符，星号（\*）是重复操作。

Python 列表截取可以接收第三个参数，参数作用是截取的步长，来截取字符串。

**3 Python列表**

List（列表） 是 Python 中使用最频繁的数据类型。列表可以完成大多数集合类的数据结构实现。它支持字符，数字，字符串甚至可以包含列表（即嵌套）。

列表用 [ ] 标识，是 Python 最通用的复合数据类型。列表中值的切割也可以用到变量 [头下标:尾下标] ，就可以截取相应的列表，从左到右索引默认 0 开始，从右到左索引默认 -1 开始，下标可以为空表示取到头或尾。加号 + 是列表连接运算符，星号 \* 是重复操作。

**4 Python 元组**

元组（tuple）是另一个数据类型，类似于 List。元组用 () 标识。内部元素用逗号隔开。但是元组不能二次赋值，相当于只读列表。元组是不允许更新的。

**5 Python 字典**

字典(dictionary)是除列表以外Python之中最灵活的内置数据结构类型。列表是有序的对象集合，字典是无序的对象集合。两者之间的区别在于：字典当中的元素是通过键来存取的，而不是通过偏移存取。字典用"{ }"标识。字典由索引(key)和它对应的值value组成。

**6 Python数据类型转换**

| [int(x [,base])](https://www.runoob.com/python/python-func-int.html)            | 将x转换为一个整数                                   |
|---------------------------------------------------------------------------------|-----------------------------------------------------|
| [long(x [,base] )](https://www.runoob.com/python/python-func-long.html)         | 将x转换为一个长整数                                 |
| [float(x)](https://www.runoob.com/python/python-func-float.html)                | 将x转换到一个浮点数                                 |
| [complex(real [,imag])](https://www.runoob.com/python/python-func-complex.html) | 创建一个复数                                        |
| [str(x)](https://www.runoob.com/python/python-func-str.html)                    | 将对象 x 转换为字符串                               |
| [repr(x)](https://www.runoob.com/python/python-func-repr.html)                  | 将对象 x 转换为表达式字符串                         |
| [eval(str)](https://www.runoob.com/python/python-func-eval.html)                | 用来计算在字符串中的有效Python表达式,并返回一个对象 |
| [tuple(s)](https://www.runoob.com/python/att-tuple-tuple.html)                  | 将序列 s 转换为一个元组                             |
| [list(s)](https://www.runoob.com/python/att-list-list.html)                     | 将序列 s 转换为一个列表                             |
| [set(s)](https://www.runoob.com/python/python-func-set.html)                    | 转换为可变集合                                      |
| [dict(d)](https://www.runoob.com/python/python-func-dict.html)                  | 创建一个字典。d 必须是一个序列 (key,value)元组。    |
| [frozenset(s)](https://www.runoob.com/python/python-func-frozenset.html)        | 转换为不可变集合                                    |
| [chr(x)](https://www.runoob.com/python/python-func-chr.html)                    | 将一个整数转换为一个字符                            |
| [unichr(x)](https://www.runoob.com/python/python-func-unichr.html)              | 将一个整数转换为Unicode字符                         |
| [ord(x)](https://www.runoob.com/python/python-func-ord.html)                    | 将一个字符转换为它的整数值                          |
| [hex(x)](https://www.runoob.com/python/python-func-hex.html)                    | 将一个整数转换为一个十六进制字符串                  |
| [oct(x)](https://www.runoob.com/python/python-func-oct.html)                    | 将一个整数转换为一个八进制字符串                    |


**7 Python常用函数**

数学常量：pi（圆周率）。e（自然常数），math.inf（正无穷大，负无穷大为 -math.inf）math.nan（非浮点数标记）。示例如下：
```py
math.fabs(x) #返回x的绝对值

math.fmod(x,y) #返回x/y的余数，其值为浮点数

math.fsum([x,y,…]) #对括号内每个元素求和，其值为浮点数

math.ceil(x) #向上取整，返回不小于x的最小整数

math.floor(x) #向下取整，返回不大于x的最大整数

math.factorial(x) #返回x的阶乘，如果x是小数或负数，返回ValueError

math.gcd(a,b) #返回a与b的最大公约数

math.frexp(x) #x = m * 2^e 返回（m,e），当x=0，返回（0.0,0）

math.ldexp(x,i) #x = m * 2^e 返回 x * 2^i的运算值，math.frexp(x)函数的反运算

math.modf(x) #返回x的小数和整数部分

math.trunc() #返回x的整数部分

math.pow(x,y) #返回x的y次幂

math.exp(x) #返回e的x次幂

math.sqrt(x) #返回x的平方根

math.log(x[,base]) #返回x的对数值，只输入x时，返回lnx

math.log10(x) #返回x的10对数值

math.degree(x) #角度x的弧度值转角度值

math.radians(x) #角度值转弧度值

math.hypot(x,y) #返回（x,y）坐标到原点（0,0）的距离

math.sin(x) #返回x的正弦函数值，x是弧度值

math.atan2(y,x) #返回y/x的反正切函数值

math.sinh(x) #返回x的双曲正弦函数值

math.erf(x) #高斯误差函数

math.erfc(x) #余补高斯误差函数

math.gamma(x) #伽马函数，也叫欧拉第二积分函数

math.lgamma(x) #伽马函数的自然对数
```
Python 提供对于复数运算的支持，复数在 Python 中的表达式为 C==c.real+c.imag\*j，复数 C 由他的实部和虚部组成。对于复数，Python 支持它的加减乘除运算，同时提供了 cmath 模块对其他复杂运算进行支持。

cmath 模块中的 polar() 方法和 rect() 方法可以对复数进行极坐标表示和笛卡尔表示方法的转换。复数的指数函数为 cmath.exp(x), 用来求解 e^x 表达式。cmath.log(x[,base]) 求以 Base 为底的 x 的对数。cmath.log10(x) 求以 10 为底 x 的对数。cmath.sqrt(x) 求 x 的平方根。

### 运算符

**1 Python算术运算符**

+，-，*，/， %（取模返回除法的余数），\*\*（幂），//（取整除）。

**2 Python比较运算符**

==，!= （不等于），\>，\<，\>=，\<= 。

**3 Python赋值运算符**

=（简单的赋值运算符），+= 加法赋值运算符（ c = a + b 将 a + b 的运算结果赋值为 c），其他在“=”加算数符号效果同上。

**4 Python位运算符**

&按位与运算符，\|按位或运算符，\^ 按位异或运算符，\~ 按位取反运算符，\<\<左移动运算符，\>\>右移动运算符。

**5 Python逻辑运算符**

and布尔"与" ，or布尔"或" ，not 布尔"非" 。

**6 Python成员运算符**

in 如果在指定的序列中找到值返回 True，否则返回 False。

not in 如果在指定的序列中没有找到值返回 True，否则返回 False。

**7 Python身份运算符**

is是判断两个标识符是不是引用自一个对象 如果引用的是同一个对象则返回 True，否则返回 False

is not 是判断两个标识符是不是引用自不同对象

**8 Python运算符优先级**

下面是优先级从高到低排序：

\*\* ，\~ + - ，\* / % // ，+ - ，\>\> \<\<，& ，\^ \|，\<= \< \> \>=，\<\> == !=，= %= /= //= -= += \*= \*\*= ，is is not，in not in，not and or

### 条件语句

Python条件语句是通过一条或多条语句的执行结果（True或者False）来决定执行的代码块。

Python程序语言指定任何非0和非空（null）值为true，0 或者 null为false。

Python 编程中 if 语句用于控制程序的执行，基本形式为：
```
if 判断条件：

执行语句……

else：

执行语句……
```
其中"判断条件"成立时（非零），则执行后面的语句，而执行内容可以多行，以缩进来区分表示同一范围。else 为可选语句，当需要在条件不成立时执行内容则可以执行相关语句。

if 语句的判断条件可以用\>（大于）、\<(小于)、==（等于）、\>=（大于等于）、\<=（小于等于）来表示其关系。当判断条件为多个值时，可以使用以下形式：
```
if 判断条件1:

执行语句1……

elif 判断条件2:

执行语句2……

elif 判断条件3:

执行语句3……

else:

执行语句4……
```
由于 Python 并不支持 switch 语句，所以多个条件判断，只能用 elif 来实现，如果判断需要多个条件需同时判断时，可以使用 or （或），表示两个条件有一个成立时判断条件成功；使用 and （与）时，表示只有两个条件同时成立的情况下，判断条件才成功。当if有多个条件时可使用括号来区分判断的先后顺序，括号中的判断优先执行，此外 and 和 or 的优先级低于\>（大于）、\<（小于）等判断符号，即大于和小于在没有括号的情况下会比与或要优先判断。

### 循环语句

Python有两个原始循环命令：while和for。

**1 While**

使用while循环，只要条件为真就可以执行一组语句。

while循环需要准备好相关的变量。

调用格式形如：
```
while 判断条件：

执行语句……
```
当判断条件为假（false）时，循环结束。

**2 For**

for循环用于迭代遍历序列（即列表，元组，字典，集合或字符串）。

for循环不需要预先设置索引变量。

调用格式形如：
```
for迭代变量in 序列:

执行语句……
```
如需循环一组代码指定的次数，可以使用 range()函数，range()函数返回一个数字序列，默认情况下从0开始，递增1直到括号内指定的数字结束（不包括该数字）。

例如，range(10)表示值从0到9。range()函数默认0为起始值，还可通过添加参数来指定起始值：如range(3,10)，表示值为3到9。

**3 循环嵌套**

嵌套循环是循环内的循环。“外循环”每迭代一次，“内循环”将执行一次。

也可以在循环体内嵌入其他的循环体，在while循环中可以嵌入for循环，在for循环中也可以嵌入while循环。

**4 中断语句**

使用**break**语句，可以直接退出循环。即使循环条件为True或者序列还没被完全递归完，也会停止执行循环语句。

使用**continue**语句，可以停止当前的迭代，并继续下一轮循环。

区别：

continue语句跳出本次循环，而break跳出整个循环。

**5 Pass语句**

pass是空语句，是为了保持程序结构的完整性的占位语句。

如果循环条件为True时不需要执行任何语句，需使用pass语句来避免错误。

### 函数

**1 函数定义**

函数是一种仅在调用时运行的代码块。可以将数据（称为参数）传递到函数中，函数处理参数并可返回结果。

书写规则：

（1）使用def关键字定义函数，后接函数名称和圆括号。

（2）任何传入参数和自变量都放在圆括号中间。信息可以作为参数传递给函数。可以根据需要添加任意数量的参数，使用逗号分隔。

（3）函数内容以冒号起始，并且缩进。

（4）使用return语句退出函数，并返回一个表达式。不带表达式的return相当于返回 None。

格式形如（方括号表示内容可省略）：
```
def 函数名( 形参 ):

执行语句……

return [表达式]
```
**2 函数调用**

使用函数名称后跟括号调用函数。括号内容由创建函数时的定义决定。

格式形如：
```
函数名(实参)
```
**3 参数传递**

发送到函数的参数可以是任何数据类型（字符串、数字、列表、字典等），并且在函数内该参数的数据类型不变。变量没有类型。

Python函数的参数传递分为可更改对象和不可更改对象。

不可变类型有整数、字符串、元组。如函数fun(a)，a是整数，传递的只是a的值，没有影响a对象本身。在函数内部修改a的值，只是修改参数传递时复制的另一个对象，不会影响a本身。

可变类型有列表、字典。如 fun(la)，la是列表，这是将la真正地传过去，在函数内修改la后，函数外部的la也会随之改变。

**4 参数分类**

调用函数时可使用的正式参数类型：必备参数、关键字参数、默认参数、不定长参数。

**必备参数**必须以按照定义时的参数顺序依次传入函数。调用时的数量必须和声明时的一样。如：
```py
#函数定义

def fun(a,b)

print(“a=”,a)

print(“b=”,b)

#函数调用，按顺序传入，1传给a，2传给b

fun(1,2)
```
**关键字参数**允许函数调用时参数的顺序与声明时不一致，Python解释器使用参数名匹配参数值。如：
```py
#函数定义

def fun(a,b)

print(“a=”,a)

print(“b=”,b)

#函数调用

fun(b=1,a=2)
```
定义函数时，可以给某个参数赋值一个默认值，具有默认值的参数即**默认参数**。调用函数时，默认参数的值如果没有传入，则被认为是默认值。如：
```py
#函数定义，b是默认参数

def fun(a,b=2)

print(“a=”,a)

print(“b=”,b)

#函数调用

fun(b=3,a=1) #输出a=1 b=3

fun(a=1) #输出a=1 b=2
```
当函数需要处理的参数个数不确定时，可使用**不定长参数**。不定长参数只能放在形参的最后位置。接收元组时参数名（一般为“args”）前加一个“*”，接收字典时参数名（一般为“kwargs”）前加两个“*”。如：
```py
#函数定义，不定长参数为元组

def num(a,b,*args):

print(a)

print(b)

print(args)

#函数调用

num(11,22,33,44)
```
输出结果为：
```
11

22

(33,44)
```
**5 匿名函数**

匿名函数指一类无须定义标识符的函数或子程序。Python用lambda语法定义匿名函数，只需用表达式而无需申明。lambda函数可以接受任意数量的参数，但只能有一个表达式，格式形如：

```
lambda [arg1 [,arg2,.....argn]]:表达式
```

**6 变量类型及作用域**

作用域指变量的有效范围，就是变量可以在哪个范围内使用。有些变量可以在整段代码的任意位置使用，有些变量只能在函数内部使用。

变量的作用域由变量的定义位置决定，在不同位置定义的变量，它的作用域不同。两种最基本的变量作用域：全局变量、局部变量。

在函数内部定义的变量，只能在其被声明的函数内部访问，出了函数就不能使用了，这样的变量称为局部变量。

在所有函数的外部定义的变量称为全局变量，可以在整个程序范围内访问。

示例如下：

```py
total = 0 # 这是一个全局变量

def sum( arg1, arg2 ):

total = arg1 + arg2 # total在这里是局部变量

print("函数内是局部变量 : ", total)

return total

#调用sum函数

sum( 10, 20 )

print("函数外是全局变量 : ", total)
```
输出结果为：
```
函数内是局部变量 : 30

函数外是全局变量 : 0
```
### 模块和包

**1 模块介绍**

模块，可以理解为是对代码更高级的封装，即把能够实现某一特定功能的代码编写在同一个.py文件中，并将其作为一个独立的模块，这样既可以方便其它程序或脚本导入并使用，同时还能有效避免函数名和变量名发生冲突。模块能定义函数、类和变量，模块里也能包含可执行的代码。

**2 引入模块**

模块可以被别的程序引入，以使用该模块中的函数等功能,这也是使用 Python 标准库的方法。使用import语句为当前程序导入模块。格式形如：

```import 模块名1[,模块名2[,... 模块名N]]```

结合from 语句从模块中导入一个指定的部分到当前命名空间中。语法如下：

```from 模块名 import 成员名1[, 成员名2[, ... 成员名N]]```

把一个模块的所有内容全都导入到当前的命名空间，使用如下声明：

```from 模块名 import *```

**3 制作自己的模块文件**

将所需代码保存在文件扩展名为.py的文件中以创建模块。

**4 包介绍**

包是一个分层次的文件目录结构，它定义了一个由模块和子包以及子包下的子包等组成的Python的应用环境。

简单来说，包就是一个目录，里面存放了.py文件，外加一个 \__init__.py文件。\__init__.py用于标识当前文件夹是一个包，该文件的内容可以为空。

**5 包的引入**

包其实本质上还是模块，因此导入模块的语法同样也适用于导入包。无论导入我们自定义的包，还是导入从他处下载的第三方包，导入方法可归结为以下 3 种：

（1）

```import 包名[.模块名 [as 别名]]```

（2）

```from 包名 import 模块名 [as 别名]```

（3）

```from 包名.模块名 import 成员名 [as 别名]```

## NumPy软件包

### 数组创建

**1数组**

**链接：** https://numpy.org/doc/stable/reference/arrays.ndarray.html

Numpy中的数组是一个值网格，所有类型都相同，并由非负整数元组索引。 维数是数组的排名; 数组的形状是一个整数元组，给出了每个维度的数组大小。

**说明：** numpy中的基本变量类型

**函数：** array()

**案例：** 创建一个大小为2×3的2维数组，由4字节的整型元素组成。
```py
>>> x = np.array([[1, 2, 3], [4, 5, 6]], np.int32)

>>> type(x) #返回对象类型

<class 'numpy.ndarray'>

>>> x.shape #返回数组形状

(2, 3)

>>> x.dtype #返回数组元素类型

dtype('int32')
```
**2创建数组**

**链接：** https://numpy.org/doc/stable/reference/arrays.ndarray.html

指定数组特征，创建一个任意大小维数。

**说明：** 返回一个数组对象。

**案例：** 常用的数组创建函数
```py
>>> import numpy as np

>>> a = np.zeros((2,2)) # 创建全0数组

>>> print("a = ")

>>> print(a)

>>> b = np.ones((1,2)) # 创建全1数组

>>> print("b = ")

>>> print(b)

>>> c = np.full((2,2), 7) # 创建常数数组

>>> print("c = ")

>>> print(c)

>>> d = np.eye(2) # 创建n维对角数组

>>> print("d = ")

>>> print(d)

>>> e = np.random.random((2,2)) # 创建随机数组

>>> print("e = ")

>>> print(e)

>>> f = np.arrange(0,10,1) # 创建按从0到9，间隔为1的等差数列

>>> print("f = ")

>>> print(f)

>>> g = np.linspace (0,9,10) # 创建按从0到9，含有10个元素的等差数列

>>> print("g = ")

>>> print(g)
```
输出：
```
a =

[[0. 0.]

[0. 0.]]

b =

[[1. 1.]]

c =

[[7 7]

[7 7]]

d =

[[1. 0.]

[0. 1.]]

e =

[[0.94310249 0.39902715]

[0.71982074 0.43460291]]

f =

[0 1 2 3 4 5 6 7 8 9]

g =

[0 1 2 3 4 5 6 7 8 9]
```
### 元素访问

**1基本索引（访问单元素）**

**链接：** https://numpy.org/doc/stable/user/basics.indexing.html#basics-indexing

数组的单元素索引的工作方式与其他标准Python序列的工作方式完全相同。它从0开始，并接受从数组末尾开始索引的负索引。

**说明：** 索引为整数

**案例：** 通过索引访问数组中的指定元素
```py
# 一维数组

>>> x = np.arange(10) # x = [0 1 2 3 4 5 6 7 8 9]

>>> x[2]

输出：

2

>>> x[-2]

输出：

8

# 多维数组

>>> x.shape = (2, 5) # x = [[0 1 2 3 4]

[5 6 7 8 9]]

>>> x[1, 3] # x第二行第四列元素

输出：

8

>>> x[1, -1] # x第二行最后一列元素

输出：

9

# 请注意，如果传入的指定索引数少于数组的维度，则会得到一个子维度数组

(类似于切片索引)

>>> x[0] # x的第一子维度数组

输出：

array([0, 1, 2, 3, 4])

# 与C语言类似，二维数组也可以采取以下形式访问元素，x[0，2]==x[0][2]。

# 但是请注意，第二种情况效率更低，因为程序在第一个索引之后创建一个新的临时数组。

>>> x[0][2] # x第一行第三列元素

输出：

2
```
**2切片索引（访问多元素）**

**链接：** https://numpy.org/doc/stable/user/basics.indexing.html#slicing-and-striding

与标准Python序列类似，可以使用冒号（:）对numpy的数组进行切片。由于数组可能是多维的，因此必须为数组的每个维指定一个切片

**说明1**：基本的切片语法是i:j:k，其中i是开始索引，j是停止索引，k是步长。该语句将选择索引值为i、i+k、…、i+（m-1）k的m个元素（在相应维度中），其中和q和r是通过将j-i除以k:j-i=q k+r得到的商和余数，因此i+（m-1）k<j。例如：

**案例：** 访问多维数组中某一维度所有元素
```py
>>> x = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])

>>> x[1:7:2]

输出：

array([1, 3, 5])
```
**说明2：** 可以将基本索引与切片索引混合使用。但是，这样做会产生比原始数组更低级别的数组，这与MATLAB处理数组切片的方式完全不同

**案例：** 基本索引与切片索引混合使用
```py
>>> x = np.array([[1,2,3,4], [5,6,7,8], [9,10,11,12]])

>>> x[1, :] # Rank 1 view of the second row of a

输出：

[5 6 7 8] # 一维数组

>>> x[1:2, :] # Rank 2 view of the second row of a

输出：

[[5 6 7 8]] #大小为1×4的二维数组
```
### 数组基本运算

**1元素运算**

**链接：** https://numpy.org/doc/stable/user/quickstart.html#basic-operations

数组的算术运算按元素执行。创建一个新数组，并用计算结果填充。

**说明：** 算术运算指加减乘除四则运算和简单的函数映射

**案例：** 数组算术运算
```py
>>> a = np.array([20, 30, 40, 50])

>>> b = np.arange(4) # [0,1,2,3]

>>> a - b

输出：

array([20, 29, 38, 47])

>>> b**2 # == b*b 即b中元素的平方

输出：

array([0, 1, 4, 9])

>>> 10 * np.sin(a) # 10sin(a)

输出：

array([ 9.12945251, -9.88031624, 7.4511316 , -2.62374854])

>>> a < 35

输出：

array([ True, True, False, False])

# 当使用不同类型的数组进行操作时，结果数组的类型对应于更一般或更精确的类型（一种称为向上转换的行为）

>>> a = np.ones(3, dtype=np.int32) # 元素为int型

>>> b = np.linspace(0, pi, 3) # 元素为float型

>>> b.dtype.name

输出：

'float64'

>>> c = a + b

>>> c

输出：

array([1. , 2.57079633, 4.14159265])

>>> c.dtype.name

输出：

'float64'

>>> d = np.exp(c * 1j)

>>> d

输出：

array([ 0.54030231+0.84147098j, -0.84147098+0.54030231j,

-0.54030231-0.84147098j])

>>> d.dtype.name

'complex128'
```
**2矩阵运算**

**链接：** https://numpy.org/doc/stable/user/quickstart.html#basic-operations

与许多矩阵语言不同，乘积运算符*在NumPy数组中按元素操作。可以使用@运算符或点函数或方法执行矩阵乘积：

**说明：** @运算符需要python版本3.5以上

**案例：** 数组矩阵运算
```py
>>> A = np.array([[1, 1],

[0, 1]])

>>> B = np.array([[2, 0],

[3, 4]])

>>> A * B # 按元素相乘

输出：

array([[2, 0],

[0, 4]])

>>> A @ B # 矩阵相乘

输出：

array([[5, 4],

[3, 4]])

>>> A.dot(B) # 另一种矩阵相乘的形式

输出：

array([[5, 4],

[3, 4]])
```
**3其他常用运算**

**函数:**sum()

**说明：** 对数组中所有元素求和，然而，通过指定维度参数（axis=n），您可以仅沿数组的指定维度n应用操作。

**案例：**
```py
>>> a = rg.random((2, 3))

>>> a

输出：

array([[0.82770259, 0.40919914, 0.54959369],

[0.02755911, 0.75351311, 0.53814331]])

>>> a.sum()

输出：

3.1057109529998157

>>> a.sum(axis = 1)

输出：

array([1.78649542, 1.31921553])
```
**函数:** min()

**说明：**  求数组中所有元素的最小值，然而，通过指定维度参数（axis=n），您可以仅沿数组的指定维度n应用操作。

**案例：**
```py
>>> a = rg.random((2, 3))

>>> a

输出：

array([[0.82770259, 0.40919914, 0.54959369],

[0.02755911, 0.75351311, 0.53814331]])

>>> a.min()

输出：

0.027559113243068367

>>> a.min(axis = 1)

输出：

array([0.40919914, 0.02755911])
```
**函数:** max()

**说明：** 求数组中所有元素的最大值，然而，通过指定维度参数（axis=n），您可以仅沿数组的指定维度n应用操作。

**案例：**
```py
>>> a = rg.random((2, 3))

>>> a

输出：

array([[0.82770259, 0.40919914, 0.54959369],

[0.02755911, 0.75351311, 0.53814331]])

>>> a.max()

输出：

0.8277025938204418

>>> a.max(axis = 1)

输出：

array([0.82770259, 0.75351311])
```
**函数:** exp()

**说明：** 求数组中所有元素的指数。

**案例：**
```py
>>> a = np.arange(3) # a = [0, 1, 2]

>>> np.exp(a)

输出：

array([1. , 2.71828183, 7.3890561 ])
```
**函数:** sqrt()

**说明：** 求数组中所有元素的平方根。

**案例：**
```py
>>> a = np.arange(3) # a = [0, 1, 2]

>>> np.sqrt(a)
```
输出：
```py
array([0. , 1. , 1.41421356])
```
## SciPy软件包

Scipy是开源的Python算法库和工具包。Scipy是基于Numpy的科学计算工具包，可以处理高级抽象函数和物理建模等问题，应用于数学、科学、工程等领域。Scipy由最优化、线性代数、积分、插值、特殊函数、快速傅里叶变换、信号处理和图像处理、常微分方程求解等子工具包组成。

使用scipy常用导入指令
```py
>>> import numpy as np

>>> import matplotlib as mpl

>>> import matplotlib.pyplot as plt
```
Scipy子工具包构成如下表：

| 名称                                                                                                          | 描述                                                                            |
|---------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| cluster                                                                                                       | Clustering algorithms（聚类分析算法）                                           |
| [constants](https://docs.scipy.org/doc/scipy/reference/reference/constants.html#module-scipy.constants)       | Physical and mathematical constants（物理和数学常数）                           |
| [fftpack](https://docs.scipy.org/doc/scipy/reference/reference/fftpack.html#module-scipy.fftpack)             | Fast Fourier Transform routines（快速傅里叶变换）                               |
| [integrate](https://docs.scipy.org/doc/scipy/reference/reference/integrate.html#module-scipy.integrate)       | Integration and ordinary differential equation solvers （积分和常微分方程求解） |
| [interpolate](https://docs.scipy.org/doc/scipy/reference/reference/interpolate.html#module-scipy.interpolate) | Interpolation and smoothing splines（插值和平滑样条曲线）                       |
| [io](https://docs.scipy.org/doc/scipy/reference/reference/io.html#module-scipy.io)                            | Input and Output（输入和输出）                                                  |
| [linalg](https://docs.scipy.org/doc/scipy/reference/reference/linalg.html#module-scipy.linalg)                | Linear algebra（线性代数）                                                      |
| [ndimage](https://docs.scipy.org/doc/scipy/reference/reference/ndimage.html#module-scipy.ndimage)             | N-dimensional image processing（N维图像处理）                                   |
| [odr](https://docs.scipy.org/doc/scipy/reference/reference/odr.html#module-scipy.odr)                         | Orthogonal distance regression（正交距离回归）                                  |
| [optimize](https://docs.scipy.org/doc/scipy/reference/reference/optimize.html#module-scipy.optimize)          | Optimization and root-finding routines（优化和寻根）                            |
| [signal](https://docs.scipy.org/doc/scipy/reference/reference/signal.html#module-scipy.signal)                | Signal processing（信号处理）                                                   |
| [sparse](https://docs.scipy.org/doc/scipy/reference/reference/sparse.html#module-scipy.sparse)                | Sparse matrices and associated routines（稀疏矩阵）                             |
| [spatial](https://docs.scipy.org/doc/scipy/reference/reference/spatial.html#module-scipy.spatial)             | Spatial data structures and algorithms（空间数据结构和算法）                    |
| [special](https://docs.scipy.org/doc/scipy/reference/reference/special.html#module-scipy.special)             | Special functions（特殊函数）                                                   |
| [stats](https://docs.scipy.org/doc/scipy/reference/reference/stats.html#module-scipy.stats)                   | Statistical distributions and functions（统计分布和函数）                       |



### 线性代数

scipy.linalg包含了numpy.linalg中的所有函数，并定义了更高级的函数功能。numpy.matrix和numpy.ndarray两个类在使用中有异同，matrix类定义方式更类似于Matlab中矩阵，支持默认运算符的操作，如矩阵乘法和转置等；而2-D的array类运算需要使用函数，输入参数为需要进行运算的两个实例化的array对象。为了防止用户在编程中使用混淆，更推荐在Python中使用numpy.ndarray。以下所有函数的调用均在相关库以及scipy导入前提下进行。

**1矩阵基本操作**

**链接：** [https://docs.scipy.org/doc/scipy/reference/tutorial/linalg.html#](https://docs.scipy.org/doc/scipy/reference/tutorial/linalg.html#)

加*部分教学要求较低，感兴趣的同学可以点击进行链接学习

**函数：linalg.inv(A)** 或者当A为矩阵类时：**A.I**

**说明：** 返回n维数组的逆矩阵

**案例：** matrix求逆
```py
>>> import numpy as np

>>> A = np.mat('[1 2;3 4]')

>>> A

matrix([[1, 2],

[3, 4]])

>>> A.I

matrix([[-2. , 1. ],

[ 1.5, -0.5]])
```
**案例：** array求逆
```py
>>> import numpy as np

>>> from scipy import linalg

>>> A = np.array([[1,2],[3,4]])

>>> A

array([[1, 2],

[3, 4]])

>>> linalg.inv(A)

array([[-2. , 1. ],

[ 1.5, -0.5]])
```
**函数：linalg.solve(A,b)**

**说明：** 求解线性方程组时可以使用linalg.solve(A,b)快速求得解向量，也可以通过逆向量乘以输出列向量求解![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image001.png)，但是速度更慢结果不稳定，不推荐使用，且两种方法得到的解向量可以进一步代入检验。

**案例：** 假设需要求解以下线性方程组：
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image002.png)

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image003.png)
为系数矩阵，
![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image004.png)
为输出列向量

```py
>>> import numpy as np

>>> from scipy import linalg

>>> A = np.array([[1,3,5],[2,5,1],[2,3,8]])

>>> A

array([[1, 3, 5],

[2, 5, 1],

[2, 3, 8]])

>>> linalg.inv(A)

array([[-1.48, 0.36, 0.88],

[ 0.56, 0.08, -0.36],

[ 0.16, -0.12, 0.04]])

>>> A.dot(linalg.inv(A))

#基于数值计算，矩阵和其逆以矩阵乘法相乘，结果不为标准单位矩阵

array([[ 1.00000000e+00, -1.11022302e-16, 4.85722573e-17],

[ 3.05311332e-16, 1.00000000e+00, 7.63278329e-17],

[ 2.22044605e-16, -1.11022302e-16, 1.00000000e+00]])
```
**函数：linalg.det(A)**

**说明：** 求矩阵的行列式

**案例：**
```py
>>> import numpy as np

>>> from scipy import linalg

>>> A = np.array([[1,2],[3,4]])

>>> A

array([[1, 2],

[3, 4]])

>>> linalg.det(A)

-2.0
```
\*求范数：**linalg.norm**

\*求解线性最小二乘问题：**linalg.lstsq**和**linalg.pinv**或者**linalg.pinv2**

\*广义逆矩阵：**linalg.pinv**或者**linalg.pinv2**

**2矩阵分解**

**函数： linalg.eig(A)**

**说明：** 求特征值和特征向量

**案例：**
```py
>>> import numpy as np

>>> from scipy import linalg

>>> A = np.array([[1, 2], [3, 4]])

>>> la, v = linalg.eig(A)

>>> la #特征值，返回一个行向量

array([-0.37228132+0.j, 5.37228132+0.j])

>>> v #特征向量，返回一个列向量

array([[-0.82456484, -0.41597356],

[ 0.56576746, -0.90937671]])
```
\*奇异值分解（Singular value decomposition）：可以被认为是特征值问题对非平方矩阵的扩展，**linalg.svd**

\*LU分解：**linalg.lu**

\*乔洛斯基分解（Cholesky decomposition）：**linalg.cholesky**

\*QR分解：**linalg.qr**

\*舒尔分解（Schur decomposition）：**linalg.schur**

\*插值分解（Interpolative decomposition）：**scipy.linalg.interpolative**

**3矩阵函数**

指数函数：**linalg.expm**

对数函数：**linalg.logm**

三角函数：**linalg.sinm, linalg.cosm**和 **linalg.tanm**

双曲三角函数：**linalg.sinhm, linalg.coshm**和 **linalg.tanhm**

\*任意函数：**linalg.funm**

**案例：** 指数函数、三角函数
```py
>>> from scipy.linalg import expm, sinm, cosm

>>> expm(np.zeros((2,2)))

array([[1., 0.],

[0., 1.]])

>>> #Euler’s identity(欧拉等式) exp(i*theta) = cos(theta) + i*sin(theta)

>>> a = np.array([[1.0, 2.0], [-1.0, 3.0]])

>>> expm(1j*a)

array([[ 0.4264593 +1.89217551j, -2.13721484-0.97811252j],

[ 1.06860742+0.48905626j, -1.71075555+0.91406299j]])

>>> cosm(a) + 1j*sinm(a)

array([[ 0.4264593 +1.89217551j, -2.13721484-0.97811252j],

[ 1.06860742+0.48905626j, -1.71075555+0.91406299j]])
```
**案例：** 指数函数、对数函数
```py
>>> from scipy.linalg import logm, expm

>>> a = np.array([[1.0, 3.0], [1.0, 4.0]])

>>> b = logm(a)

>>> b

array([[-1.02571087, 2.05142174],

[ 0.68380725, 1.02571087]])

>>> expm(b) # Verify expm(logm(a)) returns a

array([[1., 3.],

[1., 4.]])
```
**4特殊矩阵**

| **名称**          | **函数**                                                                                                                                                               | **描述**                     |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------|
| block diagonal    | [scipy.linalg.block_diag](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.block_diag.html#scipy.linalg.block_diag)                         | 从提供的数组创建块对角矩阵。 |
| circulant         | [scipy.linalg.circulant](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.circulant.html#scipy.linalg.circulant)                            | 创建循环矩阵。               |
| companion         | [scipy.linalg.companion](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.companion.html#scipy.linalg.companion)                            | 创建伴随矩阵。               |
| convolution       | [scipy.linalg.convolution_matrix](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.convolution_matrix.html#scipy.linalg.convolution_matrix) | 创建卷积矩阵。               |
| Discrete Fourier  | [scipy.linalg.dft](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.dft.html#scipy.linalg.dft)                                              | 创建离散傅里叶变换矩阵。     |
| Fiedler           | [scipy.linalg.fiedler](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.fiedler.html#scipy.linalg.fiedler)                                  | 创建对称菲德勒矩阵。         |
| Fiedler Companion | [scipy.linalg.fiedler_companion](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.fiedler_companion.html#scipy.linalg.fiedler_companion)    | 创建 Fiedler 伴随矩阵。      |
| Hadamard          | [scipy.linalg.hadamard](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.hadamard.html#scipy.linalg.hadamard)                               | 创建哈达马德矩阵。           |
| Hankel            | [scipy.linalg.hankel](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.hankel.html#scipy.linalg.hankel)                                     | 创建一个汉克尔矩阵。         |
| Helmert           | [scipy.linalg.helmert](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.helmert.html#scipy.linalg.helmert)                                  | 创建赫尔默特矩阵。           |
| Hilbert           | [scipy.linalg.hilbert](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.hilbert.html#scipy.linalg.hilbert)                                  | 创建希尔伯特矩阵。           |
| Inverse Hilbert   | [scipy.linalg.invhilbert](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.invhilbert.html#scipy.linalg.invhilbert)                         | 创建希尔伯特矩阵的逆矩阵。   |
| Leslie            | [scipy.linalg.leslie](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.leslie.html#scipy.linalg.leslie)                                     | 创建莱斯利矩阵。             |
| Pascal            | [scipy.linalg.pascal](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.pascal.html#scipy.linalg.pascal)                                     | 创建一个帕斯卡矩阵。         |
| Inverse Pascal    | [scipy.linalg.invpascal](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.invpascal.html#scipy.linalg.invpascal)                            | 创建帕斯卡矩阵的逆矩阵。     |
| Toeplitz          | [scipy.linalg.toeplitz](https://docs.scipy.org/doc/scipy/reference/reference/generated/scipy.linalg.toeplitz.html#scipy.linalg.toeplitz)                               | 创建托普利茨矩阵。           |
| Van der Monde     | [numpy.vander](https://numpy.org/devdocs/reference/generated/numpy.vander.html#numpy.vander)                                                                           | 创建一个范德蒙德矩阵。       |



### 微积分

scipy.integrate包含基于函数公式的积分和基于采样值的积分两类积分方法以及常微分方程求解。以下所有函数的调用均在相关库以及scipy导入前提下进行。

**1基于函数公式积分**

**链接：** [https://docs.scipy.org/doc/scipy/reference/tutorial/integrate.html#](https://docs.scipy.org/doc/scipy/reference/tutorial/integrate.html#)

加*部分教学要求较低，感兴趣的同学可以点击进行链接学习

**函数：integrate.quad(integrand, x1, x2, args=(a,b))**

**说明：** 使用quad( )进行通用积分，其中integrand为积分公式（或者函数），x1, x2为积分下限和上限（可以为常数或者无穷inf），args为积分式中的其他参数，求积分前需要赋值。可以在定义integrand中使用quad再对公式积分实现多重积分。

**案例：** 假设求下列积分：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image005.png)

```py
>>> from scipy.integrate import quad

>>> #定义积分函数

>>> def integrand(x, a, b):

... return a*x**2 + b

...

>>> a = 2 #积分前必须对函数中参数赋值

>>> b = 1

>>> I = quad(integrand, 0, 1, args=(a,b))

>>> I

(1.6666666666666667, 1.8503717077085944e-14)
```
**函数：**

二重积分：**integrate.dblquad(integrand, x1, x2, y1, y2)**

三重积分：**integrate.tplquad(),**

多重积分：**integrate.nquad()**

**说明：** integrand可以使用lambda函数定义变量，x1, x2和y1,y2为两次积分边界，多重积分中边界可以定义为list型的n个常数区间或者无穷边界。

**案例：** 假设求下列积分：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image006.png)

```py
>>> from scipy.integrate import dblquad #二重积分

>>> #积分范围使用lambda函数 “：”前为变量，后为函数式

>>> area = dblquad(lambda x, y: x*y, 0, 0.5, lambda x: 0, lambda x: 1-2*x)

>>> area

(0.010416666666666668, 4.101620128472366e-16)
```
**案例：** 假设求下列积分：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image007.png)

```py
>>> from scipy import integrate #多重积分

>>> N = 5

>>> def f(t, x):

... return np.exp(-x*t) / t**N

...

>>> #积分范围使用list给出

>>> integrate.nquad(f, [[1, np.inf],[0, np.inf]])

(0.2000000000189363, 1.3682975855986131e-08)
```
*高斯型积分:

**integrate.fixed_quad**（固定阶高斯积分）

**integrate.quadrature**（多阶高斯积分）

\*Romberg积分：**integrate.romberg**

**2基于采样值积分**

\*梯形法则：**integrate.trapezoid**

\*辛普森法则：**integrate.simpson**

**3常微分方程求解**

**函数：integrate.odeint()**

**说明：** 用于求解以下形式的常微分方程

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image008.png)

函数完整调用形式
```py
scipy.integrate.odeint(func, y0, t, args=(), Dfun=None, col_deriv=0, full_output=0, ml=None, mu=None, rtol=None, atol=None, tcrit=None, h0=0.0, hmax=0.0, hmin=0.0, ixpr=0, mxstep=0, mxhnil=0, mxordn=12, mxords=5, printmessg=0, tfirst=False)
```
func即y在t处的导数的函数式，y0为初值条件，用数组表示，t为求解函数值对应的时间点的序列。序列的第一个元素是与初始条件 y0 对应的初始时间 t0；时间序列必须是单调递增或单调递减的，允许重复值。。

**案例：**

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image009.png)

```py
# ode.py

from scipy.integrate import odeint

import numpy as np

import matplotlib.pyplot as plt

def dy_dt(y,t):

return np.sin(t**2)

y0=[1]

t = np.arange(-10,10,0.01)

y=odeint(dy_dt,y0,t)

plt.plot(t, y)

plt.title("picture")

plt.show()
```
运行结果如下图：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image010.png)

### 概率统计

scipy.stats包含了随机变量生成、构建分布和统计描述等多种函数，可以处理连续和离散分布，以下仅列出部分函数功能。

**1随机变量**（以连续分布为例，离散分布的特殊性有单独模块指出）

**常用方法：** 如下表：

| 名称      | 描述                             |
|-----------|----------------------------------|
| rvs( )    | 生成随机变量                     |
| pdf( )    | 概率密度函数                     |
| cdf( )    | 累积分布函数（pdf积分）          |
| sf( )     | 生存函数（1-cdf）                |
| ppf( )    | 百分位函数（cdf反函数）          |
| isf( )    | 生存函数反函数                   |
| stats( )  | 返回均值、方差、Fisher偏度和峰度 |
| moment( ) | 分布的非中心距                   |



**案例：**
```py
>>> from scipy import stats

>>> from scipy.stats import norm

>>> # random产生loc为5的标准正态分布随机数

>>> norm.cdf(0) #标准正态分布的cdf在0处函数值

0.5

>>> norm.mean(), norm.std(), norm.var()#均值、范数、方差

(0.0, 1.0, 1.0)

>>> norm**.**rvs**(**size**=3)**

array([-0.35687759, 1.34347647, -0.11710531])

>>> # random大小为3的标准正态分布向量

>>> norm**.**rvs**(5)**

5.471435163732493

>>> #随机数生成还可以使用numpy.random.Generator
```
**偏移与缩放**：所有连续分布可以调整参数loc和scale，例如标准正态分布loc是均值scale是标准差。通常情况使一个分布X标准化可以用指令X(X - loc) / scale得到，loc = 0，scale = 1。
```py
>>> norm.stats(loc=3, scale=4, moments="mv")

(array(3.0), array(16.0))
```
**形态参数：** 一般情况连续分布的形态可以由loc和scale确定，但有些情况需要额外参数确定分布的形态，例如gamma分布中参数a=1时变为指数分布。

**冻结分布：** python指令中例如调用norm或者gamma中参数可设置，当使用赋值语句生成随机变量后参数冻结，不可更改，例如rv== gamma(1, scale=2.)。

**离散分布的特殊之处：** 离散分布大多数函数与连续分布类似，概率密度函数为pmf，没有估计方法，scale不是合法参数，关键字loc仍可以用于偏移。连续分布的cdf一般为严格递增，所以有唯一的反函数ppf，而离散分布cdf为阶跃函数，所以cdf反函数ppf定义不同：
```py
ppf(q) = min{x : cdf(x) >= q, x integer}
```
**分布拟合：** 非冻结分布的参数估计方法如下

fit：分布参数的最大似然估计，包括location与scale

fit_loc_scale: 给定形态参数确定下的location和scale参数的估计

nnlf:负对数似然函数

expect:计算函数pdf或pmf的期望值。

**说明：** 运行速度因分布类型差异极大，精确计算一般更快，直接使用解析公式如scipy.special中函数，随机变量rvs还可以使用numpy.random中的函数。scipy.stats中分布仍有分布在特殊临界条件下出现错误值。

**2构建具体分布**

**连续分布：** 继承rv_continuous类

**案例：**
```py
>>> from scipy import stats

>>> class deterministic_gen(stats.rv_continuous):

... def _cdf(self, x):

... return np.where(x < 0, 0., 1.)

... def _stats(self):

... return 0., 0., 0., 0.

>>> deterministic = deterministic_gen(name="deterministic")

>>> deterministic.cdf(np.arange(-3, 3, 0.5))

array([ 0., 0., 0., 0., 0., 0., 1., 1., 1., 1., 1., 1.])

>>> deterministic.pdf(np.arange(-3, 3, 0.5))

array([ 0.00000000e+00, 0.00000000e+00, 0.00000000e+00,

0.00000000e+00, 0.00000000e+00, 0.00000000e+00,

5.83333333e+04, 4.16333634e-12, 4.16333634e-12,

4.16333634e-12, 4.16333634e-12, 4.16333634e-12])
```
**离散分布：** 继承rv_discrete类

**说明：** 构造一个任意离散的rv，其中![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image011.png)，方法是将rv_discrete初始化时（通过values=关键字）传递一个序列元组![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image012.png)，该元组仅描述那些以非零概率（![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image013.png)）出现的![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/scipy/image014.png)值。

**3样本分析**

**描述统计：**

1） x是一个numpy数组，直接查看数字特征

x.min, x.max, x.mean, x.var（np.var是有偏估计）

2）使用scipy.stats （stats.describe是无偏估计）

**案例：**
```py
>>> from scipy import stats

>>> x = stats.t.rvs(10, size=1000)

>>> #T分布生成一个自由度10大小1000的随机变量

>>> print(x.min()) # 等价于 np.min(x)

-4.791173625654017

>>> print(x.max()) # 等价于 np.max(x)

4.58334872100337

>>> print(x.mean()) # 等价于 np.mean(x)

0.02380110096856749

>>> print(x.var()) # e等价于 np.var(x))

1.2803416239455527

>>> m, v, s, k = stats.t.stats(10, moments='mvsk')

>>> #返回T分布均值、方差、偏度、峰度

>>> n, (smin, smax), sm, sv, ss, sk = stats.describe(x)

>>> 返回x一个样本的均值、方差、偏度、峰度

>>> sstr = '%-14s mean = %6.4f, variance = %6.4f, skew = %6.4f, kurtosis = %6.4f'

>>> print(sstr % ('distribution:', m, v, s ,k))

distribution: mean = 0.0000, variance = 1.2500, skew = 0.0000, kurtosis = 1.0000

>>> print(sstr % ('sample:', sm, sv, ss, sk))

sample: mean = 0.0238, variance = 1.2816, skew = 0.0655, kurtosis = 0.8404
```
*T检验和KS检验：使用t检验是否样本与给定均值（这里是理论均值）存在显著统计差异；使用Kolmogorov-Smirnov检验（KS检验）检验样本是否来自一个标准的t分布。

**4比较两个样本是否属于同一个分布**

*检验均值或使用KS检验

**5、由样本函数估计分布概率密度**

*核密度估计：单元估计或者多元估计



## Matplotlib软件包使用

Matplotlib的全称是mathematic plot library，这个名称非常简练而准确地概括了它的功能：创建各种各样的可视化内容，这些内容可以是静态的、动态的，甚至是可交互的。其官方文档请见网址https://matplotlib.org/。

pyplot是Matplotlib中的一个重要子库，它包含了各种函数使得Matplotlib的代码风格贴近Matlab，接下来以其为中心展开。

**基础图表绘制**

pyplot库支持绘制5种图表：连续平面图、散点图、柱状图、茎叶图、阶梯图。

连续平面图由matplotlib.pyplot.plot函数实现，典型范例如下：
```py
import matplotlib.pyplot as plt

import numpy as np

x = np.linspace(0, 10, 100)

y = 4 + 2 * np.sin(2 * x)

plt.plot(x, y)

plt.show()
```
对比功能相同的Matlab的代码：
```matlab
x = linspace(0, 10, 100);

y = 4 + 2 * sin(2 * x);

plot(x, y);
```
可以发现代码风格几乎相同，不同之处是前者还需要导入库，绘图的函数作为库中的方法呈现。此外，Matplotlib画完图之后可能需要使用show()方法将图窗显示出来。

其他五种图表与连续平面图绘制方法大同小异，欲绘制散点图，将本例中的plot函数改成scatter函数即可；同理，stem函数绘制茎叶图，bar函数绘制柱状图，step函数绘制阶梯图。

再看本例，绘制图形时，传入的x和y必须是相同长度的数组，否则会出错。本例中只有一个x数组和一个y数组，若需要根据多个x数组和相同数量的y集合一次性画出多个图形，例如x1, x2和y1, y2，则需要将本例中的代码修改为以下代码即可。

```plt.plot(x1, y1, x2, y2)```

如果需要在同一个图窗里放置多个坐标系，在Matlab中我们使用subplot函数，而pyplot子库也提供了相同名称的函数，用法也完全相同。subplot(m,n,p)表示将整个图窗分块为m行n列，每一块放置一个坐标系，各个分块的编号和我们平时写字的顺序是相同的：规定左上角为第1块，往右编号递增，下一行最左边的分块紧接着本行最右边的分块，而接下来所有的绘图都在第p个分块的坐标系中进行。如果m,n,p都只有一位数，此时可以把逗号去掉，例如subplot(2,2,1)可以写成subplot(221).

有一点需要注意，在Matlab中，如果我们连续两次调用绘图的函数，在调用第二次的时候默认先擦除第一次所绘制的图像，除非在第二次绘图之前使用hold on语句让其保持。但matplotlib刚好相反，连续绘制不会擦除之前的图像，除非使用pyplot中的cla函数清除当前坐标系中的图像，或使用clf函数清除当前图窗中所有坐标系的图像。

接下来的例子较为综合地应用了以上的知识点。
```py
import matplotlib.pyplot as plt

x = [1,2,3,4,5,7.2];

y = [1,3,1,2,4,1];

# 连续图和散点图画在同一个图里

plt.subplot(321)

plt.plot(x,y)

plt.scatter(x,y)

# 柱状图

plt.subplot(222)

plt.bar(x,y)

# 茎叶图

plt.subplot(223)

plt.stem(x,y)

# 阶梯图

plt.subplot(224)

plt.step(x,y)

plt.show()
```
最终弹出如下图窗（在Jupyter Notebook中弹不出图窗），Matplotlib允许使用多种格式保存图像，这里采用.svg矢量图。

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/matplotlib%E8%BD%AF%E4%BB%B6%E5%8C%85%E4%BD%BF%E7%94%A8/image001.png)

此外该图窗还允许与这些坐标系互动，可以缩放、平移等。

**线条和标识**

线条属性既可以作为绘图函数的参数输入，又可以在事后再修改。plot函数的线条有以下几个常用的属性。

| 属性（可点击）                                                                                       | 含义         | 对应函数      | 取值                          |
|------------------------------------------------------------------------------------------------------|--------------|---------------|-------------------------------|
| linewidth                                                                                            | 线宽         | set_linewidth | 浮点数，默认为1.0             |
| [linestyle](https://matplotlib.org/stable/gallery/lines_bars_and_markers/linestyles.html#linestyles) | 线的风格     | set_linestyle | 字符串，例如'-'或'solid'      |
| [color](https://matplotlib.org/stable/gallery/color/named_colors.html#list-of-named-colors)          | 颜色         | set_color     | 字符串，例如'red'或'\#ff0000' |
| [marker](https://matplotlib.org/stable/api/markers_api.html#module-matplotlib.markers)               | 数据点的标记 | set_marker    | 字符串，例如'.', 'o', '\^'    |
| label                                                                                                | 数据标签     | set_label     | 字符串，用于图例              |



使用方法一：在绘制的时候当作参数输入。

```py
plt.plot(x, y, linewidth=2, linestyle='dashdot', color='g', marker='^')
```

使用方法二：plot函数返回线条对象列表（指定了多少组x-y数组就有多少个线条对象），调用线条对象的“对应函数”（如上表所示）。
```py
lines = plt.plot(x, y)

lines[0].set_linewidth(2)

lines[0].set_linestyle('dashdot')

lines[0].set_color('green')

lines[0].set_marker('^')
```
以上两段代码效果相同。

坐标区域的属性设置和Matlab相似，在Matlab中，我们使用xlabel函数来设置横坐标的标签，ylabel函数设置纵坐标的标签，title函数设置坐标区域的标题，xlim设置x轴的范围，ylim设置y轴的范围，legend设置图例。pyplot子库也提供了名称和用法完全相同的函数。

**文字说明**

在Matlab中，我们使用text函数向坐标区中的某个点（坐标）添加文字，pyplot子库也提供了同名同功能的函数。最简单的用法是
```py
plt.text(x, y, str)
```
这一行代码将文字str添加在当前坐标区的(x,y)处，默认情况下，最后一行文字的水平中心线为y，且文字添加在该点的右侧，这些都可以修改，作为参数调用text函数。text函数如下表。

| 属性           | 含义     | 取值                                        |
|----------------|----------|---------------------------------------------|
| fontfamily     | 字体名称 | 字符串，比如'Simsun'（宋体）                |
| fontsize       | 字体大小 | 浮点数或'small', 'medium', 'large'等        |
| fontweight     | 字体粗细 | 0-1000的数值或'normal', 'regular', 'bold'等 |
| color          | 字体颜色 | 同线条的color属性                           |
| multialignment | 对齐方式 | 字符串，可取'left', 'right', 'center'       |
| position       | 文字位置 | 表示坐标的数组，主要用于事后修改            |


同线条属性，文字属性也可以事后再设置，text函数返回文字对象，调用文字对象的set_xxx函数便可以设置了，例如以下代码：

```py
plt.text(2, 3, 'string', fontfamily='Arial', fontsize='14', fontweight = 'regular')
```

等效为以下代码：
```py
txt = plt.text(2, 3, 'string')

txt.set_fontfamily('Arial')

txt.set_fontsize(14)

txt.set_fontweight('regular')
```
一种更灵活的注释方式是pyplot的annotate函数，可以看作带箭头的text函数，效果是箭头指向需要注释的点，字体的属性可以设置，箭头的属性也可以设置。

最简单的例子是：

```py
plt.annotate('string', xy=(2,3), xytext=(3,4), arrowprops=dict(facecolor='black'))
```

结合第一节的例子，效果如下图：

![image](https://github.com/mmaayybelin/signal-processing_python/blob/main/images/matplotlib%E8%BD%AF%E4%BB%B6%E5%8C%85%E4%BD%BF%E7%94%A8/image002.png)

即创建了一个注释，注释的点是第一个坐标区的(2,3)，文字放在(3,4)处并且左对齐。

