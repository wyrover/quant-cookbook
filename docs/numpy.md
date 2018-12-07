## isinstance

判断数据类型

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

## dtype

### int8

`i1`

### uint8

`u1`

### int16

`i2`

### uint16

`u2`

### int32

`i4`

### uint32

`u4`

### int64

`i8`

### uint64

`u8`

### float16

`f2`

### float32

`f4` 或 `f`

### float64

`f8` 或 `d`

### float128

`f16` 或 `g`

### complex64

`c8`

### complex128

`c16`

### complex256

`c32`

### bool

`?`

### object

`O`

### string\_

`S`

### unicode\_

`U`

## 非数值型数据

### nan

### isnan

## 创建 ndarray

### array

### asarray

### asanyarray

### arange

### empty

### empty_like

### zeros

### zero_like

### ones

### ones_like

### full

### full_like

### eye

### identity

### arange

```python
import numpy as np
a = np.arange(10)
```

### mershgrid

### where

### extract

### in1d

## 形状和纬度

### shape

### ndim

## 切片

### [n]

选取第 `n + 1` 个元素

### [n:m]

选取第 `n + 1` 到第 `m` 个元素

### [:]

选取全部元素

### [n:]

选取第 `n + 1` 到最后一个元素

### [:n]

选取第 `0` 到 第 `n` 个元素

### [bool_ndarray]

选取为 `true` 的元素

### [[x, y, m, n]]...

选取顺序和序列为 `x, y, m, n` 的 `ndarray`

### [n, m]

选取第 `n + 1` 行 第 `m + 1` 个元素

### [n][m]

选取第 `n + 1` 行 第 `m + 1` 个元素

### [n,m,...]

选取 `n` 行 `m` 列...的元素

### [n][m]...

选取 `n` 行 `m` 列...的元素

## 坐标轴

### newaxis

```python
newaxis = None
```

```python
>> x = np.arange(3)
>> x
array([0, 1, 2])
>> x.shape
(3,)

>> x[:, np.newaxis]
array([[0],
       [1],
       [2]])

>> x[:, None]
array([[0],
       [1],
       [2]])

>> x[:, np.newaxis].shape
 (3, 1)
```

## 分割

split

## 随机函数

### seed

确定随机数生成种子

- seed()
- send(int)
- seed(ndarray)

### permutation

- permutation(int) 返回一个一维从 `0-9` 的序列的随机排列
- permutation(ndarray) 返回一个序列的随机排列

### shuffle

对一个序列就地随机排列

### rand

rand(int) 产生 `int` 个均匀分布的样本值

### randint

randint(begin, end, num=1) 从给定的 `begin` 和 `end` 随机选取 `num` 个整数

### randn

生成一个 `N*M*...` 的正态分布(平均值为 `0`，标准差为 `1`)的 `ndarray`

### normal

生成一个 `N*M*...` 的正态(高斯)分布的 `ndarray`

### beta

产生 `beta` 分布的样本值，参数必须大于 `0`

### chisquare

产生卡方分布的样本值

### gamma

产生 `gamma` 分布的样本值

### uniform

产生在 `[0, 1)` 中均匀分布的样本值

## 统计函数

### sum

求和

### mean

平均数

### average

加权平均

### var

方差

### std

标准差

### median

中位数

### ptp

极差

### cumsum

累积和

### percentile

百分位数

### max

最大值

### min

最小值

### argmax

### argmin

### nansum

### nanmean

### nanstd

### nanmax

### nanmin

### nanargmax

### nanargmin

### sort

排序

### unique

数组元素去重

### bincount

数组中元素出现次数统计

## 一元计算函数

### abs fabs

### sqrt

### square

### exp

### log

### log10

### log2

### log1p

### sign

### ceil

### floor

### rint

### modf

### isnan

### isfinite

### isinf

### cos

### cosh

### sin

### sinh

### tan

### tanh

### arccos

### arccosh

### arcsin

### arcsinh

### arctan

### arctanh

### logical_not

## 多元计算函数

### add

### subtract

### multiply

### divide

### floor_divide

### power

### mod

### maximum

求最大值

### fmax

求最大值(忽略 NaN)

### minimum

求最小值

### fmin

求最小值(忽略 NaN)

### copysign

### greater

### greater_equal

### less

### less_equal

### equal

### not_equal

### logical_and

### logical_or

### logical_xor

## 文件读写

### load

### loadtxt

### save

### savetxt

### savez

### mat

数组转为矩阵

### dot

点积

## 矩阵

- 矩阵：由 m×n 个数排列成 的 m 行 n 列的数表，称为 m 行 n 列矩阵。
- 实矩阵：元素是实数的矩阵。
- 复矩阵：元素是负数的矩阵。
- 方阵：行数和列数相等的矩阵。
- 行矩阵（或行向量）：只有一行的矩阵。
- 列矩阵（或列向量）：只有一列的矩阵。
- 零矩阵：矩阵的元素全部是 0 的矩阵。
- 单位矩阵：n 行 n 列, 且主对角线上都是 1, 其他位置都是 0 的矩阵（主对角线上元素都是 1，其他位置是 0 的方阵）

### det

计算矩阵列式

### eig

计算方阵的本征值和本征向量

### inv

计算方阵的逆

### pinv

计算方阵的 `Moore-Penrose` 伪逆

### qr

计算 `qr` 分解

### svd

计算奇异值分解 `svd`

### solve

解线性方程组 `Ax = b`， 其中 `A` 为方阵

### lstsq

计算 `Ax = b` 的最小二乘解
