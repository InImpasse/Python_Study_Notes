##  分支和循环

### 小游戏

- 加载音乐

- 播放音乐（但不循环）

- 诞生飞机

  定义变量

while True:

-  if  用户点击关闭按钮

​        退出程序

- 小飞机诞生

- 小飞机移动

- 屏幕刷新

- if 用户鼠标产生移动

  我放飞机中心位置=用户鼠标位置

  屏幕刷新

- if 我方飞机与小飞机撞击

  我方over，播放撞机音乐

  修改我方飞机图案

  打印结束语

  停止背景音乐，最好淡出

#### python三元操作符

```python
small = x if x < y else y #如果x < y，x最小，否则y最小
```

#### 断言assert

```python
assert 3 > 4 #如果关键字后面的条件为假时，程序会自动崩溃，抛出AsserrtionError，为真则自动pass了
```

#### while循环（循环体）

#### for循环

```python
for 目标 in 表达式
循环体
```

#### range()

```python
range(5)  #运行结果：range(0,5)
list(range(5))  #运行结果,[0,1,2,3,4]
for i in range(5)
	print(i)  #运行结果0 1 2 3 4 不同行
for i in range(2,9)
	print(i)  #运行结果2-8 不同行
for i in range(1,10,2)
	print(i)  #运行结果1-9 不同行 每个隔2
```

#### continue语句  

#终止本轮循环，开始下一轮循环

当条件为真时，continue不执行下一条语句，条件为假，continue执行下一条语句



## 列表

### 列表基础操作

#### 添加元素

```python
#添加元素
列表名.append('1')  #向列表添加1个元素，加在最后
列表名.extend(['1','2'])  #向列表添加2个元素，加在最后
列表名.insert(位置0开始,'1') #从某一位置插入1个元素
```

#### 删除元素

```python
#删除元素
列表名.remove('元素内容')  #删除列表内某元素
del 列表名[0] #删除列表内第0个元素
del 列表名 #删除整个列表
列表名.pop() #有点类似于出栈，删除最后一个
列表名.pop(0) #删除第0个元素
```

#### 列表分片

```python
#列表分片Slice
列表名[1:3] #只显示出1和2两个元素
```

#### 列表计数

```python
#列表计数
列表名.count(元素) #会显示这个元素在列表中出现次数
```

#### 返回参数在列表中的位置

```python
#返回参数在列表中的位置
列表名.index(元素) #显示这个元素在列表中的位置，显示最先出现的那个一个
列表名.index(元素,3,7) #显示这个元素在列表3-7范围中的位置
```

#### 列表翻转

```python
#列表翻转
列表名.reverse() #最后面的移到最前面，翻转列表
```

#### 列表排序

```python
#列表排序
列表名.sort() #列表从小到大排序
列表名.sort(func,key,reverse = False) #把reverse改成True就是从大到小排序
```

#### 列表长度

```python
#列表长度
len(列表名) #链表长度
```

### 复制列表的两种方式的区别

```python
#复制列表的两种方式的区别
list0 = [0,1,2,3,4,5,6]
list1 = list0[ : ] #方式1
list2 = list0 #方式2，如此赋值只是相当于添加了一个新的标签
#注！此时，若执行list0.sort(reverse = True)，对list0进行倒排序
list0 = [6,5,4,3,2,1,0]
list1 = [0,1,2,3,4,5,6] #相当于复制了list0到新的列表里
list2 = [6,5,4,3,2,1,0] #随着list0改变而改变
```

### 元组

TUPLE 戴上了枷锁的列表

元组的复制，查找和列表一样，但是元组的元素是不能被修改的

#### 创建和访问元组

```python
tuple1 = (1,2,3,4,5,6,7,8)  #定义元组
type() #查看变量数据类型
temp = 1,
temp = ()
temp = (1,) #定义出来的数据类型都是元组
```

```python
8 * (8) #结果是64
8 *(8,) #结果是(8,8,8,8,8,8,8,8)
```

#### 更新和删除元组

```python
temp = ('0','1','2','3','4','5')
temp = temp[:2] + ('add') + temp[2:] #将add插入到temp[2]
```

不能用del temp删除temp

## 字符串 

