## Lists

```python
>>> # A list of three different-type objects
>>> L = [123, 'poe', 3.1415]
>>> # Number of items in the list
>>> len(L)
3
```

**索引 切片**

```python
>>> # Indexing by position
>>> L[0]
123
>>> # Slicing a list returns a new list
>>> L[:-1]
[123, 'poe']
>>> # Concatenation makes a new list too
>>> L + [94550, 98101, 230]
[123, 'poe', 3.1415, 94550, 98101, 230]
>>> # We're not changing the original list
>>> L
[123, 'poe', 3.1415]
>>> 
```

**添加 删除**
```python
>>> # Growing: add object at the end of list
>>> L.append('Dijkstra')
>>> L
[123, 'poe', 3.1415, 'Dijkstra']
>>>
>>> # Shrinking: delete an item in the middle
>>> L.pop(2)
3.1415
>>> 
>>> L
[123, 'poe', 'Dijkstra']
>>> 
```

**排序**
```python
>>> 
>>> M = ['Ludwig', 'van', 'Beethoven']
>>> M.sort()
>>> M
['Beethoven', 'Ludwig', 'van']
>>> M.reverse()
>>> M
['van', 'Ludwig', 'Beethoven']
>>> 
```

**多维数组**

```python
>>> 
>>> # A 3 x 3 matrix, as nested lists
>>> M = [ [1, 2, 3],
          [4, 5, 6],
          [7, 8, 9] ]
>>> M
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
>>> 
```

```python
>>> 
>>> # Get row 2
>>> M[1]
[4, 5, 6]
>>> # Get row 2, then get item 3 of that row
>>> M[1][2]
6
>>> 
```

**二维数组 操作**

第二列输出
```python
>>> 
>>> # Collect the items in column 2
>>> col2 = [A[1] for A in M]
>>> col2
[2, 5, 8]
>>> 
>>> M
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
>>> 
```

第二列加上一个数
```python
>>> 
>>> M
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
>>> 
>>> # Add 10 to each item in column 2
>>> [A[1] + 10 for A in M]
[12, 15, 18]
>>> # Filter out odd items
>>> [A[1] for A in M if A[1] % 2 == 0]
[2, 8]
>>> 

```


```python
>>> # Collect a diagonal from matrix
>>> diag = [M[i][i] for i in [0, 1, 2]]
>>> diag
[1, 5, 9]
>>>
>>> # Repeat characters in a string
>>> doubles = [ c * 2 for c in 'blah']
>>> doubles
['bb', 'll', 'aa', 'hh']
>>> 
```

累加
```python
>>> M
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
>>> 
>>> # Create a generator of row sums
>>> G = (sum(A) for A in M)
>>> # iter(G) not required here
>>> next(G)
6
>>> # Run the iteration protocol
>>> next(G)
15
>>> next(G)
24
```


map
```python
>>> # Map sum over items in M
>>> list(map(sum,M))
[6, 15, 24]
```

返回 set
```python
>>> 
>>> # Create a set of row sums
>>> {sum(A) for A in M}
{24, 6, 15}
>>> 
>>> # Creates key/value table of row sums
>>> {i : sum(M[i]) for i in range(3)}
{0: 6, 1: 15, 2: 24}
>>> 
```


```python
>>> 
>>> # List of character ordinals
>>> [ord(x) for x in 'google']
[103, 111, 111, 103, 108, 101]
>>> # Sets remove duplicates
>>> {ord(x) for x in 'google'}
{111, 108, 101, 103}
>>> # Dictionary keys are unique
>>> {x: ord(x) for x in 'google'}
{'e': 101, 'o': 111, 'g': 103, 'l': 108}
>>> 
```

## Array

### numpy.arange()

```python
>>> np.arange(3)
array([0, 1, 2])
>>> np.arange(3.0)
array([ 0.,  1.,  2.])
>>> np.arange(3,7)
array([3, 4, 5, 6])
>>> np.arange(3,7,2)
array([3, 5])
```

### numpy.diff()

```python
>>> x = np.array([1, 2, 4, 7, 0])
>>> np.diff(x)
array([ 1,  2,  3, -7])
>>> np.diff(x, n=2)
array([  1,   1, -10])
```

```python
>>> x = np.array([[1, 3, 6, 10], [0, 5, 6, 8]])
>>> np.diff(x)
array([[2, 3, 4],
       [5, 1, 2]])
>>> np.diff(x, axis=0)
array([[-1,  2,  0, -2]])
```
```python
>>> x = np.arange('1066-10-13', '1066-10-16', dtype=np.datetime64)
>>> np.diff(x)
array([1, 1], dtype='timedelta64[D]')
```