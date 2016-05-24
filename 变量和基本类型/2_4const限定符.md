## const限定符 ##
### const对象仅在文件内有效 ###
默认情况下，const对象被设定为仅在文件内有效，为了让对象在不同文件中共享，不管是声明还是定义都添加**extern**关键字，而且只需要定义一次。
```cpp
//file1.cc定义并初始化一个常量，该常量能被其他文件访问
extern const int bufsize = fcn();
//file1.h头文件，与file1.cc中的bufsize是同一个
extern const int bufsize;
```
### 指针和const ###
- 指向常量的指针：不能修改指向的值
- 常量指针：地址值不变，一直指向某一给值
- 指向常量的常量指针：不仅本身不能变，指向的值也不能变

```cpp
int err = 0;
//cur一直指向err，从右往左读，cur旁边首先是const，说明cur是一个常量对象，然后再左边的*说明是一个常量指针，其他部分就是说明到底这个常量指针指向的是什么，这里指向的是int。
int *const cur = &err;
const double pi = 3.1415;
//同理，只不过这里的pip作为常量指针指向的是双精度常量。
const double *const pip = &pi;
```
引申出两种说法：
**顶层const**：表示指针本身是个常量
**底层const**：表示指针所指的对象是一个常量
```cpp
const int *const p3 = p2; //靠右的const是顶层const，靠左的是底层const。
```
一般来说，如果认定变量是一个常量表达式，那就把它声明称constexpr类型。
```cpp
constexpr int mf = 20;
constexpr int limit = mf + 1;
```
```cpp
const int *p = nullptr;//p是一个指向整型常量的指针
constexpr int *q = nullptr;//q是一个指向整数的常量指针，是个顶层的const。
```