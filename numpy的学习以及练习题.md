# Numpy库
## Numpy是什么
Numpy是Python中最基础且强大的科学计算库之一，主要用于高效处理多维数据和矩阵运算，同时提供了大量的数学函数库。

## Numpy的核心功能
1.多维数据对象（ndarray）

（1）提供高性能的N维数组（如向量，矩阵，张量），支持数值，布尔，字符串等数据类型

（2）相比python原生列表，Numpy数组计算速度更快（底层用C实现），内存效率更高

2.数学运算

（1）支持快速的向量化运算（无需显式循环），例如加减乘除，矩阵乘法，广播等

（2）内置大量数学函数（sin，log，dot，sum，mean，FFT）等

3.广播机制

允许不同形状的数据进行数学运算（自动扩展维度）

4.线性代数，随机数生成，傅里叶变换等

提供线性代数运算，（如求逆，特征值，SVD分解），随机数生成，统计函数等

5.与其他工具集成

可无缝衔接Pandas（数据分析），Matplotilb（绘图），Scipy（科学计算）等库

## Numpy使用需求
Numpy的使用需求广泛，主要面向需要高效数值计算，大规模数据处理或科学计算的场景

以下是常见的需求分类：

1.需要高性能的数值计算（如大规模数组运算）

2.涉及数学/科学计算（如线性代数，统计）

3.与其他科学计算库协作（如Pandas，SciPy，深度学习框架）

## Numpy应用场景
Numpy作为Python科学计算的核心库，其应用场景非常广泛，几乎覆盖所有需要高效数值计算和

多维数据处理的领域

以下是Numpy的典型应用场景及具体示例：

1.科学计算与数值分析

2.数据科学与机器学习

3.图像处理与计算机视觉

4.信号处理与时间序列分析

5.金融与经济建模

# Numpy练习题之初级练习题 数组创建与基本操作
## 1.创建一个长度为10的一维全零数组
import numpy as np 

a = np.zeros(10, dtype = int) # 由于不加dtype的话，输出的类型是float类型，不满足题意，所以需要指定为int类型

print(a)

## 2.创建一个3X3的二维全1数组 拓展 创建一个3X3的二维全2或者3的数组的方法
import numpy as np 

a = np.ones((3,3), dtype = int) 

***拓展 a = np.ones((3,3), dtype = int) + 2 或者 3 另一种方法使用full()函数 a = np.full((3,3),2 或者 3, dtype = int)***

print(a)

## 3.创建一个5X5的单位矩阵 （单位矩阵 对角线全为1（也就是从左上到右下） 其余为0）
import numpy as np 

a = np.eye(5, dtype = int) 或者可以使用另一种方法 a = np.identity(5, dtype = int)

print(a)

## 4.创建一个从0到9的一维数组
import numpy as np 

a = np.arange(10)

print(a)

## 5.创建一个从10到49的一维数据
import numpy as np 

a = np.arange(10,50) # 起始值和终止值（包前不包后）

print(a)

## 6.创建一个包含20个元素的等差数列，从0到1
import numpy as np 

***.linspace用于生成等间隔数值序列 np.linspace(start, stop, num, enpoint=True（默认）, retstep=Fasle（默认）, dtype=None, axis=0)***

a = np.linspace(0,1,20) 

print(a)

## 7.创建一个3X3的随机数组（值在0到1之间）
import numpy as np 

***random() 表示随机生成 其中，rand()表示均匀分布，范围[0,1) randn()表示标准正态分布，范围（-∞，+∞），random()也表示均匀分布，范围与rand()一样 randint()离散均匀分布，范围是自定义，用法 np.random.randint(0,10,(3,3))***

a = np.random.rand(3,3) 

print(a)

## 8.创建一个10X10的随机数组，并找出最大值和最小值
import numpy as np 

#创建10X10的随机数组,值在0到1

a = np.random.rand(10,10) 

print(a)

#找出最大值最小值 （其实也可以直接用 a.min() 和 a.max() 这个方法同样也可以找到）

max_name = np.max(a)

min_name = np.min(a)

print("最小值:",min_name)

print("最大值:",max_name)

## 9.创建一个8X8的棋盘式数组（0黑，1白相间）
import numpy as np 

a = np.zeros((8,8), dtype = int)

***切片语法解析 a[start:stop:step] start包含起始索引 stop则不包括***

***1::2 表示从第1行开始，步长为2，每隔1行取一行 即 1357行***

***::2 表示从第0列开始，步长为2，每隔1列取一列 即 2468列 ::2等效于0::2***

a[1::2,::2] = 1 #  切片操作 （奇数行） 偶数索引位置设为1

***::2 表示从第0行开始，每隔1行取一行 即2468行***

***1::2 表示从第1列开始，每隔1列取一列 即1357列***

a[::2,1::2] = 1 # 偶数行 奇数索引设置为1

print(a)

## 10.创建一个自定义的5X5数组并打印其数据类型
import numpy as np 

a = np.random.randint(1,10,(5,5)) # 随机生成一个5行5列的数组 但是不知道符不符合题意 所以重新写一个

b = np.array([[1,2,3,4,5],
                [6,7,8,9,10],
                [11,12,13,14,15],
                [16,17,18,19,20],
                [21,22,23,24,25]])

print(a.dtype)

print(b.dtype)

## 初级练习题之数组创建与基本操作的总结
- np.zeros(5，dtype = int) 表示创建全零数组 用法: np.zeros(shape, dtype=float（默认float类型）) 其中shape可以是int或者tuple，比如5或者(2,3)

- np.ones((3,3), dtype = int) 表示创建全一数组 用法: np.zeros(shaple, dtype=float(默认float类型)) 其中shape可以是int或者tuple，比如5或者(3,3)

- np.eye(5, dtype = int) 表示创建单位矩阵 用法:np.eye(N, M=None, k=None, dtype=float（默认float类型）) 其中N表示行数，M表示列数(可选)，k表示对角线偏移量k=1向右偏移，k=-1向下偏移

- np.arange(10,50) 表示生成等差数列数组 用法: np.arange(start,stop,step) 其中start包含起始值，而stop不包含，步长默认是1

- np.linspace(0,1,20) 表示生成等间隔数值序列 用法: np.linspace(start, stop, num, enpoint=True（默认）, retstep=Fasle（默认）, dtype=None, axis=0)

- random() 表示随机生成 其中，rand()表示均匀分布，范围[0,1) randn()表示标准正态分布，范围（-∞，+∞），random()也表示均匀分布，范围与rand()一样 randint()离散均匀分布，范围是自定义，用法 np.random.randint(0,10,(3,3))

- np.array() 表示创建numpy的数组 用法: np.array(object, dtype=None, copy=True) 其中object表示转换成数据的数据，如列表，元组等等 dtype表示指定元素类型，如int，float，copy表示是否赋值数据，默认True

