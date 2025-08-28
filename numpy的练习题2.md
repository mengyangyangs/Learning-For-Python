# 1.使用 n=1000000对比python原生列表跟numpy计算的时差
## 代码展示
import time as t 

import numpy as np 

n = 10000000

start_time = t.time()

python_list = list(range(n))

for i in range(n):

    python_list[i] += 1
    
python_time = t.time() - start_time

print("python时间为:",python_time)

start_time = t.time()

numpy = np.arange(n)

numpy += 1

numpy_time = t.time() - start_time

print("numpy时间为:",numpy_time)

final_time = python_time/numpy_time

print("numpy快python:",final_time,"秒")

# 2.创建一个大小为10的空向量(也就是一维数组)
## 代码展示
import numpy as np 

array = np.zeros(10)  ***or array = np.empty(10)表示只分配空间，但未初始化***

print(array)

# 3.如何找到任意数组中的内存大小
## 代码展示
import numpy as np 

array = np.random.rand(3,4)

print(array.nbytes)  ***or array.itemsize * array.size也可以 其中array.item表示字节，array.size表示元素个数***

# 4.创建两个数组，分别指定32位的单精度浮点数和字符串类型
## 代码展示
import numpy as np 

c = np.random.rand(3,4).astype(np.float32)

b = np.array(['c++','python','java','numpy'], dtype='U8')  ***U8表示每个字符串最多可以接收8个字符***

print(c.dtype)

print(b.dtype)

# 5.创建一个大小为10的空向量，但第五个值为1
## 代码展示
import numpy as np 

array = np.zeros(10)

array[4] = 1

print(array)

# 6.创建一个值，范围从10到49的向量
## 代码展示
import numpy as np

array = np.arange(10,50)

print(array)

# 7.反转一个向量（第一个元素变为最后一个）
## 代码展示
import numpy as np 

array = np.arange(10)

array_ = array[::-1]  ***反转***

print(array_)

# 8.创建一个3X3的矩阵，值范围是从0到8
## 代码展示
import numpy as np 

array = np.random.randint(0,8,(3,3)) ***or array = arange(9).reshape(3,3)这样也可以，不过我的方法的值是随机的***

print(array)

# 9.找到非零元素在[1,2,0,4,0]中的索引
## 代码展示
import numpy as np 

array = np.array([1, 2, 0, 0, 4, 0])

index_c = array>0 

real_c = np.where(index_c)

print(real_c)   ***or a = np.nonzero(array) 这个方法比我的简单，且更加清晰易懂***

# 10.创建一个3X3的单位矩阵
## 代码展示
import numpy as np 

array = np.eye(3,3)

print(array)

# 11.创建一个大小为3X3X3的随机值数组
## 代码展示
import numpy as np 

array = np.random.rand(3,3,3)

print(array)

# 12.创建一个10X10的随机值数组，并找到最小值和最大值
## 代码展示
import numpy as np 

array = np.random.rand(10,10)

print("最大值是:",np.max(array),"最小值是:",np.min(array))

# 13.创建一个大小为30的随机向量，并找到平均值
## 代码展示
import numpy as np 

array = np.random.rand(30)

print(np.mean(array))

print("the other method:",np.average(array)) ***np.mean是一种方法，而np.average是另一种方法***

# 14.创建一个二维数组，边界为1，内部为0
## 代码展示
import numpy as np 

array = np.ones((10,10),dtype=int)
 
array[1:-1,1:-1] = 0    ***表示第1行，倒数第2行，第1列，倒数第2列***

print(array)

# 15.如何在现有数组周围添加一个填充为0的边界
## 代码展示
import numpy as np 

array = np.ones((5,5),dtype=int)

array_ = np.pad(array,pad_width=1, constant_values=0)   ***np.pad是NumPy中用来在数组边缘填充数值的函数，语法:np.pad(array, pad_width, mode='constant', **kwargs)***


print(array_)

# 16.创建一个5X5的矩阵，值为1，2，3，4，5，位于对角线下方
## 代码展示
 import numpy as np 

array = np.arange(5)

