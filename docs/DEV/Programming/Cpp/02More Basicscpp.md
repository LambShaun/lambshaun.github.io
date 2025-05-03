# CPP Basics-2

## 1（enum)枚举

枚举是一种用户定义的类型，由一组命名的常量组成，称为枚举器。枚举定义了可以赋值给该类型对象的完整值集。例如

```c++
enum Color {
   RED, GREEN, BLUE
} myColor;        // Define an enum and declare a variable of the enum
......
myColor = RED;    // Assign a value to an enum
Color yourColor;
yourColor = GREEN;
```

枚举器在内部表示为整数。你在赋值时必须使用名称，而不是数字。然而，在算术运算中，它会被提升为 int。默认情况下，它们是从零开始的连续数字。你可以分配不同的数字，例如，

```c++
enum Color {
   RED = 1, GREEN = 5, BLUE
};
```

要打印枚举器名称，您可能需要定义一个字符串数组，并以枚举器编号作为索引。

## 2struct结构

一个 `struct` （结构）是一个用户定义的数据结构，可用于存储一组不同类型的变量（称为成员）。要定义一个 `struct` ：

```c++
struct StructName {
   type1 var1;
   type2 var2;
   .......
};  // need to terminate by a semi-colon
```

`struct` 是面向对象编程（OOP）的中间步骤。在 OOP 中，我们使用 `class` ，这是一个用户定义的结构，包含数据成员和成员函数。

##### 示例：struct Point

```c++
#include <iostream>
using namespace std;
 
struct Point {
   int x;
   int y;
};
 
int main() {
   Point p1 = {3, 4};  // declare and init members
   cout << "(" << p1.x << "," << p1.y << ")" << endl;  // (3,4)
 
   Point p2 = {};      // declare and init numbers to defaults
   cout << "(" << p2.x << "," << p2.y << ")" << endl;  // (0,0)
   p2.x = 7;
   p2.y = 8;
   cout << "(" << p2.x << "," << p2.y << ")" << endl;  // (7,8)
   return 0;
}
```

> [!NOTE]
>
> - 你可以像第 11 行和第 14 行所示那样声明并初始化一个 `struct` 的实例。
> - 要访问 `struct` 的成员，请使用点号（ `.` ）运算符。

##### 示例：struct Person

一个 `struct` 可以包含不同类型的成员。

```c++
#include <iostream>
#include <string>
using namespace std;
 
struct Person {
   string name;
   int age;
   double height;
   double weight;
};
 
int main() {
   Person peter = {"Peter Jone", 18, 180.5, 70.5};
   cout << "Name: " << peter.name << endl;
   cout << "Age: " << peter.age << endl;
   cout << "Height: " << peter.height << endl;
   cout << "weight: " << peter.weight << endl;
   return 0;
}
```

##### structs Point and Rectangle 

```c++
#include <iostream>
using namespace std;
 
struct Point {
  int x, y;
};
 
struct Rectangle {
  Point topLeft;
  Point bottomRight;
};
 
int main() {
   Point p1, p2;
   p1.x = 0;  // p1 at (0, 3)
   p1.y = 3;
   p2.x = 4;  // p2 at (4, 0)
   p2.y = 0;
 
   cout << "p1 at (" << p1.x << "," << p1.y << ")" << endl;
   cout << "p2 at (" << p2.x << "," << p2.y << ")" << endl;
 
   Rectangle rect;
   rect.topLeft = p1;
   rect.bottomRight = p2;
 
   cout << "Rectangle top-left at (" << rect.topLeft.x
        << "," << rect.topLeft.y << ")" << endl;
   cout << "Rectangle bottom-right at (" << rect.bottomRight.x
        << "," << rect.bottomRight.y << ")" << endl;
 
   return 0;
}
```

````
p1 at (0,3)
p2 at (4,0)
Rectangle top-left at (0,3)
Rectangle bottom-right at (4,0)
````

##### C++ structs C++ 结构体

C++ 将 C 的 `struct` 演变为 OOP 类。遗留的 C 的 `struct` 包含公共数据成员。C++ 的 `struct` ，如同类一样，可能包含访问说明符（ `public` 、 `private` 、 `protected` ）、成员函数、构造函数、析构函数并支持继承。C++ 的 `struct` 和类之间的唯一区别是 `struct` 的成员默认具有 `public` 访问权限，而类的成员默认具有 `private` 访问权限，如果未使用访问说明符。此外，C++ 的 `struct` 默认采用 `public` 继承，而类默认采用 `private` 继承。

## 3Bit-wise Operations位运算

#### 3.1 位逻辑运算

位运算符以逐位的方式对一个或两个操作数执行操作。

