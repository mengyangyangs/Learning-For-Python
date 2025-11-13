# 运算符
- + ***加***
- - ***减***
- * ***乘***
- / ***除***
- % ***求余 当被除数小于除数时，余数等于被除数！***
- // ***整除***

# 自变量variable(也叫做变量)
a=1     a = "你好"  a = 1.9  

# while循环 （当条件不满足后，就不会进入while循环）
condition = 1

while condition < 10:

    print(condition)
    condition = condition + 1

# for循环
fuck = [1,2,3,4,5,6666,777]

for i in fuck:

    print(i)

 for i in range(1,10,1): //range的第三位表示步长  语法:range(start,stop,step)

    print(i) //输出的结果是1-9 左开右闭  

# if-else条件
x=1

y=2

z=3

if x>y:
    print("x大于y")

else:
    print("x小宇y")

# if elif else条件
x=1

y=2

z=3

if x>1:
    print("x大于1")

elif x<1:
    print("x<1")

else:
    print("x=1")

# def函数
#函数的定义

def function():

    print("fuck")

    a = 1+2

    print(a)

#函数的调用

function()

函数的参数
def func(a,v):
    c = a + v
    print("c",c)
    return a+v

func(a=1,v=2)

print(fun()) #打印 return的值 在这里打印出来的结果为 1+2=3，结果为3

# 函数默认参数
def sale_car(price,color="red",brand="carmy",is_second_hand=False):
    print("price:",price,
    "color:",color,
    "brand:",brand,
    "is_second_hand:",is_second_hand)

sale_car(10300,color="blue") 

#需要注意的一点是，如果默认参数没有值的话，则需要写在有值的前面，不然打印的时候会报错

# 全局变量和局部变量
X = 12 #全局变量
a = None

def fun():
    global a #全局变量
    c = 20 #局部变量
    a = 10
    return 100 + a

print(“before a:”,a)

fun()

print("after a:",a)

# 读写文件1(写)
text = "this is bullshit.\nthis is fucking bullshit" #\n 表示换行

my_file = open('my file.txt','w') # open 表示打开一个文件 其中‘w’表示可以写 ‘r’表示可以读

my_file.write(text)         # write 表示写入

my_file.close()             # 文件打开后要记得关闭，close 表示关闭

# 读写文件2（追加东西）
text = "this is bullshit.\nthis is fucking bullshit" #\n 表示换行

text1 = "\nso fuck idot"

my_file = open('my file.txt','a') # 'a' 表示追加

my_file.write(text1)

my_file.close()

# 读写文件3（读）
file = open('my file.txt','r')

content = file.readlines() 
#使用readline的话 只会读出第一行，如果使用readlines 则会输出全部，并会存储在python list中

#['this is bullshit.\n', 'this is fucking bullshit\n', 'so fuck idot']

#当然，我们可以不加lines，也可以直接写成 content = file.read() 也是可以的  read 表示读文件中的内容

print(content)

# class类
class Calculator: # Calculator 表示类的名字

    name = "fuck" # name,price表示类的属性
    price = 20

    #下面的这些表示它的功能
    def add(self,x,y):
        result = x + y
        print(result)
    def minus(self,x,y):
        result = x -y 
        print(result)

cal = Calculator()

print(cal.name)

cal.add(20,10)

cal.minus(40,20)

# 类init功能
class Calculator: # Calculator 表示类的名字

    #name = "fuck" # name,price表示类的属性
    #price = 20
    #类自己的功能
    def __init__(self,name,price,hight=20,width=30):
        self.name = name
        self.price = price
        self.h = hight   #名字可以不于上面一致，但是=后边的得一致
        self.width = width
        self.add(2,9)
        
    #下面的这些表示它的功能
    def add(self,x,y):
        result = x + y
        print(result)
    def minus(self,x,y):
        result = x -y 
        print(result)

cal = Calculator("ck",200)

print(cal.name)

print(cal.price)

print(cal.h)

print(cal.width)

print(cal.add)

cal.add(20,10)

cal.minus(40,20)

# input输入
a_input = input("give me that:")
print("what:",a_input)

if a_input == "fuck":
    print("\ngood")

elif a_input == "shit":
    print("\nallright")

else:
    print("\ngo fuck youself")

# 元组and列表
a_tuple = (1,2,3,4) #元组
another_tuple = 1,2,3,4 #元组的另一种形式

a_list = [1,5,9,11,80] #列表

 for index in a_list: #遍历列表
    print(index)

for index in a_tuple: #遍历元组
   print(index)

for index in range(len(a_list)): # range(len())表示计算长度（元素个数）

    print("index=:",index,"number in list=:",a_list[index])
    #a_list[index]表示列表中的对应下标的值，例如 a_list[0] 表示 a_list中的 1

