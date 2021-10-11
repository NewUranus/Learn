## C++编译之预处理
### 什么是预处理
预处理：Preprocessing。

### 如何得到预处理的文件
可以用下面的指令来生成
```
g++ xxx.cpp -E -o xxx.i
```
这里的-o xxx.i是不可少的，否则文件不会生成，而是内容在屏幕上打印出来了。
### 预编译的作用
- 头文件展开

include了头文件，例如有个头文件t.h，定义如下：
```
class Test
{
private:
    int i1;
}
```
在t.cpp被引用了：
```
#include "t.h"
int main()
{
    return 0;
}
```
得到的预处理文件内容如下：
```
# 1 "t1.cpp"
# 1 "<built-in>"
# 1 "<command-line>"
# 1 "t1.cpp"
# 1 "t.h" 1
class Test
{
private:
    int i1;
}
# 2 "t1.cpp" 2
int main()
{
    return 0;
}

```
可以看到，就是把include的内容用文件替换了。

- 宏替换

- 去掉注释

- 条件编译

比如常见的#ifdef，也就是在这个时候处理的。
