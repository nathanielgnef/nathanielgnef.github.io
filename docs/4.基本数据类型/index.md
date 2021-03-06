# 4.基本数据类型


## 变量

Python 中的变量不需要声明。每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建  
在 Python 中，变量没有类型，我们所说的"类型"是变量所指的内存中对象的类型

## 标准数据类型

不可变数据：
- Number（数字）
- String（字符串）
- Tuple（元组）

可变数据：
- List（列表）
- Set（集合）
- Dictionary（字典）

如果改变数据类型的值，将重新分配内存空间

## 判断数据类型

`type()`：  
语法：
1. `type(object)`
2. `type(name, bases, dict, **kwds)`

用法：https://docs.python.org/3/library/functions.html#type
```python
    >>> a,b,c,d = 20,5.5,True,4+3j
    >>> print(type(a),type(b),type(c),type(d))
    <class 'int'> <class 'float'> <class 'bool'> <class 'complex'>
```

`isinstance()`：  
语法：`isinstance(object,classinfo)`  
用法：https://docs.python.org/3/library/functions.html#isinstance
```python
    >>> a = 111
    >>> isinstance(a, int)
    True
```

`isinstance()`和`type()`的区别在于：
- `type()`不会认为子类是一种父类类型，不考虑继承关系
- `isinstance()`会认为子类是一种父类类型，考虑继承关系

```python
    >>> class A:
    ...     pass
    ... 
    >>> class B(A):
    ...     pass
    ... 
    >>> isinstance(A(), A)
    True
    >>> type(A()) == A 
    True
    >>> isinstance(B(), A)
    True
    >>> type(B()) == A
    False
```

