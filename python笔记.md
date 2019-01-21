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
