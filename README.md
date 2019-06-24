# -Hello-World-by-python
>python入门记录

## Task 1（使用简明python教程）
### 环境搭建：
>使用anaconda环境配置+Pycharm（体验超棒）
>主体：GitHub；字体：Source code pro


### python初体验：
>print:打印括号的内容至屏幕；print 总是会以一个不可见的“新一行”字符（ \n ），如不想可用end，print('a', end='')<br />
>input:键盘输入字符串！；<br />
>import使用：调包！<br />
>pep8:python特有的缩进要求，推介使用autopep8这个exe，附[教程](https://www.cnblogs.com/xiao-apple36/p/9242069.html)<br />


### 基础
>python中数值类型注意点：
>int包含了long;<br />
>不区分单引号多引号，多引号可用来表示段落；<br />
>formate函数的使用：填充<br />
>标识符名称区分大小写<br />
>算数运算符、逻辑运算符、成员运算符、身份运算符、运算符<br />


## Task 2（实现见代码部分）
### 列表（可变的数据类型，注意 Python 从 0 开始计数）
>标志:用方括号括起来,组成可以是各种元素，可以添加、 移除或搜索列表中的项目（对象）。是python里面用的最多最常用的数据类型， 可以通过下标来访问， 可以理解为java或者c里面的数组.但是功能比数组强大n倍,list可以放任意数量的python对象， 可以是字符串， 字符， 整数， 浮点等等都可以<br />
>基本操作:
>创建：用[]，list内部的对象可以是字符串， 字符， 数字， 支持混搭<br />
>访问list //直接通过下标去访问<br />
>列表的嵌套 //列表支持嵌套， 就是列表里面可以套列表， 甚至套字典， 元组等<br />
>列表的插入//内置函数append,insert<br />
>列表的删除//内置remove,pop函数：<br />
>列表支持+,*：<br />
>列表支持sort：<br />


### 元组(将多个对象保存到一起，和列表基本一样，也是一种序列， 唯一的不同在于不能修改）
>标志：aTuple=(1,2,3)
>基本操作:元组的用法和列表一模一样<br />
>要发明元组， 原因在于:<br />
>■ 有一些特殊的场合需要不可变序列， 比如后面会讲道的数据结构字典， 必须要用不
可变序列作为键值， 而列表不行。<br />
>■ 有一些内建的函数的返回值， 也必须是元组.<br />


### string字符串：
>定义:''或者“ ”形成（但python中没有char，就很舒服）<br />
>连接和合并:使用+或者join<br />
```c
zoo = ('python', 'elephant', 'penguin')
print('.'.join(zoo))
```
>相乘//比如写代码的时候要分隔符， 用python很容易实现<br />
```c
line='*'*30
print(line)
```
>字符串的分割:split只能做非常简单的分割， 而且不支持多个分隔<br />
```c
phone=,400-800-800-1234,
print(phone.split('-'))
> >['400', '800，, '800', '1234']
```

>字符串的查找和匹配:find函数<br />


>字符串相关方法、字符串格式化问题<br />
>
> 格式化：算机只能处理数字，如果要处理文本，就必须先把文本转换为数字才能处理.全世界有上百种语言，日本把日文编到Shift_JIS里，韩国把韩文编到Euc-kr里，各国有各国的标准，就会不可避免地出现冲突，结果就是，在多语言混合的文本中，显示出来会有乱码。<br />Unicode应运而生。Unicode把所有语言都统一到一套编码里，这样就不会再有乱码问题了。<br />本着节约的精神，又出现了把Unicode编码转化为“可变长编码”的UTF-8编码.记事本编辑的时候，从文件读取的UTF-8字符被转换为Unicode字符到内存里，编辑完成后，保存的时候再把Unicode转换为UTF-8保存到文件<br />
>>(•format的用法比较灵活， 参数的顺序和格式化的顺序不必完全相同， 一般推荐用format,而且也是Python3里面的官方力推， 之所以保留％主要是为了兼容以前的代码)<br />

```c



# 列表
shoplist = ['apple', 'mango', 'carrot', 'banana']
print('I have', len(shoplist), 'items to purchase.')

print('These items are: ', end='')

for item in shoplist:
    print(item, end=' ')

print('\nI also have to buy rice.')
shoplist.append('rice')
print('My shopping list is now', shoplist)

print('I will sort my list now')
shoplist.sort()
print('sort is', shoplist)

print('the first is ', shoplist[0])
olditem = shoplist[0]
del shoplist[0]


print(olditem)
print(shoplist)

shoplist.pop(0)
shoplist.insert(0, 'happy')
print(shoplist)


# 元组

zoo = ('python', 'elephant', 'penguin')
print('.'.join(zoo))


print('Number of animals in the zoo is', len(zoo))

new_zoo = 'monkey', 'camel', zoo
print(len(new_zoo))
print(new_zoo)
print(new_zoo[2])
print(new_zoo[2][2])
print(len(new_zoo) - 1 + len(new_zoo[2]))


print('.'. join(shoplist))
print(''.join(shoplist))
key = "/".join(shoplist)


line = '*' * 30
print(line)

print(key[-3:])
print(key.split('/'))
print(key.endswith('rice'))
print(key.find('rice'))
print(key.replace('rice', 'noddle'))

shoplist.remove('rice')
shoplist.pop()
print(shoplist)

shoplist.insert(1, 'ssssss')
shoplist.append('ssss123')
print(shoplist)
list1 = shoplist * 3  # 列表的乘法
print(list1)
list1 = shoplist + list1

list2 = [1, 2, 3, 4, 5, 6, 7, 5, 4, 32, 2, 2, 1, 12, 12, 1, 212]
list2.sort()
print(list2)
print(min(list2))
print(max(list2))

list2.extend(list1)
print(list2)

print(list2.count(2))
```