- 切片语法解析之一维数组 a[start:stop:step] start包含起始索引 stop则不包括，step表示步长，-1表示反转 ***用于一维数据切片***

# Numpy练习题之初级练习题 数组索引和切片
## 1.创建一个10X10数组，并提取第三行第五列的元素
import numpy as np 

a = np.arange(100).reshape(10,10) # 其中 .reshape表示转换成10X10的二维数组

b = a[2,4] #先行索引，再列索引

print(a)

print(b)

## 2.提取一个数组的所有偶数索引元素 延伸 我也可以提取奇数索引元素
import numpy as np 

a = np.array([0,1,2,3,4,5,6,7,8,9])

b = a[::2] #提取偶数

c = a[1::2] #提取奇数

print(b)

print(c)

## 3.将一个数组的所有大于5的元素替换为1，其余为0
import numpy as np 

a = np.array([0,1,2,3,4,5,6,7,8,9])

b = np.where(a>5,1,0) #表示满足大于5的元素，变为1，反之变为0

print(b)

## 4.提取一个二维数组的第2列
import numpy as np 

a = np.array([[1,2,3],[4,5,6],[7,8,9]])

b = a[:,1] # 多维数组的切片 :表示选取所有行 1表示选取第1列

print(b)

## 5.反转一个一维数组 拓展 二维数组同样也可以反转 方法也是一样的
import numpy as np 

a = np.arange(0,10)

b = a[::-1] #反转

print(a)

print(b)

## 6.反转一个二维数组的所有行
import numpy as np 

a = np.array([[1,2,3],[4,5,6]])

b = a[::-1] #反转 或者 b = a[::1 , :] 表示显示地行反转，列不变

print(b)

## 7.反转一个二维数组的所有列
import numpy as np 

a = np.array([[1,2,3],[4,5,6]])

b = a[:, ::-1] #反转

print(b)

## 8.创建一个10X10数组，并提取其中3X3的子数组
import numpy as np 

a = np.arange(100).reshape(10,10)

b = a[:3 , :3] #表示从0-3行和0-3列的所有数据，3X3

print(a)

print(b)

## 9.使用布尔索引提取数组中大于5的元素
import numpy as np 

a = np.array([0,1,2,3,4,5,6,7,8,9])

b = a>5 #布尔值的编码显示结果 true false之类的

arr = a[b]

print(arr)

## 10.使用花式索引从数组中提取特定位置的元素
import numpy as np 

a = np.array([1,2,3,4,5,6,7,8,9])

b = [0,2,4] #提取元素为 1，3，5

arr = a[b]

print(arr)


## 初级练习题之数组索引与切片的总结
- np.arange(xx).reshape(xx,xx) 表示创建一个元素为xx的数组，并reshape成xx X xx 的二维数组，例如np.arange(100).reshape(10,10) 表示创建一个0-99的数组，并把它转换成10X10的二维数组

- np.where() 表示根据条件在数组中进行元素的选择与替换 语法:np.where(condition,x,y) 如果条件为真，返回x，否则为y，逐元素进行 ***当只传入condition时，则返回的是满足条件的索引***

- 切片语法解析之多维数组 a[行切片，列切片]   例如:a[0, :]表示第0行，所有列 a[:, 1]表示所有行，第1列 a[i:k , j:v]表示多行多列区域

# Numpy练习题之初级练习题 数组操作
## 1.将两个一维数组垂直堆叠
import numpy as np 

a = np.array([1,2,3])

b = np.array([4,5,6])

c = np.vstack((a,b)) # 或者 c = np.vstack([a,b])

print(c)

## 2.将两个一维数组水平堆叠
import numpy as np 

a = np.array([1,2,3])

b = np.array([4,5,6])

c = np.hstack((a,b)) # 或者 c = np.hstack([a,b])

print(c)

## 3.将一个一维数组转换为二维行向量
import numpy as np 

a = np.array([1,2,3])

c = a.reshape(1,-1)  #  行向量

print(c)

## 4.将一个一维数组转换为二维列向量
import numpy as np 

a = np.array([1,2,3])

c = a.reshape(-1,1)  #  列向量

print(c)

## 5.计算两个数组的点积
import numpy as np 

a = np.array([1,2,3])

b = np.array([4,5,6])

c = np.dot(a,b)

print(c)

## 6.计算两个数组的元素乘积
import numpy as np 

a = np.array([1,2,3])

b = np.array([4,5,6])

c = np.multiply(a,b)

print(c)

## 7.计算数组的转置
import numpy as np 

a = np.array([[1,2,3],[4,5,6]])

print(a.T) #行变列 列变行

## 8.展平一个多维数组
import numpy as np 

a = np.array([[1,2,3],[4,5,6]])

b = a.flatten()

print(b)

## 9.改变数组的形状而不改变数据  (本题有两种解法，一种是用reshape 另一种使用 T)
import numpy as np

a = np.array([[1,2,3],[4,5,6]])

c = a.reshape(-1,1) 

print(a.T) #行变列 列变行

print(c)

## 10.计算数组的维度
import numpy as np

a = np.array([[1,2,3],[4,5,6]])

print(a.shape) #返回数组的形状信息 例如 (2,3)表示两行三列

## 初级练习题之数组操作的总结
- np.vstack 表示垂直堆叠

- np.hstack 表示水平堆叠

- np.reshape(1,-1) 其中1表示 1行 -1表示自动识别 行向量

- np.reshape(-1,1) 同理，这个表示列向量

- np.dot 表示用于向量（一维数组）/矩阵乘法的常用函数 语法:np.dot(a,b,out=None) 点积要求前一个矩阵的列数等于后一个矩阵的行数，计算方式为 c = np.dot = a[0] * b[0] + a[1] * b[1]

- np.multiply 表示对两个数组中每个对应元素进行乘法运算，返回相同形状的新数组

- a.T 是Numpy数组的转置操作，表示把该数组的行变列，列变行(二维数组而言)  等价于 a.T ==> np.transpose(a)

- a.flatten 表示把多维数组拉平成一维数组

- a.shape 是Numpy数组的属性，用于返回该数组的形状信息

# Numpy练习题之初级练习题 综合练习题
## 1.创建一个形状为（3，4）的二维数组，所有元素初始化为5 
import numpy as np

a = np.ones((3,4), dtype = int) + 4 或者 a = np.full((3,4), 5, dtype = int)

print(a)

## 2.给定一维数组 arr=np.array([10,20,30,40,50]),如何获取第2个元素和第4个元素 拓展 给定二维数组 
import numpy as np

arr = np.array([10,20,30,40,50])

