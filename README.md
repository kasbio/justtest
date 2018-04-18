###Python
#####一，很基础的语法：
######基础语法
|名称|语法|属性|备注|
|-|-|-|-|
|list数列|[]|有序，可变|list可以有一个语法,*L,可以使数列中的元素独立输出，或者[0,`*L`,0] | 
|tuple不可变数列|()|有序，不可变|假如定义一个为空的tuple:(,)，区分于数学符号|
|判断语句 | if,else,elif | | 多条件时，只要遇到符合的条件就不会继续判断下去。|
|循环语句|for xxx in xxxs  while xxxxx:|  | 都差不多，感觉不太灵活|
|字典 dict |{'xxx':'xxx','xxxx':'xxxx'} |判断key in dictxxxx 返回bool|  |
|无重复key且无value字典 Set|set([list])|其实就是使输入的数列变成无重复值的dict|可以进行交集与并集|



######函数定义

+ 定义函数: def add(x,y):
　　　　　　return x+y
+ isinstance(data,(type1,type2,type3))判断类型

+ 假如函数返回多值，实际上是返回一个多值的tuple
+ 假如没有return，默认return None
　None相当于其他语言的Null
　空函数可以用pass关键字作为方法体。
＋ 默认参数一定要用不可变对象，如果是可变对象，程序运行时会有逻辑错误！
+ 要注意定义可变参数和关键字参数的语法：
　　`*args`是可变参数，args接收的是一个tuple；
　　`**kw`是关键字参数，kw接收的是一个dict。
+ 以及调用函数时如何传入可变参数和关键字参数的语法：
　　可变参数既可以直接传入：func(1, 2, 3)，又可以先组装tuple，再通过*args传入：`func(*(1, 2, 3))`；
　　关键字参数既可以直接传入：func(a=1, b=2)，又可以先组装dict，再通过`**kw`传入：func(**{'a': 1, 'b': 2})。

#####切片
切片的意思就是在一个数列中截取部分数据
比如
``` Python
L=[1,2,3,3,5,7,8,9]
print(L[:3])#截取索引为0到3的数据(不包括3)，返回一个数列
>>>[1,2,3]
L[-1]#获取倒数第一个元素
L[:10:2]#取到索引为10，然后每个2个获取一个。
L[:]#复制一个List
#tuple与字符串也可以使用
```

######列表生成式
``` Python
#举个例子好了
L=[x*x for i in range(10) for x in 'AVBBB']
#从左边读起，在0-10的数据中乘积然后再循环AVBBB的字符串长度次数
```

######生成器generator
好像刚才的生成式，只是改变符号，
`L=(x*x for i in range(10) for x in 'AVBBB') `
生成器是一种惰性的数列，当需要取到当前的数的时候才会返回此值
有如下的代码更加直观地观察到：
定义函数 odd
``` python
def odd():
    print('step 1')
    yield 1
    print('step 2')
    yield(3)
    print('step 3')
    yield(5)

>>> o = odd()
>>> next(o)#使用Next进行取下一步操作。
step 1
1
>>> next(o)
step 2
3
>>> next(o)
step 3
5
>>> next(o)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
StopIteration
```

 

'
#####迭代器 Iterator
定义为能够用next()函数来不断获取下一个值的对象成为迭代器
`可以通过iter()函数将list,dict,str转换成Iterator


######map/reduce
+ Map
map函数接收两个参数，一个执行函数与一个序列，按照序列的顺序，每一个序列中每一个元素都成为执行
函数的参数，然后返回结果。
``` python
>>> def f(x):
            return x*x
#返回的结果是惰性数列，需要返回一个list数列回来。
>>> r=map(f,[1,2,3,4])
>>> list(r)
[1,4,9,16,25,36,49,64,81]
```

+ reduce
reduce函数不同于map函数，此函数接受两个参数，也是一个执行函数与另一个数列
相对于map的话，他是执行成`reduce(f,[x1,x2,x3,x4])=f(f(f(x1,x2),x3),x4)`

+ filter
filter是一个筛选函数，用法:filter(fn,[]),其中fn为判断函数，[]为数列


　



 
