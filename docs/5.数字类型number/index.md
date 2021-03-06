# 5.数字类型Number


Python 3 的数值类型支持 **int(整型)**、**float(浮点型)**、**bool(布尔型)**、**complex（复数）**

## Int整型

在Python 3 里，只有一种整数类型 int ，表示为长整型

## Bool布尔型

Python 3 中，bool 是 int 的子类，True 和 False 可以和数字相加，`True==1、False==0 `会返回 True，但可以通过 `is` 来判断类型
```python
    >>> True+1
    2
    >>> False+1
    1
    >>> True==1
    True
    >>> False==0
    True
    >>> 1 is True
    <stdin>:1: SyntaxWarning: "is" with a literal. Did you mean "=="?
    False
    >>> 0 is False
    <stdin>:1: SyntaxWarning: "is" with a literal. Did you mean "=="?
    False
```

## 数学运算

```python
    >>> 17 % 3                  #取余
    2
    >>> 2 ** 5                  #幂运算，2的5次方
    32
```

- 隐式转换：  
在混合计算时，Python会把较小的数据类型转换成为较大的数据类型
    ```python
        >>> 17 % 3.0
        2.0
        >>> 2 ** 5.0
        32.0
    ```

- 在交互模式中，最后被输出的表达式结果被赋值给变量 _ 。此处，_ 变量应被用户视为只读变量
    ```python
        >>> tax = 12.5 / 100
        >>> price = 100.50
        >>> price * tax
        12.5625
        >>> price + _
        113.0625
        >>> round(_, 2)             #四舍五入到第2位小数点
        113.06
    ```

数值的除法包含两个运算符：
1. / 返回一个浮点数
2. // 向下取整，返回一个整数。// 得到的并不一定是整数类型的数，它与分母分子的数据类型有关系
    ```python
        >>> 7/2
        3.5
        >>> 7//2        #向下取整，返回整数部分
        3
        >>> 7.0//2
        3.0
        >>> 7//2.0
        3.0
        >>> 7.0//2.0
        3.0
    ```

## 数学常量

1. 数学常量pi(π)
    ```python
        >>> import math
        >>> print(math.pi)
        3.141592653589793
    ```

2. 数学常量e(自然常数)
    ```python
        >>> import math
        >>> print(math.e)
        2.718281828459045
    ```

## 数字类型转换

- `int(x)`将 x 转换为 int 类型
- `float(x)`将 x 转换为 float 类型
- `complex(x)`将 x 转换为实数为 x，虚数为 0 的复数
- `complex(x,y)`返回实数为 x，虚数为 y 的复数

## 数学函数

`math.fabs()`与`abs()`的区别：
- `abs()` 是内置函数，`math.fabs()`在 math 模块中定义
- `math.fabs()` 只对浮点型跟整型数值有效，`abs()`还可以运用在复数中

`pow()`与`math.pow()`的区别：
- `pow(x,y[,z])`当z存在时，等效于`pow(x,y)%z`,对结果进行z取模
- `pow()`会把参数作为整型，`math.pow()`会把参数转换为float

`round(x[,n])`解析：
- n > 0,四舍五入到**第n位小数点**
- n = 0,四舍五入到**最接近的整数**
- n < 0,在小数点**左侧**进行四舍五入

```python
    abs(x)                   #绝对值
    import math
    math.ceil(x)             #向上取整
    math.exp(x)              #e的x次幂
    math.fabs(x)             #返回x的绝对值的浮点数类型
    math.floor(x)            #向下取整
    math.log(x)              #返回x的自然对数，x>0
    math.log10(x)            #返回以10为基底的x的对数，x>0
    max(x1,x2,...)           #最大值，参数可以为序列
    min(x1,x2,...)           #最小值，参数可以为序列
    math.modf(x)             #返回x的整数部分与小数部分，两部分的数值符号与 x 相同，整数部分以浮点型表示
    round(x[,n])             #返回浮点数x的四舍五入值
    math.sqrt(x)             #返回x的平方根，返回值为浮点数
```

## 随机数函数

`randrange([start,] stop [,step])`解析：
- start：   指定范围内的开始值，包含在范围内
- stop：    指定范围内的结束值，不包含在范围内
- step：    指定递增基数

```python
    randrange(10,100,3)         #从[10,13,16,19,...)中返回一个随机数
```

```python
    import random
    random.choice(seq)          #返回随机项，seq可以是一个列表，元组或字符串
    random.randrange([start,] stop [,step])     #从给定的范围返回随机项
    random.random()             #在[0,1)的区间内随机返回一个实数
    random.seed([x])               #改变随机数生成器的种子
    random.shuffle(list)            #对list进行随机排序
    random.uniform(x,y)            #返回一个浮点数 N，取值范围为如果 x < y 则 x <= N <= y，如果 y < x 则y <= N <= x
```

## 三角函数

`degrees(x)`与`radians(x)`解析：  
角度和弧度关系是：  
2π 弧度 = 360°。从而 1°≈0.0174533 弧度，1 弧度≈57.29578°  
- 角度转换为弧度公式：弧度=角度÷180×π
- 弧度转换为角度公式：角度=弧度×180÷π

```python
    import math
    math.acos(x)                    #返回x的反余弦弧度值，x取值[-1,1]
    math.asin(x)                    #返回x的反正弦弧度值，x取值[-1,1]
    math.atan(x)                    #返回x的反正切弧度值
    math.atan2(x,y)                 #返回x,y坐标值的反正切值
    math.cos(x)                     #返回x的弧度的余弦值，返回值为[-1,1]
    math.hypot(x,y)                 #返回欧几里德范数 sqrt(x*x + y*y)
    math.sin(x)                     #返回x的弧度的正弦值，返回值为[-1,1]
    math.tan(x)                     #返回x的弧度的正切值，返回值为[-1,1]
    math.degrees(x)                 #将弧度转换为角度
    math.radians(x)                 #将角度转换为弧度
```