| Operator |      Description      |       Usage        |
| :------: | :-------------------: | :----------------: |
|    &     |  Bit-wise AND 按位与  | *expr1* & *expr2*  |
|    \|    |  Bit-wise OR 按位或   | *expr1* \| *expr2* |
|    !     | Bit-wise NOT 按位取反 |      !*expr*       |
|    ^     | Bit-wise XOR 按位异或 | *expr1* ^ *expr2*  |

复合运算符 `&=` 、 `|=` 和 `^=` 也可用

#### 3.2位移操作

位移运算符对操作数执行左移或右移指定的位数。左移用零填充。右移可能用零或符号位填充，具体取决于实现

| Operator |              Usage               |                   Description                   |
| :------: | :------------------------------: | :---------------------------------------------: |
|    <<    | operand << number 操作数 << 数字 | Left-shift and padded with zeros 左移并用零填充 |
|    >>    | operand >> number 操作数 >> 数字 |                Right-shift 右移                 |

## 4 更多函数内容

#### 4.1内联函数

函数调用有其开销（处理参数、管理函数堆栈、分支和返回）。对于简单且短小的函数，您可以使用 `inline` 函数来消除函数调用开销。关键字 `inline` （在函数返回类型之前）建议编译器在原地“展开”函数代码，而不是执行函数调用。例如

```c++
#include <iostream>
using namespace std;
 
inline int max(int n1, int n2) {
   return (n1 > n2) ? n1 : n2;
}
 
int main() {
   int i1 = 5, i2 = 6;
   cout << max(i1, i2) << endl;  // inline request to expand to (i1 > i2) ? i1 : i2
   return 0;
}
```

编译器可能会将第 11 行扩展为：

```c++
cout << (i1 > i2) ? i1 : i2 << endl;
```

展开的语句比调用函数更快。代价是代码体积更大。

Inline 只是一个建议。编译器可能不支持或可能忽略该建议。

##### 内联函数与 #define 宏

在 C 语言中，你可以使用 `#define` 预处理器指令来定义带参数的宏，这些宏会在预处理过程中被展开。例如，

```c++
#include <iostream>
using namespace std;
 
#define SQUARE(x) x*x     // Macro with argument
 
inline int square(int x) { return x*x; }  // inline function
 
int main() {
   cout << SQUARE(5) << endl;  // expand to 5*5 (25)
   int x = 2, y = 3;
   cout << SQUARE(x) << endl;  // expand to x*x (4)
 
   // Problem with the following macro expansions
   cout << SQUARE(5+5) << endl;   // expand to 5+5*5+5 - wrong answer
   cout << square(5+5) << endl;   // Okay square(10)
   cout << SQUARE(x+y) << endl;   // expand to x+y*x+y - wrong answer
   cout << square(x+y) << endl;   // Okay
      // can be fixed using #define SQUARE(x) (x)*(x)
 
   cout << SQUARE(++x) << endl;   // expand to ++x*++x (16) - x increment twice
   cout << x << endl;             // x = 4
   cout << square(++y) << endl;   // Okay ++y, (y*y) (16)
   cout << y << endl;             // y = 4
}
 
```

内联函数比宏展开更受欢迎，如上例所示。

#### 4.2省略号(...)

省略号 ( `...` ) 可以作为函数的最后一个参数使用，表示零个或多个未知类型的参数。编译器会暂停对这些参数的类型检查。例如，

```c++
#include <iostream> 
#include <cstdarg>
using namespace std;  
int sum(int, ...);  
int main() {   
  cout << sum(3, 1, 2, 3) << endl;       // 6   
  cout << sum(5, 1, 2, 3, 4, 5) << endl; // 15    
  return 0; 
}  
int sum(int count, ...) {   
  int sum = 0;    // Ellipses are accessed thru a va_list
  va_list lst;  // Declare a va_list
  // Use function va_start to initialize the va_list,   	// with the list name and the number of parameters.   
  va_start(lst, count);   
  for (int i = 0; i < count; ++i) {      
    // Use function va_arg to read each parameter from va_list,      
    // with the type.      
    sum += va_arg(lst, int);   }   
  // Cleanup the va_list.   
  va_end(lst);    
  return sum; 
}
```

#### 4.3作用域解析运算符

符号 `::` 被称为作用域解析运算符。如果一个全局变量被同名的局部变量隐藏（当然不推荐这样做），你可以使用作用域解析运算符来获取被隐藏的全局变量。例如，

```c++
#include <iostream>
using namespace std;
 
// Global variable
int x = 5;
 
int main() {
   // A local variable having the Same name as a global variable,
   // which hides the global variable
   float x = 55.5f;
 
   // Local
   cout << x << endl;
 
   // Use unary scope resolution operator to retrieve the global variable
   cout << ::x << endl;
 
   return 0;
}
```