# 列表list
a = [111,333,222,444,111,666]
print("原来的数据:",a)
a.append(555) #追加后的数据，放在末尾
print("追加后的数据:",a)

a.insert(2,555) #表示在第二位中，添加 555
print("追加后的数据:",a)

a.remove(111) #表示删除第一次出现的这个值
print("修改过的值:",a)

print(a[-1]) #打印最后一位的值 666

print(a[0:3]) #表示从第0位到第三位的值 [111, 222, 333] 左闭右开

print(a.index(222)) #表示出现 222 这个值的下标是多少

print(a.count(111)) # 表示 111 这个值出现了几次

a.sort() #排序，默认从小到大
a.sort(reverse=True) #表示从大到小排序
print("排序后的数据:",a)

# 多维列表
a = [[1,2,3],
    [2,3,4],
    [3,4,5]] #一共有三列
print(a[0][2]) #[0]表示第一列，[2]表示第一列中的第三个值 3

print(a[-1][-1]) # 表示最后一列，最后一个元素

# 字典 dictionary
d = {"apple":1, "pear":[1,2], "orange":3} 
d2 = {1:[1,2,33], 2:{1:2,"n":4}} #字典中的value 可以是字典或列表甚至函数

for key in d.keys(): # 遍历字典中的key
print(key)

for value in d.values(): # 遍历字典中的value
print(value)

for key,value in d.items(): # 遍历字典中的key和value
print(key,value)

print(d2)

print("原始的字典:",d)
del d["apple"] #删除字典中的key
d["xigua"] = 4 # 在字典中添加key
print("操作后的字典:",d)

print(d["pear"][0]) # 可以访问到对应key中的第几个value

# import载入模块
import time as t # as表示把time重命名为t

from time import time,localtime #表示在使用localtime和time时，无需在前面输入 time.localtime 而是可以直接time

from time import * # 表示time中的所有的功能都可以使用

print(localtime())

print(time())

# 自己的模块？
与C++中的在外部写一个头文件，然后在源文件中调用是一样的，不过要注意的是，这个文件一定要与源文件处于同一个目录下

import txt 

txt.fun("世界")

# continue & break
a = True
while a:
    b = input("请输出些什么:")

    if b == "1":
        a = False  # 使用 a 当作变量的话，如果条件成立 b == 1时，则会跳出循环，并打印 “我已经出来”
    else:
        pass
        print("我还在里面")
print("我已经出来")  

while True:
    b = input("请输出些什么:")

    if b == "1":
        break   #   跳出while循环
    else:
        print("我还在里面，你打不着")
        pass
print("我出来了，你打我啊")

while True:
    b = input("请输出些什么:")

    if b == "1":
        continue   #   不会跳出while循环，相反 continue 会一直重复进入while中
    else:
        print("我还在里面，你打不着")
        pass
print("我出来了，你打我啊")

# 错误处理try
try:        # 如果try语句中的except成立，则会执行except中的语句，否则会执行else的语句

    file = open("eee","r+")

except Exception as e:  # 这句表示 把报错信息存储到变量e中

    print("there is no file as eee")
    
    response = input("Do you want to creat a new file\n")

    if response == "y":
        file = open("eee","w")
    else:
        pass

else:  #这个为 try中的 else部分

    file.write("ccc")
file.close()

# zip，lambada，map三者
#zip
a = [1,2,3]

b = [4,5,6]

zip(a,b)        # 表示 第一个列表的第一个元素 与 第二个列表的第一个元素 组合到一起 [(1, 4), (2, 5), (3, 6)]

print(zip(a,b)) #直接打印zip的话，会出现这个 <zip object at 0x1055abbc0>

print(list(zip(a,b))) # 我们需要加上 list 才能看到我们的结果 [(1, 4), (2, 5), (3, 6)]

print(list(zip(a,a,b))) # 也可以zip多个元素

for i,j in zip(a,b):

    print("a:",i+1,"b:",j+4)
    
#lambada 类似于函数
def func1(a,b):

    return a + b

print("func1的结果:",func1(2,5))

func2 = lambda x,y:x+y

print("func2的结果:",func2(4,6))

#map

#result = map(func1,[3],[7] # 这个列表中的值[]可以是1个 也可以是多个 第一个列表中的第一个元素与第二个列表中的第一个元素匹配，同理后续也一样

result = map(func1,[2,3],[4,7]) # 多个元素

print(list(result)) # 输出同样需要用list 结果是 [6, 10]

# 浅复制copy和深复制deepcopy
import copy as c #玩了个小聪明 把copy重新命名为c 方便我的代码书写

a = [1,2,3]

b = a

print("before a:",a)

