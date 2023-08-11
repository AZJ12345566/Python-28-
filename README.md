# Python-28-
Python学习笔记(28)
# p89 函数参数传递的内存分析
#实际参数和形式参数名称不相同
def fun(arg1,arg2):
    print('arg1',arg1)
    print('arg2',arg2)
    arg1=100
    arg2.append(10)
    print('arg1',arg1)
    print('arg2',arg2)

n1=11
n2-[22,33,44]
print('n1',n1)
print('n2',n2)
fun(n1,n2)  #按位置传参，arg1,arg2,是函数定义处的形参，n1，n2是函数调用处的实参

print('n1',n1)
print('n2',n2)

‘’'在函数调用的过程中，进行参数的传递，如果是不可变对象，在函数体的修改不会影响实参的值，(arg1修改为100，不会影响到n1的值)
如果是可变对象，在函数体内的修改会影响函数实参的值(arg2的修改，会影响到n2的值)'‘’



# p90 函数的返回值
print(bool(0))  #False
print(bool(1))  #True

def fun(num):
    odd=[]  #存奇数
    even=[]  #存偶数
    for i in num:
        if i%2:
            odd.append(i)
        else:
            even.append(i)
    return odd,even

#函数的调用
lst=[10,29,34,23,44,53,55]
print(fun(lst))

'''函数的返回值
(1)如果函数没有返回值，return可以省略不写
(2)函数的返回值，如果是一个，直接返回原类型1
(3)函数的返回值，如果是多个，返回的结果是元组
‘’‘

def fun1():
    print('hello')
    
fun1()


def fun2():
    return 'hello'
res=fun2()
print(res)


def fun3():
    return 'hello','world'
print(fun3())
#输出为('hello','world')

‘’‘函数在定义时，是否需要返回值，看情况而定’‘’



# p91 函数参数定义_默认值参数
def fun(a,b=10):  #默认值参数
    print(a,b)

#函数的调用
fun(100)  #输出为100 10
fun(20,30)  #输出为20 30

print('hello' end='\t')  #这里输出就是hello world了，因为把end的默认值给修改了
print('world')