a = [1,3] 或者 a = arr[[1,3]] # ***第2个元素和第4个元素  一维数组取多个指定位置，用数组或列表：a = [1,3]列表形式 a = arr[[1,3]]数组形式  二维数组用a[1,3]***

***拓展 a =  arr[1,3] print(a) 即可完成 拓展中的要求***

b = arr[a]

print(b)

## 3.将一维数组 np.arange(12) 转换为形状为(3,4)的二维数组
import numpy as np

arr = np.arange(12).reshape(3,4)

print(arr)

## 4.将两个数组 a = np.array([1,2,3]) 和 b = np.array([4,5,6]) 垂直堆叠成一个二维数组
import numpy as np

a = np.array([1,2,3])

b = np.array([4,5,6]) 

c = np.vstack([a,b])

print(c)

## 5.计算数组 np.array([1,2,3,4]) 中所有元素的平方和
import numpy as np

a = np.array([1,2,3,4]) 

b = np.sum(a**2)

print(b)

## 6.给定矩阵 A = np.array([[1,2],[3,4]]) 和 B = np.array([[5,6],[7,8]]),计算它们的矩阵*乘积*
import numpy as np

A = np.array([[1,2],[3,4]])

B = np.array([[5,6],[7,8]])

c = np.dot(A,B)

print(c)

## 7.计算数组np.array([1,2,3,4,5,6,7,8,9])的平均值和标准差
import numpy as np

a = np.array([1,2,3,4,5,6,7,8,9])

c = np.average(a) #求平均值

b = np.mean(a) # 求平均值

d = np.std(a) #求标准差

print("c的打印:",c,"b的打印:",b)

print(d)

## 8.从数据 arr=np.array([1,2,3,4,5,6,7,8,9])中筛出所有大于5的元素
import numpy as np

a = np.array([1,2,3,4,5,6,7,8,9])

b = a>5 #满足符合a>5的元素，返回的值是bool类型

arr = a[b] #根据b的返回值，拿到a对应满足结果的具体值 

print(arr) # 或者直接写成 print(a[a>5])

## 9.将一维数组np.array([1,2,3]) 与 二维数据np.array([1],[2],[3])相加，解释结果
import numpy as np #解释：用到了广播机制来解决

a = np.array([1,2,3])

b = np.array([[1],[2],[3]])

#出发广播机制

print(a+b)

## 10.生成一个形状为(3X3)的数组，其中的元素是从标准正态分布中随机抽取的
import numpy as np 

a = np.random.randn(3,3)

print(a)


## 初级练习题之综合练习题的总结

- np.full() 是Numpy中用于创建所有元素都相同的数组的函数 语法:np.full(shape , fill_value, dtype=None) shape表示形状元组，例如(3,4)表示三行四列，fill_value表示填充的值，所有元素都是这个值

- np.sum() 是Numpy中用来对数组元素求和的函数 语法:np.sum(a, axis=None, dtype=None,keepdims=False) a表示输入数组 axis指定沿哪个轴求和(默认是所有元素总和)axis=0表示对列方向求和，axis=1表示对行方向求和(适用于二维及更高维数组)  dtype表示返回结果的类型 keepdims表示是否保持原有的维度(通常用于多维数组)

- np.mean() 是Numpy中计算数组元素的算术平均值(普通平均值) 语法:np.mean(a,axis=None,dtype=None,keepdims=False) a表示要计算的数组 axis指定沿哪个轴求和(默认全部元素) 其他参数一般用不到

- np.average() 是Numpy中计算加权平均数 语法:np.average(a,axis=None,weights=None,returned=False) a表示输入数组 weights表示权重 比如 weights=[1,1,2] 如果不给权重weights，效果和 np.mean一样

- np.std() 是Numpy中计算数组元素的标准差(衡量离散程度) 语法:np.std(a,axis=None,dtype=None,ddof=0,keepdims=False) a表示输入数组，ddof表示自由度调整，一般用默认即可

- 广播机制 是Numpy中一个非常重要的特性，用来让不同形状的数组能够进行'自动匹配'进行运算 

- np.random.randn() 是Numpy中随机生成数组 其中randn表示标准正态分布，范围（-∞，+∞）

# Numpy练习题之中级练习题 逻辑操作与过滤
## 1.提取数组中所有唯一的元素
import numpy as np 

a = np.array([1,2,3,4,5,6,1,2,3,4,5,6])

print(np.unique(a)) #找出数组中所有不重复的元素的函数

## 2.计算数组中每个元素的和
import numpy as np 

a = np.array([1,2,3,4,5,6,1,2,3,4,5,6])

print(np.sum(a))

## 3.提取数组中所有非零元素的索引
import numpy as np 

a = np.array([1,2,0,4,5,0,1,2,0,0,5,6])

print(np.nonzero(a)) 

## 4.检查两个数组是否相等
import numpy as np 

a = np.array([1,2,0,4])

b = np.array([1,2,3,4])

d = np.array_equal(a,b) # 或者 d = np.all(a == b)

print(d)

## 5.检查数据是否有NaN值
import numpy as np 

a = np.array([1,2,0,4,np.nan,6,8,np.nan])

print(np.isnan(a)) # ***print(a[np.isnan(a)]) 表示 打印nan***  ***print(a[~np.isnan(a)]) 表示打印非nan的值 即1，2，3，4等等***

## 6.替换数组中所有NaN值为0
import numpy as np 

a = np.array([1,2,0,4,np.nan,6,8,np.nan])

c = np.nan_to_num(a,nan = 0) #或 c = np.nan_to_num(a,0) 版本差异的话用后者即可

print(c)

## 7.提取数组中所有大于平均值的数据
import numpy as np  # 这个是我自己写的 不确定对不对哈

a = np.array([1,2,0,4,6,8])

b = np.mean(a) #3.5  # ***b = np.nanmean(a) c = a[a>b] print(c) 比较简单的方法***
 
c = b>a  #bool类型 

print(c)

d = a[~c] #大于平均值 # ***也可以直接简化成d = a[a>b]***

print(d)

## 8.计算数组中满足条件的元素数量
import numpy as np 

a = np.array([1,2,0,4,6,8,np.nan])

b = np.nanmean(a)

c = a>b

d = np.count_nonzero(c) #统计数组中非零(True)元素个数的函数

print(d)

## 9.对数组应用自定义函数
import numpy as np 

b = np.array([1,2,0,4,6,8])

def func(a):

    return a + 10

print(func(b))

## 10.使用where函数替换数组元素
import numpy as np 

b = np.array([1,2,0,4,6,8])

a = np.where(b>5,1,0)

print(a)

## 中级练习题之逻辑操作与过滤的总结

