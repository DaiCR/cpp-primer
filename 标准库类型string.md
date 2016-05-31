## 标准库类型string ##
```cpp
#include<string>
using std::string
```
初始化分为**直接初始化**和**拷贝初始化**。
```cpp
string s1 = "dai"		//直接初始化
string s2 = ("dai")		//拷贝初始化
```

**利用getline()函数可以读取一整行**，例子如下：
```cpp
string line;
while(getline(cin,line))
	cout << line << endl;
```
读取到换行符为止。

string的size()函数和length()函数都会返回字符串的实际长度，比如"dai"，会返回3。

**c++11中使用for来处理字符串中每一个元素**
```cpp
string str("daichengrui nupt");
for(auto c : str)
	cout << c << endl;
```
