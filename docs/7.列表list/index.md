# 7.列表List


格式：
- 空列表：`[]`
- 含有元素的列表：`[a]`，`[a,b,c,d,...]`

补充说明：
- 列表中元素的数据类型可以不相同
    ```python
    >>> list1 = [4,'Runoob']
    >>> list2 = [1,2,3,'Hello','World',12.0,3+4j,list]
    >>> list2
    [1, 2, 3, 'Hello', 'World', 12.0, (3+4j), [4, 'Runoob']]
    >>> list2[7][1]
    'Runoob'
    ```

- List中的元素是可以改变的
    ```python
        >>> list1 = [1,2,3,4,5,6]
        >>> list1[0] = 9
        >>> list1[2:4] = []
        >>> list1
        [9, 2, 5, 6]
        >>> del list1[0]
        >>> list1
        [2, 5, 6]
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

格式：`for x in [1,2,3]:print(x,end=" ")`

## 运算符

```python
    +                           #列表连接
    *                           #重复列表为一个列表
    []                          #通过索引获取值
    [:]                         #截取列表，左闭右开
    in                          #成员运算符，如果列表中包含给定的值返回 True
    not in                      #成员运算符，如果列表中不包含给定的值返回 True
```

```python
    >>> list1 = [[1,2,3]]
    >>> list2 = [1,2,3]+[4,5,6]+list1
    >>> list2
    [1, 2, 3, 4, 5, 6, [1, 2, 3]]
    >>> list2 = list2*2             #元素中包含可变序列时，重复是对可变序列的引用
    >>> list2
    [1, 2, 3, 4, 5, 6, [1, 2, 3], 1, 2, 3, 4, 5, 6, [1, 2, 3]]
    >>> list2[6][1] = 4             #当元素中的可变序列中的元素被修改时，引用会一起被修改
    >>> list2
    [1, 2, 3, 4, 5, 6, [1, 4, 3], 1, 2, 3, 4, 5, 6, [1, 4, 3]]
```

## 支持List的函数

```python
    len(list1)                  #返回list1的元素个数
    max(list1)                  #返回list1的元素最大值
    min(list1)                  #返回list1的元素最小值
    list(iterable)              #将可迭代对象iterable转换为List，并返回该List
```

## List的方法

`list.sort([key=None],[reverse=False])`解析：
- key：指定带有一个参数的函数，用于从每个列表元素中提取比较键(例如`key=str.lower`)。默认值为`None`(直接比较元素)
- reverse：排序规则，`reverse = True`降序，`reverse = False`升序(默认)

```python
    list.append(obj)                #在列表末尾添加一个新的对象
    list.count(obj)                 #返回对象在列表中出现的次数
    list.extend(seq)                #在列表末尾追加一个序列中的元素
    list.index(x[,start[,end]])     #返回从列表中找出x第一个匹配项的索引位置
    list.insert(index,obj)          #将指定对象插入列表的指定位置
    list.pop([index])               #删除列表中指定位置的元素(默认index=-1)，并返回被删除的元素
    list.remove(obj)                #移除列表中某个值的第一个匹配项
    list.reverse()                  #反向列表中元素
    list.sort([key=None],[reverse=False])   #对原列表进行排序
    list.clear()                    #清空列表
    list.copy()                     #复制列表
```

```python
    >>> list1 = [1,2,3,4,1,2,3,4]
    >>> list2 = ['Hello','World']
    >>> list1.append(list2)
    >>> list1
    [1, 2, 3, 4, 1, 2, 3, 4, ['Hello', 'World']]
    >>> list1.count(1)
    2
    >>> list1.extend(list2)
    >>> list1
    [1, 2, 3, 4, 1, 2, 3, 4, ['Hello', 'World'], 'Hello', 'World']
    >>> list1.index(1)
    0
    >>> list1.insert(3,5) 
    >>> list1
    [1, 2, 3, 5, 4, 1, 2, 3, 4, ['Hello', 'World'], 'Hello', 'World']
    >>> list1.pop()
    'World'
    >>> list1
    [1, 2, 3, 5, 4, 1, 2, 3, 4, ['Hello', 'World'], 'Hello']
    >>> list1.pop(3)
    5
    >>> list1
    [1, 2, 3, 4, 1, 2, 3, 4, ['Hello', 'World'], 'Hello']
    >>> list1.remove(1)
    >>> list1
    [2, 3, 4, 1, 2, 3, 4, ['Hello', 'World'], 'Hello']
    >>> list1.reverse()
    >>> list1
    ['Hello', ['Hello', 'World'], 4, 3, 2, 1, 4, 3, 2]
    >>> list2.sort(reverse=True)
    >>> list2
    ['World', 'Hello']
    >>> list1.clear()
    >>> list1
    []
    >>> list1 = list2.copy()
    >>> list1
    ['World', 'Hello']
```
