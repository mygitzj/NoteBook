**1.python 中所有异常都是BaseException的实例**  

- BaseException                     # 所有异常的父类
  - SystemExit                     # 由sys.exit()抛出的异常
  - KeyBoardInterrupt              # 通常由ctrl+c或者Delete抛出的异常
  - GeneratorExit                  # 当生成器被关闭时抛出的异常
  - Exception                      # 
    - StopIteration              # 迭代结束异常
    - StopAsyncIteration         # 由异步迭代的`__anext__()`抛出的异常
    - ArithmeticError            # 各种算数错误引起的异常
      - FloatingPointError     # 浮点数操作错误
      - OverflowError          # 结果超出范围
      - ZeroDivisionError      # ０为除数异常
  - AssertionError                 # assert错误异常
  - AttributeError                 # 属性引用异常
  - BufferError                    # 缓存错误
  - EOFError                       # 读不到数据
  - ImportError                    # import错误
    - ModuleNotFoundError        # 找不多模块
  - LookupError                    # 由索引和key值引起的异常
    - IndexError                 # 索引错误
    - KeyError                   # 字典key值错误
  - MemortError                    # 内存溢出异常
  - NameError                      # 本地和全局找不到变量名
    - UnboundLocalError          # 局部变量没有赋值
  - OSError                        # system错误
    - BlockingIOError            # 调用阻塞异常错误
    - ChildProcessError          # 子进程
    - ConnectionError            # 连接
      - BrokenPipeError        # 管道读写异常
      - ConnectionAbortedError # 连接失败
      - ConnectionRefusedError # 连接拒绝
      - ConnectionResetError   # 连接重置
    - FileExistsError            # 创建文件和文件夹错误
    - FileNotFoundError          # 文件未找到
    - InterruptedError           # 中断错误
    - IsADirectoryError          # 文件操作用在文件夹上
    - NotADirectoryError         # 不是文件夹
    - PermissionError            # 权限
    - ProcessLookupError         # 进程不存在
    - TimeoutError               # 超时
  - ReferenceError                 # 引用异常
  - RuntimeError                   # 
    - NotImplementedError        # 运行抽象方法
    - RecursionError             # 超出最大递归深度
  - SyntaxError                    # 语法错误
    - IndentationError           # 缩进错误
      - TabError               # tab错误
  - SystemError                    # 解释器中断
  - TypeError                      # 类型错误
  - ValueError                     # 赋值错误
    - UnicodeError               # 
      - UnicodeEncodeError     # unicode编码错误
      - UnicodeDecodeError     # unicode解码错误
      - UnicodeTranslateError  # unicode转换错误
  - Warning                        # 
    - DeprecationWarning         # 操作不赞成警告
    - PendingDeprecationWarning  # 表明此操作将来会被弃用
    - UserWarning                # 用于用户生成警告
    - SyntaxWarning              # 语法可疑警告
    - RuntimeWarning             # 运行警告
    - FutureWarning              # 将会改变警告
    - ImportWarning              # 导入警告
    - UnicodeWarning             # unicode相关警告
    - BytesWarning               # 字节相关警告
    - ResourceWarning            # 资源使用情况警告  
     
 **2.流程 **  
 
``` 
try:
...
except BaseException as e:
  print(e)
else finally,除except外else、finally可选
 
 **3.
 
 
  
