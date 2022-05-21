# 3.基础语法


## 编码

默认情况下，Python 3 源码文件以 UTF-8 编码，所有字符串都是 Unicode 字符串

## 标识符

* 第一个字符必须是字母表中字母或下划线`_`
* 标识符的其他的部分由字母、数字和下划线`_`组成
* 标识符对大小写敏感

在Python3中，可以用中文作为变量名，非 ASCII 标识符也是允许的

Python可以同一行显示多条语句，方法是用分号`;`分开

## Python保留字
保留字即关键字，我们不能把它们用作任何标识符名称
Python的标准库提供了一个keyword模块，可以输出当前版本的所有关键字
```python
        >>> import keyword
        >>> keyword.kwlist
        ['False', 'None', 'True', '__peg_parser__', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

## 注释

- 单行注释以#开头  
- 多行注释可以用多个`#`号，还有`'''`和`"""`

```python
        # 注释1
        # 注释2

        '''
        注释块1
        '''

        """
        注释块2
        """
```

## 行和缩进

Python最具特色的就是使用缩进来表示代码块，不需要使用大括号{}  
缩进的空格数是可变的，但是同一个代码块的语句必须包含相同的缩进空格数

## 多行语句

1. 多行连接符：`\`
```python
        >>> str = "item_one " + \
        ...       "item_two " + \
        ...       "item_three"
        >>> 
        >>> print(str)        
        item_one item_two item_three
```

2. 语句中包含`[]`,`{}`或`()`括号就不需要使用多行连接符
```python
        >>> days = ['Monday', 'Tuesday', 'Wednesday','Thursday', 'Friday']
        >>> print(days)
        ['Monday', 'Tuesday', 'Wednesday', 'Thursday','Friday']
```

## 空行

函数之间或类的方法之间用空行分隔，表示一段新的代码的开始。类和函数入口之间也用一行空行分隔，以突出函数入口的开始  
空行与代码缩进不同，空行并不是 Python 语法的一部分。书写时不插入空行，Python 解释器运行也不会出错  
但是空行的作用在于分隔两段不同功能或含义的代码，便于日后代码的维护或重构  
**记住**：空行也是程序代码的一部分

## 同一行使用多条语句

Python 可以在同一行中使用多条语句，语句之间使用分号`;`分割

## 多个语句构成代码组

缩进相同的一组语句构成一个代码块，我们称之代码组  
像`if`、`while`、`def`和`class`这样的复合语句，首行以关键字开始，以冒号`:`结束，该行之后的一行或多行代码构成代码组  
我们将首行及后面的代码组称为一个子句(clause)
```python

        if expression :
        suite
        elif expression :
        suite
        else :
        suite
```

## print输出

print 默认输出是换行的，如果要实现不换行需要设置参数`end=""`，参数默认值为`end="\n"`
```python
        >>> x = 1
        >>> y = 2 
        >>> print(x);print(y)
        1
        2
        >>> print(x,end="");print(y,end="")
        12>>>
```

## import 与 from...import

在 Python 用`import`或者`from...import`来导入相应的模块
将整个模块(somemodule)导入，格式为：`import somemodule`  
从某个模块中导入某个函数,格式为：`from somemodule import somefunction`
从某个模块中导入多个函数,格式为：`from somemodule import firstfunc, secondfunc, thirdfunc`  
将某个模块中的全部函数导入，格式为： `from somemodule import *`

## 命令行参数

Python 可以使用`-h`参数查看各参数帮助信息

## 删除对象

可以使用`del`语句删除一些对象
语法：`del var1[,var2[,var3[....,varN]]]`
```python
    del var
    del var1,var2
```

