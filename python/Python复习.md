# Python复习 #
----------------------
## 模块 ##
1.海龟画图--turtle

2.时间模块 -- time 
	
	 time.time() 获得当前时刻，返回的值是以秒为单位
3.修改字符串模块--import io
	
	>>> import io
	>>> s = "hello, sxt"
	>>> sio = io.StringIO(s)
	>>> sio
	<_io.StringIO object at 0x02F462B0>
	>>> sio.getvalue()
	'hello, sxt'
	>>> sio.seek(7)
	7
	>>> sio.write("g")
	1
	>>> sio.getvalue()
	'hello, gxt'
## 语法 ##
1.打印

	print("a")
	print('a') 
	print('asfsde')
	a = 1;  print(a)

	不换行打印	sep间隔 end结尾
	print(a,b,sep="."end=' ')
2.控制台输入

	name = input("请输入姓名：")
2.Tab键缩进决定层次，避免空格与Tab混合使用

3.Python区分大小写

4.注释
	
	单行注释 #
	多行注释 ''' '''   """ """ 连续三个或三个以上的单引号或双引号

5.行连接符\
	
	b = "asdaf
         \ssdg"

6.Python一切皆对象

每个对象由：标识id()，类型type()，值 组成

7.Pass语句

	def sample(n_samples):
    pass
	该处的 pass 便是占据一个位置，因为如果定义一个空函数程序会报错，当你没有想好函数的内容是可以用 pass 填充，使程序可以正常运行。
## 数据类型 ##
## 字符串、列表、元组、字典、集合 ##
### 编程基础 ###

1.标识符命名规则

	1.模块，包名，函数名 ---- 全小写
	2.类名 --- 驼峰原则
	3.常量名 --- 全大写

2.变量使用前必须赋值

3.del删除回收不再使用的变量

	a = 1
	del a

4.赋值

	链式赋值      	a = b = 123
	系列解包赋值    a,b,c = 1,23,34
	变量交换 		a,b = b,a

5.基本数据类型和运算符
	
整形int 123546
	
	二进制 0b 0B      0b101
	八进制 0o 0O      0o37
	十六进制 0x 0X    0xFA
	★Python3 中，int 可以存储任意大小的整数，long 被取消

浮点型float 3.14  314e-2
 
	round(value) 返回四舍五入的值
布尔型	true , False

字符串型 'asd',"asd"

6.数字基本运算

	+加 -减 *乘 /浮点除法 
	注：+操作 	 3+2=5  
			 	"3"+"2"="32"字符拼接
			 	[10,20,30]+[5,100,12] = [10,20,30,5,100,12]
		*操作	3*2 ==> 6
				“sxt”*3 ==> ”sxtsxtsxt”
				[10,20,30]*3 ==> [10,20,30,10,20,30,10,20,30]
	//除法取整 
	%除法取余 
	**幂  2**3=8

7.增强型赋值运算符
	
	“+=”中间不能加空格！

8.比较运算符

	== != > < >= <=

9.逻辑运算符

	or and not

10.同一运算符
	
	is	比较对象地址是否相同  ==比较两个值是否相同		a is b
	is not 

11.移位运算符

	>>  << 

12.按位运算
	
	~翻转 |按位或 ^按位异或 &按位与

13.成员运算符
	
	in 
	not in 
	20 in (10,20,30) 返回true
### 字符串语法 ###
	
1.创建字符串
	
	用单引号或双引号创建
	例如：a=’abc’; b=”sxt”
	
	允许空字符串的存在，不包含任何字符且长度为 0
	
	转义字符 “\+特殊字符”
	\(在行尾时) 续行符
	\\ 反斜杠符号
	\' 单引号
	\b 退格(Backspace)
	\n 换行
	\t 横向制表符
	\r 回车

2.字符串的编码

	ord()可以把字符转换成对应的 Unicode 码
	>>> ord('A')
	65
	chr()可以把十进制数字转换成对应的字符
	>>> chr(66) 
	'B'