print("before b:",b)

b[0] = 6

print("after a:",a)

print("after b:",b)

print("id a:",id(a))  # id a: 4375907136

print("id b:",id(b))  # id b: 4375907136

print(id(a) == id(b)) #True 表示a与b的地址是一样的，所以当b的值发生改变，a的值也会发生改变

c = c.copy(a) # 说明c copy a 只是copy了他的地址，所以当c的值发生改变，而不会影响a的值

print("id c:",id(c)) #id c: 4380572416

print("before c:",c)

c[0] = 7

print("after c:",c) # after c: [7, 2, 3]

print("after a:",a) #after a: [1, 2, 3]

#浅copy，还会保留一部分相同的东西，例如在第二个列表中的所有东西都会被保留，地址和值，所以我改变第二个列表中的值，相对应的 d 中的第二个列表的值也会发生改变

d = [11,22,[44,777]]

e = c.copy(d)

print("before e:",e)

print("before d:",d)

print(id(d) == id(e)) #False

print(id(d[2]) == id(e[2])) #True

e[2][0] = 666

print("after e:",e) #after e: [11, 22, [666, 777]]

print("after d:",d) #after d: [11, 22, [666, 777]]

#深copy deepcopy 不会保留任何东西

f = [1,1,[22,55]]

g = c.deepcopy(f)

print(id(f[2]) == id(g[2])) #False

g[2][0] = 333

print("after f:",f) after f: [1, 1, [22, 55]]

print("after g:",g) # after g: [1, 1, [333, 55]]

# pickle 存放数据
import pickle 

#pickle用于实现对象序列化和反序列化。它可以将 Python 对象转换为字节流（序列化），也可以将字节流转换回 Python 对象（反序列化）

#序列化(Pickling) 将 Python 对象（如列表、字典、类实例等）转换为字节流（二进制格式）的过程。

#反序列化(Unpickling) 将字节流转换回 Python 对象的过程。

a_dict = {"aa":111, 2:[1,2,3,4],"ll":{1:2,"ni":9}}

file = open("pick_example.pickle",'wb') # 'wb'表示以二进制方式写入

pickle.dump(a_dict,file) # 对象序列化 把a_dict这个字典中的内容,搬到file文件中去

file.close()

with open("pick_example.pickle",'rb') as file: # 'rb' 表示以二进制方式读取

    a_dict1 = pickle.load(file) # 反序列化 表示加载file文件中的内容,并赋值给 a_dict1 

print(a_dict1)

# set 用于创建无序、不重复元素的集合
char_list = ['a','a','b','c','d','d']

list = [1,2]

#print(set([[char_list,list]])) # set 中无法传入列表加列表的形式，否则会报错 TypeError: unhashable type: 'list'

print(set(char_list))

unique_char = set(char_list)

unique_char.add('x') # 向set中添加元素 只能单独添加，不能添加列表

unique_char.clear() #清除所有 

delect = unique_char.remove('a') # 删除 set中的某个元素

print(unique_char)

print(delect) # 但是返回的结果是 None 而不是对应的值 如果想要重新看到值，则需要重新打印 unique_char

.pop() 随机删除并返回任意元素

.discard() 删除指定元素(不存在则不报错)

.add() 添加单个元素

.update() 添加多个元素

# 关键字大全
## 逻辑值
- True ***布尔真值***
- False ***布尔假值***
- None ***表示空值或无值***

## 逻辑运算 ***例如a=20，b=30***
- and ***与 a为False，则 a and b 返回a的值，否则返回b的值 ***
- or ***或 a为True，则 a or b 返回a的值，否则返回b的值 ***
- not ***非 a为True，返回False，a为False，返回True ***

## 位运算符 ***例如a=1100(二进制，但是变量不能以二进制输入) b=1011***
- & ***按位与运算符，全1则为1 a&b = 1000***
- ｜ ***按位或运算符，有1则为1 a|b = 1111***
- ^ ***按位异或运算符，有0有1则为1 a^b = 0111***
- ~ ***按位取反运算符，0变1，1变0 ～a = 0011 但是如果 a = 10,则～a = -11 计算公式:-(a+1)***
- << ***左移动运算符（相当于✖️2 例如 1<<3 返回8 表示乘以2的3次方），高位丢弃，低位补0 a<<2 = 0011***
- ">>" ***右移动运算符（相当于➗2 8>>3 返回1 表示除以2的3次方） a >> 2 = 0000*** 

## 成员运算符
- in ***如果在指定序列中找到该值，则为True，反之为False x 在 y 序列中 , 如果 x 在 y 序列中返回 True***
- not in ***如果在指定序列中找不到该值，则为True，反之为False***

