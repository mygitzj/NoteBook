## import ##  

1.from module import *  
调用内容时不需要前缀（直接调用），但是有可能命名污染  

2.import module   
调用时需要前缀，防止命名污染

## \_\_all\_\_ ##

1.__all__只能影响到 from import * 这种import 方式, 对于from import 的 import 方式没有影响  

2.在普通的*.py中,表示形式:  
```
__all__=["class_name","function_name"] 
```
在使用 from module_name import * 时,表示import 该module中的__all__中所列出类、函数、变量  

3.在__init__.py文件中，表示形式:

```
__all__=["module_a","module_b"] 
```
在使用``` from package_name import * ```时 , 表示import 该package 中的 两个module及 两个module相关的类、方法等

## 命名空间 ##

1.用于区分不同位置，不同功能但是相同名称的函数或变量的特定前缀
2.作用是防止命名冲突  

```
setName()
student.setName()
Dog.setName()

