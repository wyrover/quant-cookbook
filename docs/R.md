## 概述

R 语言是用于统计分析，图形表示和报告的编程语言和软件环境。 R 语言由 Ross Ihaka 和 Robert Gentleman 在新西兰奥克兰大学创建，目前由 R 语言开发核心团队开发。

R 语言的核心是解释计算机语言，其允许分支和循环以及使用函数的模块化编程。 R 语言允许与以 C，C ++，.Net，Python 或 FORTRAN 语言编写的过程集成以提高效率。

R 语言在 GNU 通用公共许可证下免费提供，并为各种操作系统（如 Linux，Windows 和 Mac）提供预编译的二进制版本。

R 是一个在 GNU 风格的副本左侧的自由软件，GNU 项目的官方部分叫做 GNU S.

### R 的演变

R 语言最初是由新西兰奥克兰奥克兰大学统计系的 Ross Ihaka 和 Robert Gentleman 写的。 R 语言于 1993 年首次亮相。

一大群人通过发送代码和错误报告对 R 做出了贡献。

自 1997 年年中以来，已经有一个核心组（“R 核心团队”）可以修改 R 源代码归档。

### R 的特点

如前所述，R 语言是用于统计分析，图形表示和报告的编程语言和软件环境。 以下是 R 语言的重要特点：

R 语言是一种开发良好，简单有效的编程语言，包括条件，循环，用户定义的递归函数以及输入和输出设施。

R 语言具有有效的数据处理和存储设施，

R 语言提供了一套用于数组，列表，向量和矩阵计算的运算符。

R 语言为数据分析提供了大型，一致和集成的工具集合。

R 语言提供直接在计算机上或在纸张上打印的图形设施用于数据分析和显示。

作为结论，R 语言是世界上最广泛使用的统计编程语言。 它是数据科学家的第一选择，并由一个充满活力和有才华的贡献者社区支持。 R 语言在大学教授并部署在关键业务应用程序中。 本教程将教您 R 编程与适当的例子在简单和容易的步骤。

## 环境设置

尝试在线环境
你真的不需要设置自己的环境来开始学习 R 编程语言。 原因很简单，我们已经在线设置了 R 编程环境，以便您可以在进行理论工作的同时在线编译和执行所有可用的示例。 这给你对你正在阅读的信心，并用不同的选项检查结果。 随意修改任何示例并在线执行。

点击官方网站右上角的 Try it 按钮，尝试运行一下以下的实例：

```R
# Print Hello World.
print("Hello World")

# Add two numbers.
print(23.9 + 11.6)
```

对于本教程中给出的大多数示例，您将在官方网站上找到 Try it 选项，因此只需使用它并享受您的学习。

## 本地环境设置

如果你仍然愿意为 R 语言设置你的环境，你可以按照下面的步骤。

### Windows 安装

您可以从 R-3.2.2 for Windows（32/64 位）下载 R 的 Windows 安装程序版本，并将其保存在本地目录中。

因为它是一个名为 “R-version-win.exe” 的 Windows 安装程序（.exe）。 您只需双击并运行安装程序接受默认设置即可。 如果您的 Windows 是 32 位版本，它将安装 32 位版本。 但是如果你的窗口是 64 位，那么它安装 32 位和 64 位版本。

安装后，您可以找到该图标，以在 Windows 程序文件下的目录结构 “R \ R3.2.2 \ bin \ i386 \ Rgui.exe” 中运行程序。 单击此图标会打开 R-GUI，它是 R 控制台来执行 R 编程。

### Linux 安装

R 语言适用于多版本的 Linux 系统。

各版本 Linux 的各有不同。具体的安装步骤在上述资源中有对应的教程。但是，如果你是在赶时间，那么你可以用 yum 命令，如下所示的安装指令
安装 R

```
$ yum install R
```

以上命令将安装 R 编程的核心功能与标准包，额外的包需要另外安装，而后你可以按如下提示启动 R。

```
$ R
```

```
R version 3.2.0 (2015-04-16) -- "Full of  Ingredients"
Copyright (C) 2015 The R foundation for Statistical Computing
Platform: x86_64-redhat-linux-gnu (64-bit)

R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under certain conditions.
Type 'license()' or 'licence()' for distribution details.

R is a collaborative project with many  contributors.
Type 'contributors()' for more information and
'citation()' on how to cite R or R packages in publications.

Type 'demo()' for some demos, 'help()' for on-line help, or
'help.start()' for an HTML browser interface to help.
Type 'q()' to quit R.

>
```