array_ = np.diag(1+array,k=0) 
***np.diag()是NumPy中一个非常实用的函数，用来：从已有数组中提取对角线上的元素，或根据给定的一维数组，创建一个对角矩阵，语法:np.diag(v, k=0) k=0表示主对角线，k>0表示上三角对角线，k<0表示下三角对角线***

print(array_)

# 17.创建一个8X8的矩阵，要求行列分别为0，1交替出现
## 代码展示
import numpy as np 

array = np.ones((8,8), dtype=int)

array[::2,1::2] = 0 

array[1::2,::2] = 0

print(array)

# 18.一个shape为(6,7,8)的数组，第100个元素的索引(z,y,z)是什么？
## 代码展示
import numpy as np 

shape = (6,7,8)

index = 99

res = np.unravel_index(99, shape) ***将一维索引转换为多维数组的坐标***

print(shape)

print(res)

# 19.使用tile函数创建一个8X8的棋盘矩阵
## 代码展示
import numpy as np 

base = np.array([[1,0],[0,1]])

array = np.tile(base, (4, 4)) ***用于重复数组，按照指定次数在各个维度上进行重复拼接***

print(array)

# 20.规范化(均值方差标准化)一个5X5的随机矩阵
## 代码展示
import numpy as np 

arr = np.random.random((5, 5))  ***创建一个5x5的随机矩阵***

np.mean(arr)  ***计算均值***

base = (arr - np.mean(arr)) / np.std(arr)  ***均值方差标准化***

print(base)  ***打印规范化后的矩阵***

# 21.创建一个自定义数据类型，描述一个颜色为四个无符号字节(RBGA)
## 代码展示
import numpy as np 

color = np.dtype([('r', np.ubyte), ('g', np.ubyte), ('b', np.ubyte), ('a', np.ubyte)])  ***# 定义颜色数据类型或者把ubyte变成uint8***

print(color)  ***# 打印颜色数据类型***

# 22.将一个5X3的矩阵乘一个3X2的矩阵，矩阵元素都是1
## 代码展示
import numpy as np 

arr = np.ones((5, 3),dtype=int)  ***# 创建一个5x3的矩阵，元素都是1***

arr1 = np.ones((3, 2),dtype=int)  ***# 创建一个3x2的矩阵，元素都是1***

brr = np.dot(arr, arr1)  ***# 矩阵乘法 或者使用 brr = arr @ arr1***

print(brr)  ***# 打印结果***

# 23.给定一个一维数组，原地将所有大小在3到8之间的元素取反
## 代码展示
import numpy as np 

arr = np.array([1,2,3,5,6,8,7,9,10])  # ***创建一个一维数组***

arr[(arr >= 3) & (arr <= 8)] = -arr[(arr >= 3) & (arr <= 8)]  # ***原地将所有大小在3到8之间的元素取反***

print(arr)  # ***打印结果***

# 24.如何将浮点数组向外取整
## 代码展示
import numpy as np 

arr = np.random.uniform(-10, 10, (3, 4))  # ***创建一个3x4的随机浮点数组***

arr_ceil = np.ceil(arr)  # ***向外取整***

print(arr_ceil)  # ***打印向外取整后的数组***

# 25.如何找到两个数组中的公共值
## 代码展示
import numpy as np 

arr = np.array([11,22,44,55])

brr = np.array([11,666,33,44])

common = np.intersect1d(arr, brr)  # ***找出两个数组的公共元素***

print(common)  # ***打印结果***

# 26.如何获取，昨天，今天和明天的日期
## 代码展示
import numpy as np 

today = np.datetime64("today", "D") # ***Get today's date***

tomorrow = today + np.timedelta64(1, "D") # ***Get tomorrow's date***

yesterday = today - np.timedelta64(1, "D") # ***Get yesterday's date***

print("Today:", today)

print("Tomorrow:", tomorrow)

print("Yesterday:", yesterday)

# 27.如何获取2025年的5月所有日期
## 代码展示
import numpy as np 

start = np.datetime64('2025-05-01') # ***开始时间***

end = np.datetime64('2025-05-31')  # ***结束时间***

dete = np.arange(start, end, dtype='datetime64[D]') # ***生成日期范围***

