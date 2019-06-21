# -Hello-World-by-python
>python入门记录

## Day 1（使用简明python教程）
###环境搭建：
>使用anaconda环境配置+Pycharm（体验超棒）
>主体：GitHub；字体：Source code pro


###python初体验：
>print:打印括号的内容至屏幕；print 总是会以一个不可见的“新一行”字符（ \n ），如不想可用end，print('a', end='')
>input:键盘输入；
>pylp( )：没查到。。。
>import使用：调包！！！！
>pep8:python特有的缩进要求，推介使用autopep8这个exe，附[教程](https://www.cnblogs.com/xiao-apple36/p/9242069.html)


###基础
>python中数值类型注意点：
>int包含了long;
>不区分单引号多引号，多引号可用来表示段落；
>formate函数的使用：填充
>标识符名称区分大小写


>算数运算符、逻辑运算符、成员运算符、身份运算符、运算符（使用见代码）

###代码部分
(''')
print("hello world")  # 学习print的函数

 字面常量
 数字，文本，字面意义上的值
 多引号的使用：
'''
asdassdasdasdasdasd
ssssssss123333
'''

age = 2
name = 'Swaroop'
print('{0} was {1} years old when he wrote this book' .format(name, age)) 
print('why is {0} playing with that python'.format(name))
print(name + 'is' + str(age) + 'years old')

print('{0:.3f}'.format(1.0 / 3), end='')
print('{name} wrote {book}'.format(name='123', book='2222'))

 print('what\'s your name\n my name is jxW')

 r"asdasdasdasdasd by \n"
 print(r'\1')


变量

i = 5
print(i)

i = i+1
print(i)

s = '''
This is a multi-line string.\
This is the second line.
'''
print(s)
i = \
5

print(i)

print('sss' * 3)



运算符
length = 5
breadth = 2

area = length * breadth
print('Area is', area)
print('Perimeter is', 2* (length + breadth))

成员运算符;身份运算符
成员运算符：in 如果在指定的序列中找到值返回 True，否则返回 False
a = 2
list = [1,2,3]
if a in list:
    print("a is in list")

#身份运算符：is 是判断两个标识符是不是引用同一个对象

d=2
c = 2*d
b = 6-d
if(b is c):
    print("ok")
(''')






---------