现在，您可以在 R 语言提示符下使用 install 命令安装所需的软件包。 例如，以下命令将安装为 3D 图表所需的 plotrix 软件包。

```
> install.packages("plotrix")
```

## 基本语法

我们将开始学习 R 语言编程，首先编写一个 “你好，世界！ 的程序。 根据需要，您可以在 R 语言命令提示符处编程，也可以使用 R 语言脚本文件编写程序。 让我们逐个体验不同之处。

### 命令提示符

如果你已经配置好 R 语言环境，那么你只需要按一下的命令便可轻易开启命令提示符

```
$ R
```

这将启动 R 语言解释器，你会得到一个提示 > 在那里你可以开始输入你的程序，具体如下。

```R
> myString <- "Hello, World!"
> print ( myString)
[1] "Hello, World!"
```

在这里，第一个语句先定义一个字符串变量 myString，并将 “Hello，World！” 赋值其中，第二句则使用 print() 语句将变量 myString 的内容进行打印。

### 脚本文件

通常，您将通过在脚本文件中编写程序来执行编程，然后在命令提示符下使用 R 解释器（称为 Rscript）来执行这些脚本。 所以让我们开始在一个命名为 test.R 的文本文件中编写下面的代码

```R
# My first program in R Programming
myString <- "Hello, World!"

print ( myString)
```

将上述代码保存在 test.R 文件中，并在 Linux 命令提示符下执行，如下所示。 即使您使用的是 Windows 或其他系统，语法也将保持不变。

```
$ Rscript test.R
```

当我们运行上面的程序，它产生以下结果。

```
[1] "Hello, World!"
```

### 注释

注释能帮助您解释 R 语言程序中的脚本，它们在实际执行程序时会被解释器忽略。 单个注释使用＃在语句的开头写入，如下所示

```R
# My first program in R Programming
```

R 语言不支持多行注释，但你可以使用一个小技巧，如下

```R
if(FALSE) {
   "This is a demo for multi-line comments and it should be put inside either a single
      OR double quote"
}

myString <- "Hello, World!"
print ( myString)
```

虽然上面的注释将由 R 解释器执行，但它们不会干扰您的实际程序。 但是你必须为内容加上单引号或双引号。

## 数据类型

通常，在使用任何编程语言进行编程时，您需要使用各种变量来存储各种信息。 变量只是保留值的存储位置。 这意味着，当你创建一个变量，你必须在内存中保留一些空间来存储它们。

您可能想存储各种数据类型的信息，如字符，宽字符，整数，浮点，双浮点，布尔等。基于变量的数据类型，操作系统分配内存并决定什么可以存储在保留内存中。

与其他编程语言（如 C 中的 C 和 java）相反，变量不会声明为某种数据类型。 变量分配有 R 对象，R 对象的数据类型变为变量的数据类型。尽管有很多类型的 R 对象，但经常使用的是：

- 矢量
- 列表
- 矩阵
- 数组
- 因子
- 数据帧
-

这些对象中最简单的是向量对象，并且这些原子向量有六种数据类型，也称为六类向量。 其他 R 对象建立在原子向量之上。

<table>
<tr>
    <td>数据类型</td><td>例</td><td>校验</td>
</tr>
<tr>
    <td>Logical（逻辑型）</td><td>TRUE, FALSE</td><td>
<pre>
v <- TRUE 
print(class(v))
</pre>
它产生以下结果 -
<pre>
[1] "logical"

</pre>
</td>

</tr>

<tr>
    <td>Numeric（数字）</td><td>12.3，5，999</td><td>
<pre>
v <- 23.5
print(class(v))
</pre>
它产生以下结果 -
<pre>
[1] "numeric"

</pre>
</td>

</tr>

<tr>
    <td>Integer（整型）</td><td>2L，34L，0L</td><td>
<pre>
v <- 2L
print(class(v))
</pre>
它产生以下结果 -
<pre>
[1] "integer"

</pre>
</td>

</tr>

<tr>
    <td>Complex（复合型）</td><td>3 + 2i</td><td>
<pre>
v <- 2+5i
print(class(v))
</pre>
它产生以下结果 -
<pre>
[1] "complex"

</pre>
</td>

</tr>

<tr>
    <td>Character（字符）</td><td>'a' , '"good", "TRUE", '23.4'</td><td>
