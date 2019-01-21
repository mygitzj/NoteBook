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
 <class 'byte'>
```
python2:
```
text=u"测试"
b_str=text.encode('utf-8')
type(b_str)
<class 'str'>
```
