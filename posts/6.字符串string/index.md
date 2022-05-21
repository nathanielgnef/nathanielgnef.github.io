# 6.字符串String


格式：
- 单引号：`'允许包含有 "双" 引号'`
- 双引号：`"允许包含有 '单' 引号"`
- 三重引号：`'''三重单引号'''`，`"""三重双引号"""`

补充说明：
- Python 没有单独的字符类型，一个字符就是长度为 1 的字符串
- Python 中单引号 ' 和双引号 " 使用完全相同
- 按字面意义级联字符串，如`"this ""is ""string"`会被自动转换为`this is string`
- 使用三引号 ( ''' 或 """ ) 可以指定一个多行字符串
    ```python
        >>> str1 = """这是一个
        ... 多行字符串"""
        >>> print(str1)
        这是一个
        多行字符串
    ```
- Python 中的字符串不能被修改，向一个索引位置赋值，比如`word[0] = 'm'`会导致错误

## 编码

在 Python 3 中，所有的字符串默认都是 Unicode 字符串

## 转义字符

```python
    \\                          #反斜杠
    \'                          #单引号
    \"                          #双引号
    \a                          #响铃
    \b                          #退格
    \000                        #空
    \n                          #换行
    \v                          #纵向制表符
    \t                          #横向制表符
    \r                          #回车，将 \r 后面的内容移到字符串开头，并逐一替换开头部分的字符，直至将 \r 后面的内容完全替换完成
    \f                          #换页
    \ooo                        #八进制值
    \xhh                        #十六进制值
```

## 原始字符r/R

使用 r/R 可以让反斜杠 \ 不发生转义
```python
    >>> str1 = 'Ru\noob'
    >>> print(str1)
    Ru
    oob
    >>> str2 = r"Ru\noob"
    >>> str3 = R"Ru\noob"
    >>> print(str2)
    Ru\noob
    >>> print(str3)
    Ru\noob
```

## 索引

格式：`变量[下标]`  
索引方式：
- 从左往右以0开始
- 从右往左以-1开始

取值：不能越界

## 截取(切片)

格式：`变量[start:stop[:step]]`  
取值：
- 取值区间左闭右开，会自动处理越界索引
- step默认值为1，为正顺序，为负逆序

```python
    >>> str1 = 'HelloWorld'
    >>> print(str1)                  #打印str1
    HelloWorld
    >>> print(str1[2:-2])            #打印从第三个到倒数第三个字符的字符串
    lloWor
    >>> print(str1[2:])              #打印从第三个到结束的字符串
    lloWorld
    >>> print(str1[2:5])             #打印从第三个到第五个字符的字符串
    llo
    >>> print(str1[2:-2:2])          #以步长2顺序打印从第三个到倒数第三个的字符串
    loo
    >>> str1[:12]                    #截取到下标12的字符串
    'HelloWorld'
    >>> str1[-12:]                   #截取下标-12到结束的字符串
    'HelloWorld'
    >>> str1[::-1]                   #以步长-1逆序截取整个字符串
    'dlroWolleH'
    >>> str1[0:12:-1]                #以步长-1逆序截取下标0到下标12的字符串
    ''
    >>> str1[0::-1]                  #以步长-1逆序截取下标0到结束的字符串
    'H'
    >>> str1[-1::-1]                 #以步长-1逆序截取下标-1到结束的字符串
    'dlroWolleH'
    >>> str1[-1:-12:-1]              #以步长-1逆序截取下标-1到下标-12的字符串
    'dlroWolleH'
```

## 迭代

格式：`for x in 'HelloWorld':print(x,end=" ")`

## f-string

f-string是 python3.6 之后版本添加的，称之为字面量格式化字符串，是新的格式化字符串的语法
```python
    >>> str1 = "World"           #替换字符串
    >>> f'Hello {str1}'
    Hello World
    >>> f'{1+2}'                #使用表达式
    3
```

在 Python 3.8 的版本中可以使用 `=` 符号来拼接运算表达式与结果：
```python
    >>> f'{1+2=}'
    1+2=3
```

## 运算符

```python
    +                           #字符串连接
    *                           #重复字符串为一个字符串
    []                          #通过索引获取字符
    [:]                         #截取字符串，左闭右开
    in                          #成员运算符，如果字符串中包含给定的字符返回 True
    not in                      #成员运算符，如果字符串中不包含给定的字符返回 True
    r/R                         #原始字符串
    %                           #格式字符串
```

```python
    >>> str1 = 'Hello'
    >>> str2 = 'World'
    >>> newstr = str1+str2
    >>> newstr1 = newstr*2
    >>> print(newstr)
    HelloWorld
    >>> print(newstr1)
    HelloWorldHelloWorld
    >>> print('H' in str1)
    True
    >>> print('a' not in str1)
    True
```

## 支持String的函数

```python
    len(str1)                  #返回str1的元素个数
    max(str1)                  #返回str1的元素最大值
    min(str1)                  #返回str1的元素最小值
    str(object)                #将对象object的打印转换为String，并返回该String
```

## String的方法

`encode()`与`decode()`解析：  
在Python中，str 表示字符串，bytes 表示字节串。str 类型和 bytes 类型之间转换需要使用`encode()`和`decode()`方法

`encode()`语法：  
`str.encode([encoding="utf-8"][,errors="strict"])`

`decode()`语法：  
`bytes.decode([encoding="utf-8"][,errors="strict"])`  

`errors`取值：
- strict：遇到无法编码的字符就抛出异常，默认取值为strict
- ignore：忽略无法编码的字符
- replace：用“？”替换无法编码的字符
- xmlcharrefreplace：用xml字符替换无法编码的字符
- backslashreplace：使用反斜杠代替无法编码的字符
- namereplace：用说明字符的文本替换无法编码的字符

```python
    >>> str1 = 'heLLOWorld'
    >>> print(str1.capitalize())             #将字符串的首字符进行大写，其余小写
    Helloworld
    >>> print(str1.center(20,'*'))           #返回一个指定的宽度 width 居中的字符串，fillchar 为填充的字符，默认为空格
    *****heLLOWorld*****
    >>> print(str1.center(1))                #width小于原字符串，将返回原字符串
    heLLOWorld
    >>> substr = "Wo"
    >>> print(str1.count('L'))               #返回字符串在str中出现的次数
    2
    >>> print(str1.count(substr,3))             #返回从第3个字符开始查找字符串在str中出现的次数
    1
    >>> print(str1.count(substr,3,len(str1)))    #返回字符串在设定字符串中出现的次数
    1
    str2 = "中文字符串"
    >>> print(str2.encode())                 #对str1进行默认utf-8编码，默认错误处理方式为strict
    >>> print(str2.encode("GB2312"))         #对str1指定GB2312编码，默认错误处理方式为strict
    >>> print(str2.encode(encoding="GBK",errors="backslashreplace"))              #对str1指定GBK编码，错误处理方式为backslashreplace
    bytes = str2.encode()
    >>> print(bytes.decode())                #对bytes进行默认utf-8解码，默认错误处理方式为strict
    >>> print(bytes.decodeO("GB2312"))       #对bytes指定GB2312解码，默认错误处理方式为strict
    >>> print(bytes.decode(encoding="GBK",errors="backslashreplace"))              #对bytes指定GBK解码，错误处理方式为backslashreplace
```