## 身份运算符 （is 和 == 的区别: == 看"长得像不像"（比较的是具体的值），is 看"是不是同一个人"（比较的是内存中的地址））
- is  ***判断两个标识符是不是引用自一个对象  x is y, 类似 id(x) == id(y) , 如果引用的是同一个对象则返回 True，否则返回 False***
- not is ***是判断两个标识符是不是引用自不同对象***
- == ***比较二者的值是否相等，如果相等则返回True，反之返回False***

## 数学函数
- abs(x) ***返回数字的绝对值 例如 abs(-10) 返回10***
- celi(x) ***返回数字的上入整数 例如 math.celi(4.2) 返回5***
- exp(x) ***返回e的x次幂 例如 math.exp(1) 返回2.718281828459045***
- fabs(x) ***以浮点形式返回数字的绝对值 例如math.fabs(-10) 返回10.0***
- floor(x) ***返回数字的下舍整数 例如math.floor(4.9) 返回4***
- log(x) ***例如 math.log(math.e) 返回1.0 math.log(100,10) 返回2.0***
- log10(x) ***返回以10为基数的x的对数 例如 math.log10(100) 返回2.0***
- max(x1,x2) ***返回给定参数的最大值，参数可以为序列***
- min(x1,x2) ***返回给定参数的最小值，参数可以为序列***
- modf(x) ***返回x的整数部分与小数部分，两部分的数值符号与x相同，整数部分以浮点型表示***
- pow(x,y) ***x的y次幂的值 例如 pow(2,3) 返回8***
- sqrt(x) ***返回x的数字平方根***

## 随机数函数
- choice(seq) ***从序列的元素中随机挑选一个元素，比如random.choice(range(10))，从0到9中随机挑选一个整数***
- randrange(start,stop,step) ***从指定范围内，按指定基数递增的集合中获取一个随机数，基数为1 例如 random.randrange(1,100,2)***
- random() ***随机生成下一个实数，它在[0,1)范围内 例如 random.random()***
- seed[x] ***改变随机数生成器的种子seed***
- shuffle(lst) ***将序列的所有元素随机排序***
- uniform(x,y) ***随机生成下一个实数，它在[x,y]范围内***

## 三角函数
- acos(x) ***返回x的反余弦弧度值 math.acos(x)***
- asin(x) ***返回x的反正弦弧度值 math.asin(x)***
- atan(x) ***返回x的反正切弧度值 math.atan(x)***
- atan2(y,x) ***返回给定的X及Y坐标值的正反切直 math.atan2(y,x)***
- cos(x) ***返回x的弧度的余弦值 math.cos(x)***
- sin(x) ***返回x的弧度的正弦值 math.sin(x)***
- tan(x) ***返回x的弧度的正切值 math.tan(x)***
- hypot(x,y) ***返回欧几里德范数 sqrt(x * x + y * y) math.hypot(x,y)***
- degrees(x) ***将弧度转换为角度，如degrees(math.pi/2),返回90度  math.degrees(x)***
- radians(x) ***将角度转换为弧度 math.radians(x)***

## 数学常量
- pi ***数学常量pi(圆周率)***
- e ***数学常数e，e即自然常数(自然常数)***