- np.unique() 是Numpy中常用来找出数组中所有不重复的元素的函数，也可以返回这些元素在原数组中的索引位置 语法:np.unique(ar,return_index=False,return_inverse=False,return_counts=False,axis=None) ar表示数组，return_index表示是否返回原数组中每个唯一值第一次出现的位置 return_inverse表示是否返回原数组可以由唯一值重建的索引 return_count表示是否返回每一个唯一值出现的次数 axis对多维数组指定操作的轴(一般用不到) 例如: 返回唯一值及每个值出现的次数 values,counts = np.unique(a, return_counts=True) print(values,counts)

- np.nonzero() 是Numpy中用于找出数组中所有非零元素的位置的函数，它返回的是索引，而不是具体的值 语法:np.nonzero(a) a表示输出数组，可以是一维，也可以是二维或更高维

- np.array_equal() 是Numpy中检查两个数组内容是否完全相等的函数 语法:np.array_equal(a1,a2,equal_nan=False) a1,a2表示要比较的两个数组 equal_nan表示是否把NaN看作相等(默认为False，如果为True，则两个位置上都是NaN也算相等)

- np.all() 是Numpy中用来判断数组所有元素是否都为True的函数，常用于布尔条件判断 语法:np.all(a,axis=None,out=None,keepdims=False) a表示输入数组(可以是布尔数组或数值数组) axis表示指定在哪个维度上判断(默认对所有元素判断) keepdims表示保持维度

- np.isnan() 是Numpy用来判断数组中哪些元素是NaN(Not a Number，表示确实或非法值)的函数 语法:np.isnan(x) x表示输入的数组或单个数值(可以是一维，二维或更高维) 返回同样形状的布尔数组，元素是True说明对应位置是NaN，False说明不是

- np.nan_to_num() 是Numpy用来把数组里的NaN(缺失值)或无穷大(inf)等特殊值替换为你指定的数值的函数，常用于数据清理 语法:np.nan_to_num(x,copy=True,nan=0.0,posinf=None,neginf=None)
x表示输入数组，copy表示是否复制原数组(一般默认为True)，nan表示用来替换NaN的数值(默认是0.0)，posinf表示用来替换正无穷（+inf）的数值（默认是最大有限值），neginf：用来替换负无穷（-inf）的数值（默认是最小有限值）

- np.nanmean() 是Numpy中用于求数组的均值(平均值)时自动忽视NaN值的函数 如果数组中有 np.nan，普通的 np.mean() 会返回 NaN，而 np.nanmean() 会自动跳过这些 NaN 元素，返回实际有效值的平均数 语法:np.nanmean(a,axis=None,dtype=None,out=None,keepdims=None) a表示输入数组，axis指定在哪个轴上计算均值(默认是所有元素)，其他参数用默认即可

- np.count_nonzero() 是Numpy中用来统计数组中非零(True)元素个数的函数，非常适合统计布尔条件成立的次数 语法:np.count_nonzero(a, axis=None, keepdims=False) a表示输入数组(可以是数值型或布尔型)，axis表示指定统计的轴（默认是所有元素），keepdims表示是否保持原有维度（通常不需要管）

# Numpy练习题之中级练习题 数组操作进阶
## 1.找到数组中最大值的索引
import numpy as np  # ***这是我的方法 而我的方法不仅可以这样，还可以寻找多个最大值的索引*** 

a = np.array([1,2,0,4,6,8])

max = np.max(a) # ***c = np.argmax(a) print(c) 这是她的方法 argmax表示只关心第一次出现的最大值的索引***

b = np.where(a == max) #or b = np.argwhere(a == max) ***np.where返回的是元组，而np.argwhere返回的是数组***

print(b)

## 2.找到数组中前五个最大值的索引
import numpy as np 

a = np.array([1,2,0,4,6,8,6,3])

b = np.argpartition(a,-5)[-5:] # ***(a,-5)中的-5表示 最后5个位置是元素a中最大的5个值的索引，但顺序不确定 [-5:]表示取数组的最后5个元素***

print(b)

## 3.对一个数组进行归一化(0-1范围)
import numpy as np 

a = np.array([10,20,30,40,50])

b = (a - a.min()) / (a.max() - a.min())  # ***归一化的操作***

print(b)

## 4.对一个数组进行标准化(均值为0，标准差为1)
import numpy as np 

a = np.array([10,20,30,40,50])

b = (a - a.mean()) / a.std() # ***标准化***

print(b)

## 5.计算数据的移动平均值
import numpy as np 

a = np.array([1,2,0,4,6,8])

b = 3

c = np.convolve(a,np.ones(b)/b, mode='valid')  #***np.ones(b)/b 创建了一个长度为3的平均核[1/3,1/3,1/3],表示对相邻三个数求平均， valid表示只取完全重合的部份***

print(c)

## 6.计算数组中的差分
import numpy as np 

a = np.array([1,2,0,4,6,8]) 

c = np.diff(a) # ***计算相邻元素的差值***

print(c)

## 7.计算数组的梯度
import numpy as np 

a = np.array([1,2,0,4,6,8])

c = np.gradient(a) # ***计算梯度***

print(c)

## 8.对数组进行排序
import numpy as np 

a = np.array([1,2,0,4,6,8])

c = np.sort(a) #***排序(默认升序)***

print(c)

## 9.对数组的每行进行排序
import numpy as np 

a = np.array([[1,2,3],[5,4,6],[9,1,4]])

c = np.sort(a,axis=1) # ***axis=1表示行排序***

print(c)

## 10.对数组的每列进行排序
import numpy as np 

a = np.array([[1,2,3],[5,4,6],[9,1,4]])

c = np.sort(a,axis=0) #***axis=0表示列排序***

print(c)

## 中级练习题之数组操作进阶的总结

- np.argmax() 是Numpy中用于返回数组中最大值的索引的函数 语法:np.argmax(a, axis=None) a表示输入的数组，可以是一维或多维 axis表示指定轴的方向（默认 None，即把数组展平后再找最大值的索引）

- np.argpartition() 是Numpy中一种快速找出前/后若干个最大值或最小值的索引的方法 语法:np.argpartition(a, k) 返回一个数组，表示将数组a进行部份排序，使得第k个元素左边都是较小(或较大)元素，右边都是较大(或较小)的元素，返回是索引

- np.convolve() 是NumPy 中用于一维卷积运算的函数 语法:np.convolve(a,v,mode='full') a表示一维输入数组 v表示另一维的数组(也称为卷积核)，mode表示指定输出的大小，有以下三种取值；
‘full’默认值，返回完全卷积结果，长度为len(a)+len(v)-1  ‘same’返回与a长度相同的卷积结果(中心对齐) ‘valid‘只返回完全重叠部份的卷积结果，长度为len(a)-len(v)+1