![Char_Method1](https://github.com/InImpasse/Python_Study_Notes/blob/main/Note_Picture/Char_Method1.png)

![Char_Method2](https://github.com/InImpasse/Python_Study_Notes/blob/main/Note_Picture/Char_Method2.png)

```python
str1 = 'woshishuaibi'
str2 = str1.capitalize() #Woshishuaibi首字母大写
str2.casefold() #woshishuaibi所有小写
```

### 格式化

```python
"{0}love{1}.{2}".format("I","FishC","com")
"{a}love{b}.{c}".format(a = "I",b = "FishC",c = "com") #两个的结果一样
'{0:.1f}{1}'.format(27.658,'GB') #'27.7GB',f格式化符号自动四舍五入
```

#### 字符串格式化符号含义

```python
'%c' % 97 #'a', %c格式化字符及ASCII码
'%c %c %c' % (97,98,99) #'a b c' #元组
'%s' % 'Jiang Jiang' #'Jiang Jiang'，%s格式化字符串
'%d + %d = %d' % (4,5,4+5) #'4 + 5 = 9'，%d格式化整数
%o #%o格式化八进制
%x #%x格式化十六进制
%X #%X格式化十六进制
'%f' % 27.658 #'27.658000'，%f格式化定点数，可指定小数点后的精度
'%e' % 27.658 #'2.7658000e+01'，%e用科学计数法格式化定点数
'%E' % 27.658 #'2.7658000E+01'，%E用科学计数法格式化定点数
'%g' % 27.658 #'27.658,'%g根据值的大小决定使用%f或%e
'%G' % 27.658 #'27.658,'%G根据值的大小决定使用%F或%E
```

#### 格式化操作符辅助指令

```python
m.n #m表示占多少位，n表示小数点后的位数
'%5.1f' % 27.658 #' 27.7'，占用5个位，小数点后1位
'%.2e' % 27.658 #'2.77e+01'
'%10d' % 5 #'          5'
- #左对齐
+ #在正数前面加+
#o #在八进制前加0
#X #在十六进制前加0x
```

### 转义字符

```
\n #换行
\t #横向制表符tab
\v #纵向制表符
\\ #\
\0 #空格
```

## 序列

#### list()

```python
a = list() #a = []
b = 'I love Jiang'
b = list(b) #b = ['I',' ','l','o','v','e',' ','J','i','a','n','g']
c = (1,1,2,3,5,8,13,21,34) #元组，斐波那契数列
c = list(c) #c = [1,1,2,3,5,8,13,21,34] 
```

#### tuple()

使用方法与list相同

```
help(tuple) #查看使用方法
```

#### str(obj)

把obj对象转换为字符串

#### len()

返回参数的长度

#### max()

返回序列或者参数集合中的最大值（按照ASCII码）、

chars字符串中也是按照单个数字

#### min()

返回序列或者参数集合中的最小值（按照ASCII码）

#### sum()

可以把元组/数组的内容相加（必须都是int型）

#### sorted()

返回一个排序的列表（默认从小到大，使用类似list.sort）

#### reversed()

```python
list(reversed(列表)) #从大到小排序
```

#### enumerate()

```python
numbers =  [5,4,23,325,53,354,3]
list(enumerate(numbers)) # [(0,5),(1,4),(2,23),(3,325),(4,53),(5,354),(6,3)]  每个元素变成了一个元组，并新增了一个索引值
```

#### zip()

```python
a = [1,2,3,4,5,6,7,8]
b = [4,5,6,7,8]
list(zip(a,b)) #[(1,4),(2,5),(3,6),(4,7),(5,8)]
```

## 函数

函数、对象、模块

### 函数基础操作

#### 创建函数

```python
def MyFirstFunction():
	print('This is my first function!')
	print('It is so cool!')
```

#### 执行函数

```python
NyFirstFunction()
```

### 参数

#### 函数的参数

```python
def MySecondFuction(name):
	print(name + 'I love you') #name就是参数
```

```python
def add(num1,num2):
	result = num1 + num2
	print(result)
```

```python
def add(num1,num2):
	return(num1 + num2) #用返回值传参

print(add(num1,num2))
```

#### 形参和实参

```python
def MyFirstFuction(name): #此处name是形参，Ta只是一个形式，表示占据一个参数位置
    print('传递进来的' + name + '叫做实参，因为Ta是具体的参数值')
MyFirstFuction('江江') #江江是实参，因为Ta是具体的参数值
```

#### 关键字参数

```python
def SaySome(name,words):
	print(name + '->' + word)

Saysome('江江','帅！') # 江江->帅！
Saysome(words='江江',name='帅！') #帅！->江江
```

#### 默认参数

定义了默认值的参数

```python
def Saysome(name = '江江',words = '帅！'):
	print(name + '->' + words)
    
Saysome() # 江江 -> 帅！
Saysome('小江') # 小江 -> 帅！
Saysome('小江','好帅！') # 小江 -> 好帅！
```

#### 收集参数（可变参数）

```python
#单个参数
def vary(*text):
    print('参数的长度：',len(text))
    print('第一个参数：',text[0])
    
vary(1,2,3,4,5,6) # 参数的长度：6 第一个参数：1
```

```python
#多个参数
def vary(*text , exp = 8):
    print('参数的长度：',len(text), exp)
    print('第一个参数：',text[0])
    
vary(1,2,3,4,5,6) # 参数的长度：6 8 第一个参数：1
```

### 函数与过程

```python
del hello():
	print('Hello World')
    
temp = hello()
#执行temp，没有返回值，因为hello()没有return
#执行print(temp)，返回None
#执行type(temp)，<class 'NoneType'>
```

```python
del back():
	return[1,'666',3.14]

back()
#[1,'666',3.14]

```

```python
del back():
	return 1,'666',3.14

back()
#(1,'666',3.14),默认返回一个元组
```

### 函数变量的作用域

 变量的可见性

局部变量（Local Variable），全部变量（Global Variable）

```python
global 变量
变量定义  # 把局部变量变成全局变量
```

### 内嵌函数

```python
def fun1():
	print('fun1()正在被调用...')
	def fun2():
		print('fun2()正在被调用...')
	fun2() # fun2只能在fun1里面被调用
```

### 闭包（closure）

如果在一个内部函数里，对一个外部作用域（但不是在全局作用域的变量进行引用），那么内部函数就会被认为是闭包（closure）

```python
def FunX(x):
	def FunY(y):
		return x * y
	return FunY # 就说FunY是一个闭包

i = FunX(8)
#<function FunX.<locals>.FunY at 0x000001FBFE9163A0>
FunX(8)(5)
#40
#闭包也不能在外部函数进行调用
FunY(5) #会报错
```

变量x在局部调用x的时候如果会报错，x会被屏蔽

此时需要用nonlocal强制声明x不是局部变量（用法类似global）

```python
#报错实例
def Fun1():
    x = 5
    def Fun2():
        x *= x
        return x
    return Fun2()

Fun1()
# UnboundLocalError: local variable 'x' referenced before assignment
```

```python
#修改，用nonlocal强制声明
def Fun1():
    x = 5
    def Fun2():
        nonlocal x
        x *= x
        return x
    return Fun2()

Fun1()
#25
```

### 匿名函数

#### lambda表达式的作用

1. python写一些执行脚本的时候，lambda可以剩下定义函数的过程，是的代码更加精简
2. 对于比较抽象且执行只需要调用一两次的函数，不用单独给函数起名，用lambda替代即可
3. 简化代码可读性

```python
def ds(x)
	return 2 * x + 1

ds(5)
#11
```

```python
lambda x : 2 * x + 1 #只是返回一个没有名字的函数对象，不使用时，内存会自动清除这个函数
#<function <lambda> at 0x00000144A9A57310>
```

```python
lambda x , y : x + y
#<function <lambda> at 0x00000144A9A57430>

g = lambda x , y : x + y
g(3,4)
#7
```

### 内置函数（BIF）

#### filter()

过滤器

```python
list(filter(None, [1, 0, False, True])) #filter()输出为True或1的值
#[1, True]
```

##### 输出0-9范围内的奇数

```python
#输出0-9范围内的奇数1
def odd(x)
	return x % 2 #对2求余
temp = range(10) #范围0-9
show = filter(odd,temp) #输出余数为1的数（奇数）
list(show)
#[1,3,5,7,9]
```

```python
#输出0-9范围内的奇数2（lambda）
list(filter(lambda x : x % 2,range(10))
#[1,3,5,7,9]
```

#### map()

映射

```python
list(map(lambda x : x * 2,range(10))
#[0,2,4,6,8,10,12,14,16,18]
```

## 递归

### 什么是递归

函数调用自身的行为

```python
def recursion():
	return recursion() #调用会是一个死循环，python保护递归最大深度100层
```

### 设置递归深度

```python
import sys
sys.setrecursionlimit(层数)
```

### 递归的应用

#### 递归求阶乘

正整数阶乘从1 * 2 * 3 * 4 * ... * n

```python
#非递归版本
def factorial(n):
	result = n
	for i in range(1,n):
		result *= i
	return result

number = int(input('请输入一个正整数：'))、
result = factorial(number)
print('%d的阶乘是：%d'%(number,result))
```