#### 4.4命令行参数

在命令行中包含参数，例如在运行程序时，

```
$ gcc -o test test.cpp
```

" `-o test test.cpp` " 被称为命令行参数。每个参数都是一个字符串，所有参数组成一个字符串数组，并传递到程序的 `main()` 函数中。

要处理命令行参数， `main()` 函数应使用此头文件：

```
int main(int argc, char *argv[]) { ...... }
```

第二个参数 `char *argv[]` 捕获字符串数组，而第一个参数捕获数组的大小，或参数的数量。

```c++
#include <iostream>
#include <cstdlib>
using namespace std;
 
int main(int argc, char *argv[]) {
 
   if (argc != 4) {
      cout << "Usage: Arithmetic num1 num2 operator" << endl;
      exit(1);
   }
 
   int operand1 = atoi(argv[1]);  // Parse string to int
   int operand2 = atoi(argv[2]);  // Parse string to int
   char op = argv[3][0];          // Extract first character only
 
   switch (op) {
      case '+':
         cout << operand1 << " + " << operand2 << " = " << operand1 + operand2 << endl;
         break;
      case '-':
         cout << operand1 << " - " << operand2 << " = " << operand1 - operand2 << endl;
         break;
      case '*':
         cout << operand1 << " * " << operand2 << " = " << operand1 * operand2 << endl;
         break;
      case '/':
         cout << operand1 << " / " << operand2 << " = " << operand1 / operand2 << endl;
         break;
      default:
         cout << "Unknown operator" << endl;
         exit(1);
   }
 
   return 0;
}
```

## 5更多关于预处理器的内容

预处理器指令以 `#` 开头（例如，" `#include <stdio.h>` "，" `#define PI 3.14256295` "）。当你编译一个 C/C++ 程序时，这些命令将被预处理以生成实际编译的源文件（例如，在此程序中包含特定的头文件或定义某个宏替换）。

预处理器命令不是 C 语句，也不以分号结尾。

`#include` : `#include` 最常用于将头文件包含到此源文件中以进行后续编译。语法如下：

````
// Syntax
#include header_file
   
// Examples   
#include <stdio.h>      // Search the compiler's include paths
#include "myHeader.h"   // Search the current directory first

````

`#define` , `#undef` : `#define` 可用于定义宏。当宏模式随后在源代码中出现时，它将被宏的主体替换或替代。宏可以带有参数。 ``你可以使用 `#undef` 来取消定义宏。

````
// Define a macro substitution
#define marco_name macro_value
   
// Define a macro with parameters
#define marco_name(args) marco_definition
   
   
   
   
// Un-define a macro name
#undef marco_name






// Example   
#define PI 3.14159256
   
// Example
#define square(x)  (x*x)
#define max(x,y)   ((x > y) ? x : y)
#define REP(i,n)   for (i = 0; i < n; ++i)
#define FOR(i,a,b) for (i = a; i < b; ++i)
   
// Example
#undef PI
````

使用 `#define` 命令进行宏替换时，常见的两个错误是：

```
#define PI = 3.14159265   // 1
#define PI 3.14159265;    // 2
```

在情况 1 中，宏名称“ `PI` ”被定义为“ `= 3.14159265` ”（带有前导 `'='` 符号）。在情况 2 中，它是“ `3.14159265;` ”（带有尾随 `';'` ）。这些肯定会在实际编译过程中在您的程序中触发错误。

`#define` 也常用于定义一个空体的宏名，用于条件指令中，如 `#ifdef` 和 `#ifndef` 。

`#ifdef` , `#ifndef` , `#if` , `#elif` , `#endif` : 条件指令可用于控制程序发送到编译的部分：

```
// if the marco_name is defined
#ifdef macro_name
  ......
#endif
  
// if the macro_name is NOT defined
#ifndef macro_name
  ......
#endif
  
// conditional if else
#if expression
  ......
#elif condition
  ......
#else
  ......
#endif
```

例如，

```
#ifndef SIZE
#define SIZE 1000
#endif
......
```

例如，在头文件中（例如， `myHeader.h` ），通常使用以下指令来防止该头文件在源文件中被多次包含。

```
#ifndef __MY_HEADER
#define __MY_HEADER
#endif
......
```

`#pragma` ：指令 `#pragma` 可用于指导编译器处理系统相关信息。常见用法是：

```
#ifdef _MSC_VER                        // This pragma comment works on MS Visual C++ only, NOT Gcc
#pragma comment(lib, "opengl32.lib")   // Direct compiler to include this library, same as -l command-line option
#endif
```

其他：其他指令包括 `#errors` 和 `#line` ，它们不常用。