- np.diff() 是Numpy库中的一个函数，用于计算数组中相邻元素的差值 语法:np.diff(a,n=1,axis=-1,prepend=<no value>,append=<no value>) a表示输入数组，可以是一个一维或多维的数组 n表示进行差分操作的次数，默认为1 axis表示按最后一个轴进行差分，默认值为-1 prepend表示在计算差分前，在数组的前面添加的值。可以是一个标量或数组，形状需要与输入数组相符，默认值为None append表示在计算差分后，在数组的后面添加的值。可以是一个标量或数组，形状需要与输入数组相符，默认值为None

- np.gradient() 是 NumPy库中的一个函数，用于计算数组的数值梯度。梯度是指数据点的变化速率。通常用于计算一维或多维数组的离散差分 语法:np.gradient(f, *varargs, **kwargs) f表示输入数组，数据点 varargs表示可选的数值输入参数，用于指定数据点之间的间隔(如果不是均匀间隙的情况下) kwargs表示可选的额外参数

- np.sort() 是Numpy中用于排序数组的函数 语法:np.sort(a,axis=-1,kind=None,order=None) a表示要排序的数组，可以是任意维度 axis表示排序的轴向,axis=1表示按行排序，axis=0表示按列排序(默认为-1，即最后一个轴) kind表示排序算法，可选:'quicksort','mergesort','heapsort','stable' order表示当数组是结构化数组时，指定排序的字段（如 order='age'）

# Numpy练习题之中级练习题 随机数与统计
## 1.生成10个0-1之间的随机数
import numpy as np 

a = np.random.rand(10) # ***.rand表示均匀分布***

print(a)

## 2.生成10个符合正态分布的随机数
import numpy as np 

a = np.random.randn(10) # ***.randn表示正态分布***

print(a)

## 3.生成10个整数随机数，（范围1-100）
import numpy as np 

a = np.random.randint(1,101,10) # ***.randint表示离散均匀分布***

print(a)

## 4.随机打乱一个数组
import numpy as np 

a = np.array([1,2,3,4,5,6,7])

np.random.shuffle(a) # ***.shuffle表示打乱数组***

print(a)

## 5.从数据中进行随机抽样
import numpy as np 

a = np.array([1,2,3,4,5,6,7])

b = np.random.choice(a, size=5, replace=False) # ***.choice表示随机抽取***

print(b)

## 6.计算数组的百分位数
import numpy as np 

a = np.array([1,2,3,4,5,6,7])

print(np.percentile(a,[25,50,75])) # ***.percentile表示计算百分位数***

## 7.计算数组的协方差矩阵
import numpy as np 

a = np.array([[1,2,3],[5,4,6],[9,1,4]]) 

print(np.cov(a))  # ***.cov表示计算协方差***

## 8.计算数组的相关系数矩阵
import numpy as np 

a = np.array([[1,2,3],[5,4,6],[9,1,4]])

print(np.corrcoef(a)) # ***.corrcoef表示计算相关系数***

## 9.计算数组的直方图
import numpy as np 

data = np.random.normal(0,1,1000) # ***.normal表示生成正态分布***

x,y = np.histogram(data, bins=10) # ***.histogram表示计算直方图***

print(x,y)

## 10.计算数组的累积分布函数
import numpy as np 

data = np.random.normal(0,1,1000)

c = np.sort(data)

df = np.arange(1,len(c)+1) / len(c)  # ***len(array) 是 Python 中用来“数一下数组里有几个元素”的函数。***

print(df)


## 中级练习题之随机数与统计的总结
- np.random.rand() 是Numpy中随机生成数组，其中rand表示均匀分布，范围[0,1)

- np.random.randn() 是Numpy中随机生成数组 其中randn表示标准正态分布，范围（-∞，+∞）

- np.random.randint() 是Numpy中随机生成数组 其中randint表示离散分布 语法:numpy.random.randint(low, high=None, size=None, dtype=int) low表示随机数的最小值，high表示随机数的最大值，不包含此值，size表示输出数组的形状(例如10，（3，4）)，dtype表示数据类型

- np.random.shuffle() 是Numpy中原地打乱数组顺序（适用于一维或多维数组的第一维） 语法:np.random.shuffle(x) x表示需要打乱顺序的数组(可以是多维数组，但只打乱第一维)

- np.random.choice() 是 NumPy中用于从给定的数组或整数范围中随机抽取元素 语法:np.random.choice(a, size=None, replace=True, p=None) a如果表示数组，则从数组中随机抽取，如果是整数n，就相当于从np.arange(n)中选 size表示要返回的数量，可以是一个整数，也可以是元组 replace表示是否可以重复选择(默认为True)，如果为False，表示不放回抽样 p表示每一个被选中元素的概率，默认为等概率

- np.percentile() 是 NumPy中用于计算数组中某个或某些百分位数 语法:np.percentile(a, q, axis=None, out=None, interpolation='linear', keepdims=False, method='linear')a表示输入数组，q表示百分位数值，可以是一个数或一个数组，范围是0～100，axis表示沿哪个轴计算百分位数，默认对整个数组进行计算，interpolation(method)表示定义百分位计算方式(如'linear','nearest','midpoint'等)，keepdims表示是否保留原始维度

- np.cov() 是 NumPy中用于计算协方差矩阵 语法:np.cov(m, y=None, rowvar=True, bias=False, ddof=None, fweights=None, aweights=None) m表示输入的数组。可以是一维或二维，y表示可选的第二个数据数组（用于两个变量的协方差），rowvar表示默认为 True，表示每一行代表一个变量，每一列是一个观测样本；如果为 False，表示每列是一个变量，bias表示是否使用有偏估计（除以 N）而不是无偏估计（除以 N-1）。默认是 False（使用无偏估计），ddof表示自由度调整，覆盖bias，fweights表示整数型频率权重，aweights表示实数型权重
 
 - np.random.normal() 用来生成正态分布数据  语法:np.random.normal(loc=0.0, scale=1.0, size=None) loc表示正态分布的 均值 μ（默认是 0），scale表示正态分布的 标准差 σ（默认是 1），size表示输出样本数量（可以是整数或元组）

 - np.histogram() 用来统计直方图数据  语法:np.histogram(a, bins=10, range=None, density=False, weights=None) a表示输入的原始数据（通常是 1 维数组） bins表示分箱数量，或指定的分箱边界（默认为 10 个） range表示指定范围 (min, max)，超出这个范围的不会计入 density表示是否返回概率密度而非频数（默认为 False） weights表示权重数组，与输入数据同维度

# Numpy练习题之中级练习题 线性代数的运算
## 1.计算矩阵的行列式
import numpy as np 

a = np.array([[1,2],[4,5]])

data = np.linalg.det(a) # ***计算矩阵行列式***

print(data)

## 2.计算矩阵的逆
import numpy as np 

a = np.array([[1,2],[4,5]])

