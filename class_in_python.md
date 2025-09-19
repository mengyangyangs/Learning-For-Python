# 这里是用作python中的class的学习，从很多个方面去学习，例如继承，组合，重写等等

## 入门基础：理解如何定义类、如何使用 __init__ 构造函数设置初始属性
<!-- class Student():
    def __init__(self,name,age):
        self.name = name 
        self.age = age

    def introduce(self):
        return f"名字是{self.name},年龄是{self.age}"

st = Student("张三",20)
print(st.introduce()) -->

## 核心应用：理解方法如何操作和改变对象内部的属性（即对象的状态)
<!-- class BankAccount():
    def __init__(self,account_holder,initial_balance):
        self.account_holder = account_holder
        self.initial_balance = initial_balance

    def deposit(self,amount):
        self.initial_balance += amount
        return f"存款成功，当前余额为{self.initial_balance}"
    
    def withdraw(self,amount):
        if amount > self.initial_balance:
            return f"余额不足，当前余额为{self.initial_balance}"
        else:   
            self.initial_balance -= amount
            return f"取款成功，当前余额为{self.initial_balance}"

my_account = BankAccount("张三",1000)
print(my_account.deposit(500))
print(my_account.withdraw(200))
print(my_account.withdraw(1200)) -->

## 进阶概念：学习类属性与实例属性的区别，并让不同对象进行简单的互动
<!-- class Animal():
    total_animal = 0
    def __init__(self,name):
        self.name = name
        Animal.total_animal += 1

dog = Animal("狗")
cat = Animal("猫")
print(Animal.total_animal) -->

## 继承与重写：学习如何定义子类 (Child Class) 继承父类 (Parent Class) 的属性和方法，以及如何使用 super()
<!-- class Person():
    def __init__(self,name,age):
        self.name = name
        self.age = age

    def introduce(self):
        return f"名字是{self.name},年龄是{self.age}"

class Employee(Person):
    def __init__(self,name,age,employee_id):
        super().__init__(name,age)
        self.employee_id = employee_id
    
    def get_details(self): # 重写的过程，调用了父类的introduce()方法
        lala = super().introduce()
        return f"{lala},员工编号是{self.employee_id}"

emp1 = Employee("张三",20,1001)
print(emp1.get_details()) -->

## 综合应用：学习组合 (Composition) 模式（一个类包含另一个类的对象），以及实现简单的封装概念
<!-- class CPU():
    def __init__(self,model,core_count):
        self.model = model
        self.core_count = core_count

    def display_info(self):
        return f"CPU型号是{self.model},核心数是{self.core_count}"

class Computer():
    def __init__(self,brand,CPU):
        self.brand = brand
        self.CPU = CPU
    
    def run_benchmark(self):
        return f"品牌是{self.brand},{self.CPU.display_info()}"

my_cpu = CPU("Intel i7",8)
my_computer = Computer("戴尔",my_cpu)
print(my_computer.run_benchmark()) -->

## 简单封装(私有属性约定)
<!-- class Wallet():
    def __init__(self,balance):
        self.__balance = balance # 私有属性的封装 __

    def get_balance(self):
        return self.__balance

    def set_balance(self,amount):
        self.__balance += amount
        return f"余额更新为{self.__balance}"
    
    def spend(self,amount):
        self.__balance -= amount
        return f"余额更新为{self.__balance}"

my_wallet = Wallet(100)
print(my_wallet.get_balance())
print(my_wallet.set_balance(200))
print(my_wallet.spend(50)) -->

## 多态：理解多态的实现机制——不同的对象对同一个方法调用能做出不同的响应，这在设计插件式系统时非常有用
<!-- class Vehicle():
    def move(self):
        return "交通工具正在移动"

class Car(Vehicle):
    def move(self):
        return "汽车正在移动"

class Bike(Vehicle):
    def move(self):
        return "自行车正在移动"

ls = [Car(),Bike()]
for i in ls:
    print(i.move()) -->

## 特殊方法：学习如何通过特殊方法（以双下划线开头和结尾的方法，如 __str__）来自定义类的行为，使其更像 Python 内置类型
<!-- class Book():
    def __init__(self,title,author,page_count):
        self.title = title
        self.author = author
        self.page_count = page_count

    def __lt__(self,other):
        if self.page_count < other.page_count:
            return True

    def __gt__(self,other):
        if self.page_count > other.page_count:
            return True

    def __str__(self): 
        return f"书名是{self.title},作者是{self.author}"

book1 = Book("红楼梦","曹雪芹",100)
book2 = Book("西游记","吴承恩",200)
print(book1 < book2) 
print(book1) -->
<!-- ps：会自动匹配方法
操作符 / 函数	                调用的特殊方法	                含义
print(obj) 或 str(obj)	       obj.__str__()	        转换为用户友好的字符串
obj1 < obj2	                   obj1.__lt__(obj2)	         小于比较
obj1 + obj2	                   obj1.__add__(obj2)	         加法操作
len(obj)	                   obj.__len__()	           获取对象的长度 -->

## 单例模式：学习如何保证一个类在整个程序运行期间只创建一个对象（即单例）。这常用于配置管理、日志记录器等只需要一个全局实例的场景
<!-- class Logger():
    # 类属性，用于存储唯一的实例
    _instance = None
    # 标志位，用于防止多次初始化
    _initialized = False
    def __new__(cls):
        # 如果实例不存在，则创建实例
        if cls._instance is None:
            # 调用父类的__new__方法创建实例
            cls._instance = super().__new__(cls)
        # 返回实例
        return cls._instance
    
    def __init__(self):
        # 保护机制：确保初始化代码只运行一次
        if not self._initialized:
            # 设置标志位，防止重复初始化
            self._initialized = True
            print("Logger initialized")
        else:
            print("Logger already initialized")

logger1 = Logger()
logger2 = Logger()
# 验证两个变量指向同一个对象 (内存地址相同)
print(id(logger1))
print(id(logger2))
print(logger1 is logger2) -->
            
## 常用数据结构类：创建一个标准的数据对象，确保它能被清晰地打印和调试
<!-- class Color():
    def __init__(self,red,green,blue):
        self.red = red
        self.green = green
        self.blue = blue
    
    def __str__(self): # 返回人类可读的字符串
        return f"RGB: ({self.red},{self.green},{self.blue})"

    def __repr__(self): # 返回机器可读/调试的字符串
        return f"Color(red={self.red},green={self.green},blue={self.blue})"

color = Color(255,0,0)
print(color)
print(repr(color)) -->

## 属性的计算与动态获取：学习使用 @property 装饰器，将方法伪装成属性来使用，常用于计算属性或对属性进行保护
<!-- class Rectangle():
    def __init__(self,width,height):
        self.width = width
        self.height = height
    
    @property
    def area(self):
        return self.width * self.height -->
<!-- 
    <!-- @property
    def width(self):
        return self._width # 加上 _ 是为了避免无限递归，同时实现了封装和数据验证，如果不加 _ 的话，则会导致在调用width时，会无限递归

    @width.setter # setter依赖于property对象 可以创建一个属性，并设置一个setter方法，当属性被赋值时，会调用setter方法
    def width(self,value):
        if value > 0:
            self._width = value 
        else:
            raise ValueError("宽度必须是正数")
    
r1 = Rectangle(10,20)
print(r1.area)
r1.width = 20
print(r1.area) --> -->
