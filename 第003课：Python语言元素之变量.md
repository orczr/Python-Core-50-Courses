## 第003课：Python语言元素之变量

经常被外行问到两个问题，其一是“什么是（计算机）程序”，其二是“写（计算机）程序能做什么”，这里我们先来回答这两个问题。**程序是指令的集合**，**写程序就是用指令控制计算机做我们想让它做的事情**。那么，为什么要用Python语言来写程序呢？因为**Python语言简单优雅**，相比C、C++、Java这样的语言，**Python对初学者更加友好**，当然这并不是说Python不像其他语言那样强大，**Python几乎是无所不能的**，还能用来粘合其他语言开发的系统，所以也被戏称为“**胶水语言**”。

### 一些计算机常识

计算机的硬件系统通常由五大部件构成，包括：**运算器**、**控制器**、**存储器**、**输入设备**和**输出设备**。其中，运算器和控制器放在一起就是我们通常所说的**中央处理器**，它的功能是执行各种运算和控制指令。刚才说过了，程序是指令的集合，写程序就是将一系列的指令按照某种方式组织到一起，然后通过这些指令去控制计算机做我们想让它做的事情。今天我们大多数人使用的计算机都是“冯·诺依曼体系结构”的计算机，这种计算机有两个关键点：一是要将**存储设备与中央处理器分开**；二是将**数据以二进制方式编码**。

二进制是一种“逢二进一”的计数法，跟我们人类使用的“逢十进一”的计数法没有实质性的区别，人类因为有十根手指所以使用了十进制，因为在数数时十根手指用完之后就只能进位了。当然凡事都有例外，玛雅人可能是因为长年光着脚的原因把脚趾头也算上了，于是他们使用了二十进制的计数法，在这种计数法的指导下，玛雅人的历法就与我们平常使用的历法不一样。按照玛雅人的历法，2012年是上一个所谓的“太阳纪”的最后一年，而2013年则是新的“太阳纪”的开始，后来这件事情被以讹传讹的方式误传为”2012年是玛雅人预言的世界末日“的荒诞说法。今天很多人都在猜测，玛雅文明之所以发展缓慢跟使用了二十进制是有关系的。对于计算机来说，二进制在物理器件上来说是最容易实现的（高电压表示1，低电压表示0）。不是说写程序的人必须都需要知道十进制与二进制如何相互转换，大多数时候我们也用不上这些知识，但是我们必须要知道的是我们的**计算机使用二进制**，不管什么**数据到了计算机内存中都是以二进制形式存在的**。

### 变量和类型

在程序设计中，**变量是一种存储数据的载体**。简单的说，变量是保存数据的一块内存空间，**变量的值可以被读取和修改**，这是所有计算和控制的基础。计算机能处理的数据有很多种类型，除了数值之外还可以处理文本、图形、音频、视频等各种各样的数据。虽然最终数据都是以二进制的形态存在的，但是我们可以用不同类型的变量来表示数据类型的差异。**Python中的数据类型很多**，而且也**允许我们自定义新的数据类型**（这一点在后面会讲到），我们先介绍几种常用的数据类型。

- 整型（int）：Python中可以处理任意大小的整数，而且支持二进制（如`0b100`，换算成十进制是4）、八进制（如`0o100`，换算成十进制是64）、十进制（`100`）和十六进制（`0x100`，换算成十进制是256）的表示法。
- 浮点型（float）：浮点数也就是小数，之所以称为浮点数，是因为按照科学记数法表示时，一个浮点数的小数点位置是可变的，浮点数除了数学写法（如`123.456`）之外还支持科学计数法（如`1.23456e2`）。
- 字符串型（str）：字符串是以单引号或双引号括起来的任意文本，比如`'hello'`和`"hello"`。
- 布尔型（bool）：布尔值只有`True`、`False`两种值，要么是`True`，要么是`False`。

### 变量命名

对于每个变量我们需要给它取一个名字，就如同我们每个人都有属于自己的响亮的名字一样。在Python中，变量命名需要遵循以下这些必须遵守硬性规则和强烈建议遵守的非硬性规则。

- 硬性规则：
  - 变量名由**字母**（广义的Unicode字符，不包括特殊字符）、数字和**下划线**构成，数字不能开头。
  - **大小写敏感**（大写的`a`和小写的`A`是两个不同的变量）。
  - **不要跟关键字**（有特殊含义的单词，后面会讲到）和系统**保留字**（如函数、模块等的名字）**冲突**。
- 非硬性规则
  - 用小写字母拼写，多个单词用下划线连接。
  - 受保护的变量用单个下划线开头（后面会讲到）。
  - 私有的变量用两个下划线开头（后面会讲到）。

当然，作为一个专业的程序员，给变量（事实上应该是所有的标识符）命名时做到见名知意也是非常重要的。

### 变量的使用

下面通过几个例子来说明变量的类型和变量使用。

```Python
"""
使用变量保存数据并进行加减乘除运算

Version: 0.1
Author: 骆昊
"""
a = 321
b = 12
print(a + b)    # 333
print(a - b)    # 309
print(a * b)    # 3852
print(a / b)    # 26.75
```

在Python中可以使用`type`函数对变量的类型进行检查。程序设计中函数的概念跟数学上函数的概念是一致的，数学上的函数相信大家并不陌生，它包括了函数名、自变量和因变量。如果暂时不理解这个概念也不要紧，我们会在后续的内容中专门讲解函数的定义和使用。

```Python
"""
使用type()检查变量的类型

Version: 0.1
Author: 骆昊
"""
a = 100
b = 12.345
c = 'hello, world'
d = True
print(type(a))    # <class 'int'>
print(type(b))    # <class 'float'>
print(type(c))    # <class 'str'>
print(type(d))    # <class 'bool'>
```

可以使用Python中内置的函数对变量类型进行转换。

- `int()`：将一个数值或字符串转换成整数，可以指定进制。
- `float()`：将一个字符串转换成浮点数。
- `str()`：将指定的对象转换成字符串形式，可以指定编码。
- `chr()`：将整数转换成该编码对应的字符串（一个字符）。
- `ord()`：将字符串（一个字符）转换成对应的编码（整数）。

下面的例子为大家演示了Python中的类型转换。

```Python
"""
Python中的类型转换

Version: 0.1
Author: 骆昊
"""
a = 100
b = 12.345
c = 'hello, world'
d = True
# 整数转成浮点数
print(float(a))    # 100.0
# 浮点型转成字符串 (输出字符串时不会看到引号哟)
print(str(b))      # 12.345
# 字符串转成布尔型 (有内容的字符串都会变成True)
print(bool(c))     # True
# 布尔型转成整数 (True会转成1，False会转成0)
print(int(d))      # 1
# 将整数变成对应的字符 (97刚好对应字符表中的字母a)
print(chr(97))     # a
# 将字符转成整数 (Python中字符和字符串表示法相同)
print(ord('a'))    # 97
```

### 总结

在Python程序中，我们可以**使用变量来保存数据**，**变量有不同的类型**，**变量可以做运算**（下一课会有详细的讲解），**变量还可以进行类型转换**。

>**温馨提示**：大家如果觉得这个专栏还不错，**一定记得点赞收藏哟**！如果学习中遇到困难，可以发私信给我进行交流，也可以看看我们为大家录制的入门视频，视频链接地址：https://pan.baidu.com/s/10y7sGM016YBM7gDdauGqLw，密码：4s6r。