data = np.linalg.inv(a) #***计算矩阵的逆***

print(data)

## 3.计算矩阵的特征值和特征向量
import numpy as np 

a = np.array([[1,2],[4,5]])

data,value = np.linalg.eig(a) # ***计算特征值和特征向量***

print(data,value)

## 4.解线性方程组
import numpy as np 

a = np.array([[1,2],[4,5]])

b = np.array([2,1])

data = np.linalg.solve(a,b)  # ***解方程组***

print(data)

## 5.计算矩阵的奇异值分解
import numpy as np 

a = np.array([[1,2],[4,5]])

u,s,v = np.linalg.svd(a) # ***奇异值分解***

print(u)
print(s)
print(v)

## 6.计算矩阵的QR分解
import numpy as np 

a = np.array([[1,2],[4,5]])

q,r = np.linalg.qr(a) # ***QR分解***

print(q,r)

## 7.计算矩阵的Cholesky分解
import numpy as np 

a = np.array([[2,-1],[-1,2]])

data = np.linalg.cholesky(a) # ***Cholesky分解***

print(data)

## 8.计算矩阵的迹
import numpy as np 

a = np.array([[1,2],[4,5]]) 

print(np.trace(a)) # ***迹***

## 9.计算矩阵的范数
import numpy as np 

a = np.array([[1,2],[4,5]])

data = np.linalg.norm(a)  # ***范数***

print(data)

## 10.计算矩阵的秩
import numpy as np 

a = np.array([[1,2],[4,5]])

data = np.linalg.matrix_rank(a) # ***秩***

print(data)



## 中级练习题之线性代数的运算的总结
- np.linalg.det() 是Numpy中用于计算矩阵行列式的函数 语法:np.linalg.det(a) a表示输入数组，必须是一个方阵（二维，且行数=列数）

- np.linalg.inv()  是Numpy中用于计算矩阵的逆矩阵的函数 语法:np.linalg.inv(a) a表示输入数组，必须是一个方阵

- np.linalg.eig() 是Numpy中用于计算矩阵的特征值和特征向量的函数 语法:np.linalg.eig(a) a表示输入数组，必须是一个方阵

- np.linalg.solve() 是 NumPy中用于解线性方程组的函数 语法:numpy.linalg.solve(a, b) a表示输入数组，必须是一个方阵 b表示常数项向量或矩阵

- np.linalg.svd() 是 NumPy中用于执行奇异值分解的函数，在数据压缩，主成分分析，推荐系统等领域广泛应用 语法:numpy.linalg.svd(a, full_matrices=True, compute_uv=True, hermitian=False) a表示要分解的原始矩阵 full_matrices默认为True，是否返回完整的U和V矩阵 compute_uv表示是否计算并返回U和V的值，(设置为False只返回奇异值) hermitian表示针对对称矩阵优化，一般保持为False

- np.linalg.qr() 是 NumPy 中用于执行 QR 分解的函数，在数值分析，最小二乘法解线性方程组等领域非常常见 语法:np.linalg.qr(a,mode='reduced') a表示输入矩阵，二维(可以是方阵，也可以不是)
mode表示控制返回结果的形状，常见有三种：‘reduced’，‘complete‘，‘raw'默认是‘reduced'

- np.linalg.cholesky() 是 NumPy 中用于执行 Cholesky 分解的函数 语法:numpy.linalg.cholesky(a) a表示一个对称正定矩阵，a.T == a 且所有特征>0(正定)

- np.trace() 是 NumPy 中用来计算 矩阵主对角线元素之和（迹）的函数 语法:numpy.trace(a, offset=0, axis1=0, axis2=1, dtype=None, out=None) a表示一个二维矩阵，返回主对角线(从左上到右下)的元素之和  offset默认是0，表示主对角线。如果是正数，表示上对角线；负数表示下对角线  axis1/axis2指定二维矩阵的哪两个轴进行追踪（高级用法）
 
 - np.linalg.norm() 是 NumPy 中用于计算 向量或矩阵的范数（norm）的函数。范数表示向量或矩阵的“长度”或“大小”，在数值计算、优化、机器学习中非常常用 语法:numpy.linalg.norm(x, ord=None, axis=None, keepdims=False) a表示输入的向量或矩阵  ord表示范数类型，决定计算哪种'大小'  axis表示计算的轴  keepdims表示是否保持纬度一直，默认是False

- np.linalg.matrix_rank() 是 NumPy 中用来计算 矩阵的秩（Rank）的函数。 语法:numpy.linalg.matrix_rank(M, tol=None) M表示输入的矩阵（二维数组） tol表示判定矩阵是否为“零”的容差，默认自动设定，通常不用改

# Numpy练习题之高级练习题 高级应用
## 1.实现一个简单的神经网络前向传播
import numpy as np 

def name_df(x):  ***激活函数***

    return 1 / (1+np.exp(-x))

def name_df1(X,W1,b1,W2,b2):   ***前向传播  每一层的前向传播 = 线性变化 + 非线性激活 *** 

    df1 = name_df(X @ W1 + b1)      ***隐藏层***  #  @ 是Numpy中的矩阵乘法，和np.dot()功能类似
    df2 = name_df(df1 @ W2 + b2)   ***输出层***
    return df2

X = np.random.randn(3,4)

W1 = np.random.randn(4,5)

b1 = np.random.randn(5)

W2 = np.random.randn(5,2)

b2 = np.random.randn(2)

print(name_df1(X,W1,b1,W2,b2))

## 2.计算两个矩阵的卷积 （2维卷积 convolve用来处理一维卷积 而convolve2d用来处理二维卷积）
import numpy as np 

from scipy.signal import convolve2d     # ***导入库***

a = np.array([[1,2,3],[4,5,6],[7,8,9]])

b = np.array([[1,0],[0,1]])

c = convolve2d(a,b, mode='valid')

print(c)

## 3.实现图像处理中的滤波操作 （高斯滤波方法）
import numpy as np 

from scipy.ndimage import gaussian_filter  # ***导入库 高斯***

a = np.random.rand(100,100) * 255  # ***模拟噪声图像 将 [0,1] 范围的值转换为 [0,255] 灰度图值*** 

c = gaussian_filter(a, sigma=1) # ***对任意维度的数组进行高斯模糊（不仅限于图像）***

print(c)

## 4.计算数组的快速傅里叶变换 （傅里叶变换是一种将时域信号转化为频域信号的数学工具）
import numpy as np 
 
a = np.array([1,2,1,3,1,4])  # ***模拟一个时间序列，可以是音频片段、图像行、传感器数据***

c = np.fft.fft(a) # ***执行快速傅里叶变换***

print(c)

## 5.计算数组的逆傅里叶变换 (从频域还原回时域)
import numpy as np 