<pre>
v <- "TRUE"
print(class(v))
</pre>
它产生以下结果 -
<pre>
[1] "character"

</pre>
</td>

</tr>

<tr>
    <td>Raw（原型）</td><td>"Hello" 被存储为 48 65 6c 6c 6f</td><td>
<pre>
v <- charToRaw("Hello")
print(class(v))
</pre>
它产生以下结果 -
<pre>
[1] "raw"

</pre>
</td>

</tr>

</table>

在 R 编程中，非常基本的数据类型是称为向量的 R 对象，其保存如上所示的不同类的元素。 请注意，在 R 中，类的数量不仅限于上述六种类型。 例如，我们可以使用许多原子向量并创建一个数组，其类将成为数组。

### Vectors 向量

当你想用多个元素创建向量时，你应该使用 c() 函数，这意味着将元素组合成一个向量。

```R
# Create a vector.
apple <- c('red','green',"yellow")
print(apple)

# Get the class of the vector.
print(class(apple))
```

当我们执行上面的代码，它产生以下结果

```
[1] "red"    "green"  "yellow"
[1] "character"
```

### Lists 列表

列表是一个 R 对象，它可以在其中包含许多不同类型的元素，如向量，函数甚至其中的另一个列表。

```R
# Create a list.
list1 <- list(c(2,5,3),21.3,sin)

# Print the list.
print(list1)
```

当我们执行上面的代码，它产生以下结果

```
[[1]]
[1] 2 5 3

[[2]]
[1] 21.3

[[3]]
function (x)  .Primitive("sin")
```

### Matrices 矩阵

矩阵是二维矩形数据集。 它可以使用矩阵函数的向量输入创建。

```R
# Create a matrix.
M = matrix( c('a','a','b','c','b','a'), nrow = 2, ncol = 3, byrow = TRUE)
print(M)
```

当我们执行上面的代码，它产生以下结果

```
     [,1] [,2] [,3]
[1,] "a"  "a"  "b"
[2,] "c"  "b"  "a"
```

### Arrays 数组

虽然矩阵被限制为二维，但阵列可以具有任何数量的维度。 数组函数使用一个 dim 属性创建所需的维数。 在下面的例子中，我们创建了一个包含两个元素的数组，每个元素为 3x3 个矩阵。

```R
# Create an array.
a <- array(c('green','yellow'),dim = c(3,3,2))
print(a)
```

当我们执行上面的代码，它产生以下结果

```
, , 1

     [,1]     [,2]     [,3]
[1,] "green"  "yellow" "green"
[2,] "yellow" "green"  "yellow"
[3,] "green"  "yellow" "green"

, , 2

     [,1]     [,2]     [,3]
[1,] "yellow" "green"  "yellow"
[2,] "green"  "yellow" "green"
[3,] "yellow" "green"  "yellow"
```

### Factors 因子

因子是使用向量创建的 r 对象。 它将向量与向量中元素的不同值一起存储为标签。 标签总是字符，不管它在输入向量中是数字还是字符或布尔等。 它们在统计建模中非常有用。
使用 factor() 函数创建因子。nlevels 函数给出级别计数。

```R
# Create a vector.
apple_colors <- c('green','green','yellow','red','red','red','green')

# Create a factor object.
factor_apple <- factor(apple_colors)

# Print the factor.
print(factor_apple)
print(nlevels(factor_apple))
```

当我们执行上面的代码，它产生以下结果

```
[1] green  green  yellow red    red    red    yellow green
Levels: green red yellow
# applying the nlevels function we can know the number of distinct values
[1] 3
```

### Data Frames 数据帧

数据帧是表格数据对象。 与数据帧中的矩阵不同，每列可以包含不同的数据模式。 第一列可以是数字，而第二列可以是字符，第三列可以是逻辑的。 它是等长度的向量的列表。
使用 `data.frame()` 函数创建数据帧。

```R
# Create the data frame.
BMI <- 	data.frame(
   gender = c("Male", "Male","Female"),
   height = c(152, 171.5, 165),
   weight = c(81,93, 78),
   Age = c(42,38,26)
)
print(BMI)
```

当我们执行上面的代码，它产生以下结果

```
  gender height weight Age
1   Male  152.0     81  42
2   Male  171.5     93  38
3 Female  165.0     78  26
```

## 变量

变量为我们提供了我们的程序可以操作的命名存储。 R 语言中的变量可以存储原子向量，原子向量组或许多 Robject 的组合。 有效的变量名称由字母，数字和点或下划线字符组成。 变量名以字母或不以数字后跟的点开头。