3.函数

	创建整数列表
	range([start,] end [,step])
	>>> list(range(3,15,2))
	[3, 5, 7, 9, 11, 13]
	
	len() 计算字符串含有多少字符
	
	str() 数字 转 字符串
	str(3.14e2)==>’314.0’
	
	replace() 字符串替换
	>>> a = 'abcdefghijklmnopqrstuvwxyz'
	>>> a
	'abcdefghijklmnopqrstuvwxyz'
	>>> a = a.replace('c','高')
	'ab 高 defghijklmnopqrstuvwxyz

	split() 分割
	>>> a = "to be or not to be"
	>>> a.split()
	['to', 'be', 'or', 'not', 'to', 'be']
	>>> a.split('be')
	['to ', ' or not to ', '']
	
	join() 合并 速度快(推荐)
	>>> a = ['sxt','sxt100','sxt200']
	>>> '*'.join(a)
	'sxt*sxt100*sxt200'
	
	字符串拼接
	'aa'+ 'bb' ==> 'aabb'
	'aa''bb'   ==> 'aabb'
  
	strip()	去除首尾	lstrip("*") rstrip("*")
	>>> "*s*x*t*".strip("*")
	's*x*t'
	
	查找
	a.startswith('我是高淇') 以指定字符串开头 	True
	a.endswith('过我') 以指定字符串结尾 		True
	a.find('高') 	第一次出现指定字符串的位置 	2
	a.rfind('高') 	最后一次出现指定字符串的位置 29
	a.count("编程") 	指定字符串出现了几次 		3
	a.isalnum() 	所有字符全是字母或数字 		False

	大小写转换
	a.capitalize() 产生新的字符串,首字母大写
	a.title() 产生新的字符串,每个单词都首字母大写
	a.upper() 产生新的字符串,所有字符全转成大写
	a.lower() 产生新的字符串,所有字符全转成小写
	a.swapcase() 产生新的,所有字母大小写转换
	
	格式排版
	center()、ljust()、rjust()
	>>> a.center(10,"*")
	'***SXT****'
	>>> a.center(10)
	' SXT '
	>>> a.ljust(10,"*")
	'SXT*******'

	 isalnum() 是否为字母或数字
	 isalpha() 检测字符串是否只由字母组成(含汉字)。
	 isdigit() 检测字符串是否只由数字组成。
	 isspace() 检测是否为空白符
	 isupper() 是否为大写字母
	 islower() 是否为小写字母
5.字符串复制

	>>> a = 'Sxt'*3
	>>> a
	'SxtSxtSxt'

6.[]提取字符

	a = "zxcvasd"
	a[0] >>> 'z'
	a[-1] >>> 'd'

7.切片
	
	str[起始偏移量 start：终止偏移量 end：步长 step]
	
8.字符串比较和同一性

	==,!=对字符串进行比较，是否含有相同的字符
	is / not is，判断两个对象是否同一个对象。比较的是对象的地址
9.成员操作符
	
	in /not in 关键字，判断某个字符(子字符串)是否存在于字符串中。

10.字符串格式化
	
	通过 {} 和 : 来代替以前的 % 。
	format 函数可以接受不限个参数，位置可以不按顺序
	例
	>>> b = "名字是：{0}，年龄是{1}。{0}是个好小伙"
	>>> b.format("高淇",18)
	例
	>>> c = "名字是{name}，年龄是{age}"
	>>> c.format(age=19,name='高淇')

	print("{0:<10}={1：10}".format("看我是不是左对齐","别看我我没动"))

	填充与对齐
	^、<、>分别是居中、左对齐、右对齐，后面带宽度
	>>>"{:*>8}".format("245")
	'*****245'
	>>> a = "我是{0}，我的存款有{1:.2f}"
	>>> a.format("高淇",3888.234342)
	'我是高淇，我的存款有 3888.23'
### 序列 ###
**序列就是一块用来存放多个值的连续的内存空间。**
序列中存储的是整数对象的地址，而不是整数对象的值
	
1.创建列表
	
	列表中的元素可以各不相同，可以是任意类型。
	比如：a = [10,20,'abc',True]
	
	>>> a = list() #创建一个空的列表对象
	>>> a = list(range(10))
	>>> a = list("gaoqi,sxt")
	>>> a
	['g', 'a', 'o', 'q', 'i', ',', 's', 'x', 't']

	>>>a = [x*2 for x in range(100) if x%9==0] #通过 if 过滤元素