## python的字符串内建函数
- capitalize() ***将字符串的第一个字符转换为大写，其余都变成小写 例如:a = "hello"  a_ = a.capitalize() 返回 “ Hello ”***
- center(width,fillchar) ***返回一个指定的宽度 width 居中的字符串，fillchar 为填充的字符，默认为空格 例如: a = "Hello" a_ = a.center(10,"-") 返回是 --Hello--- ***
- len(string) ***返回字符串长度 例如: a = "Hello" a_ = len(a) 返回 5***
- count(str,start=0,end=len(string)) ***返回 str 在 string 里面出现的次数，如果给start和end赋值，则在她们范围内寻找，str出现的次数 例如: a = "Hello" a_ = a.count("l",0(start 可以设置),len(a) end 也可以设置) 返回 2 因为"l"在a中出现两次*** 
- str.startswith(prefix[, start[, end]]) ***检查字符串是否以str开头，如果如果给start和end赋值，则在她们范围内寻找,如果是，则返回True，否则返回False***
- str.endswith(str,suffix[, start[, end]]) ***检查字符串是否以str结尾,如果给start和end赋值，则在她们范围内寻找,如果是，则返回True，否则返回False 例如: a = "Hello world" a_ = a.endswith("world") 返回True***
- find(str,start=0,end=len(string)) ***检查str是否包含在字符串中，如果给start和end赋值，则在她们范围内寻找，如果找到，则返回对应的索引，否则返回 -1 例如: a = "Hello" a_ = a.find("e") 返回 "e"的索引 为 1***
- index(str,start=0,end=len(string)) ***与find()方法一样，只不过如果str不在字符串中，会报一个异常 例如: a = "Hello" a_ = a.index(b) 返回 ValueError: substring not found *** 
- rindex() ***从字符串的最右边开始查找,直到返回最后一个匹配项的索引***
- lindex() ***从字符串的最左边开始查找,直到返回最后一个匹配项的索引***
- lower() ***转换字符串中所有大写字符为小写 例如: a = "HELLO" a_ = a.lower() 返回 hello***
- upper() ***转换字符串中所有小写字符为大写 例如: a = "hello" a_ = a.upper() 返回 Hello***
- str.strip() ***用于去除字符串开头和结尾的所有空白字符 例如: a = "  Hello  " a_ = a.strip() 返回 Hello ***
- lstrip() ***用于截掉字符串左边的空格或指定字符 例如: a = "---777Hello" a_ = a.lstrip("-,7") 返回 Hello***
- rstrip() ***用于截掉字符串末尾的空格或指定字符 例如: a = "Hello---44" a_ = a.rstrip("-,4) 返回 Hello lstrip和rstrip二者可以结合起来 例如: a = "---Hello___" a_ = a.lstrip("-").rstrip("_") 返回 Hello***
- str.replace(old,new,times) ***把字符串中的old替换成new，如果指定times，则不超过times次 例如: a = "Hello" a_ = a.replace("Hello","hello") 返回 hello***
- max(str) ***返回字符串中最大的字母 例如: a = "Hello" a_ = max(a) 返回 o ***
- min(str) ***返回字符串中最小的字母 例如: a = "Hello" a_ = min(a) 返回 H ***
- str.split() ***将字符串分割成单词列表（默认按空格分割）,并返回一个列表***

## 字符串的大小写转换 zz = "www.cc123.com"
- str.lower() ***把所有字符中的大写字母转换成小写字母 zz.lower() 返回 www.cc123.com***
- str.upper() ***把所有字符中的小写字母转换成大写字母 zz.upper() 返回 WWW.CC123.COM***
- str.title() ***把每个单词的第一个字母转化为大写，其余小写 zz.title() 返回 Www.Cc123.Com***
- str.capitalize() ***把第一个字母转化为大写字母，其余小写 zz.capitalize() 返回 Www.cc123.com***
- str.join()  ***用于连接字符串，字符串join的用法(只能用于字符串)：“分隔符”.join(可迭代对象) 例如: a = ["a","b","c"] a_ = " ".join(a) 返回a b c 或者 a_ = "-".join(a) 返回 a-b-c***

## 字符串的判断(字母，数字，符号)
- isalpha() ***判断字符串中的字符是否都是字母***
- isdigit() ***判断字符串中的字符是否都是数字***
- isalnum() ***判断字符串中的字符是否是字母和数字***
- islower()/isupper() ***判断字符串中的字符是否是小写/大写***
- isspace() ***判断字符串中的字符是否包含空白字符***

## 列表
- 列表也支持使用切片的方法去删除和追加元素噢，同时也能嵌套列表 ***例如: list = ["111","222","333"] list[1:]  返回 222,333 a = ["1","2"] b = ["3","4"] c = a+b 返回["1","2","3","4"]***
- 列表也能比较，只是列表比较需要引入 operator 模块的 eq 方法 ***例如: import operator(导入库) a = [1,2] b = [3,4] print(operator.eq(a,b)) 返回False***

## 列表函数
- len(list) ***查看列表中的元素个数***
- max(list) ***返回列表中最大值 如果是字符串，则对比字母大小，如果是int类型，则对比数字大小***
- min(list) ***返回列表中最小值 同理***
- list(seq) ***将元组转换为列表 例如: a = (1,2,3) a_ = list(a) 返回 [1,2,3]***
- sum(list) ***返回列表中的和***
- list(dict.values()) ***把字典中的values变成列表，即可计算字典中的values的平均值mean，最大最小值max/min***

## 列表方法
- list.append(obj) ***用于追加列表中的元素，通常追加后的元素会放在列表的末尾 例如: list = ["1","2"] list.append("3") 则最新的 list = ["1","2","3"] 注意，使用append不会生成新的列表***
- list.count(obj) ***统计某个元素在列表中出现的次数***
- list.extend(seq) ***用于在列表末尾一次性追加另一个序列中的多个值 seq可以是列表，元组，字典，集合等等 与 list.append 不同的是，list.append 追加整个对象为一个元素，而list.extend 是把可迭代对象中的元素逐个加进去 注意，使用extend不会生成新的列表***
- list.index(obj) ***从列表中找出某个值，第一个匹配项的索引位置 例如: a = [1,1,2,3] a.index(1) 返回0 ***
- list.insert(index,obj) ***将对象插入列表，可以指定位置插入 例如: a = [1,2,4,6] a.insert(2,3) 返回[1,2,3,4,6]***
- list.pop(index=-1) ***删除指定索引的列表项，(默认删除最后一个元素)，并返回该元素的值 例如: a = [1,2,3,4] a.pop() 返回 4***
- del list[ ] ***用于删除列表中的元素，只能通过索引的值来删除元素，不能指定删除元素，如果想要指定删除某个元素，可以使用 list.remove(obj)的方法，或者 del list[list.index(obj)] 通过索引的方式来删除***
- list.remove(obj) ***删除指定值的列表项，如果重复出现值，则删除第一次出现的值 例如: a = [1,25,1,2,3,4] a.remove(1) 返回 [25,1,2,3,4]***
- list.reverse() ***反向列表中的元素 例如: a = [1,3,5,6,7] a.reverse() 返回 [7,6,5,3,1]***
- list.sort(key=None,reverse=False) ***对原列表进行排序，如果指定参数key，则使用比较函数指定的比较函数 reverse=False 默认升序 例如: a = [1,3,2,7,5,6] a.sort() 返回[1,2,3,5,6,7]***
- list.clear() ***清空列表 例如: a = [1,2,3] a.clear() 返回[] 类似 del a[:] 返回[] 二者是同样的效果***
- list.copy() ***复制列表,修改复制后的列表，不会影响原来的列表 例如: a = [1,2,3] a_ = a.copy() 返回 [1,2,3]***

## 元组
- 元组与字符串类似，下标索引从0开始，可以进行截取，组合等
- 但元组中的元素值是不允许修改的，但是可以对元组进行连接组合 例如: tup1 = (1,2,3) tup2 = ('a','b') tup3 = tup1 + tup2 返回 1,2,3,'a','b'
- 元组中的元素值是不允许删除的，但是可以使用del语句来删除整个元组 例如: tup1 = (1,2,3) del tup1 返回 NameError: name 'tup' is not defined

## 元组内置函数
- len(tuple) ***计算元组中的元素个数***
- max(tuple) ***返回元组中元素最大值 例如: a = (1,33,4,55) a_ = max(a) 返回 55***
- min(tuple) ***返回元组中元素最小值 例如: a = (1,33,4,55) a_ = min(a) 返回 1***
- tuple(iterable) ***将可迭代系列转换为元组(列表转元组) 例如: a = [1,2,3] a_ = tuple(a) 返回 (1,2,3)***

## 字典的内置函数
- len(dict) ***计算字典元素个数，即键的总数***
- srt(dict) ***输出字典，将字典 转换成字符串（str 类型）例如: a = {'name':'Alice','age':19,'city':'New York'} 返回 字典类型 str(a) 返回 字符串类型***
- type(variable) ***返回输入的变量类型，如果变量是字典就返回字典类型***

## 字典的方法（ new_dict = {v:k for k,v in d.items()} 用于键,值的调换）
- dict.clear() ***删除字典内所有元素 例如: a = {'a':1,'b':2} a.clear() 返回 {} ***
- dict.copy() ***返回一个字典的浅复制***
- dict.fromkeys(seq,value) ***创建一个新的字典，以seq作为键，value作为键的初始值，默认设置为None 例如: a = {'name','age'} a_ = dict.fromkeys(a,10) 返回 {'name':10,'age':10}***
- dict.get(key,value) ***返回指定键的值 如果键不在字典中返回默认值，如果不指定默认值，则返回 None 例如: a = {"name":lili,"age":20} a_ = a.get("name") 返回 lili 如果a_ = a.get("fuck") 返回 None***
- key in dict ***判断键是否在字典中，如果在则返回True，否则False 例如: a = {'name':lili,'age':20} a_ = 'name' in a 返回 True***
- dict.items() ***返回的内容是以元组形式的(key和value),也可以单独打印键和值 dict.keys表示键(列表形式) dict.values表示值(列表形式)***
- dict.update(dict2) ***把dict2的键和值，更新到dict中 例如: a = {'name':lili,'age':20} a_ = {'country':CN,'city':shanghai} a.update(a_) 返回 {'name':lili,'age':20,'country':CN,'city':shanghai} 或者也可以用 res = {**a,**a_} ***
- dict.pop(key,default) ***删除key对应的值，返回被删除的值。如果键不存在，则可以返回一个默认值 例如: a = {'name':lili,'age':20} a_ = a.pop('name') 返回 lili a_ = a.pop('city',None) 返回 None del dict(key.default)*** 
- dict.popitem() ***返回并删除字典中的最后一对键值***

## collection库中的Counter方法 假设：count = Counter(words) Counter是字典的子类哟，具有字典的所有功能，还增加了计数功能
- count.most_common() ***统计最常见的元素***
- count.total() ***总计数***
- count.elements() ***所有元素***
- count.subtract(other) ***减法操作***
- count.update(other) ***更新操作***

## 集合内置方法（a = {1,2,3,4},b = {3,4,5,6）
- set.add() ***为集合添加新的元素 a.add(5) 返回 {1,2,3,4,5}***
- set.clear() ***移除集合中的所有元素 a.clear() 返回{} ***
- set.copy() ***拷贝一个集合 a_ = a.copy() 返回 {1,2,3,4}***
- set.difference() ***返回集合的差集，即返回的集合元素包含在第一个集合中，但不包含在第二个集合(方法的参数)中 c = a.difference(b) 返回 {1,2}***
- set.difference_update() ***用于移除两个集合中都存在的元素,与difference不同，difference_update没有返回值 a.difference_update(b) print(a) 返回 {1,2}***
- set.discard() ***用于删除指定的集合元素，与remove()不同的是，remove()在移除一个不存在的元素时，会报错  a.discard(1) 返回 {2,3,4}***
- set.remove() ***移除指定元素 用法与discard()一样***
- set.pop() ***随机移除元素 a.pop() 具体返回什么我也不知道***
- set.len() ***计算集合中的元素个数 len(a) 返回 4***
- max(set) ***返回集合中最大的元素值 max(a) 返回 4***
- min(set) ***返回集合中最小的元素值 min(a) 返回 1***

## 条件控制
- if ***条件判断语句***
- elif ***否则如果(else if的缩写)***
- else ***否则分支***

## 循环控制
- for ***迭代循环***
- while ***条件循环***
- break ***跳出循环***
- continue ***跳出当前循环的剩余部分，进入下一次迭代***

## 异常处理 (import traceback用于打印错误类型的信息 用法: info=traceback.format_exc() print(info) )
- try ***尝试执行代码块***
- except ***捕获异常***
- finally ***无论是否发生异常都会执行的代码块***
- raise ***抛出异常***
- else ***没有异常时执行的代码***

## 函数定义
- def ***定义函数 如果函数里面没有定义其他的函数，则称为普通函数，如果函数中定义匿名函数 则叫做 高阶函数，此时调用函数时，需要注意传参***
- return ***从函数返回值***
- lambda ***创建匿名函数 如果在def 中创建匿名函数 lambda时，传入的参数一个是传给def函数，另一个是传给 lambda函数的    lambda函数通常与map(),filter(),reduce()这三个内置函数一起使用，map()会对可迭代对象中的每个元素应用一个函数，并返回结果，filter()会筛选出让函数返回 True 的元素,reduce()需要从 functools 导入，会把一个函数连续作用在序列上，将序列缩减成一个值 ***

## 类与对象
- class ***定义类 如果看到 __obj = "" 时，表示这是定义的私有属性，外部无法直接访问，如果想要访问这个私有属性，可以在类中 为了他写一个函数，然后外部就去访问这个函数即可 def get_obj(self): return self.__obj ***
- del ***删除对象饮用***
- 父类与子类 ***父类:被继承的类(也称基类，超类) 子类:继承父类的类(也称派生类)，子类会拥有父类的所有属性和方法(私有成员除外)，如果子类想要调用父类的私有成员，则，self._类名__属性，并且可以添加自己特有的属性和方法，或者重写父类的方法，super()调用父类方法的工具***

## 类的专有方法
- __init__ ***构造函数，在生成对象时调用***
- __del__ ***析构函数，释放对象时使用***
- __repr__ ***打印，转换***
- __setitem__ ***按照索引赋值***
- __getitem__ ***按照索引获取值***
- __len__ ***获取长度***
- __cmp__ ***比较运算***
- __call__ ***函数调用***
- __add__ ***加运算***
- __sub__ ***减运算***
- __mul__ ***乘运算***
- __truediv__ ***除运算***
- __mod__ ***求余运算***
- __pow__ ***乘方***

## 模块导入
- import ***导入模块***
- from ***从模块中导入特定部分***
- as ***为导入的模块或对象重命名***

## 作用域
- global ***声明全局变量 必须在第一次使用变量之前声明，不能在读取之后再声明该变量是全局变量，不然就会报错 SyntaxError: name 'x' is used prior to global declaration(语法错误：在全局声明之前使用了名称“x”)***
- nonlocal ***可以让内层函数修改外层函数的变量 不能声明已经声明为全局变量的变量(用于嵌套函数)***

## 异步编程
- async ***声明异步函数***
- await ***等待异步操作完成***

## 其他
- assert ***断言，用于测试条件是否为真***
- in ***检查成员关系***
- is ***检查对象身份(是否是同一个对象)***
- pass ***空语句，用于占位***
- with ***上下文管理器，用于资源管理***
- yield ***从生成器函数返回值***
- end ***将结果输出到同一行，或者在输出的末尾添加不同的字符 例如: print(a,end=",")***
-  “*”  ***用于解包序列(list，tuple)等***
- “**  ***用于解包字典(键值对)***
- round ***用于对数字做四舍五入，语法:round(number,ndigits) number:要处理的数字 ndigits:保留的小数位数 例如:a = 3.14556 a_ = round(a,2) 表示保留两位小数 返回 3.15***
- ord(str) ***表示根据字符找序号，例如ord("h") 返回的是104***
- chr(数字) ***表示根据序号找字符,例如chr(104) 返回的是字符串h***
- locals() ***列出所有本地变量***
- str.isidentifier() ***判断字符串str是否符合标准，即不以数字做为开头***
- _ ***表示上次表达式的值***
- sorted() ***排序时迭代***
- map() ***对指定序列中的每一个元素应用一个给定的函数 语法:map(funtion，iterable) iterable:一个或多个可迭代对象***
- reduce() ***对序列中的元素按照一定的规则进行累积计算 语法:reduce(function,iterable,initializer) iterable:一个或多个可迭代对象 initializer:可选参数，作为累积计算的初始值***
- filter() ***从可迭代对象(如列表，元组，字符串)中筛出满足特定条件的元素，并返回一个迭代器，包含所有”判断为True“的元素 语法:filter(function,interable)***
- any() ***与 或运算一样，有真则为真，全假则为假***
- all() ***与 与运算一样，全真则为真，有假则为假***
- enumerate(iterable,start=0) ***在遍历一个可迭代对象时，同时获取到元素的索引和元素本身***

# os库中常用的函数
## 文件和目录相关
- os.listdir(path) ***返回指定目录下所有文件和文件夹名字(列表形式)***
- os.mkdir(path) ***创建一个新目录(如果目录存在则报错)***
- os.makedirs(path,exist_ok=False) ***递推创建目录(可以一次创建多级目录)，exist_ok=True表示如果目录存在，则不报错***
- os.rmdir(path) ***删除空目录***
- os.removedirs(path) ***递归删除多级空目录(上级也会删除，直到出现非空目录)***
- os.remove(path) ***删除文件***
- os.rename(old,new) ***重命名文件或者移动文件***
- os.stat(path) ***获取文件或目录的详细信息(大小，创建时间，修改时间等)***

## 路径操作
- os.path.join(path1,path2...) ***拼接路径，自动加斜杠 os.path.join(filename,file)***
- os.path.exists(path) ***判断路径是否存在(文件或目录都可以)***
- os.path.isfile(path) ***判断路径是否是文件***
- os.path.isdir(path) ***判断路径是否是目录***
- os.path.abspath(path) ***返回绝对路径***
- os.path.basename(path) ***返回路径中的文件名***
- os.path.dirname(path) ***返回路径中的目录部分***
- os.path.split(path) ***返回(目录，文件名)的元组***
- os.path.splitext(path) ***分割文件名和拓展名，返回(文件名，后缀)***
- os.path.getsize(path) ***返回指定文件的大小(字节数)***
- os.path.getctime(path) ***返回指定文件的创建时间(在windows),而在macOS和linux则返回的是文件最近修改的时间***
- os.path.getmtime(path) ***返回文件最后修改的时间***

## 当前工作目录和环境
- os.getcwd() ***获取当前工作目录***
- os.chdir(path) ***切换当前工作目录***
- os.environ() ***获取系统环境变量***
- os.putenv(key,value) ***设置环境变量(临时有效)***

## 其他常用
- os.system(command) ***只执行系统命令(比如 ls,dir,echo 等)***
- os.walk(path) ***遍历目录及其子目录，返回一个生成器，通常用于批量处理文件 使用 for root,files.dirs in os.walk(path):***
- os.path.getsize(path) ***获取文件大小（字节为单位)***
- os.path.getmtime(path) ***获取文件修改时间（时间戳)***

# json库中常用的函数
## 序列化(将python对象转换为json格式)
- json.dumps(obj) ***将python对象(如字典，列表)转换为json格式的字符串***
- json.dump(obj,fp) ***将python对象(如字典，列表)转换为json格式，并写入fp(写入文件)***

## 反序列化(将json格式转换为python对象)
- json.loads(s) ***将json格式的字符串(s)解析为python对象(如字典，列表)***
- json.load(fp) ***从文件对象fp中读取json格式的数据，并将其解析为python对象(读取文件)***










