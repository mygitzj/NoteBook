## python2.x与python3.x的区别
**1.print函数**

python3中没有print语句，python2.6与2.7中以下3种情况等效：
```
print "aaa"
print ("aaa")
print("aaa")
```
python2.6中支持使用以下新写法：
```
from __future__ import print_function
print("fish", "panda", sep=', ')
```
**2.unicode**

>unicode：在本文中表示用4byte表示的unicode编码，也是python内部使用的字符串编码方式。

对于python2,内置的字符串类型有str和unicode。比如'abc'是str,u'你好'则是unicode  
python3里没有预定义unicode类型，内置的字符串就是str,因此使用isinstance(key,unicode)的时候会报错  
Python 2 中unicode() 是单独的，不是 byte 类型  
Python 3，我们最终有了 Unicode (utf-8) 字符串，以及一个字节类：byte 和 bytearrays  
Python3.X 源码文件默认使用utf-8编码，这就使得以下代码是合法的  

```
 中国='china'
 print(中国)
 ```
 python3:
 ```
 text="测试"
 b_str=text.encode('utf-8')
 type(b_str)
 <class 'bytes'>
```
python2:
```
text=u"测试"
b_str=text.encode('utf-8')
type(b_str)
<class 'str'>
```
**3.除法运算**

在python 2.x中/除法就跟我们熟悉的大多数语言，比如Java啊C啊差不多，整数相除的结果是一个整数，把小数部分完全忽略掉，浮点数除法会保留小数点的部分得到一个浮点数的结果。  
在python 3.x中/除法不再这么做了，对于整数之间的相除，结果也会是浮点数。  
python2.x:
```
>>>1/2
0
>>>1.0/2.0
0.5
```
python3.x:
```
>>>1/2
0.5
```
而对于//除法，这种除法叫做floor除法，会对除法的结果自动进行一个floor操作（不大于结果得最大整数），在python 2.x和python 3.x中是一致的。  
python2.x:
```
>>>-1//2
-1
```
python3.x:
```
>>>-1//2
-1
```
**4.异常**

捕获异常及抛出异常得语法改变  (Python 2.6同时支持这两种语法)
python2.x:
```
raise IOError, "file error" #抛出异常
except NameError, err: #捕捉异常
```
python3.x:
```
raise IOError("file error") #抛出异常
except NameError as err: #捕捉异常
```
在2.x时代，所有类型的对象都是可以被直接抛出的  
在3.x时代，只有继承自BaseException的对象才可以被抛出。 

**5.xrange**

 Python 2 中xrange() 函数 比 range() 更快  
 Python 3 中，range() 是像 xrange() 那样实现以至于一个专门的 xrange() 函数都不再存在  
**6.八进制表示**
 
 python3中八进制数必须写成0o777，二进制必须写成0b111  
 python3中新增了一个bin()函数用于将一个整数转换成二进制字串  
 在Python 3.x中，表示八进制字面量的方式只有一种，就是0o1000  
 python2.x:  
 ```
 >>> 0o1000
512
>>> 01000
512
```
python3.x: 
```
>>> 01000
  File "<stdin>", line 1
    01000
        ^
SyntaxError: invalid token
>>> 0o1000
512
```
**7.不等运算符**  

Python 2.x中不等于有两种写法 != 和 <>  
Python 3.x中去掉了<>, 只有!=一种写法  
**8.去掉repr表达式**  

repr() 函数将对象转化为供解释器读取的形式，将对象转换为string
```
>>>s = 'RUNOOB'
>>> repr(s)
"'RUNOOB'"
>>> dict = {'runoob': 'runoob.com', 'google': 'google.com'};
>>> repr(dict)
"{'google': 'google.com', 'runoob': 'runoob.com'}"
>>>
```
Python 2.x 中反引号相当于repr函数的作用,Python 3.x 中去掉了这种写法，只允许使用repr函数  

**9.多个模块被改名（根据PEP8）**  

|旧名|新名|
|-|-|
|\_winreg|winreg|
|ConfigParser|configparser|
|Queue|queue|
|SocketServer|socketserver|
|Queue|queue|
|repr|reprlib|

StringIO模块现在被合并到新的io模组内( Python 2.6已经支持新的io模组)  
new, md5, gopherlib等模块被删除  
httplib, BaseHTTPServer, CGIHTTPServer, SimpleHTTPServer, Cookie, cookielib被合并到http包内
取消了exec语句，只剩下exec()函数( Python 2.6已经支持exec()函数)  

**10.数据类型**

1）Py3.X去除了long类型，现在只有一种整型——int，但它的行为就像2.X版本的long 
2）新增了bytes类型，str对象和bytes对象可以使用.encode() (str -> bytes) or .decode() (bytes -> str)方法相互转化

```
>>> b = b'china' 
>>> type(b) 
<type 'bytes'> 
```

```
>>> s = b.decode() 
>>> s 
'china' 
>>> b1 = s.encode() 
>>> b1 
b'china' 
```
**11.打开文件**  

python2.x:file( ..... )或 open(.....)  
python3.x:只能用open(.....)  

**12.录入字符串**  

在python2.x中raw_input()和input( )，两个函数都存在，其中区别为：
>raw_input()---将所有输入作为字符串看待，返回字符串类型  
>input()-----只能接收"数字"的输入，在对待纯数字输入时具有自己的特性，它返回所输入的数字的类型（int, float ） 
在python3.x中raw_input()和input( )进行了整合，去除了raw_input()，仅保留了input()函数，其接收任意任性输入，将所有输入默认为字符串处理，并返回字符串类型。

**13.map、filter 和 reduce**  

 Python2.x中  map、filter和reduce都是built-in function(内置函数)
 ```
 >>> map
<built-in function map>
>>> filter
<built-in function filter>
>>>
```
它们输出的结果类型都是列表:  
```
>>> map(lambda x:x *2, [1,2,3])
[2, 4, 6]
>>> filter(lambda x:x %2 ==0,range(10))
[0, 2, 4, 6, 8]
>>>
```  
Python3.x中  map、filter和reduce从函数变成了类
```
>>> map
<class 'map'>
>>> map(print,[1,2,3])
<map object at 0x10d8bd400>
>>> filter
<class 'filter'>
>>> filter(lambda x:x % 2 == 0, range(10))
<filter object at 0x10d8bd3c8>
>>>
```
Python3.x中  map、filter和reduce返回结果也从当初的列表成了一个可迭代的对象  

```
>>> f =filter(lambda x:x %2 ==0, range(10))
>>> next(f)
0
>>> next(f)
2
>>> next(f)
4
>>> next(f)
6
>>>
```
 



 
 