2.方法汇总
	
	list.append(x) 增加元素 将元素 x 增加到列表 list 尾部
	list.extend(aList) 增加元素 将列表 alist 所有元素加到列表 list 尾部
	list.insert(index,x) 增加元素 在列表 list 指定位置 index 处插入元素 x
	list.remove(x) 删除元素 在列表 list 中删除首次出现的指定元素 x
	list.pop([index]) 删除元素 删除并返回列表 list 指定为止 index 处的元素，默认是最后一个元素
	list.clear() 删除所有元素 删除列表所有元素，并不是删除列表对象
	list.index(x) 访问元素 返回第一个 x 的索引位置，若不存在 x 元素抛出异常
	index(value,[start,[end]])。其中，start 和 end 指定了搜索的范围。
	list.count(x) 计数 返回指定元素 x 在列表 list 中出现的次数
	len(list) 列表长度 返回列表中包含元素的个数
	list.reverse() 翻转列表 所有元素原地翻转
	list.sort() 排序 所有元素原地排序
	a.sort(reverse=True) #降序排列
	>>> import random
	>>> random.shuffle(a) #打乱顺序
	sorted()进行排序，这个方法返回新列表，不对原列表做修改 
	a = sorted(a) #默认升序
	c = sorted(a,reverse=True) #降序
	list.copy() 浅拷贝 返回列表对象的浅拷贝
	max(a)， min(a)返回列表最大最小值
	sum(a)列表求和
3.del删除列表
	
	>>> a = [100,200,888,300,400]
	>>> del a[1]
	>>> a
	[100,200,300,400]
4.[]直接访问

	>>> a = [10,20,30,40,50,20,30,20,30]
	>>> a[2]
	30
5.列表遍历

	for obj in listObj:
	print(obj)
6.复制列表
	
	list2 = list1
	list2 = [] + list1
7.reversed()返回迭代器
	
	>>> a = [20,10,30,40]
	>>> c = reversed(a)
	>>> c
	<list_reverseiterator object at 0x0000000002BCCEB8>
	>>> list(c)
	[40, 30, 10, 20]
	>>> list(c)
	[]
8.二维列表

	套循环打印二维列表所有的数据（mypy_08.py）（由于没有学循环，照着敲一遍即可）：
	a = [
	["高小一",18,30000,"北京"],
	["高小二",19,20000,"上海"],
	["高小一",20,10000,"深圳"],
	]
	for m in range(3):
	for n in range(4):
	print(a[m][n],end="\t")
	print() #打印完一行，换行

### 元组 ###
元组属于不可变序列，元组没有增加元素、修改元素、删除元素相关的方法。

1.元组操作
	
	1. 索引访问
	2. 切片操作
	3. 连接操作
	4. 成员关系操作
	5. 比较运算操作
	6. 计数：元组长度 len()、最大值 max()、最小值 min()、求和 sum()等。
2.创建
	
	a = (10,20,30) 或者 a = 10,20,30
	元组只有一个元素，则必须后面加逗号
	>>> a = (1,) #或者 a = 1,

	tuple()创建元组
	b = tuple() #创建一个空元组对象
	b = tuple("abc")
	b = tuple(range(3))
	b = tuple([2,3,4])
3.[]直接访问，返回元组对象

	>>> a = (10,20,30,40,50,20,30,20,30)
	>>> a[1:3]
	20，30
4.对元组进行排序生成新的列表
	
	>>> a = (20,10,30,9,8)
	>>> sorted(a)
	[8, 9, 10, 20, 30]
5.zip函数
	
	zip(列表 1，列表 2，...)将多个列表对应位置的元素组合成为元组，并返回这个 zip 对象。
	>>> a = [10,20,30]
	>>> b = [40,50,60]
	>>> c = [70,80,90]
	>>> d = zip(a,b,c)
	>>> d
	<zip object at 0x03B0FB88>
	>>> list(d)
	[(10, 40, 70), (20, 50, 80), (30, 60, 90)]
6.生成器
	
	>>> s = (x*2 for x in range(5)) #只能使用一次
	>>> s
	>>> tuple(s)
	(0, 2, 4, 6, 8)
	>>> s.__next__()   #遍历
### 字典 ###
1.字典的创建
	
	1.通过{}、dict()来创建字典对象。
	>>> a = {'name':'gaoqi','age':18,'job':'programmer'}
	>>> b = dict(name='gaoqi',age=18,job='programmer')
	>>> a = dict([("name","gaoqi"),("age",18)])
		
	2.通过 zip()创建字典对象
	>>> k = ['name','age','job']
	>>> v = ['gaoqi',18,'techer']
	>>> d = dict(zip(k,v))
	>>> d
	{'name': 'gaoqi', 'age': 18, 'job': 'techer'}

	3.通过 fromkeys 创建值为空的字典
	>>> a = dict.fromkeys(['name','age','job'])
	>>> a
	{'name': None, 'age': None, 'job': None}