| 变量名                  | 合法性 | 原因                                                 |
| ----------------------- | ------ | ---------------------------------------------------- |
| `var_name2.`            | 有效   | 有字母，数字，点和下划线                             |
| `.var_name`, `var.name` | 有效   | 可以用一个点 (.)，但启动点 (.)，不应该后跟一个数字。 |
| `VAR_NAME％`            | 无效   | 有字符'％'。只有点 (.) 和下划线允许的。              |
| `2var_name`             | 无效   | 以数字开头                                           |
| `.2var_name`            | 无效   | 起始点后面是数字使其无效。                           |
| `_var_name`             | 无效   | 开头_这是无效的                                      |



### 变量赋值
可以使用向左，向右和等于运算符来为变量分配值。 可以使用 print() 或 cat() 函数打印变量的值。 cat() 函数将多个项目组合成连续打印输出。
```R
# Assignment using equal operator.
var.1 = c(0,1,2,3)           

# Assignment using leftward operator.
var.2 <- c("learn","R")   

# Assignment using rightward operator.   
c(TRUE,1) -> var.3           

print(var.1)
cat ("var.1 is ", var.1 ,"
")
cat ("var.2 is ", var.2 ,"
")
cat ("var.3 is ", var.3 ,"
")
```
当我们执行上面的代码，它产生以下结果 -
```
[1] 0 1 2 3
var.1 is  0 1 2 3 
var.2 is  learn R 
var.3 is  1 1 
```
> 注 - 向量 c（TRUE，1）具有逻辑和数值类的混合。 因此，逻辑类强制转换为数字类，使 TRUE 为 1。

### 变量的数据类型

在 R 语言中，变量本身没有声明任何数据类型，而是获取分配给它的 R - 对象的数据类型。 所以 R 称为动态类型语言，这意味着我们可以在程序中使用同一个变量时，一次又一次地更改变量的数据类型。
```R
var_x <- "Hello"
cat("The class of var_x is ",class(var_x),"
")

var_x <- 34.5
cat("  Now the class of var_x is ",class(var_x),"
")

var_x <- 27L
cat("   Next the class of var_x becomes ",class(var_x),"
")
```
当我们执行上面的代码，它产生以下结果 -
```
The class of var_x is  character 
   Now the class of var_x is  numeric 
      Next the class of var_x becomes  integer
```

### 查找变量

要知道工作空间中当前可用的所有变量，我们使用 ls() 函数。 ls() 函数也可以使用模式来匹配变量名。
```R
print(ls())
```
当我们执行上面的代码，它产生以下结果 -
```
[1] "my var"     "my_new_var" "my_var"     "var.1"      
[5] "var.2"      "var.3"      "var.name"   "var_name2."
[9] "var_x"      "varname" 
```
> 注意 - 它是一个示例输出，取决于在您的环境中声明的变量。

ls() 函数可以使用模式来匹配变量名。
```R
# List the variables starting with the pattern "var".
print(ls(pattern = "var"))   
```
当我们执行上面的代码，它产生以下结果 -
```
[1] "my var"     "my_new_var" "my_var"     "var.1"      
[5] "var.2"      "var.3"      "var.name"   "var_name2."
[9] "var_x"      "varname"    
```
以点 (.) 开头的变量被隐藏，它们可以使用 ls() 函数的 “all.names = TRUE” 参数列出。
```R
print(ls(all.name = TRUE))
```
当我们执行上面的代码，它产生以下结果 -
```
[1] ".cars"        ".RanDOM.seed" ".var_name"    ".varname"     ".varname2"   
[6] "my var"       "my_new_var"   "my_var"       "var.1"        "var.2"        
[11]"var.3"        "var.name"     "var_name2."   "var_x"  
```
### 删除变量

可以使用 rm() 函数删除变量。 下面我们删除变量 var.3。 打印时，抛出变量错误的值。
```R
rm(var.3)
print(var.3)
```
当我们执行上面的代码，它产生以下结果 -
```
[1] "var.3"
Error in print(var.3) : object 'var.3' not found
```
所有的变量可以通过使用 `rm()` 和 `ls()` 函数一起删除。
```R
rm(list = ls())
print(ls())
```
当我们执行上面的代码，它产生以下结果 -
```
character(0)
```

### 手册(http://www.kubiji.cn/book/r/RJiaoCheng/RYuYanYunSuanFu.html)