print(dete)

# 28.如何以原地计算的方式逐步执行表达式(A+B)*(-A/2)的计算过程？请分解步骤
## 代码展示
import numpy as np 

a = np.array([1, 2, 3, 4, 5],dtype = np.float64)

b = np.array([6, 7, 8, 9, 10])

sum = np.add(a, b) # ***数组相加***

np.negative(a, out=a)  # ***取负数***

np.divide(a, 2, out=a) # ***除以2***

result = np.multiply(a, sum) # ***数组相乘***

print(result)

# 29.使用四种不同的方法提取一个随机正数数组的整数部分
## 代码展示
import numpy as np 

arr = np.random.uniform(0, 10,10)

print(arr-arr%1)    # ***向下取整到最近的整数***

print(arr//1)   # ***整数除法（向下取整）***

print(np.floor(arr)) # ***向下取整到最近的整数***

print(arr.astype(int)) # ***转换为整数类型***

# 30.创建一个5X5的矩阵，值的范围从0-4
## 代码展示
import numpy as np 

arr = np.zeros((5, 5))  # ***创建一个5x5的零矩阵***   

arr = arr + np.arange(5) # ***将0-4的数组加到每一行***

print(arr)

# 31.创建一个生成器函数生成10个整数，并用它构建一个数组
## 代码展示
import numpy as np 

def generate(): # ***生成器函数***
    """生成器函数，生成0到9的数字"""
    for i in range(10): # ***生成0到9的数字***
        yield i # ***使用yield关键字返回值 遇到yield则返回一个值***
    
arr = np.fromiter(generate(), dtype=float)  # ***使用fromiter函数创建数组***

print(arr)  # ***输出数组内容***

# 32.创建一个大小为10的向量，值范围从0-1
## 代码展示
import numpy as np 

arr = np.linspace(0, 1, 10)  # ***创建一个包含10个元素的数组，从0到1均匀分布***

print(arr)  # ***输出数组内容***

# 33.创建一个大小为10的随机向量，并对其进行排序
## 代码展示
import numpy as np 

arr = np.random.random(10)

brr = np.sort(arr) # ***排序***

print("Sorted array:", brr)

# 34.两个随机数组A和B，检查他们是否相等
## 代码展示
import numpy as np 

arr = np.random.randint(1, 10, 5)

brr = np.random.randint(1, 10, 5)

equal = np.array_equal(arr, brr) # ***检查两个数组是否相等***

print(equal)

# 35.使数组不可变（只读）
## 代码展示
import numpy as np 

arr = np.ones(10) # ***创建一个包含10个元素的数组，初始值为1***

arr[0] = 0 # ***将第一个元素设置为0***

arr.flags.writeable = False # ***设置数组为只读***

arr[0] = 5 # ***尝试修改第一个元素，将会引发错误***

print(arr) # ***输出数组内容***

# 36.一个随机的10X2矩阵，表示笛卡尔坐标(x,y)，将其转换为极坐标
## 代码展示
import numpy as np 

arr = np.random.uniform(-10,10,(10,2))

x,y = arr[:,0],arr[:,1] # ***将二维数组拆分为x和y两个一维数组***

r = np.sqrt(x**2 + y**2) # ***计算每个点到原点的距离***

jiaodu = np.arctan2(y, x) # ***计算每个点的极角***

res = np.column_stack((r, jiaodu)) # ***将距离和极角组合成新的二维数组***

print(res) # ***输出结果***

# 37.创建一个大小为10的随机向量，并将最大值替换为0
## 代码展示
import numpy as np 

arr = np.random.uniform(0,10,10)

arr_max = np.max(arr) # ***找到数组中的最大值***

res = np.where(arr == arr_max,0,arr) # ***将最大值替换为0***

print("Original array:", arr) # ***输出原始数组***

print("Modified array:", res)   # ***输出修改后的数组***

# 38.创建一个结构化数组，包含覆盖[0,1]x[0,1]区域的x和y坐标
## 代码展示
import numpy as np

arr = np.zeros((5,5),[("x",float),("y",float)]) # ***创建一个5x5的数组***

x = np.linspace(0, 1, 5)  # ***生成0到1之间的5个等间距点***

y = np.linspace(0, 1, 5)  # ***生成0到1之间的5个等间距点***

arr["x"],arr["y"] = np.meshgrid(x, y)  # ***创建网格***

print(arr)

# 39.给定两个数组X和Y，构造柯西矩阵Cij=1/(Xi-Yi)
## 代码展示
import numpy as np

x = np.arange(10)

y = x - 0.5

c = 1.0 / np.subtract.outer(x,y) #  ***计算外差分***

print(c)

# 40.打印每种numpy标量类型的最小值和最大值
## 代码展示
import numpy as np

for dtype in [np.int16,np.int32,np.int64]:

    print("最大值:",np.iinfo(dtype).max)  # ***打印最大值***

    print("最小值:",np.iinfo(dtype).min)  # ***打印最小值***

print("---------")

for dtype in [np.float16,np.float32,np.float64]:

    print("最大值:",np.finfo(dtype).max)  # ***打印最大值***

    print("最小值:",np.finfo(dtype).min)  # ***打印最小值***

# 41.创建一个结构化数组，表示位置(x,y)和颜色(r,g,b)
## 代码展示
import numpy as np

dtype = np.dtype([('position', [('x', np.float64), ('y', np.float64)]), ('color', [('r', np.float64), ('g', np.float64), ('b', np.float64)])]) # ***定义复合数据类型***

arr = np.zeros((10,),dtype=dtype) # ***创建一个包含10个元素的数组，元素类型为dtype定义的复合数据类型***

print(arr)

# 42.创建一个形状为(10,2)的随机向量，表示坐标，逐点计算距离
## 代码展示
import numpy as np

arr = np.random.random((10,2))

x,y = np.atleast_2d(arr[:,0],arr[:,1]) # ***将一维数组转换为二维数组***

res = np.sqrt((x-x.T)**2 + (y-y.T)**2) # ***计算距离矩阵***

print(res)

# 43.如何原地将一个浮点(32位)数组转换为整数(32位)数组
## 代码展示
import numpy as np

arr = (np.random.rand(10)*100).astype(np.float32) # ***创建一个随机数组***

res = arr.view(np.int32)  # ***将数组视图转换为int32类型***

res[:] = arr # ***将原数组的值赋给视图***

print(res)  # ***打印转换后的数组***

# 44.生成一个通用的二维高斯样式数组
## 代码展示
import numpy as np

x,y = np.meshgrid(np.linspace(-1,1,10),np.linspace(-1,1,10)) # ***创建网格***

D = np.sqrt(x*x + y*y) # ***计算每个点到原点的距离***

sigma,mu = 1.0, 0.0 # ***设置高斯函数的参数***

res = np.exp(-((D - mu)**2) / (2 * sigma**2)) # ***计算高斯函数值 np.exp为numpy中的指数函数，以e为底的幂***

print(res) # 打印结果

# 45.如何随机放置P个元素在一个二维数组中
## 代码展示
import numpy as np

n = 10

p = 5

arr = np.zeros((n,n))

np.put(arr,np.random.choice(range(n*n),p,replace=False),1) # ***随机选择p个位置填充1 np.random.choice从序列中随机抽取元素 np.put在指定位置修改数组值***

print(arr)

# 46.从矩阵中减去每行的均值
## 代码展示
import numpy as np

arr = np.random.rand(5,10)

res = arr - np.mean(arr, axis=1, keepdims=True) # ***按行减去均值***

print(res)  

# 47.如何按第n列对数组进行排序
## 代码展示
import numpy as np

arr = np.random.randint(0,10,(5,4))

print("before sort:",arr)

brr = np.sort(arr,axis=0) # ***按列排序***

print("after sort:",brr)

# 48.如何判断给定的二维数组是否有空列
## 代码展示
import numpy as np

arr = np.array([[0,1,np.nan],[3,4,np.nan],[5,7,np.nan]])

print(np.isnan(arr))  # ***检查每个元素是否为 NaN*** 

print(np.isnan(arr).all(axis=0))  # ***检查每列是否全为 NaN*** 