2.字典元素访问
	
	>>> a = {'name':'gaoqi','age':18,'job':'programmer'}
	
	1.通过 [键] 获得“值”
	>>> a['name']
	
	2. get()方法获得“值”，指定键不存在，返回 None；也可以设定指定键不存在时默认返回的对象
	>>> a.get('name')
	'gaoqi'
	>>> a.get('sex','男人') #不存在设置返回值‘男人’
	'男人'

	3.列出所有的键值对
	>>> a.items()
	dict_items([('name', 'gaoqi'), ('age', 18), ('job', 'programmer')])

	4.列出所有的键，列出所有的值
	>>> a.keys()
	>>> a.values()
3.字典元素添加、修改、删除
	
	>>>a = {'name':'gaoqi','age':18,'job':'programmer'}
	1.给字典新增“键值对”
	>>> a['address']='西三旗 1 号院'
	
	2.update()将新字典中所有键值对全部添加到旧字典对象上
	>>> a = {'name':'gaoqi','age':18,'job':'programmer'}
	>>> b = {'name':'gaoxixi','money':1000,'sex':'男的'}
	>>> a.update(b)    #b添加到a中
	>>> a
	{'name': 'gaoxixi', 'age': 18, 'job': 'programmer', 'money': 1000, 'sex': '男的'}
	
	3.del()方法；或者 clear()删除所有键值对；pop()删除指定键值对，并返回对应的“值对象”
	>>>del(a['name'])
	>>>b = a.pop('age')
	>>>b
	18
	
	4.popitem() ：随机删除和返回该键值对
	>>> a.popitem()
	('age', 18)

4.序列解包,对多个变量赋值
	
	>>> x,y,z=(20,30,10)
	>>> (a,b,c)=(9,8,10)
	>>> [a,b,c]=[10,20,30]

	>>> s = {'name':'gaoqi','age':18,'job':'teacher'}
	>>> name,age,job=s.items() #s的键依次赋值给左边
	>>> name,age,job=s.values() #s的值依次赋值给左边
### 集合 ###
1.创建集合
	
	{}创建集合对象
	>>> a = {3,5,7}
	>>> a.add(9)  #添加元素

	set()，将列表、元组等可迭代对象转成集合如果原来数据存在重复数据，则只保留一个。
	>>> a = ['a','b','c','b']
	>>> b = set(a)
	>>> b
	{'b', 'a', 'c'}

	remove()删除指定元素；clear()清空整个集合
	>>> a.remove(20)
2.集合操作
	
	>>> a|b #并集
	>>> a&b #交集
	>>> a-b #差集
	>>> a.union(b) #并集
	>>> a.intersection(b) #交集
	>>> a.difference(b) #差集	
## 控制语句 ##
### if语句 ###
1.单分支选择结构
	
	if int(num)<10:
		print(num)
2.双分支选择结构
	
	if int(num)<10:
		print(num)
	else:
		print("数字太大")
3.三元条件运算符
	
	条件为真时的值 if (条件表达式) else 条件为假时的值
	print( num if int(num)<10 else "数字太大")
### while语句 ###
1.循环结构
	
	while num<=10:
		num += 1	
### for语句 ###
1.循环结构

	for x in (20,30,40): #遍历元组
		print(x*3)

	for x in "sxt001":  #遍历字符串
		print(x)
	
	d = {'name':'gaoqi','age':18,'address':'西三旗 001 号楼'}
	for x in d: 	     #遍历字典所有的 key
		print(x)
	for x in d.keys():   #遍历字典所有的 key
		print(x)
	for x in d.values(): #遍历字典所有的 value
		print(x)
	for x in d.items():  #遍历字典所有的"键值对"
		print(x)

	for i in range(10)：
2.break跳出循环
3.continue结束本次循环，继续下一次

## 常用函数 ##
1.help() --- 查看关键字帮助文档

2.divmod(13,3) --- 同时得到商和余数

3.int() --- 整形类型转换,int(9.9)舍去小数部分，结果为9,int(True)=1,int(False)=0

4.float() --- 转换成浮点型

5.round(value) --- 返回四舍五入的值 注：但不会改变原有值，而是产生新的值

6.bin() --- 可以将数字转成二进制表示