a = np.array([1,2,1,3,1,4])

c = np.fft.ifft(a)  # ***逆快速傅里叶变换***

print(np.real(c)) # ***np.real()取出复数的实部，避免干扰后续计算或显示***

# Numpy练习题之高级练习题 性能优化
## 1.向量化代替循环 （🧠 “不要在 NumPy 中写 for 循环” 因为在处理大规模数组或矩阵时：Python 的 for 循环是慢的，因为它是解释执行 而NumPy 向量化是“底层实现高效并行”的方案，速度可快几十倍甚至百倍）
import numpy as np 

import timeit  # ***测量运行时间***

***问题：计算数组中每个元素的平方和，分别用循环和向量化操作实现，比较性能***
  
arr = np.random.rand(10**6)  # ***生成100万个数据***

***方法1:循环计算***

def name_df():

    nums = 0
    for x in arr:
        nums += x**2
    return nums

***方法2:向量化计算***

def name_df1():

    return np.sum(arr**2)

name1 = timeit.timeit(name_df, number=10)

name2 = timeit.timeit(name_df1,number=10)

print(name1)  ***向量化的性能优于循环***

print(name2)

## 2.视图与拷贝的内存优化 ***如果不想影响原始数据，但又要修改数据，请务必用copy方法***
import numpy as np 

***问题：有一个大数组，取其前半部份。如何避免不必要的内存拷贝？***

arr = np.random.rand(10**7)

***视图（不会复制数据，节省内存）***

