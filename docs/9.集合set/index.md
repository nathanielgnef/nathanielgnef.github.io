# 9.集合Set


Python 3 中有两种内置集合类型，set 和 frozenset

## 集合Set

格式：
- 使用花括号：`{value01,value02,...}`
- 使用集合推导式：`{c for c in 'abracadabra' if c not in 'abc'}`
- 使用类型构造器：`set()`，`set(iterable)`

补充说明：
- 集合中的重复元素会被删除
    ```python
        >>> set1 = {1,2,3,1,2,3,3,3}
        >>> set1
        {1, 2, 3}
    ```

- 集合中的元素数据类型可以不相同，但必须是可哈希的(hashable)
    - 可哈希的(hashable)：不可变，如字符串、元组等，不能对元素修改
    - 不可哈希的(unhashable)：可变，如列表、字典等，能对元素修改

    ```python
        >>> set1 = {1,2,3,'Hello World',(7,8,9)}
        >>> set1
        {1, 2, 3, (7, 8, 9), 'Hello World'}
    ```

- 集合是无序的，不支持索引、切片
- 集合是不可哈希的(unhashable)，无法成为其他集合的元素，能对元素进行修改

### 迭代

格式：`for x in {1,2,3}:print(x,end=" ")`

### 运算符

```python
    set - other - ...           #返回一个新集合，其中包含原集合中在 others 指定的其他集合中不存在的元素
    set | other | ...           #返回一个新集合，其中包含来自原集合以及 others 指定的所有集合中的元素
    set & other & ...           #返回一个新集合，其中包含原集合以及 others 指定的所有集合中共有的元素
    set ^ other                 #返回一个新集合，其中的元素或属于原集合或属于 other 指定的其他集合，但不能同时属于两者
    set <= other                #检测是否集合中的每个元素都在 other 之中
    set < other                 #检测集合是否为 other 的真子集，即 set <= other and set != other
    set >= other                #检测是否 other 中的每个元素都在集合之中
    set > other                 #检测集合是否为 other 的真超集，即 set >= other and set != other
    in                          #成员运算符，如果集合中包含给定的值返回 True
    not in                      #成员运算符，如果集合中不包含给定的值返回 True
```

```python
    >>> a = set('abracadabra')
    >>> b = set('alacazam')
    >>> a
    {'d', 'a', 'c', 'r', 'b'}
    >>> b
    {'a', 'c', 'l', 'm', 'z'}
    >>> a - b
    {'d', 'b', 'r'}
    >>> a | b
    {'d', 'a', 'c', 'b', 'r', 'l', 'm', 'z'}
    >>> a & b
    {'c', 'a'}
    >>> a ^ b
    {'d', 'b', 'm', 'r', 'z', 'l'}
```

### 支持Set的函数

```python
    len(set1)                   #返回Set1的元素个数
    max(set1)                   #返回Set1的元素最大值
    min(set1)                   #返回Set1的元素最小值
    set(iterable)               #将可迭代对象iterable转换为Set，并返回该Set
```

### Set的方法

```python
    set.add(object)                                     #添加一个元素到集合中，如果该元素已经存在，则不进行操作
    set.clear()                                         #清空集合
    set.copy()                                          #返回集合的复制
    set.difference(iterable[,iterable,...])             #返回该集合中不存在于其他可迭代对象iterable中的元素的集合
    set.difference_update(iterable[,iterable,...])      #移除该集合中存在于其他可迭代对象iterable中的元素
    set.discard(object)                                 #删除该集合中的对象object，如果该集合中不存在对象object，则不进行操作
    set.intersection(iterable[,iterable,...])           #返回该集合与其他可迭代对象iterable的交集，如果参数有Str，则交集为空集
    set.intersection_update(iterable[,iterable,...])    #使用该集合与其他可迭代对象iterable的交集更新该集合
    set.isdisjoint(iterable)                            #如果该集合与可迭代对象iterable的交集为空返回True，否则返回False
    set.issubset(iterable)                              #如果该集合是可迭代对象iterable的子集，返回True，否则返回False
    set.issuperset(iterable)                            #如果该集合是可迭代对象iterable的超集，返回True，否则返回False
    set.pop()                                           #删除一个元素
    set.remove(object)                                  #删除该集合中的一个对象object，如果不存在该对象，则报错KeyError
    set.symmetric_difference(iterable)                  #返回该集合与可迭代对象iterable不同时存在的元素的集合
    set.symmetric_difference_update(iterable)           #使用该集合与可迭代对象iterable不同时存在的元素的集合更新该集合
    set.union(iterable[,iterable,...])                  #返回该集合与其他可迭代对象iterable的并集
    set.update(iterable[,iterable,...])                 #使用该集合与其他可迭代对象iterable的并集更新该集合
```

```python

```

## 冻结集合Frozenset

格式：
- 使用类型构造器：`frozenset()`，`forzenset(iterable)`

补充说明：
- 冻结集合是可哈希的(hashable)，可以成为其他集合的元素，不能对元素进行修改

