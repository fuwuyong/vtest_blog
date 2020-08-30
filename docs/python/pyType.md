# Python 之六大基础数据类型

> 不可变数据：Number（数字）、String（字符串）、Tuple（元组）

> 可变数据：List（列表）、Dictionary（字典）、Set（集合）

## 1. Number 类型

    # 常用的数字函数
    abs(x) #返回数字的绝对值，如 abs(-10) 返回 10
    math.fabs(x) #返回数字的绝对值，如 math.fabs(-10) 返回 10.0
    exp(x) #返回 e 的 x 次幂(e^x),如 math.exp(1) 返回 2.718281828459045
    math.log(x) #返回 x 的对数如 math.log(math.e)返回 1.0,math.log(100,10)返回 2.0
    math.log10(x) #返回以 10 为基数的 x 的对数，如 math.log10(100)返回 2.0
    math.modf(x) #返回 x 的整数部分与小数部分，两部分的数值符号与 x 相同，整数部分以浮点型表示
    pow(x) #返回 x\*\*y 运算后的值
    math.sqrt(x) #返回数字 x 的平方根
    round(x,[n]) #返回浮点数 x 的四舍五入值，如给出 n 值，则代表舍入到小数点后的位数
    math.sin(x) #返回的 x 弧度的正弦值

## 2. String 类型

### 2.1 string 切片索引

字符串是 Python 中最常用的数据类型。我们可以使用引号( ’ 或 " )来创建字符串

    str = 'VTestDemo'
    print(str)          # 输出字符串
    print(str[0:-1])    # 输出第一个到倒数第二个的所有字符
    print(str[0])       # 输出字符串第一个字符
    print(str[2:5])     # 输出从第三个开始到第五个的字符
    print(str[2:])      # 输出从第三个开始的后的所有字符
    print(str * 2)      # 输出字符串两次
    print(str + "TEST") # 连接字符串

    # 输出
    VTestDemo
    VTestDem
    V
    est
    estDemo
    VTestDemoVTestDemo
    VTestDemoTEST

### 2.2 Python 三引号

python 三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符，如下举例：

    para_str = """这是一个多行字符串的实例
    多行字符串可以使用制表符
    TAB ( \t )。
    也可以使用换行符 [ \n ]。
    """
    print (para_str)

    # 输出
    这是一个多行字符串的实例
    多行字符串可以使用制表符
    TAB ( )。
    也可以使用换行符 [
    ]。

## 3. List 类型

    list.append(obj)          #在列表末尾添加新的对象
    list.count(obj)           #统计某个元素在列表中出现的次数
    list.extend(seq)          #在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）
    list.index(obj)           #从列表中找出某个值第一个匹配项的索引位置
    list.pop([index=-1])      #移除列表中的一个元素（默认最后一个元素），并且返回该元素的值
    list.remove(obj)          #移除列表中某个值的第一个匹配项
    list.reverse()            #反向列表中元素
    list.sort( key=None, reverse=False)    #对原列表进行排序,True 降序,False 升序（默认）
    list.clear()              #清空列表
    list.copy()               #复制列表

## 4.Tuple 类型

元组与列表类似，不同之处在于元组的元素不能修改

## 5.Dict 类型

字典是另一种可变容器模型，且可存储任意类型对象,每个键值(key=>value)对用冒号(:)分割，每个对之间用逗号(,)分割，整个字典包括在花括号({})中。

> 注意：键必须是唯一的，但值则不必；值可以取任何数据类型，但键必须是不可变的，如字符串，数字或元组

    dict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
    '''
    del dict['Name']     # 删除键 'Name'
    dict.clear()         # 清空字典
    del dict             # 删除字典
    '''
    print ("dict['Name']: ", dict['Name'])
    print ("dict['Age']: ", dict['Age'])

    # 输出
    dict['Name']:  Runoob
    dict['Age']:  7

## 6. Set 类型

集合是一个无序的不重复元素序列，可以使用大括号 { } 或者 set() 函数创建集合

> 注意：创建一个空集合必须用 set() 而不是 { }，因为 { } 是用来创建一个空字典

    basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
    print(basket)                      # 去重功能
    #输出
    {'orange', 'banana', 'pear', 'apple'}

    'orange' in basket                 # 快速判断元素是否在集合内
    #输出
    True

    'crabgrass' in basket
    #输出
    False

    # 下面展示两个集合间的运算
    a = set('abracadabra')
    b = set('alacazam')
    print(a)
    #输出
    {'a', 'r', 'b', 'c', 'd'}

    print(a - b)                              # 集合a中包含而集合b中不包含的元素
    #输出
    {'d', 'b', 'r'}

    print(a | b)                              # 集合a或b中包含的所有元素
    #输出
    {'c', 'b', 'r', 'z', 'l', 'm', 'a', 'd'}

    print(a & b)                              # 集合a和b中都包含了的元素
    #输出
    {'a', 'c'}

    print(a ^ b)                              # 不同时包含于a和b的元素
    #输出
    {'l', 'b', 'z', 'r', 'm', 'd'}
