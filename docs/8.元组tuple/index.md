# 8.元组Tuple


格式：
- 空元组`()`
- 含有元素的元组：
    - 带括号：`(a,)`，`(a,b,c,d,...)`
    - 不带括号：`a,`，`a,b,c,d,...`

补充说明：
- 定义含有一个元素的带括号的元组，应当在元素后面加`,`,以区分`变量 = (值或表达式)`把`()`作为运算符的定义方式
    ```python
        >>> tuple1 = (20)
        >>> tuple1
        20
        >>> type(tuple1)
        <class 'int'>
        >>> tuple2 = (20,)
        >>> tuple2
        (20,)
        >>> type(tuple2)
        <class 'tuple'>
    ```

- 元组中的元素不能被修改，但是可以修改其中的可变序列对象中的元素
    ```python
        >>> tuple1 = 1,2,3,[4,5,6]
        >>> tuple1[3][0] = 9
        >>> tuple1
        (1, 2, 3, [9, 5, 6])
    ```

- 元组中的元素数据类型可以不相同
    ```python
        >>> tuple1 = (1,2,3,'1')
        >>> list1 = ['Hello',7,8,9]
        >>> str1 = 'World'
        >>> tuple2 = (4,5,6,tuple1,str1,list1)
        >>> tuple2
        (4, 5, 6, (1, 2, 3, '1'), 'World', ['Hello', 7, 8, 9])
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

## 迭代

格式：`for x in (1,2,3):print(x,end=" ")`

## 运算符

```python
    +                           #元组连接
    *                           #重复元组为一个元组
    []                          #通过索引获取值
    [:]                         #截取元组，左闭右开
    in                          #成员运算符，如果元组中包含给定的值返回 True
    not in                      #成员运算符，如果元组中不包含给定的值返回 True
```

## 支持Tuple的函数

```python
    len(tuple1)                 #返回Tuple1的元素个数
    max(tuple1)                 #返回Tuple1的元素最大值
    min(tuple1)                 #返回Tuple1的元素最小值
    tuple(iterable)             #将可迭代对象iterable转换为Tuple，并返回该Tuple
```

## Tuple的方法

```python
    tuple.count(obj)                    #返回对象obj在元组中的个数
    tuple.index(obj[,start[,stop]])     #返回对象obj在元组中的第一个索引，可指定位置
```

