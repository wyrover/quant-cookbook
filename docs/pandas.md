Pandas 基于两种数据类型：series 与 dataframe。

一个 series 是一个一维的数据类型，其中每一个元素都有一个标签。series 类似于 Numpy 中元素带标签的数组。其中，标签可以是数字或者字符串。
一个 dataframe 是一个二维的表结构。Pandas 的 dataframe 可以存储许多种不同的数据类型，并且每一个坐标轴都有自己的标签。你可以把它想象成一个 series 的字典项。

## 数据结构

### Series

### DataFrame

## 查看数据

### index

### columns

### values

### head(n=5)

### tail(n=5)

### describe()

### sort_index()

### sort_values()

## 选择数据

### 数组选择

```python
df['A']
```

### 切片选择

```python
df[0:3] 或 df['20130102':'20130104']
```

### 标签选择

```python
df.loc['20130102':'20130104',['A','B']]
```

### 位置选择

```python
df.iloc[3:5,0:2]
```

### 混合选择

```python
df.ix[:3,['A','C']]
```

### 条件判断选择

```python
df[df.A > 0]
```

## 数据清洗

```
df.columns = ['a','b','c'] | Rename columns
pd.isnull() | Checks for null Values, Returns Boolean Arrray
pd.notnull() | Opposite of pd.isnull()
df.dropna() | Drop all rows that contain null values
df.dropna(axis=1) | Drop all columns that contain null values
df.dropna(axis=1,thresh=n) | Drop all rows have have less than n non null values
df.fillna(x) | Replace all null values with x
s.fillna(s.mean()) | Replace all null values with the mean (mean can be replaced with almost any function from the statistics section)
s.astype(float) | Convert the datatype of the series to float
s.replace(1,'one') | Replace all values equal to 1 with 'one'
s.replace([1,3],['one','three']) | Replace all 1 with 'one' and 3 with 'three'
df.rename(columns=lambda x: x + 1) | Mass renaming of columns
df.rename(columns={'old_name': 'new_ name'}) | Selective renaming
df.set_index('column_one') | Change the index
df.rename(index=lambda x: x + 1) | Mass renaming of index
```

### 删除丢失数据的行

```python
df.dropna(how='any')
```

### 填充丢失数据

```python
df.fillna(value=5)
```

### 数据值是否为 `NaN`

```python
pd.isna(df1)
```

## 合并数据

```python

```

## 导入导出

### read_csv()

### read_excel()

### read_sql()

### read_json()

### read_html()

### read_clipboard()

### to_csv()

### to_excel()

### to_sql()

### to_json()

## 过滤，排序和分组

### `df[df[col] > 0.5]`

### `def[(df[col] > 0.5) & (df[col] < 0.7>)]`

### sort_values()

### groupby()

## 统计函数

### describe()

### mean()

### corr()

### count()

### max()

### min()

### median()

### std()

## 常见问题

### 显示数据长度

```
pd.options.display.max_rows = 1000000
```

## cheatsheet

![](https://raw.githubusercontent.com/kailashahirwar/cheatsheets-ai/master/Pandas-3.png)

## 读取 csv 文件为 dataframe

```python
import pandas as pd filepath = r'C:/Users/lenovo/Desktop/20180108-百度地图/20180108-百度地图/data.csv' df = pd.read_csv(filepath)
#为了方便，我只显示三行，其实结果并不是这样子
print(df)

#检测下数据格式是否为
DataFrame print(type(df))
#输出class 'pandas.core.frame.DataFrame
```
