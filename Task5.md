# 类和对象（编写一个大型程序或面对某一更适合此方法的问题）
>一个类（ Class） 能够创建一种新的类型（ Type） ， 其中对象（ Object） 就是类的实例（ Instance） 

>自行车可以是一个类，他有轮子，有车把手，有链条，有座椅。抽象
>凤凰牌A1自行车就这个类的对象，是一个实例。具体

## 1、类
>使用class 变量名 来定义类，每个类中存在变量和函数，在类中，变量被称为字段，函数被称为方法（用于区分）
	Class A：
		Pass
	B =A（）
A是一个类，B为A类的对象


## 2、方法：定义类方法时，必存在（self）

	classperson:
		Def __init__(self,name):
		self.name=name
	
		Def sayhi(self):
		print('HelloWorld,MyNameis',self.name)
	
	p=person('Reiki')
	p.sayhi()
	
	sayhi是定义的方法，_init_是特殊的方法，__init__ 方法会在类的象被实例化（ Instantiated） 时立即运行。 这一方法可以对任何你想进行操作的目标对象进行初始化（ Initialization） 操作。 这里你要注意在 init 前后加上的双下划线。 

## 3、区分类变量和对象变量
>类变量（ Class Variable） 是共享的（ Shared） ——它们可以被属于该类的所有实例访问。该类变量只拥有一个副本， 当任何一个对象对类变量作出改变时， 发生的变动将在其它所有实例中都会得到体现。
>对象变量（ Object variable） 由类的每一个独立的对象或实例所拥有。 在这种情况下， 每个对象都拥有属于它自己的字段的副本， 也就是说， 它们不会被共享， 也不会以任何方式与其它不同实例中的相同名称的字段产生关联。 

class person:
    def __init__(self, name):
        self.name = name

    def sayhi(self):
        print('Hello World, My Name is', self.name)


p = person('Reiki')
p.sayhi()


class Robot:
    population = 0

    def __init__(self, name):
        self.name = name
        print("(Initializing {})".format(self.name))

        Robot.population += 1

    def die(self):
        print("{} is Byebye".format(self.name))
        Robot.population -= 1

        if Robot.population == 0:
            print("{} is the last one".format(self.name))
        else:
            print(
                "There are still {:d} robots working".format(
                    Robot.population))

    def sayhi(self):
        print("hello {}".format(self.name))

    @classmethod
    def howmany(cls):
        print("we have {:d} robots".format(cls.population))


droid1 = Robot("R2-D2")
droid1.sayhi()
Robot.howmany()

droid2 = Robot("c-P30")
droid2.sayhi()
Robot.howmany()


droid1.die()
droid2.die()

Robot.howmany()



## 4、继承：继承最好是想象成在类之间实现类型与子类型（ Type and Subtype）关系的工具 

从实际中理解，现在假设你希望编写一款程序来追踪一所大学里的老师和学生。 有一些特征是他们都具有的， 例如姓名、 年龄和地址。 另外一些特征是他们独有的， 一如教师的薪水、 课程与假期，学生的成绩和学费。
你可以为每一种类型创建两个独立的类， 并对它们进行处理。 但增添一条共有特征就意味着将其添加进两个独立的类。 这很快就会使程序变得笨重。
一个更好的方法是创建一个公共类叫作 SchoolMember ， 然后让教师和学生从这个类中继承（ Inherit） ， 也就是说他们将成为这一类型（ 类） 的子类型， 而我们就可以向这些子类型中添加某些该类独有的特征。 

# coding = UTF-8

class SchoolMember:
    '''代表任何学校成员'''
    def __init__(self, name, age):
        self.name = name
        self.age = age
        print('(Initialized SchoolMember: {})'.format(self.name))

    def tell(self):
        print('Name:"{}" Age:"{}" '.format(self.name, self.age), end='')



class Teacher(SchoolMember):
    def __init__(self, name, age, salary):
        SchoolMember.__init__(self,name,age)
        self.salary = salary
        print('(Initialized Teacher: {})'.format(self.name))

    def tell(self):
        SchoolMember.tell(self)
        print('Salary: "{}"'.format(self.salary))

class Student(SchoolMember):
    def __init__(self, name, age, marks):
        SchoolMember.__init__(self, name, age)
        self.marks = marks
        print('(Initialized Student: {})'.format(self.name))

    def tell(self):
        SchoolMember.tell(self)
        print('Marks: "{:d}"'.format(self.marks))


t = Teacher('Mark', 22,123123123)
s = Student('reiki', 11, 99)

print()


members = [t,s]
for member in members:
    member.tell()