view = arr[:len(arr)//2]  ***共享原数据内存***  ***arr[:len(arr)//2]表示取前一半的元素***

***拷贝（会复制数组，占用额外内存）***

copy = arr[:len(arr)//2].copy()  ***浪费内存***

print(f"view.nbytes为: ",view.nbytes,"MB ")  ***.nbytes 整个数组的内存占用***

print(f"copy.nbytes为: ",copy.nbytes,"MB")  

## 3.选择适合的数据类型
import numpy as np 

***问题：存醋0-255范围内的整数，使用哪种Numpy数据类型最节省内存？***

a = np.array([100,300,500],dtype=np.int32) 

 ***dtype=int 和 dtype=np.int32的区别:dtype=int是平台相关的整数类型，而dtype=np.int32是固定的整数类型，但在深度学习以及图像处理中，最好是用dtype=np.int32***

print(a)

## 4.使用Numpy内置函数 (没什么好说的，看例子就知道了)
import numpy as np

a = np.array([12,23,11])

print(a)

## 5.避免重复计算中间结果
import numpy as np 

***问题:计算数组中每个元素的平方再求和，如何优化？***

a = np.random.rand(10**7)

***错误的方法 bad idea 会导致内存的增多***

names = a**2

s = np.sum(names)

print(s)

***正确的方法 good idea***

print(np.sum(a**2))

# Numpy练习题之高级练习题 综合项目
## 1.大型数据处理优化

***题目： 假设你有一个1亿元素的浮点数组，需要计算滑动平均(窗口大小为100)，如何高效实现并避免内存问题***

- 解答

    - 1.可以使用Numpy当中的创建滑动窗口视图函数方法去处理，而非副本。

    - 2.大型处理块这里可以使用将数组分成适当大小的块进行处理。 ***chunk_size=10**6***

    - 3.处理边界情况。

    - 4.提供一个内存优化方案：优化浮点数组的字节大小来减少内存占用

 ***代码展示***

import numpy as np 

from numpy.lib.stride_tricks import sliding_window_view  ***导入库：滑动窗口视图***

***创建滑动窗口视图函数，其中(chunk_size=10**6)用于分块处理防止内存爆炸，默认每次是100万个***

def sliding_mean_large_array(data, window_size=100, chunk_size=10**6):  
- 高效滑动平均实现：

    - 使用 sliding_window_view 避免复制

    - 支持分块处理大数据

    - 使用 float32 减少内存

    - 自动处理边界重叠

    data = np.asarray(data, dtype=np.float32)   ***使用 np.asarray的方法,确保传入的data是一个Numpy的数组***

    n = len(data)  ***获取n的长度***

    if data.ndim != 1:

        raise ValueError("输入数据必须为一维数组")

    if n < window_size:

***raise是Python中用于主动抛出异常的关键字，当程序遇到无法继续执行的错误条件时，强制中断当前流程，并向上层传递错误信息***
        raise ValueError("数组长度小于滑动窗口大小") 
        
    result = []

***每块处理大小需包含前后 window_size -1 的重叠，由于窗口大小是100，即前面的99个元素都是重复的***

    overlap = window_size - 1  

    start = 0

***将超大数组 data 分成多个小块，逐块高效地计算滑动平均值（含窗口重叠），最终拼接出完整结果，避免内存爆炸***
    while start < n:  

 ***这个 min() 是为了防止越界，同时确保最后一个处理块不会出错或缺失滑动窗口数据***
        end = min(start + chunk_size + overlap, n)  

        block = data[start:end]

     #创建滑动窗口视图（不会复制）

        windows = sliding_window_view(block, window_shape=window_size)

***axis=-1表示最后一个维度，因为window_size=100,所以前99个都是无效的，所以只需要计算最后一个即可***
        mean_block = windows.mean(axis=-1) 

        #如果不是首块就去掉重叠前缀部份

        if start != 0:
***避免重复计算***
            mean_block = mean_block[overlap:] 

        result.append(mean_block)

        start += chunk_size

***合并数据，在滑动平均计算中，将前无效窗口（补 NaN）和有效滑动平均结果拼接起来，形成完整输出***
    return np.concatenate(result)  

***astype() 是 NumPy 数组的一个方法，用来转换数组的数据类型***

data = np.random.rand(10**8).astype(np.float32)   

avg = sliding_mean_large_array(data,window_size=100,chunk_size=10**6)

print(avg.shape)    ***shape是Numpy数组中的一个属性，用于获取数组的维度信息(即各轴的长度)***

## 2.多维数组操作
***题目：给定形状为(1000,1000, 3)的RGB图像数组，如何高效地：1.转换为灰度图像 2.应用高斯模糊 3.找出所有亮度大于0.6的像素坐标***

- 解答
    - 1.进行灰度图像转换(避免循环)
    - 2.使用广播方法实现向量化高斯模糊
    - 3.条件查找像素坐标

***代码展示***
import numpy as np 

from scipy.ndimage import gaussian_filter  ***导入相关库***

img = np.random.rand(100,100,3)  ***构造一个模拟 RGB 图像（范围 [0,1]) 100行100列的三维数组***

***使用加权平均法求灰度值=0.2989*R + 0.5870*G + 0.1140*B***

gray = np.dot(img[...,:3],[0.2989,0.5870,0.1140])  ***img[...,:3]表示保留所有行列,仅取前3个通道(R,G,B) 由于多维数组中,最后一个维度通常是颜色通道 所以:3 就表示R G B三个值***

blurred = gaussian_filter(gray,sigma=1) ***高斯模糊***

coords = np.argwhere(blurred > 0.6) # ***np.argwhere返回的是二维数组,每一行都是一个完整坐标，不同于 np.where,它返回的是每个轴上的索引数组组成的元组***

print(coords)

## 3.性能关键型计算
***题目：实现一个函数计算两个大型矩阵的余弦相似度矩阵，并优化性能***

- 解答
    - 1.优化点积计算
    - 2.广播机制避免循环
    - 3.归一化处理，使用向量化操作

***代码展示***
import numpy as np 

def name(A,B):

***实现归一化的操作 axis=1表示对每一行求范数 keepdims=True表示保持数组维度形状***
    A_ = A / np.linalg.norm(A,axis=1,keepdims=True)  

    B_ = B / np.linalg.norm(B,axis=1,keepdims=True)

***矩阵乘法的规则要求：第一个矩阵的列数 必须等于 第二个矩阵的行数***

***计算两个矩阵 A 和 B 的余弦相似度矩阵 的核心计算式*** ***如果不加.T则会因为维度不匹配而报错，.T的作用是为了转置B，把B的行变列，列变行***
    C_ = np.dot(A_,B_.T) 

    return C_

A = np.random.rand(3,4)

B = np.random.rand(3,4)

print(name(A,B))

## 4.内存高效算法
***题目：处理两个形状为(1M,256)的矩阵的成对距离计算，如何避免内存错误？***

- 解答
    - 1.分块处理技术
    - 2.选择适当距离度量(如欧式距离) ***欧式距离公式：||a - b||² = ||a||² + ||b||² - 2⟨a, b⟩***
    - 3.考虑内存布局和连续性问题
    - 4.使用对应形式重用内存

***代码展示***
import numpy as np 

def df(A,B, block_size=1000):  ***定义函数***

- 分块计算 A 和 B 的成对欧式距离，避免内存溢出。

    - 参数：
    - A, B: numpy.ndarray，形状为 (N, D)
    - block_size: int，每次处理 A 中的行数
    - 返回：
    - 每次返回 (block_size, B.shape[0]) 的一个欧式距离子块

        A = np.ascontiguousarray(A, dtype=np.float32) ***使用 np.ascontiguousarray() 保证它是内存连续的***

        B = np.ascontiguousarray(B, dtype=np.float32)   
    
***只计算一次B的范数平方，因为A被拿去做了分块，如果B被拿去做分块，则只计算一次A***
        B_ = np.sum(B**2, axis=1).reshape(1,-1) 

***np.empty() 是 NumPy 中用来创建一个指定形状和数据类型但未初始化内容的数组的函数***
- 预分配结果数组，用于重复使用
        results = np.empty((block_size,B.shape[0]),dtype=np.float32)  ***shape[0]表示获取第一个维度的大小，即行数 shape[1]表示列数 shape[-1]表示最后一个维度***

        for i in range(0, A.shape[0], block_size):

***当前块***
            A_block = A[i:i+block_size] 

            real_A_block = A_block.shape[0] 

            A_ = np.sum((A_block**2),dtype=np.float32).reshape(-1,1)

            dot = np.dot(A_block, B.T)

***将计算结果存入预分配的 results 数组中，计算的是[:real_A_block] 表示取real_A_block的前面行***
            np.subtract(A_ + B_, 2 * dot, out=results[:real_A_block])  

- np.subtract 是 NumPy 中的减法函数，支持广播和原地操作 out是他的语法中的一个，如有兴趣可以去了解一下

***开平方 np.sqrt***
            np.sqrt(results[:real_A_block], out=results[:real_A_block])

- np.sqrt 是 NumPy 中计算平方根的函数，out也是他的语法中的一个，有兴趣也可以去了解一下

***yield关键字 暂停函数执行，返回一个值给调用者，同时保持函数的状态，后续可以继续执行***
            yield results[:real_A_block].copy() 

if __name__ == "__main__":

***astype() 是 NumPy 数组的一个方法，用来转换数组的数据类型***
    A = np.random.rand(10000, 256).astype(np.float32) 

    B = np.random.rand(10000, 256).astype(np.float32)

***enumerate() 是 Python 内置函数，常用来在循环中同时获得元素索引和值 语法：enumerate(iterable, start=0) iterable：任何可迭代对象，如列表、元组、生成器等 start：可选参数，指定索引起始值，默认从 0 开始***

    for i, dist_block in enumerate(df(A, B, block_size=1000)): 

        print(f"第 {i+1} 块距离矩阵 shape: {dist_block.shape}")

## 5.复杂统计计算
***题目：实现一个函数计算大型数据集的滚动统计量(均值，标准差，偏度，峰度)，窗口为100，步长为10***

- 解答
    - 1.创建滑动窗口
    - 2.使用相关处理统计量函数去处理
    - 3.优化内存访问模式
    - 4.处理边界情况 

***代码展示***
import numpy as np 

from scipy.stats import skew, kurtosis  ***#skew偏度 kurtosis峰度***

from numpy.lib.stride_tricks import sliding_window_view  ***导入滑动窗口的库***

def df(data,window_size=100, step=10):

***确保data一定是一个数组***

    data = np.asarray(data)  

***.nidm这是 NumPy 中的属性，表示数组的“维度数”***  

***处理边界情况：数据长度必须 >= 窗口大小***

    if data.ndim != 1:  

        raise ValueError ("输入的长度必须为一维数组")

    if len(data) < window_size:

        raise ValueError ("数据长度不足一个窗口大小")

***构建滑动窗口视图（优化内存访问，不复制数据）***

    windows = sliding_window_view(data, window_shape=window_size)

***按步长截取***

    total_windows = (len(data) - window_size) // step + 1

***[:total_windows]用于边界控制***

    selected_windows = windows[::step][:total_windows] 

***计算统计量（向量化)***

***等效于 means = np.mean(selected_windows,axis=1)***

    means = selected_windows.mean(axis=1) 

    stds = np.std(selected_windows,axis=1)

    skews = skew(selected_windows, axis=1, bias=False)

    kurtoes = kurtosis(selected_windows, axis=1, bias=False)

***返回一个字典，用于存放键值对***

    return {
        'means':means,
        'stds':stds,
        'skews':skews,
        'kurtosis':kurtoes
    }

data = np.random.rand(1000000)

dfc = df(data,window_size=100,step=10)

print("dfc的means:",dfc['means'])

print("dfc的stds:",dfc['stds'])

print("dfc的skews:",dfc['skews'])

print("kurtosis:",dfc['kurtosis'])






    