>Python 总会从当前的实际类型中开始寻找方法， 在本例中即是如此。 如果它找不到对应的方法， 它就会在该类所属的基本类中依顺序逐个寻找属于基本类的
>方法， 这个基本类是在定义子类时后跟的元组指定的 






# 2）正则表达式：
字符串是编程时涉及到的最多的一种数据结构，对字符串进行操作的需求几乎无处不在。比如判断一个字符串是否是合法的Email地址，虽然可以编程提取@前后的子串，再分别判断是否是单词和域名，但这样做不但麻烦，而且代码难以复用。
正则表达式是一种用来匹配字符串的强有力的武器。它的设计思想是用一种描述性的语言来给字符串定义一个规则，凡是符合规则的字符串，我们就认为它“匹配”了，否则，该字符串就是不合法的。

# 3)re模块：
Python提供re模块，包含所有正则表达式的功能。

## match模块：
>match()方法判断是否匹配，如果匹配成功，返回一个Match对象，否则返回None。常见的判断方法就是：
test = '用户输入的字符串'
if re.match(r'正则表达式', test):
    print('ok')
else:
    print('failed')


## 切分字符串
用正则表达式切分字符串比用固定的字符更灵活，请看正常的切分代码：
>>> 'a b   c'.split(' ')
['a', 'b', '', '', 'c']
嗯，无法识别连续的空格，用正则表达式试试：
>>> re.split(r'\s+', 'a b   c')
['a', 'b', 'c']


## 提取分组：
正则表达式还有提取子串的强大功能。用()表示的就是要提取的分组（Group）。
提取子串非常有用。来看一个更凶残的例子：
>>> t = '19:05:30'
>>> m = re.match(r'^(0[0-9]|1[0-9]|2[0-3]|[0-9])\:(0[0-9]|1[0-9]|2[0-9]|3[0-9]|4[0-9]|5[0-9]|[0-9])\:(0[0-9]|1[0-9]|2[0-9]|3[0-9]|4[0-9]|5[0-9]|[0-9])$', t)
>>> m.groups()
('19', '05', '30')







# 4）http请求
我们可能需要通过某些http接口提交一些数据到我们的资产管理系统、监控系统等，我们可以使用python的第三方库requests来进行操作，优雅而简单
## 1、发送请求
import requests #导入requests，然后就可以为所欲为了
#发送get请求
r0 = requests.get("http://yunweicai.com")
#发送post请求
r1 = requests.post("http://yunweicai.com",data={key:value})
#发送post请求，带json串
json_data = {"user":"yunweicai","op":"post"}
r11 = requesets.post("http://yunweicai.com",json=json_data)
#put、delete、head、optiions请求也很简单
r = requests.put('http://yunweicai.com/put', data = {'key':'value'})
r = requests.delete('http://yunweicai.com/delete')
r = requests.head('http://yunweicai.com/get')
r = requests.options('http://yunweicai.com/get')
## 2、URL参数
URL 的查询字符串(query string)传递某种数据。如果你是手工构建 URL，那么数据会以键/值对的形式置于 URL 中，跟在一个问号的后面。例如， yunweicai.com/get?key=val。
requests库操作就比较优雅了，requests 允许你使用 params 关键字参数，以一个字符串字典来提供这些参数。
payload = {'key1': 'value1', 'key2': 'value2'}
r = requests.get("http://yunweicai.com/get", params=payload)
通过打印输出该 URL，你能看到 URL 已被正确编码：
print(r.url)
## 3、相应内容
通过发送请求返回的对象，我们就可以获取到服务器对我们的相应内容了。Requests 会自动解码来自服务器的内容。请求发出后，Requests 会基于 HTTP 头部对响应的编码作出有根据的推测。当你访问 r.text 之时，Requests 会使用其推测的文本编码。
你可以找出 Requests 使用了什么编码，并且能够使用 r.encoding 属性来改变它:
>>> r.encoding'utf-8'>>> r.encoding = 'ISO-8859-1'
如果返回的json串，可以直接使用r.json()获取到字典对象进行操作
如果响应内容是二进制呢？
对于响应内容是非文本请求，可以使用r.content访问到内容。
例如，以请求返回的二进制数据创建一张图片，你可以使用如下代码：
>>> from PIL import Image>>> from io import BytesIO>>> i = Image.open(BytesIO(r.content))
## 4、定制请求头
有些请求需要有指定的请求头才能正确获取到内容。
headers = {'user-agent': 'my-app/0.0.1'}
r= requests.get("http://yunweicai.com",headers=headers)
## 5、cookies
有些请求需要依赖于cookies来完成操作，就需要从上个请求中获取到cookies然后传入下一个请求：
r0 = requests.get("http://yunweicai.com/login")
r1 = requests.post("http://yunweicai.com/asset",data={"hostname":"yunweicai",cookies= r0.cookies}



