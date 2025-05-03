# CPP Basics-1

## 1.变量

### 1.1变量定义

- 名称(或者标识符)
- 类型
- 值

### 1.2变量命名的约定

- 变量名是一个名词，或者由几个词组成的名词短语。第一个词小写，其余词首字母大写，词与词之间没有空格。（如thefontSize ,roomNumber。）

- 选择一个有自描述性的词语。
- 谨慎使用单数和复数名词来区分单数和复数变量。

### 1.3变量声明

要在程序中使用变量，需要先通过声明来“引入"它。

- 在cpp中，需要在使用变量前声明变量的名称。
- cpp是一种“强类型”的语言。变量有类型。一旦变量的类型被声明。就只能存储属于特定类行的值。
- 每个变量只能声明一次。
- 可以在程序的任意位置声明变量。仅仅需要在使用前声明即可。
- 变量的类型在程序中不能更改。

#### *注意*

当一个变量被声明时，在你赋予其值之前，它所包含的**都是垃圾值**。需要注意的是，c/c++不会在使用变量之前初始化它发出警告和错误。

## 2.标识符

标识符来命名变量（或者其他实体，如函数或者类）

### 2.1规则

- 标识符必须以字母或下划线开头。**不能以数字开头** 。以下划线开头的标识符通常保留给系统使用。
- 标识符不能为关键字或者保留字面量（如：int ,double, if ,else ,for)
- 标识符区分**大小写**

#### *注意*

不要使用空白字符作为名称（标识符）

## 3.常量 (const)

常量是不可改变的值，使用关键字**const**声明。

值在执行程序的过程中无法更改。需要在声明时就初始化。

### 3.1常量命名约定

使用大写字母，用下划线连接。如MIIN_VALUE, MAX_SIZE

## 4.表达式

表达式是由运算符（如：' + ', ' - ', ' * ', ' / ')和操作数（变量值或字面值）组合而成。可以计算特定类型的值。

## 5.赋值 （=）

- 写法

  variable = literal - value;

  variable = expression;

如 number = 88;

sum = sum + number ;

### 5.1赋值语句解释：

赋值语句解释：首先计算右侧表达式的值（RHS）以产生一个结果值（rvalue或右值）。然后将rvalue值赋给左侧的变量（LHS）或lvalue。**先计算右侧,在将结果赋给左侧**。

符号' = '被称为赋值运算符，和数学中的含义不同，是赋值而不是等于。

## 6.基本类型

### 6.1整数

整数：char,   short,  int,  long,  long long, 按大小非递减顺序排列。

除了**char**之外的整数都是有符号数（可以存储零、正数和负数）。可以使用关键字 **unsigned ** [char  | short | int | long | long long]来声明无符号整数（只能存储零和正数）。

总共有十种数据类型 -signed 和 unsigned 与 char | short | int | long | long long 组合。

### 6.2字符char

字符：例如 'a' , 'Z' , '0' , '9'。在ASCII中被编码为整数，并以 **char** 类型存储。例如: '0'是48（十进制）或'30H'(16进制)

类型char 可以解释为ASCII代码中的字符，或一个8位整数。与 int 和 long 不同。后者是signed 。而 char 可以根据数据来实现是signed或unsigned。

我们可以用signed char 或 unsigned char来明确声明是 signed 还是 unsigned char。

### 6.3 浮点数

- float : 单精度
- double : 双精度
- long double : 长双精度

### 6.4 bool类型

特殊类型被称为 bool ，值可以为 true 或 false

#### *特殊*

此外，许多C++库函数使用一种**size_t**的类型，它等同于（typedef) 一个 unsigned int ，用于计数 、大小或长度，包含0和正整数。

## 7.sizeof 运算符

C/C++提供了一个一元sizeof 运算符来获取操作数的大小（以字节为单位）。

```c++
#include <iostream>
using namespace std ;

int main(){
    cout <<  "sizeof(char) is "<< sizeof(char) << " bytes " << endl;
    cout <<  "sizeof(short) is "<< sizeof(short) << " bytes " << endl;
    cout <<  "sizeof(int) is "<< sizeof(int) << " bytes " << endl;
    cout <<  "sizeof(long) is "<< sizeof(long) << " bytes " << endl;
    cout <<  "sizeof(long long) is "<< sizeof(long long) << " bytes " << endl;
    cout <<  "sizeof(float) is "<< sizeof(float) << " bytes " << endl;
    cout <<  "sizeof(double) is "<< sizeof(double) << " bytes " << endl;    
    cout <<  "sizeof(long double) is "<< sizeof(long double) << " bytes " << endl;
    cout <<  "sizeof(bool) is "<< sizeof(bool) << " bytes " << endl;
    return 0;
}
```

```
sizeof(char) is 1 bytes
sizeof(short) is 2 bytes
sizeof(int) is 4 bytes
sizeof(long) is 4 bytes
sizeof(long long) is 8 bytes
sizeof(float) is 4 bytes
sizeof(double) is 8 bytes
sizeof(long double) is 8 bytes
sizeof(bool) is 1 bytes
```

 输出结果取决于系统；

## 9.*Header<climits>*

climits头文件（从C的 limits.h移植到C++）包含整数类型的限制信息。

```c++
#include<iostream>
#include<climits>
using namespace std;

int main(){
cout<< "int max = " << INT_MAX << endl;
cout<< "int min = " << INT_MIN << endl;
cout<< "unsigned int max = " << UINT_MAX << endl;
cout<< "long long max = " << LLONG_MAX << endl;
cout<< "long long min = " << LLONG_MIN << endl;
cout<< "unsigned long long max = " << ULLONG_MAX << endl;
cout<< "Bits in char = " << CHAR_BIT << endl;
cout<< "char max = " << CHAR_MAX << endl;
cout<< "char min = " << CHAR_MIN << endl;
cout<< "signed char max = " << SCHAR_MAX << endl;
cout<< "signed char min = " << SCHAR_MIN << endl;
cout<< "unsigned char max = " << UCHAR_MAX << endl;
return 0;
}
```

```
int max = 2147483647
int min = -2147483648
unsigned int max = 4294967295
long long max = 9223372036854775807
long long min = -9223372036854775808
unsigned long long max = 18446744073709551615
Bits in char = 8
char max = 127
char min = -128
signed char max = 127
signed char min = -128
unsigned char max = 255
```

 输出结果取决于系统

- 无符号整数的最小值始终为 0 。

## *10.Headr<cfloat>*

同样，cfloat 头文件从（C的float.h移植而来）包含有关浮点数的限制信息，例如有效数字的最小位数（FLT_DIG，DBL_DIG , LDBL_DIG分别对应float,double , 和long double。尾数的位数(number of bits for mantissa)（FLT_MANT_DIG , FLT_MANT_DIG, LDBL_MANY_DIG)，最大和最小指数数值等

## 11.选择类型

需要选择变量并决定程序中使用的变量类型。例如：使用整数类型来计数和表示整数；浮点数类型来表示带有小数部分的数字，char 用于单个字符， boolean 用于二进制的结果

### 11.1 经验法则

- 使用int 表示整数，使用 double 表示浮点数。只有在有充分理由选择特定精度的时候，才使用byte , short , long和 float。
- 使用int(或unsigned int)进行计数和索引，而不是浮点类型。（float or double)。这是因为整数类型int在操作中更精确且高效。
- 如果可能，使用整数类型。只有当数字包含小数部分时，才使用浮点类型。

There is a subtle difference between int 0 and double 0.0

#### *注意*

在解释一个值之前，必须要先知道该值的类型。

## 12.typedef语句

多次输入" unsigned int "太过麻烦。typedef语句可以用来为现有类型创建新名称（类似#define）。例如：可以为" unsigned int "创建一个名为 " uint "的类型。

- 应该将typedef 紧接着放在 #include之后。
- 谨慎使用typedef 可能会使得程序难以理解。

### 12.1使用方式

```c++
typedef unsigned int uint ;
```

### 12.2size_t

许多C/C++编译器定义了一种名为 size_t的类型。它是 typedef的unsigned int

## 13基本类型和字符串的字面量

字面量是一个特定的常量值。例如：123、-456、3.14、'a'、"Hello".  可以直接赋值给变量；或作为表达式的一部分使用。它们被称为字面量，因为它们明确的标注了它们的值。

### 13.1整数字面量

一个整数，例如123和-456.默认情况下被视为int。

```c++
int number = -123;
int sum = 4567;
int bigSum = 8234567890; // ERROR : this value is outside the range of int 
```

一个int 字面量可以以加号 + 或 - 开头，后面跟着数字。不允许使用逗号或特殊符号。（例如，$或空格）（例如：1,123和$123都是无效的）。也不允许前面有 0 （例如：007也是无效的）

除了默认的十进制整数外，可以使用**前缀 '0' 来表示八进制值**， **前缀 '0x'表示十六进制**，以及**前缀'0b'表示二进制的值（在某些编译器里)**,例如

```c++
int number1 = 1234;		//Decimal
int number2 = 01234;	//octal
int number3 = 0x1abc;	//hexadecimal
int number4 = 0b10001001;	//binary (may not in some compilers)
```

一个 long 字面量通过**后缀 'L' 或 'l' 标识（避免使用小写字母，可能会与数字 1 混淆）**。

一个 long long int 通过**后缀 'LL'标识**。

还可以使用 'U' 表示 unsigned int ，'UL' 表示 unsigned long ，以及 'ULL' 表示unsigned long long int.

```c++
long number = 123456789L;
long sum = 123; 	//int 123 auto-casts to long 123L
long long bigNumber = 98534354353LL;
```

short 字面量不需要后缀。只能使用允许范围内的整数值。

```c++
short smallNumber = 1234567890;		//ERROR: this value is outside the range of shor
short midSizeNumber = -12345;
```

### 13.2浮点字面量

一个带有小数点的数，例如：55.66，-33.44，在默认情况下被是视为double。我们也可以用科学计数法来表示它们。例如：`1.2e3`， -5.5E-6, 其中e或E表示以10为底的的指数。分数部分或指数部分前可以加上 + 或 - 。指数必须是整数。数字中不得有空格或其他字符。

- 必须为float字面量使用 'f' 或 'F'后缀，例如-1.2345F

```c++
float average = 55.66 //ERROR:RHS is a double. Need suffix 'f' for float 
float average = 55.66f;
```

使用后缀 'L' （或 'l'）用于 long double 

### 13.3 字符字面量和转义序列

一个可打印的 `char`字面量通过用一对单引号包围字符来编写，例如 `'z'` ， `'$'` 和 `'9'` 。在 C++ 中，字符使用 8 位 ASCII 码表示，并且可以在算术运算中被视为 8 位有符号整数。换句话说， `char` 和 8 位有符号整数是可以互换的。你还可以将范围在 `[-128, 127]` 内的整数赋值给一个 `char` 变量；以及将 `[0, 255]` 赋值给一个 `unsigned char` 。

```c++
char letter = 'a';             // Same as 97
char anotherLetter = 98;       // Same as the letter 'b'
cout << letter << endl;        // 'a' printed
cout << anotherLetter << endl; // 'b' printed instead of the number
anotherLetter += 2;            // 100 or 'd'
cout << anotherLetter << endl; // 'd' printed
cout << (int)anotherLetter << endl;  // 100 printed
```

| **Escape Sequence** 转义序列 | **Description** 描述                                         | **Hex (Decimal)** 十六进制 (十进制) |
| :--------------------------- | ------------------------------------------------------------ | ----------------------------------- |
| \n                           | New-line (or Line-feed) 新行（或换行）                       | 0AH (10D)                           |
| \r                           | Carriage-return 回车                                         | Carriage-return 回车                |
| \t                           | Tab 制表符                                                   | 09H (9D)                            |
| \\" "                        | Double-quote (needed to include " in double-quoted string) 双引号（需要在双引号字符串中包含 "） | 22H (34D)                           |
| \\'                          | Single-quote 单引号                                          | 27H (39D)                           |
| \\\                          | Back-slash (to resolve ambiguity) 反斜杠（用于解决歧义）     | 5CH (92D)                           |

> [!NOTE]
>
> - 新行（ `0AH` ）和回车（ `0dH` ），分别由 `\n` 和 `\r` 表示，用作行分隔符（或行末，或 EOL）。然而，请注意，Unixes/Mac 使用 `\n` 作为 EOL，Windows 使用 `\r\n` 。
>
> - Horizontal Tab (`09H`) is represented as `\t`.
>   水平制表符 ( `09H` ) 表示为 `\t` 
>
> - To resolve ambiguity, characters back-slash (`\`), single-quote (`'`) and double-quote (`"`) are represented using escape sequences `\\`, `\'` and `\"`, respectively. This is because a single back-slash begins an escape sequence, while single-quotes and double-quotes are used to enclose character and string.
>
>   为了解决歧义，字符反斜杠 (\)、单引号 (') 和双引号 (") 分别使用转义序列 \\、\' 和 \" 表示。这是因为单个反斜杠用于启动转义序列，而单引号和双引号用于括住字符和字符串。
>
> - Other less commonly-used escape sequences are: `\?` or `?`, `\a` for alert or bell, `\b` for backspace, `\f` for form-feed, `\v` for vertical tab. These may not be supported in some consoles.
>   其他不常用的转义序列有： `\?` 或 `?` ， `\a` 用于警报或铃声， `\b` 用于退格， `\f` 用于换页， `\v` 用于垂直制表符。这些在某些控制台中可能不受支持。

### 13.4 The <cctype> Header

`cctype`头文件（从`C`的`cctype.h`移植而来）。提供了诸如 `isalpha()` 、 `isdigit()` 、 `isspace()` 、 `ispunct()` 、 `isalnum()` 、 `isupper()` 、 `islower()` 等函数来确定字符类型；以及 `toupper()` 、 `tolower()` 用于大小写转换。

## 13.5 字符串字面量

字符串字面量可能包含转义序列。在`String` 中。需要使用`\"`来表示双引号，区别结束的双引号。例如：`"\"quoted\""`。在`String`中的单引号不需要转义序列。

```c++
cout << "Use \\\" to place\n a \" withiin\ta\tsting" <<endl;
```

### 13.6 bool Literals bool字面量

- 只有俩个bool字面量，即`true` 和`false`。

```c++
bool done = true;
bool gameOver = false;
int i;
if (i == 9) {
	..........
}
```

在表达式中，`bool`值和字面量被转换成`int 0`表示`false`,以及`1`或非零值表示`true`.

```c++
#include<iostream>
using namespace std;

int main(){
 char gender = 'm';
 bool isMarried = true;
 unsigned short numChildren = 8;
 short yearOfBirth = 1945;
 unsigned int salary = 88000;
 double weight = 88.88;
 float gpa = 3.88f;

 cout << "Gender is " << gender << endl;
 cout << "Is married is " << isMarried << endl;
 cout << "Number  of children is " << numChildren << endl;
 cout << "Year of birth is " << yearOfBirth << endl;
 cout << "Salary is " << salary << endl;
 cout << "Weight is " << weight << endl;
 cout << "GPA is " << gpa << endl;
 return 0;
}
```

```c++
Gender is m
Is married is 1 //true ，false 0;
Number  of children is 8
Year of birth is 1945
Salary is 88000
Weight is 88.88
GPA is 3.88
```

## 14 运算符

### 14.1 算数运算符

C++ 支持以下数字运算符： `short` , `int` , `long` , `long long` , `char` (视为 8 位有符号整数), `unsigned short` , `unsigned int` , `unsigned long` , `unsigned long long` , `unsigned char` , `float` , `double` 和 `long double` 。

| Operator |          Description 描述          |    Usage 使用     |        Examples 示例         |
| :------: | :--------------------------------: | :---------------: | :--------------------------: |
|    *     |        Multiplication 乘法         | *expr1* * *expr2* |  2 * 3 → 6; 3.3 * 1.0 → 3.3  |
|    /     |           Division 除法            | *expr1* / *expr2* |  1 / 2 → 0; 1.0 / 2.0 → 0.5  |
|    %     | Remainder (Modulus) 余数 (Modulus) | *expr1* % *expr2* |    5 % 2 → 1; -5 % 2 → -1    |
|    +     |           Addition 添加            | *expr1* + *expr2* |  1 + 2 → 3; 1.1 + 2.2 → 3.3  |
|    -     |          Subtraction 减法          | *expr1* - *expr2* | 1 - 2 → -1; 1.1 - 2.2 → -1.1 |

以上所有运算符都是二元运算符，即它们需要两个操作数。乘法、除法和取余运算优先于加法和减法。在同一优先级（例如加法和减法）内，表达式从左到右进行计算。例如， `1+2+3-4` 被计算为 `((1+2)+3)-4` 。

> [!CAUTION]
>
> `int /int`会产生一个`int`，结果会被截断，例如`1/2 = 0(而不是 0.5)`。
>
> C/C++ 没有指数（幂）运算符（ `'^'` 是异或运算符，不是指数）。

### 14.2算术表达式

以下算术表达式：

![img](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/JavaBasics_ArithmeticExpression.png)

必须写成 `(1+2*a)/3 + (4*(b+c)*(5-d-e))/f - 6*(7/g+h)` 。不能省略乘法符号 `'*'` （如数学中所示）。

像数学一样，乘法 `'*'` 和除法 `'/'` 优先于加法 `'+'` 和减法 `'-'` 。括号 `()` 具有更高的优先级。运算符 `'+'` 、 `'-'` 、 `'*'` 和 `'/'` 是左结合的。也就是说， `1 + 2 + 3 + 4` 被视为 `(((1+2) + 3) + 4)` 。

### 14.3混合运算符

如果算术运算的两个操作数属于同一类型，则该运算将在该类型中进行，并且结果也属于该类型。例如， `int/int → int; double/double → double` 。

|  Type  |  Example  |                         Operation                         |
| :----: | :-------: | :-------------------------------------------------------: |
|  int   |   2 + 3   |                   int 2 + int 3 → int 5                   |
| double | 2.2 + 3.3 |           double 2.2 + double 3.3 → double 5.5            |
|  mix   |  2 + 3.3  | int 2 + double 3.3 → double 2.0 + double 3.3 → double 5.3 |
|  int   |   1 / 2   |                   int 1 / int 2 → int 0                   |
| double | 1.0 / 2.0 |           double 1.0 / double 2.0 → double 0.5            |
|  mix   |  1 / 2.0  | int 1 / double 2.0 → double 1.0 + double 2.0 → double 0.5 |

```c++
include <iostream>
#include <iomanip>   // needed for formatting floating-point numbers
using namespace std;
 
int main() {
   int i1 = 2, i2 = 4;
   double d1 = 2.5, d2 = 5.0;
 
   // Print floating-points in fixed format with 1 decimal place
   cout << fixed << setprecision(1);  // need <iomanip>
 
   cout << i1 << " + " << i2 << " = " << i1+i2 << endl;  // 6
   cout << d1 << " + " << d2 << " = " << d1+d2 << endl;  // 7.5
   cout << i1 << " + " << d2 << " = " << i1+d2 << endl;  // 7.0  <==
 
   cout << i1 << " - " << i2 << " = " << i1-i2 << endl;  // -2
   cout << d1 << " - " << d2 << " = " << d1-d2 << endl;  // -2.5
   cout << i1 << " - " << d2 << " = " << i1-d2 << endl;  // -3.0 <==
 
   cout << i1 << " * " << i2 << " = " << i1*i2 << endl;  // 8
   cout << d1 << " * " << d2 << " = " << d1*d2 << endl;  // 12.5
   cout << i1 << " * " << d2 << " = " << i1*d2 << endl;  // 10.0 <==
 
   cout << i1 << " / " << i2 << " = " << i1/i2 << endl;  // 0    <==
   cout << d1 << " / " << d2 << " = " << d1/d2 << endl;  // 0.5
   cout << i1 << " / " << d2 << " = " << i1/d2 << endl;  // 0.4  <==
   return 0;
}
```

在算术运算中，如果结果值超出其范围（即溢出或下溢），则会回绕。C++ 运行时不会发出错误/警告消息，但会产生错误的结果。

重要的是要注意，检查溢出/下溢是程序员的责任。

此功能是一个遗留设计，当时处理器速度较慢。检查溢出/下溢会消耗计算能力并降低性能。

检查算术溢出（称为安全编码）是繁琐的。谷歌搜索“INT32-C. Ensure that operations on signed integers do not result in overflow” @ www.securecoding.cert.org。

### 14.4.复合赋值运算符

除了之前描述的常见简单赋值运算符 `'='` 外，C++ 还提供了所谓的复合赋值运算符，如下所列：

| Operator |      Usage      |                    Description 描述                    |       Example 示例        |
| :------: | :-------------: | :----------------------------------------------------: | :-----------------------: |
|    =     | *var* = *expr*  | Assign the value of the LHS to the variable at the RHS |          x = 5;           |
|    +=    | *var* += *expr* |             same as *var* = *var* + *expr*             | x += 5; same as x = x + 5 |
|    -=    | *var* -= *expr* |             same as *var* = *var* - *expr*             | x -= 5; same as x = x - 5 |
|    *=    | *var* *= *expr* |             same as *var* = *var* * *expr*             | x *= 5; same as x = x * 5 |
|    /=    | *var* /= *expr* |             same as *var* = *var* / *expr*             | x /= 5; same as x = x / 5 |
|    %=    | *var* %= *expr* |             same as *var* = *var* % *expr*             | x %= 5; same as x = x % 5 |

### 14.5递增/递减运算符

C++ 支持这些一元算术运算符：递增 `'++'` 和递减 `'--'` 。

| Operator | Example  |             Result             |
| :------: | :------: | :----------------------------: |
|    ++    | x++; ++x | Increment by 1, same as x += 1 |
|    --    | x--; --x | Decrement by 1, same as x -= 1 |

```c++
#include <iostream>
using namespace std;
 
int main() {
   int mark = 76;        // declare & assign
   cout << mark << endl; // 76
 
   mark++;               // increase by 1 (post-increment)
   cout << mark << endl; // 77
 
   ++mark;               // increase by 1 (pre-increment)
   cout << mark << endl; // 78
 
   mark = mark + 1;      // also increase by 1 (or mark += 1)
   cout << mark << endl; // 79
 
   mark--;               // decrease by 1 (post-decrement)
   cout << mark << endl; // 78
 
   --mark;               // decrease by 1 (pre-decrement)
   cout << mark << endl; // 77
 
   mark = mark - 1;      // also decrease by 1 (or mark -= 1)
   cout << mark << endl; // 76
   return 0;
}
```

一元递增/递减运算符可以放在操作数之前（前缀运算符），也可以放在操作数之后（后缀运算符）。它们在操作中具有不同的含义。

| Operator |                         Description                          | Example  |             Result             |
| :------: | :----------------------------------------------------------: | :------: | :----------------------------: |
|  ++var   | Pre-Increment 前置递增 Increment *var*, then use the new value of *var* 增加 var 的值，然后使用 var 的新值 | y = ++x; |      same as x=x+1; y=x;       |
|  var++   | Post-Increment 后增量 Use the old value of *var*, then increment *var* 使用 var 的旧值，然后增加 var 的值 | y = x++; | same as oldX=x; x=x+1; y=oldX; |
|  --var   |                     Pre-Decrement 预递减                     | y = --x; |      same as x=x-1; y=x;       |
|  var--   |                    Post-Decrement 后递减                     | y = x--; | same as oldX=x; x=x-1; y=oldX; |

如果 '++' 或 '--' 涉及另一个操作，那么前置或后置顺序对于指定两个操作的顺序非常重要。

```c++
x = 5;
cout << x++ << endl;  // Save x (5); Increment x (=6); Print old x (5).
x = 5;
cout << ++x << endl;  // Increment x (=6); Print x (6).
// This is confusing! Try to avoid! What is i=++i? What is i=i++?
```

前缀运算符（例如， `++i` ）在某些情况下可能比后缀运算符（例如， `i++` ）更高效。

### 14.6.隐式类型转换与显式类型转换

将一个值从一种类型转换为另一种类型称为类型转换（或类型转换）。类型转换有两种：

- 编译器自动执行的隐式类型转换

- 通过一元类型转换运算符以 (new-type)operand 或 new-type(operand) 的形式进行显式类型转换。

#### 14.6.1隐式（自动）类型转换

将一个基本（内置）类型的值赋给另一个基本类型的变量时，如果这两种类型兼容，C++ 会自动将该值转换为接收类型。例如，

- 如果将一个 `int` 值赋值给一个 `double` 变量，编译器会自动将 `int` 值转换为 `double` double（例如，从 1 转换为 1.0），然后将其赋值给 `double` 变量
- 如果将一个 `double` 值赋给一个 `int` 变量，编译器会自动将 `double` 值转换为 `int` 值（例如，从 1.2 转换为 1），并将其赋给 `int` 变量。小数部分将被截断并丢失。一些编译器会发出警告/错误“可能丢失精度”；而其他编译器则不会。

```c++
#include <iostream>
#include <iomanip>
using namespace std;
int main() {
 int i;
 double d;

 cout << fixed << setprecision(1);
 i = 3;
 d = i;
 cout << " d = " << d << endl; //3.0

 d = 5.5;
 i = d;
 cout << " i = " << i << endl; //5 (int)

 i = 6.6;
 cout << " i = "<< i << endl; // 6(int)
 return 0;
}
```

如果两种类型不兼容，C++ 不会执行自动类型转换，

#### 14.6.2 显式类型转换

可以通过所谓的单目类型转换运算符以 `(*new-type*)*operand*` 或 `*new-type*(*operand*)` 的形式显式执行类型转换。类型转换运算符接受特定类型的一个操作数，并返回新类型中的等效值。请注意，这是一个产生结果值的操作，类似于加法操作，尽管加法涉及两个操作数。例如，

```c++
// Print floating-point number in fixed format with 1 decimal point (need <iomanip>)
cout << fixed << setprecision(1);
 
cout << (double)5 << endl;  // int 5 → double 5.0
cout << (int)5.5 << endl;   // double 5.5 → int 5
 
double aDouble = 5.6;
int anInt = (int)aDouble; // return 5 and assign to anInt. aDouble does not change!
 
// C++ also supports function-style type cast.
cout << double(5) << endl;     // 5.0
cout << int(5.5) << endl;      // 5
cout << int(aDouble) << endl;  // 5
```

假设你想找到介于 `1` 和 `100` 之间的整数的平均值（以 `double` 表示）。研究以下代码：

```c++
#include <iostream>
#include <iomanip>
using namespace std;
 
int main() {
   int sum = 0;
   double average;
   for (int number = 1; number <= 100; ++number) {
      sum += number;      // Final sum is int 5050
   }
   average = sum / 100;   // Won't work (average = 50.0 instead of 50.5)
   cout << fixed << setprecision(1);
   cout << "Average is " << average << endl;  // Average is 50.0
   return 0;
}
```

无法获得小数部分，尽管 `average` 是一个 `double` 。这是因为 `sum` 和 `100` 都是 `int` 。除法的结果是一个 `int` ，然后被隐式转换为 `double` 并赋值给 `double` 变量 `average` 。要获得正确答案，你可以选择以下任一方式：

```c++
average = (double)sum / 100;     // Cast sum from int to double before division
average = sum / (double)100;     // Cast 100 from int to double before division
average = sum / 100.0;
average = (double)(sum / 100);   // Won't work. why?
 //先 （int 5050/100) 然后（double 50)
// C++ also support function-style type casting in the form of new-type(operand)
average = double(sum) / 100;     // Same as (double)sum / 100
```

Example

```c++
/* Test Type Casting (TestTypeCast.cpp) */
#include <iostream>
#include <iomanip>
using namespace std;
 
int main() {
   // Print floating-point number in fixed format with 1 decimal place
   cout << fixed << setprecision(1);
 
   // Test explicit type casting
   int i1 = 4, i2 = 8;
   cout << i1 / i2 << endl;           // 0
   cout << (double)i1 / i2 << endl;   // 0.5
   cout << i1 / (double)i2 << endl;   // 0.5
   cout << (double)(i1 / i2) << endl; // 0.0
 
   double d1 = 5.5, d2 = 6.6;
   cout << (int)d1 / i2 << endl;      // 0
   cout << (int)(d1 / i2) << endl;    // 0
 
   // Test implicit type casting
   d1 = i1;             // int implicitly casts to double
   cout << d1 << endl;  // 4.0
   i2 = d2;             // double truncates to int! (Warning?)
   cout << i2 << endl;  // 6
}
```

```c++
/*
 * Converting between Celsius and Fahrenheit (ConvertTemperature.cpp)
 *   Celsius = (5/9)(Fahrenheit–32)
 *   Fahrenheit = (9/5)Celsius+32
 */
#include <iostream>
#include <iomanip>   // needed for formatting floating-point numbers
using namespace std;
 
int main() {
   double celsius, fahrenheit;
 
   // Format floating-points in fixed with 2 decimal places
   cout << fixed << setprecision(2);
 
   cout << "Enter the temperature in celsius: ";
   cin >> celsius;
   fahrenheit = celsius*9/5 + 32;
   // 9/5*celsius + 32 gives wrong answer! Why?
   cout << celsius << "C is " << fahrenheit << "F" << endl;
 
   cout << "Enter the temperature in fahrenheit: ";
   cin >> fahrenheit;
   celsius =  (fahrenheit - 32)*5/9;
   // 5/9*(fahrenheit - 32) gives wrong answer! Why?
   cout << fahrenheit << "F is " << celsius << "C" << endl;
   return 0;
}
```

### static-cast<type>

C++ 引入了一个名为 `static_cast<*type*>` 的新运算符来执行类型转换（因为之前提到的常规转换过于宽松，可能会产生预期结果）。 `static_cast` 如果转换失败，则会发出错误信号。例如，

```c++
double d = 5.5;
int i = static_cast<int>(d);
float f = static_cast<float>(i);
long l = static_cast<logn>(d);
```

### 14.7关系和逻辑运算符

通常情况下，你需要在决定采取何种行动之前比较两个值，例如，如果 mark 大于或等于 50，则打印 "PASS"。

C++ 提供了六个比较运算符（或关系运算符）：

| Operator |             Description             |       Usage        | Example (x=5, y=8) |
| :------: | :---------------------------------: | :----------------: | :----------------: |
|    ==    |            Equal to 等于            | *expr1* == *expr2* |  (x == y) → false  |
|    !=    |         Not Equal to 不等于         | *expr1* != *expr2* |  (x != y) → true   |
|    >     |          Greater than 大于          | *expr1* > *expr2*  |  (x > y) → false   |
|    >=    | Greater than or equal to 大于或等于 | *expr1* >= *expr2* |  (x >= 5) → true   |
|    <     |           Less than 小于            | *expr1* < *expr2*  |  (y < 8) → false   |
|    <=    |  Less than or equal to 小于或等于   | *expr1* >= *expr2* |  (y <= 8) → true   |

在 C++ 中，这些比较操作返回一个值为 `bool` 的 `false` (0) 或 `true` (1 或非零值)。

每次比较操作涉及两个操作数，例如 `x <= 100` 。在编程中写 `1 < x < 100` 是无效的。相反，你需要拆分出两个比较操作 `x > 1` ， `x < 100` ，并使用逻辑与运算符连接，即 `(x > 1) && (x < 100)` ，其中 `&&` 表示与运算符。

C++ 提供了四个逻辑运算符（仅对 `boolean` 操作数进行操作）：

| Operator |     Description      |        Usage         |
| :------: | :------------------: | :------------------: |
|    &&    |  Logical AND 逻辑与  |  *expr1* && *expr2*  |
|   \|\|   |  Logical OR 逻辑或   | *expr1* \|\| *expr2* |
|    !     |  Logical NOT 逻辑非  |       !*expr*        |
|    ^     | Logical XOR 逻辑异或 |  *expr1* ^ *expr2*   |

真值表如下：

|   AND (&&)    |   true   |   false   |
| :-----------: | :------: | :-------: |
|     true      |   true   |   false   |
|     false     |  false   |   false   |
| **OR (\|\|)** | **true** | **false** |
|     true      |   true   |   true    |
|     false     |   true   |   false   |
|  **NOT (!)**  | **true** | **false** |
|               |  false   |   true    |
|  **XOR (^)**  | **true** | **false** |
|     true      |  false   |   true    |
|     false     |   true   |   false   |

```c++
// Return true if x is between 0 and 100 (inclusive)
(x >= 0) && (x <= 100)
// wrong to use 0 <= x <= 100
  
// Return true if x is outside 0 and 100 (inclusive)
(x < 0) || (x > 100)   //or
!((x >= 0) && (x <= 100))
 
// Return true if year is a leap year
// A year is a leap year if it is divisible by 4 but not by 100, or it is divisible by 400.
((year % 4 == 0) && (year % 100 != 0)) || (year % 400 == 0)// 如果 x 在 0 到 100 之间（包含边界），返回 true (x >= 0) && (x <= 100) // 错误使用 0 <= x <= 100
// 如果 x 在 0 到 100 之外（包含边界），返回 true (x < 0) || (x > 100) // 或 !((x >= 0) && (x <= 100))
// 如果 year 是闰年，返回 true
// 如果一个年份能被 4 整除但不能被 100 整除，或者能被 400 整除，则为闰年。((year % 4 == 0) && (year % 100 != 0)) || (year % 400 == 0)
```

## 15 Flow Control

有三种基本的流程控制结构 - 顺序、条件（或决策）和循环（或迭代），如下图所示。

![structure constructs](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/Flowchart_FlowControl.png)

### 15.1顺序流程控制

一个程序是一系列指令的集合。顺序流是最常见且最直接的方式，其中编程语句按照它们书写的顺序执行——从上到下依次进行。

### 15.2  条件（决策流程图）

| Syntax 语法                                                  | Example 示例                                                 |                       Flowchart 流程图                       |
| :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------: |
| `// if-then `<br />**if (** *booleanExpression* **) {**   <br />*true-block* **;** **}** | if (mark >= 50) {   <br />cout << "Congratulation!" << endl;   <br />cout << "Keep it up!" << endl; <br />} | ![img](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/Flowchart_IfThen.png) |
| `// if-then-else `<br />**if (** *booleanExpression* **) {** <br />  *true-block* **;**<br /> **} else {**   *false-block* **;** **}** | if (mark >= 50) { <br />  cout << "Congratulation!" << endl; <br />  cout << "Keep it up!" << endl; <br />} else {   cout << "Try Harder!" << endl; <br />} | ![img](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/Flowchart_IfElse.png) |
| `// nested-if`<br /> **if (** *booleanExpr-1* **) {**  <br /> *block-1* **; <br />} else if (** *booleanExpr-2* **) {**<br />*block-2* **; <br />} else if (** *booleanExpr-3* **) {**   <br />*block-3* **;<br /> } else if (** *booleanExpr-4* **) {**  <br /> ......<br /> **} else {**   *elseBlock* **;<br /> }** | if (mark >= 80) { <br />  cout << "A" << endl; <br />} else if (mark >= 70) {   <br />cout << "B" << endl; <br />} else if (mark >= 60) { <br />  cout << "C" << endl; <br />} else if (mark >= 50) {   <br />cout << "D" << endl; <br />} else {   cout << "F" << endl;<br /> } | ![img](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/Flowchart_NestedIf.png) |
| `// switch-case` <br />**switch (** *selector* **) {  <br /> case** *value-1*: <br />*block-1*; **break;   <br />case** *value-2*:      <br />*block-2*; **break; **  <br />**case** *value-3*:     <br />*block-3*; **break;**<br />   ......   <br />**case** *value-n*:  <br /> *block-n*; **break;**   <br />**default:**     <br />*default-block*; <br />**}** | char oper; int num1, num2, result; <br />...... <br />switch (oper) {  <br /> case '+':     <br /> result = num1 + num2; break;   <br />case '-':      <br /> result = num1 - num2; break;  <br /> case '*':      <br /> result = num1 * num2; break;   <br />case '/':       <br />result = num1 / num2; break;   <br />default:      <br />cout << "Unknown operator" << endl; <br />} | ![img](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/Flowchart_SwitchCase.png) |

“switch-case” 是“nested-if”的替代。在*switch-case*语句中，`break`每个 case 都需要一个语句。如果`break`缺少一个，则执行将流向下一个 case。您可以使用`int`或`char`变量作为 case*选择器*。

条件运算符：条件运算符是一个三元（3 个操作数）运算符，形式为 `booleanExpr ? trueExpr : falseExpr` 。根据 `booleanExpr` 的情况，它会评估并返回 `trueExpr` 或 `falseExpr` 的值。

|              Syntax 语法               |                         Example 示例                         |
| :------------------------------------: | :----------------------------------------------------------: |
| `booleanExpr ? trueExpr :falseExpr   ` | `cout << (mark >= 50) ? "PASS" : "FAIL" << endl;   // return either "PASS" or "FAIL", and put to cout max = (a > b) ? a : b;   // RHS returns a or b abs = (a > 0) ? a : -a;  // RHS returns a or -a   ` |

大括号：如果块内只有一条语句，您可以省略大括号 `{ }` 。例如，

```c++
if (mark >= 50) 
   cout << "PASS" << endl;   // Only one statement, can omit { } but not recommended
else {                           // more than one statements, need { }
   cout << "FAIL" << endl;
   cout << "Try Harder!" << endl;
}
```

建议保留大括号，即使块中只有一条语句，以提高程序的可读性。

### 15.3循环流控制

有几种类型的循环：for-loop、while-do 和 do-while。

|                         Syntax 语法                          |                         Example 示例                         |                       Flowchart 流程图                       |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| `// for-loop `<br />**for (init;*test* *post-proc***) **{**<br />  *body* **;** <br />**}** | `// Sum from 1 to 1000 `<br />int sum = 0; <br />for (int number = 1; number <= 1000; ++number) {  <br />sum += number; <br />} | ![img](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/Flowchart_For.png) |
| `// while-do `<br />**while (** *condition* **) {**   <br />*body* **; <br />}** | int sum = 0, number = 1; <br />while (number <= 1000) {   <br />sum += number;  <br /> ++number;<br /> } | ![img](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/Flowchart_While.png) |
| `// do-while`<br /> **do {**   *body* ; <br />} <br />while ( *condition* ) ; | int sum = 0, number = 1; <br />do {   sum += number;  <br /> ++number; <br />} while (number <= 1000); | ![img](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/Flowchart_DoWhile.png) |

假设程序提示用户输入一个介于 `1` 到 `10` 之间的数字，并检查输入是否有效，使用带有布尔标志的 do-while 循环可能更合适。

```c++
// Input with validity check
bool valid = false;
int number;
do {
  // prompt user to enter an int between 1 and 10
  ......
  // if the number entered is valid, set done to exit the loop
  if (number >=1 && number <= 10) {
     valid = true;
  }
} while (!valid);   // Need a semi-colon to terminate do-while
```

使用`while-do`的例子

```C++
// Game loop
bool gameOver = false;
while (!gameOver) {
   // play the game
   ......
   // Update the game state 
   // Set gameOver to true if appropriate to exit the game loop
   ......
}
```

示例（计数器控制循环）：提示用户输入一个上限。计算从 1 到给定上限的整数之和，并计算其平均值。

```c++
#include<iostream>
using namespace std;
int main() {
	int sum = 0;
	int upperbound;
	cout << "Enter upperbound : ";
	cin >> upperbound;

	for (int number = 1; number <= upperbound; ++number) {
		sum += number;
	}
	cout << "sum is " << sum << endl;
	cout << "Average is " << (double)sum / upperbound << endl;

	int count = 0;
	sum = 0;
	for (int number = 1; number <= upperbound; number = number + 2) {
		++count;
		sum += number;
	}
	cout << "Sum of odd number is " << sum << endl;
	cout << "Average is " << (double)sum / upperbound << endl;
	
}
```

```c++
Enter upperbound : 1000
sum is 500500
Average is 500.5
Sum of odd number is 250000
Average is 250
```

示例（哨兵控制循环）：提示用户输入正整数，并显示计数、最大值、最小值和平均值。当用户输入 -1 时终止。

```c++
#include<iostream>
#include<climits>
#include<iomanip>

using namespace std;


int main() {
	int numberIn;
	int count = 0;
	int sum = 0;
	int max = 0;
	int min = INT_MAX;
	int sentinel = -1;

	cout << "enter a positive integer or " << sentinel << "to exit: ";
	while (cin >> numberIn && numberIn != sentinel) {

		if (numberIn > 0) {
			++count;
			sum += numberIn;
			if (max < numberIn)max = numberIn;
			if (min > numberIn)min = numberIn;
		}else {
			cout << "error: input must be positive! try again..." << endl;
		}
		cout << "Enter a positive integer or " << sentinel << " to exit: ";
	}
	cout << endl;
	cout << "Count is " << count << endl;
	if (count > 0) {
		cout << "Maximum is " << max << endl;
		cout << "Minimum is " << min << endl;
		cout << fixed << setprecision(2);
		cout << "Average is  " << (double)sum / count << endl;
	}
}
```

- 在计算中，哨兵值是一个特殊的值，用于表示数据的结束（例如，使用负值来结束一系列正值、文件结束符、null 终止字符串中的 null 字符）。在这个例子中，我们使用-1 作为哨兵值来表示输入的结束，这是一系列正整数。为了灵活性和易于维护，我们没有硬编码-1 的值，而是使用一个名为 `sentinel` 的变量。
- 请注意读取输入时的 while 循环模式。在这种模式下，需要重复提示语句。

```c++
cout << fixed << setprecision(n);
```

- 要控制浮点数的精度，请使用：其中 n 是小数点后的位数。您需要包含 `<iomanip>` 头文件。 `setprecision()` 是粘性的。也就是说，它将一直有效，直到设置另一个值。

### 15.4 中断循环流程- "break"和"continue"

`break` 语句会跳出并退出当前（最内层）循环

`continue` 语句会中止当前迭代，并继续执行当前（最内层）循环的下一个迭代。

`break` 和 `continue` 是较差的结构，因为它们难以阅读和理解。只有在绝对必要时才使用它们。你总是可以编写相同的程序，而不使用 `break` 和 `continue` 。

示例（中断）：以下程序列出了 2 到一个上限之间的非质数。

```c++
#include <iostream>
#include <cmath>
using namespace std;
 
int main() {
   int upperbound;
   cout << "Enter the upperbound: ";
   cin >> upperbound;
   for (int number = 2; number <= upperbound; ++number) {
      // Not a prime, if there is a factor between 2 and sqrt(number)
      int maxFactor = (int)sqrt(number);
      for (int factor = 2; factor <= maxFactor; ++factor) {
         if (number % factor == 0) {   // Factor?
            cout << number << " ";
            break;   // A factor found, no need to search for more factors
         }
      }
   }
   cout << endl;
   return 0;
}
```

重写上面的程序，以列出所有的质数。使用一个名为 `isPrime` 的 `boolean` 标志来指示当前的 `number` 是否为素数。然后用它来控制打印。

```c++
#include <iostream>
#include <cmath>
using namespace std;
 
int main() {
   int upperbound;
   cout << "Enter the upperbound: ";
   cin >> upperbound;
   for (int number = 2; number <= upperbound; ++number) {
      // Not a prime, if there is a factor between 2 and sqrt(number)
      int maxFactor = (int)sqrt(number);
      bool isPrime = true;  // boolean flag to indicate whether number is a prime
      for (int factor = 2; factor <= maxFactor; ++factor) {
         if (number % factor == 0) {   // Factor?
            isPrime = false;   // number is not a prime
            break;   // A factor found, no need to search for more factors
         }
      }
      if (isPrime) cout << number << " ";
   }
   cout << endl;
   return 0;
}
```

重写上面的程序，不使用 `break` 语句。使用 `while` 循环（由 `boolean` 标志控制）来代替带有 `break` 的 `for` 循环。

```c++
#include <iostream>
#include <cmath>
using namespace std;
 
int main() {
   int upperbound;
   cout << "Enter the upperbound: ";
   cin >> upperbound;
 
   for (int number = 2; number <= upperbound; ++number) {
      // Not prime, if there is a factor between 2 and sqrt of number
      int maxFactor = (int)sqrt(number);
      bool isPrime = true;
      int factor = 2;
      while (isPrime && factor <= maxFactor) {
         if (number % factor == 0) {   // Factor of number?
             isPrime = false;
         }
         ++factor;
      }
      if (isPrime) cout << number << " ";
   }
   cout << endl;
   return 0;
}
```

示例（继续）：

```c++
// Sum 1 to upperbound, exclude 11, 22, 33,...
int upperbound = 100;
int sum = 0;
for (int number = 1; number <= upperbound; ++number) {
   if (number % 11 == 0) continue;  // Skip the rest of the loop body, continue to the next iteration
   sum += number;
}
// It is better to re-write the loop as:
for (int number = 1; number <= upperbound; ++number) {
   if (number % 11 != 0) sum += number;
```

示例（break 和 continue）：研究以下程序。

```c++
#include <iostream>
using namespace std;
 
int main() {
   int number = 1;
   while (true) {
      ++number;
      if ((number % 3) == 0) continue;
      if (number == 133) break;
      if ((number % 2) == 0) {
         number += 3;
      } else {
         number -= 3;
      }
      cout << number << " ";
   }
   cout << endl;
   return 0;
}
```

### 15.5 终止程序

有几种方法可以在到达程序语句结束之前终止你的程序。

exit(): 可以调用函数 `exit(int exitCode)` ，在 `<cstdlib>` 中（从 C 的“ `stdlib.h` ”移植而来），以终止程序并将控制权返回给操作系统。按照惯例，返回代码为零表示正常终止；而非零的 `exitCode` (-1) 表示异常终止。例如，

abort()：头文件<cstdlib>还提供了一个名为abort()的函数，可用于异常终止程序

```c++
if (errorCount > 10) {
   cout << "too many errors" << endl;
   exit(-1);  // Terminate the program
              // OR abort();
}
```

"return" 语句：您也可以在 `main()` 函数中使用 " `return *returnValue*` " 语句来终止程序并将控制权返回给操作系统。例如，

```c++
int main() {
   ...
   if (errorCount > 10) {
      cout << "too many errors" << endl;
      return -1;  // Terminate and return control to OS from main()
   }
   ...
}
```

### 15.6 嵌套循环

下面的图表展示了嵌套的 for 循环，即一个内部 for 循环嵌套在一个外部 for 循环中。

![NestedForLoop.png](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/NestedForLoop.png)

```c++
#include <iostream>
using namespace std;
 
int main() {
   int size = 8;
   for (int row = 1; row <= size; ++row) {     // Outer loop to print all the rows
      for (int col = 1; col <= size; ++col) {  // Inner loop to print all the columns of each row
         cout << "# ";
      }
      cout << endl;   // A row ended, bring the cursor to the next line
   }
 
   return 0;
}
```

```
# # # # # # # #
# # # # # # # #
# # # # # # # #
# # # # # # # #
# # # # # # # #
# # # # # # # #
# # # # # # # #
# # # # # # # #
```

这个程序包含两个嵌套的 for 循环。内层循环用于打印一行八个“ `# `”，随后打印一个换行符。外层循环重复内层循环以打印所有行。

假设你想打印这个图案

```
# # # # # # # #
 # # # # # # # #
# # # # # # # #
 # # # # # # # #
# # # # # # # #
 # # # # # # # #
# # # # # # # #
 # # # # # # # #
```

你需要在偶数行打印一个额外的空格。你可以在第 8 行之前添加以下语句来实现。

```
if ((row % 2) == 0) {   // print a leading space for even-numbered rows
   cout << " ";
}
```

Print these patterns using nested loop (in a program called `PrintPattern1x`). Use a variable called `size` for the size of the pattern and try out various sizes. You should use as few printing statements as possible.

```
 # * # * # * # *    # # # # # # # #    # # # # # # # #    1                                1
# * # * # * # *     # # # # # # #        # # # # # # #    2 1                            1 2
 # * # * # * # *    # # # # # #            # # # # # #    3 2 1                        1 2 3
# * # * # * # *     # # # # #                # # # # #    4 3 2 1                    1 2 3 4
 # * # * # * # *    # # # #                    # # # #    5 4 3 2 1                1 2 3 4 5
# * # * # * # *     # # #                        # # #    6 5 4 3 2 1            1 2 3 4 5 6
 # * # * # * # *    # #                            # #    7 6 5 4 3 2 1        1 2 3 4 5 6 7
# * # * # * # *     #                                #    8 7 6 5 4 3 2 1    1 2 3 4 5 6 7 8
     (a)                  (b)                (c)                (d)                (e)
```

(a)

```c++
#include <iostream>
using namespace std;

int main() {
	int size = 8;
	for (int row = 1; row <= size; ++row) {
		if ((row % 2) != 0) {
			cout << " ";
		}
		for (int col = 1; col <= size; ++col) {
			if ((col % 2) != 0) {
				cout << "# ";
			}else {
				cout << "* ";
			}
		}
		cout << endl;
	}
	cout << endl;
	
	cout << "(b)" << endl;
	for (int row = 1; row <= size; ++row) {
		for (int col = 1; col <= size - row + 1; ++col) {
			cout << "# ";
		}
		cout << endl;
	}
	cout << endl;

	cout << "(c)" << endl;
	for (int row = 1; row <= size; ++row) {
		for (int col = 1; col <= size ; ++col) {
			if (col >= row) {
				cout << "# ";
			}
			else {
				cout << "  ";
			}
		}
		cout << endl;
	}
	cout << endl;

	cout << "(d)" << endl;
	for (int row = 1; row <= size; ++row) {
		for (int num = row; num >=1; --num) {
			cout << num<<" ";
		}
		cout << endl;
	}
	cout << endl;
	cout << "(e)" << endl;
	for (int row = 1; row <= size; ++row) {
		for (int col = 1; col <= size; ++col) {
			if (col >= size - row +1) {
				int num = col - (size - row);
				cout << num << " ";
			}
			else {
				cout << "  ";
			}
		}
		cout << endl;
	}
}
```

乘法表打印（`if-else`)

```c++
#include<iostream>
using namespace std;

int main() {
	int size = 9;
	for (int row = 1; row <= size; ++row) {
		for (int col = 1; col <= size; ++col) {
			int product = row * col;
			if (product < 10) {
				cout << "  " << product;
			}
			else {
				cout << " " << product;
			}
		}
		cout << endl;
	}
}
```

使用嵌套循环打印这些图案。

```
# # # # # # #      # # # # # # #      # # # # # # #      # # # # # # #      # # # # # # #
#           #        #                          #          #       #        # #       # #
#           #          #                      #              #   #          #   #   #   #
#           #            #                  #                  #            #     #     #
#           #              #              #                  #   #          #   #   #   #
#           #                #          #                  #       #        # #       # #
# # # # # # #      # # # # # # #      # # # # # # #      # # # # # # #      # # # # # # #
     (a)                 (b)               (c)                (d)                (e)
```

### 15.7流量控制的一些问题

**Dangling** else: 悬挂else问题可以如下说明：

```c++
if (i == 0)
   if (j == 0)
      cout << "i and j are zero" << endl;
else cout << "i is not zero" << endl;   // intend for the outer-if
```

上面的代码中的 `else` 子句在语法上适用于 outer-if 和 inner-if。C++ 编译器总是将 `else` 子句与最内层的 if（即最近的 if）相关联。悬挂的 else 可以通过使用明确的括号来解决。上面的代码在逻辑上是不正确的，需要如下所示使用明确的括号。

```c++
f ( i == 0) {
   if (j == 0) cout << "i and j are zero" << endl;
} else {
   cout << "i is not zero" << endl;   // non-ambiguous for outer-if
}
```

**Endless Loop:** The following constructs:
无穷循环：以下结构：

```
while (true) { ...... }
```

常被使用。它看起来像是一个无限循环（或无穷循环），但通常通过循环体内的 `break` 或 `return` 语句来终止。这种代码难以阅读 - 如果可能，通过重写条件来避免。

## 16 编写正确且优秀的程序

编写能够产生正确结果程序非常重要。同样重要的是编写其他人（以及三天后的自己）能够理解的程序，这样的程序才是能被称为好的程序。

### 建议

- 遵循既定的惯例，以便每个人都能有相同的理解基础。
- 源代码的格式和布局应使用适当的缩进、空格和空行。缩进使用3或4个空格，并使用空行分隔代码段。
- 选择具有自描述性和意义的好名字（如`row`,`col`,`size`,`xMax`,`numStudents`.)不要使用没有意义的名称，例如 a, b, c, d.避免使用单个字母的名称，除非是常见名称如 x, y, z,用于坐标，i用于索引。
- 提供注释以解释重要且突出的概念。大量注释你的代码。
- 在编写程序时同时编写程序文档。
- 避免使用非结构化的构造，例如 `break` 和 `continue` ，这些构造难以理解。
- 使用“等宽”字体（如 Consola、Courier New、Courier）来编写/显示您的程序。

### 16.1 编程错误

编程错误通常分为三类：

- 编译错误（或语法错误）：可以轻松修复。
- 运行时错误：程序提前停止而未产生结果 - 也可以轻松修复。
- 逻辑错误：程序可以完成但产生错误的结果。如果程序总是产生错误结果，很容易检测。如果程序大部分时间产生正确结果，但有时产生错误结果，则极难修复。例如，

```c++
// Can compile and execute, but give wrong result – sometimes!
if (mark > 50) {
   cout << "PASS" << endl;
} else {
   cout << "FAIL" << endl;
}
```

如果在生产前没有发现这类错误，后果会非常严重。编写优质程序有助于减少和检测这些错误。需要一个好的测试策略来确保程序的正确性。

## 17 字符串

C++支持俩种类型的字符串：

- 原始C风格字符串：字符串是一个`char`数组，以`NULL`字符`'\0'`（十六进制0）终止。它也被称为字符串或C风格字符串。
- C++98中引入新的`string`类。

推荐使用“high-level” `string` 类，因为它更容易使用和理解。然而，许多遗留程序使用了 C-strings；许多程序员也使用“low-level” C-strings 以获得完全控制和效率；此外，在某些情况下，如命令行参数，只支持 C-strings。因此，你可能需要了解这两套字符串。然而，除非绝对必要，否则避免使用 C-string。

### 17.1 字符串声明和初始化

要使用 `string` 类，请包含 `<string>` 头文件和 " `using namespace std` "。

你可以声明并 (a) 用字符串字面量初始化一个字符串，(b) 初始化为空字符串，或者 (c) 用另一个字符串对象初始化。例如，

```c++
#include <string>
using namespace std;
 
string str1("Hello");  // Initialize with a string literal (Implicit initialization)
string str2 = "world"; // Initialize with a string literal (Explicit initialization via assignment operator)
string str3;           // Initialize to an empty string
string str4(str1);     // Initialize by copying from an existing string object
```

### 17.2字符串输入/输出

```c++
/* Testing string class input and output (TestStringIO.cpp) */
#include <iostream>
#include <string>     // Need this header to use string class
#include <limits>
using namespace std;  // Also needed for <string>
 
int main() {
   string message("Hello");
   cout << message << endl;
 
   // Input a word (delimited by space) into a string
   cout << "Enter a message (no space): ";
   cin >> message;
   cout << message << endl;
 
   cin.ignore(numeric_limits<streamsize>::max(), '\n');
      // flush cin up to newline (need <limits> header)
 
   // Input a line into a string
   cout << "Enter a message (with spaces): ";
   getline(cin, message);  // Read input from cin into message
   cout << message << endl;
   return 0;
}
```

### 17.3 字符串操作

- 检查字符串长度

```c++
int length();
int size();
   both of them return the length of the string
```

```c++
#include <string>
string str("Hello, world");
cout << str.length() << endl;  // 12
cout << str.size()   << endl;  // 12
```

- 检查空字符串：

```c++
bool empty();
   Check if the string is empty.
```

```c++
string str1("Hello, world");
string str2;                   // Empty string
cout << str1.empty() << endl;  // 0 (false)
cout << str2.empty() << endl;  // 1 (true)
```

- 从另一个字符串复制：只需使用赋值（ `=` ）运算符。

```c++
string str1("Hello, world"), str2;
str2 = str1;
cout << str2 << endl;   // Hello, world
```

- 与另一个字符串连接：使用加号 (+) 运算符，或复合加号 ( `+=` ) 运算符。

```c++
string str1("Hello,");
string str2(" world");
cout << str1 + str2 << endl;  // "Hello, world"
cout << str1 << endl;         // "Hello,"
cout << str2 << endl;         // " world"
str1 += str2;
cout << str1 << endl;  // "Hello, world"
cout << str2 << endl;  // " world"
string str3 = str1 + str2;
cout << str3 << endl;  // "Hello, world world"
str3 += "again";
cout << str3 << endl;  // "Hello, world worldagain"
```

- 读写字符串中的单个字符：

```c++
char& at(int index);
   Return the char at index, index begin at 0. Perform index bound check.

[]
   indexing (subscript) operator, no index bound check
```

```c++
string str("Hello, world");
cout << str.at(0) << endl;  // 'H'
cout << str[1] << endl;     // 'e'
cout << str.at(str.length() - 1) << endl;  // 'd'

str.at(1) = 'a';  // Write to index 1
cout << str << endl;  // "Hallo, world"

str[0] = 'h';
cout << str << endl;  // "hallo, world"

```

- 提取子字符串：

```c++
string substr(int beginIndex, int size);
   Return the sub-string starting at beginIndex, of size
```

```c++
string str("Hello, world");
cout << str.substr(2, 6) << endl;  // "llo, w
```

- 与另一个字符串进行比较：

```c++
int compare(string another);
   Compare the content of this string with the given another. 
   Return 0 if equals; a negative value if this string is less than another; positive value otherwise.

== and != Operators
   Compare the contents of two strings
```

```c++
string str1("Hello"), str2("Hallo"), str3("hello"), str4("Hello");
cout << str1.compare(str2) << endl;   // 1   'e' > 'a'
cout << str1.compare(str3) << endl;   // -1  'h' < 'H'
cout << str1.compare(str4) << endl;   // 0
 
// You can also use the operator == or !=
if (str1 == str2) cout << "Same" << endl;
if (str3 != str4) cout << "Different" << endl;
cout << boolalpha;  // print bool as true/false
cout << (str1 != str2) << endl;
cout << (str1 == str4) << endl;
```

- 搜索/替换字符：您可以使用 `<algorithm>` 中提供的功能，例如 `replace()` 。例如，

```c++
#include <algorithm>
......
string str("Hello, world");
replace(str.begin(), str.end(), 'l', '_');
cout << str << endl;      // "He__o, wor_d"
```

```c++
/* Example on C++ string function (TestStringOp.cpp) */
#include <iostream>
#include <string>    // use string class
using namespace std;
 
int main() {
   string msg = "hello, world!";
   cout << msg << endl;
   cout << msg.length() << endl;  // length of string
   cout << msg.at(1) << endl;     // char at index 1
   cout << msg[1] << endl;        // same as above
   cout << msg.empty() << endl;   // test for empty string
   cout << msg.substr(3, 3) << endl; // sub-string begins at
                                     // pos 3 of size 3
   cout << msg.replace(3, 3, "why") << endl; // replace sub-string
   cout << msg.append("end") << endl;        // append behind
   cout << msg + "end" << endl;              // same as above
   cout << msg.insert(3, "insert") << endl;  // insert after pos 3
 
   string msg1;
   msg1 = msg;   // copy
   cout << msg1 << endl;
 
   cout << "Enter a line: ";
   getline(cin, msg);   // read a line of input
   cout << msg << endl;
}
```

```
hello, world!
13
e
e
0
lo,//应用参数 (3, 3):
我们从索引 3 开始。让我们在 "hello, world!" 中找到这个位置的字符：
索引 0: 'h'
索引 1: 'e'
索引 2: 'l'
索引 3: 'l' (这是第二个 'l')
我们需要提取从索引 3 开始的 3 个字符。
提取字符:
从索引 3 ('l') 开始，提取 3 个字符：
索引 3 处的字符: 'l'
索引 4 处的字符: 'o'
索引 5 处的字符: ','
结果: 由这三个字符组成的子字符串就是 "lo,"。
helwhy world!
helwhy world!end
helwhy world!endend
helinsertwhy world!end
helinsertwhy world!end
Enter a line: 124
124
```

> [!CAUTION]
>
> C++是从0开始索引，所以第一个是h.

##  18 使用IO操纵器格式化输入/输出（头文件）

 使用 IO 整理器格式化输入/输出（头文件） <iomanip> 标头提供了所谓的 I/O 操纵器，用于格式化输入和输出：

- `setw(int field-width)` ：设置下一次 IO 操作的字段宽度。 `setw()` 是非粘性的，必须在每次 IO 操作之前发出。每次操作后字段宽度会重置为默认值（宽度刚好足够容纳该字段）。
- `setfill(char fill-char)` : 设置填充字符以适应字段宽度。
- `left|right|internal` : 设置对齐方式
- `fixed/scientific` （对于浮点数）：使用定点表示法（例如，12.34）或科学计数法（例如，1.23e+006）。
- `setprecision(int numDecimalDigits)` （对于浮点数）：指定小数点后的位数。
- `boolalpha` / `noboolalpha` (对于 `bool` ): 将 `bool` 值显示为字母字符串 (true/false) 或 1/0。

### 18.1 输出格式化

```c++
/* Test Formatting Output (TestFormattedOutput.cpp) */
#include <iostream>
#include <iomanip>    // Needed to do formatted I/O
using namespace std;
 
int main() {
   // Floating point numbers
   double pi = 3.14159265;
   cout << fixed << setprecision(4); // fixed format with 4 decimal places
   cout << pi << endl;
   cout << "|" << setw(8) << pi << "|" << setw(10) << pi << "|" << endl;
      // setw() is not sticky, only apply to the next operation.
   cout << setfill('-');
   cout << "|" << setw(8) << pi << "|" << setw(10) << pi << "|" << endl;
   cout << scientific;  // in scientific format with exponent
   cout << pi << endl;
 
   // booleans
   bool done = false;
   cout << done << endl;  // print 0 (for false) or 1 (for true)
   cout << boolalpha;     // print true or false
   cout << done << endl;
   return 0;
}
```

### 18.2 输入格式化

```c++
/* Test Formatting Input (TestFormattedInput.cpp) */
#include <iostream>
#include <iomanip>
#include <string>
using namespace std;
 
int main() {
   string areaCode, phoneCode;
   string inStr;
 
   cout << "Enter your phone number in this format (xxx)xxx-xxxx : ";
   cin.ignore();   // skip '('
   cin >> setw(3) >> areaCode;
   cin.ignore();   // skip ')'
   cin >> setw(3) >> phoneCode;
   cin.ignore();   // skip '-'
   cin >> setw(4) >> inStr;
   phoneCode += inStr;
 
   cout << "Phone number is (" << areaCode << ")"
        << phoneCode.substr(0, 3) << "-"
        << phoneCode.substr(3, 4) << endl;
   return 0;
}
```

## 19 数组

### 19.1 数组声明与使用

假设你想计算一个有 30 名学生的班级的平均分数，你肯定不想创建 30 个变量： `mark1` , `mark2` , ..., `mark30` 。相反，你可以使用一个包含 30 个元素的单一变量，称为数组。

数组是一组相同类型的元素列表，由一对方括号 `[ ]` 标识。要使用数组，您需要用三件事来声明数组：名称、类型和维度（或大小，或长度）。语法是：

```c++
type arrayName[arraylength];  // arraylength can be a literal or a variable
```

我建议为数组使用复数名称，例如， `marks` ， `rows` ， `numbers` 。例如，

```c++
int marks[5];        // Declare an int array called marks with 5 elements
double numbers[10];  // Declare an double array of 10 elements
const int SIZE = 9;
float temps[SIZE];   // Use const int as array length

// Some compilers support an variable as array length, e.g.,
int size;
cout << "Enter the length of the array: ";
cin >> size;
float values[size];
```

请注意，在 C++ 中，元素在声明后的值是未定义的。

C++ 标准要求内置数组的大小必须在编译时就能确定（即必须是常量表达式）。

还可以在声明时用逗号分隔的值列表初始化数组，如下所示：

```c++
// Declare and initialize an int array of 3 elements
int numbers[3] = {11, 33, 44};
// If length is omitted, the compiler counts the elements
int numbers[] = {11, 33, 44};
// Number of elements in the initialization shall be equal to or less than length
int numbers[5] = {11, 33, 44};  // Remaining elements are zero. Confusing! Don't do this
int numbers[2] = {11, 33, 44};  // ERROR: too many initializers

// Use {0} or {} to initialize all elements to 0
int numbers[5] = {0};  // First element to 0, the rest also to zero
int numbers[5] = {};   // All element to 0 too
```

```c++
/* Test local array initialization (TestArrayInit.cpp) */
#include <iostream>
using namespace std;
 
int main() {
   int const SIZE = 5;
 
   int a1[SIZE];   // Uninitialized
   for (int i = 0; i < SIZE; ++i) cout << a1[i] << " ";
   cout << endl;   // ? ? ? ? ?
 
   int a2[SIZE] = {21, 22, 23, 24, 25}; // All elements initialized
   for (int i = 0; i < SIZE; ++i) cout << a2[i] << " ";
   cout << endl;   // 21 22 23 24 25
 
   int a3[] = {31, 32, 33, 34, 35};   // Size deduced from init values
   int a3Size = sizeof(a3)/sizeof(int);
   cout << "Size is " << a3Size << endl;   // 5
   for (int i = 0; i < a3Size; ++i) cout << a3[i] << " ";
   cout << endl;   // 31 32 33 34 35
 
   int a4[SIZE] = {41, 42};  // Leading elements initialized, the rests to 0
   for (int i = 0; i < SIZE; ++i) cout << a4[i] << " ";
   cout << endl;   // 41 42 0 0 0
 
   int a5[SIZE] = {0};  // First elements to 0, the rests to 0 too
   for (int i = 0; i < SIZE; ++i) cout << a5[i] << " ";
   cout << endl;   // 0 0 0 0 0
 
   int a6[SIZE] = {};   // All elements to 0 too
   for (int i = 0; i < SIZE; ++i) cout << a6[i] << " ";
   cout << endl;   // 0 0 0 0 0
}
```

您可以通过方括号 `[ ]` 内的索引（或下标）来引用数组的元素。C++ 的数组索引从零开始。例如，假设 `marks` 是一个包含 5 个元素的 `int` 数组，那么这 5 个元素分别是： `marks[0]` 、 `marks[1]` 、 `marks[2]` 、 `marks[3]` 和 `marks[4]` 。

```c++
// Declare & allocate a 5-element int array
int marks[5];
// Assign values to the elements
marks[0] = 95;
marks[1] = 85;
marks[2] = 77;
marks[3] = 69;
marks[4] = 66;
cout << marks[0] << endl;
cout << marks[3] + marks[4] << endl;
```

![Array.png](data:image/png;imt_275ef05c3e30dd198acef1645d38d63d429e44393ba7081f6407a8afde193930;base64,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YfR19pbrLvR1S7TzsCRPw6I3yRs4nOrRW+PI974Xn0doAPm19rL6DQcv38MEmAATYAJMICoEHh06Cbnv/agcLSUfMnVes9pYlD/EsOeHNqi74Ha80YpFb1S6XfJkovoG0Vuj+chS1bc3eWrLNWECTIAJMAEmkJgEaL2W994c0SqgGqv8rtcON1ax6E3Mvh61Upv9gnOGTcLId3+0zP+CZnXwRz5FcgDIABwHfvJR48AZMQEmwASYABNIGAISkDNM/iprdcnW3qEJU53yKiiL3vIiHefPIfH77/Y9aNDhcZ0vr2+h2dob5w3JxWMCTIAJMIGkJ6D/Kuuvsrxe+5Jh0Zv0QyNYBb1x9FRfXn93kHW31bl18NfUFyo+wnSwavHvTIAJMAEmwAQSnIClN4IfK69+Hw5V+7zm9bAob7CBgHb6qkMPXWXRm+ADIirFV84GXLCoBIcPHRVZul0uZA/9GH8v24CfP35MfozLA0hutGndGMcfVykqj+ZMmAATYAJMgAkwASsCilFKKF/jQQ/69ZruJFeHv5etx88fP27IiNdrI1cWvTzSRFgT+SBD43Vl19fwy8Ll8Kx+X/nB+nQVRsgEmAATYAJMgAlEm4AHkuQKctCEbIy66q6XMWthobxeO3yzWqBWYNEb7T6aRPldeder+GXBCp3oTaLKcVWYABNgAkyACSQJAV6v7TUki157nByZigeRI5udK80EmAATYAIJRoDXa3sNxqLXHidHpuJB5Mhm50ozASbABJhAghHg9dpeg7HotcfJkal4EDmy2bnSTIAJMAEmkGAEeL2212Aseu1xcmQqHkSObHauNBNgAkyACSQYAV6v7TUYi157nByZigeRI5udK80EmAATYAIJRoDXa3sNxqLXHidHpuJB5Mhm50ozASbABJhAghHg9dpeg7HotcfJkal4EDmy2bnSTIAJMAEmkGAEeL2212Aseu1xcmQqHkSObHauNBNgAkyACSQYAV6v7TUYi157nByZigeRI5udK80EmAATYAIJRoDXa3sNxqLXHidHpuJB5Mhm50ozASbABJhAghHg9dpeg7HotcfJkal4EDmy2bnSTIAJMAEmkGAEeL2212Aseu1xcmQqHkSObHauNBNgAkyACSQYAV6v7TUYi157nByZigeRI5udK80EmAATYAIJRoDXa3sNxqLXHidHpuJB5Mhm50oz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)

要创建一个数组，你需要提前知道数组的长度（或大小），并相应地进行分配。一旦数组被创建，其长度就固定了，无法更改。有时，很难确定数组的长度（例如，一个班级有多少学生？）。尽管如此，你需要估计长度并分配一个上限。这可能是使用数组的主要缺点。C++ 有一个 `vector` 模板类（并且 C++11 增加了一个 `array` 模板类），它支持动态可调整大小的数组

您可以使用表达式 `sizeof(arrayName)/sizeof(arrayName[0])` 找到数组长度，其中 `sizeof(arrayName)` 返回数组的总字节数， `sizeof(arrayName[0])` 返回第一个元素的字节数。

C/C++ 不会执行数组索引边界检查。换句话说，如果索引超出了数组的边界，它不会发出警告/错误。例如，

```c++
const int size = 5;
int numbers[size];  // array index from 0 to 4
 
// Index out of bound!
// Can compiled and run, but could pose very serious side effect!
numbers[88] = 999;
cout << numbers[77] << endl;
```

这是 C/C++ 的另一个陷阱。检查索引边界会消耗计算能力并影响性能。然而，安全比速度更重要。较新的编程语言如 Java/C# 会执行数组索引边界检查。

### 19.2数组和循环

Arrays 与循环密切配合。你可以通过循环处理数组中的所有元素，例如，

```c++
/*
 *  Find the mean and standard deviation of numbers kept in an array (MeanStdArray.cpp).
 */
#include <iostream>
#include <iomanip>
#include <cmath>
#define SIZE 7
using namespace std;
 
int main() {
   int marks[] = {74, 43, 58, 60, 90, 64, 70};
   int sum = 0;
   int sumSq = 0;
   double mean, stdDev;
   for (int i = 0; i < SIZE; ++i) {
      sum += marks[i];
      sumSq += marks[i]*marks[i];
   }
   mean = (double)sum/SIZE;
   cout << fixed << "Mean is " << setprecision(2) << mean << endl;
 
   stdDev = sqrt((double)sumSq/SIZE - mean*mean);
   cout << fixed << "Std dev is " << setprecision(2) << stdDev << endl;
 
   return 0;
}
```

### 19.3 基于范围的for循环 （c++11）

C++11引入了基于范围的`for`循环（或`for-each`循环）来遍历数组。

```c++
/* Testing For-each loop (TestForEach.cpp) */
#include <iostream>
using namespace std;
 
int main() {
   int numbers[] = {11, 22, 33, 44, 55};

   // For each member called number of array numbers - read only 
   for (int number : numbers) {
      cout << number << endl;
   }
 
   // To modify members, need to use reference (&)
   for (int &number : numbers) {
      number = 99;
   }
 
   for (int number : numbers) {
      cout << number << endl;
   }
   return 0;
}
```

```
11
22
33
44
55
99
99
99
99
99
```

### 19.4 多维数组

```
int[2][3] = { {11, 22, 33}, {44, 55, 66} };
```

![Array2D.png](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/Array2D.png)

对于 2D 数组（表），第一个索引是行号，第二个索引是列号。元素以所谓的*行优先*方式存储，其中列索引首先用完。

在 C++ 中声明多维数组时，如果您提供了初始化列表，可以省略第*一*个维度的大小。编译器将根据初始化列表中为该维度提供的元素数量来确定其大小。但是，您**必须**指定所有后续维度的大小（在此例中，是列数 `[3]`）。

```c++
/* Test Multi-dimensional Array (Test2DArray.cpp) */
#include <iostream>
using namespace std;
void printArray(const int[][3], int);
 
int main() {
   int myArray[][3] = {{8, 2, 4}, {7, 5, 2}}; // 2x3 initialized
                 // Only the first index can be omitted and implied
   printArray(myArray, 2);
   return 0;
}
 
// Print the contents of rows-by-3 array (columns is fixed)
void printArray(const int array[][3], int rows) {
   for (int i = 0; i < rows; ++i) {
      for (int j = 0; j < 3; ++j) {
         cout << array[i][j] << " ";
      }
      cout << endl;
   }
}
```

### 19.5 字符数组-C-String

在 C 语言中，字符串是由 NULL 字符 `'\0'`（十六进制 `0` 的 ASCII 代码）终止的 `char` 数组。C++ 在标头 `<string>` 下提供了一个新的`字符串`类。C 中的原始字符串称为 C 字符串（或 C 样式字符串或字符串）。您可以通过以下方式分配 C 字符串：

```c++
char message[256];     // Declare a char array 
                       // Can hold a C-String of up to 255 characters terminated by '\0'
char str1[] = "Hello"; // Declare and initialize with a "string literal".
                       // The length of array is number of characters + 1 (for '\0').
char str1char[] = {'H', 'e', 'l', 'l', 'o', '\0'};  // Same as above
char str2[256] = "Hello";  // Length of array is 256, keeping a smaller string.
```

对于新手，请避免使用 C 字符串。使用前面讨论的 C++ `字符串 `（在标头 `<string>` 中）。

> [!TIP]
>
> 你可以使用 `cin` 和 `cout` 来处理 C 字符串。
>
> - `cin <<` 读取由空格分隔的字符串;
> - `cin.getline（var， size）` 将字符串读取到 *var* 直到长度不超过 `size-1` 的换行符，丢弃换行符（替换为 `'\0'`）。` 大小`通常对应于 C 字符串数组的长度。
> - `cin.get（var， size）` 读取字符串直到换行符，但将换行符保留在输入缓冲区中。
> - `cin.get（）` 读取下一个字符。

## 20 函数

### 20.1 为什么要用函数

有时，一定部分代码必须多次使用。与其多次重写代码，不如将它们放入一个“子例程”中，并多次“调用”这个“子例程”——以便于维护和理解。子例程称为方法（在 Java 中）或函数（在 C/C++ 中）。

使用函数的好处是：

- *分而治之* ：从简单的小块或组件构建程序。将程序模块化为自包含的任务。
- *避免重复代码* ：复制和粘贴很容易，但很难维护和同步所有副本。
- *软件重用* ：您可以通过将函数打包到库代码中来重用其他程序中的函数。

使用函数涉及两方：调用函数的*调用方*和被调用*的函数* 。调用方将*参数*传递给函数。该函数接收这些参数，在函数体内执行编程作，并将一段结果返回给调用方。

### 20.2使用函数

假设我们需要多次计算一个圆的面积，最好写一个叫 `getArea（）` 的函数，需要的时候重用它。

![Function.png](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/Function.png)

```c++
/* Test Function (TestFunction.cpp) */
#include <iostream>
using namespace std;
const int PI = 3.14159265;
 
// Function Prototype (Function Declaration)
double getArea(double radius);
 
int main() {
   double radius1 = 1.1, area1, area2;
   // call function getArea()
   area1 = getArea(radius1);
   cout << "area 1 is " << area1 << endl;
   // call function getArea()
   area2 = getArea(2.2);
   cout << "area 2 is " << area2 << endl;
   // call function getArea()
   cout << "area 3 is " << getArea(3.3) << endl;
}
 
// Function Definition
// Return the area of a circle given its radius
double getArea(double radius) {
   return radius * radius * PI;
}
```

```
area 1 is 3.63
area 2 is 14.52
area 3 is 32.67
```

在上面的示例中，定义了一个名为 `getArea（）` 的可重用函数，该函数从调用者接收参数（` 双精度 `），执行计算，并将结果（` 双精度 `）返回给调用者。在 `main（）` 中，我们调用了三次 `getArea（）` 函数，每次使用不同的参数。

在 C++ 中，您需要声明一个*函数* *原型* （在使用函数之前），并提供*一个函数定义* ，其中包含一个包含编程作的主体。

#### Function Definition 功能定义

函数定义的语法如下：

```c++
returnValueType functionName ( parameterList ) {
   functionBody ;
}
```

*parameterList* 由逗号分隔的 *parameter-type* 和 *parameter-name* 组成，即 `param-1-type param-1-name, param-2-type param-2-name,...`

*returnValueType* 指定返回值的类型，例如 `int` 或 `double`。可以使用名为 `void` 的特殊返回类型来表示函数不返回任何值。在 C++ 中，允许函数返回一个值或不返回任何值 （`void`）。它不能返回多个值。[C++ 不允许返回数组！]

#### “return” 语句

在函数体内部，你可以使用一个`return`语句来返回一个值（该值`*returnValueType*`在函数头中声明），并将控制权交还给调用者。语法如下：

```
return expression;   // Evaluated to a value of returnValueType declared in function's signature
return;              // For function with return type of void
```

请注意，调用函数（由调用方）会将控制权转移给函数。函数中的 `return` 语句将控制权转移回调用方。

#### 函数命名约定

函数的名称应为动词或动词短语 （action），由一个或多个单词组成。第一个单词为小写，其余单词为首字母大写（称为*驼峰式大小写* ）。例如，`getArea（）、setRadius（）、moveDown（）、isPrime（）` 等。

#### Function Prototype 函数原型

函数原型告诉编译器函数的接口，即返回类型、函数名称和参数类型列表（参数的数量和类型）。现在可以在文件中的任何位置定义该函数。 例如

```
// Function prototype - placed before the function is used.
double getArea(double);  // without the parameter name
int max(int, int);
```

您可以选择在函数原型中包含参数名称。编译器将忽略这些名称，但用作文档。 例如

```
// Function Prototype
double getArea(double radius);  // parameter names are ignored, but serve as documentation
int max(int number1, int number2);
```

函数原型通常被组合在一起，并放置在所谓的头文件中。头文件可以被许多程序包含。

我们有一个名为 `max（int， int）` 的函数，它接受两个 `int` 并返回它们的最大值。我们从 `main（）` 调用 `max（）` 函数。

```c++
/* Testing max function (TestMaxFunction.cpp) */
#include <iostream>
using namespace std;
 
int maximum(int, int); // Function prototype (declaration)
 
int main() {
   cout << maximum(5, 8) << endl; // Call maximum() with literals
 
   int a = 6, b = 9, c;
   c = maximum(a, b);             // Call maximum() with variables
   cout << c << endl;
 
   cout << maximum(c, 99) << endl; // Call maximum()
}
 
// Function definition
// A function that returns the maximum of two given int
int maximum(int num1, int num2) {
   return (num1 > num2) ? num1 : num2;
}
```

这行代码使用了 C++ 中的 **三元条件运算符 (`? :`)** 来返回两个数 `num1` 和 `num2` 中较大的那一个。

详细解释如下：

1. **三元运算符 `? :`**

   - 它是一种编写简单 `if-else` 语句并产生一个值的简洁方式。
   - 基本语法是： `条件 ? 条件为真时的值 : 条件为假时的值`

2. **分析您的代码: `(num1 > num2) ? num1 : num2`**

   - **`条件 (condition)`**: `(num1 > num2)` - 检查变量 `num1` 的值是否严格大于变量 `num2` 的值。
   - **`?`**: 分隔符。
   - **`条件为真时的值 (value_if_true)`**: `num1` - 如果条件 `(num1 > num2)` 为 `true`，则整个表达式的值就是 `num1` 的值。
   - **`:`**: 分隔符。
   - **`条件为假时的值 (value_if_false)`**: `num2` - 如果条件 `(num1 > num2)` 为 `false` （意味着 `num1` 小于或等于 `num2`），则整个表达式的值就是 `num2` 的值。

   **总而言之，这行代码的作用是：**

   - 比较 `num1` 和 `num2`。
   - 如果 `num1` 更大，就返回 `num1`。
   - 否则（即 `num2` 更大或两者相等），就返回 `num2`。

   所以，这行代码的意思是：“返回 `num1` 和 `num2` 中的最大值（较大的那个值）。

   

它等同于下面的 `if-else` 语句：

```
if (num1 > num2) {
  return num1;
} else {
  return num2;
}
```

####  “void” 返回类型

假设你需要一个函数来执行某些作（例如，打印），而不需要向调用者返回值，你可以将其返回值类型声明为 `void`。在函数的主体中，你可以使用不带返回值的 “`return;”` 语句将控制权返回给调用者。在这种情况下，`return` 语句是可选的。如果没有 `return` 语句，则将执行整个主体，并在主体末尾将控制权返回给调用者。

#### 实际参数与形式参数

回想一下，函数从其调用者接收*参数* ，执行函数体中定义的作，并向调用者返回一个值（或不返回任何内容）。

在上面的示例中，在 `getArea（double radius）` 的签名中声明的变量 `（double radius）` 称为*形式参数* 。其范围在函数的主体内。当调用者调用函数时，调用者必须提供所谓的*实际参数* s（或*参数* ），其值随后用于实际计算。例如，当通过 “`area1 = getArea（radius1）”` 调用函数时，`radius1` 是实际参数，值为 `1.1`。

#### 函数的局部变量和参数的范围

在函数内声明的所有变量（包括函数的参数）都仅对函数可用。它们是在调用函数时创建的，并在函数返回后释放（销毁）。它们被称为*局部变量* ，因为它们是函数的本地变量，在函数外部不可用。它们也被称为*自动变量* ，因为它们是自动创建和销毁的 - 无需程序员的显式作来分配和释放它们。

#### 布尔函数

布尔函数向调用方返回一个`布尔`值（`true` 或 `false`）。

假设我们希望编写一个名为 `isOdd（）` 的函数来检查给定的数字是否为奇数。

```c++
#include <iostream>
using namespace std;
 
// Function Prototype
bool isOdd(int);
 
int main() {
   cout << boolalpha;   // print bool as true or false
   cout << isOdd(5) << endl;  // true
   cout << isOdd(6) << endl;  // false
   cout << isOdd(-5) << endl; // false
}
 
bool isOdd(int number) {
   if (number % 2 == 1) {
      return true;
   } else {
      return false;
   }
}
```

这个看似正确的代码会为 `-5` 生成 `false`，因为 `-5%2` 是 `-1` 而不是 `1`。你可以重写条件：

```c++
bool isOdd(int number) {
   if (number % 2 == 0) {
      return false;
   } else {
      return true;
   }
}
```

上面的代码生成了正确的答案，但很差。对于布尔函数，您应该简单地返回比较的结果 `bool` 值，而不是使用条件语句，如下所示：

```c++
bool isEven(int number) {
   return (number % 2 == 0);
}
 
bool isOdd(int number) {
  return !(number % 2 == 0);  // OR return !isEven(number);
}
 
int main() {
   int number = -9;
   if (isEven(number)) {      // Don't write (isEven(number) == true)
      cout << "Even" << endl;
   }
}
```

### 20.3 默认参数

C++ 引入了函数的所谓*默认参数* 。如果调用者在调用函数时省略了相应的实际参数，则将使用这些默认值。默认参数在函数原型中指定，不能在函数定义中重复。默认参数根据它们的位置进行解析。因此，它们只能用于替换*尾随*参数以避免歧义。 例如

```c++
#include <iostream>
using namespace std;
 
// Function prototype - Specify the default arguments here
int fun1(int = 1, int = 2, int = 3);
int fun2(int, int, int = 3);
 
int main() {
   cout << fun1(4, 5, 6) << endl; // No default
   cout << fun1(4, 5) << endl;    // 4, 5, 3(default)
   cout << fun1(4) << endl;       // 4, 2(default), 3(default)
   cout << fun1() << endl;        // 1(default), 2(default), 3(default)
 
   cout << fun2(4, 5, 6) << endl; // No default
   cout << fun2(4, 5) << endl;    // 4, 5, 3(default)
// cout << fun2(4) << endl;
      // error: too few arguments to function 'int fun2(int, int, int)'
}
 
int fun1(int n1, int n2, int n3) {
      // cannot repeat default arguments in function definition
   return n1 + n2 + n3;
}
 
int fun2(int n1, int n2, int n3) {
   return n1 + n2 + n3;
}
```

应该在函数原型（声明）中指定默认参数。它们只能定义一次（单定义规则），并且不能在函数定义中重复。

**重要规则:**

- 默认参数必须是参数列表中的**尾随 (trailing)** 参数。也就是说，一旦你给某个参数指定了默认值，它**之后的所有参数**也必须有默认值。你不能有一个带默认值的参数后面跟着一个没有默认值的参数。
- 默认值**不能**在函数定义（实现）中重复指定（如果已经有原型声明了默认值），如 `fun1` 定义中的注释所示。

**函数调用:**

- `fun1` 的调用:
  - `fun1(4, 5, 6)`: 提供了所有 3 个参数，不使用默认值。返回 `4+5+6 = 15`。
  - `fun1(4, 5)`: 提供了前 2 个参数。第 3 个参数 `n3` 使用默认值 `3`。返回 `4+5+3 = 12`。
  - `fun1(4)`: 只提供了第 1 个参数。第 2 个参数 `n2` 使用默认值 `2`，第 3 个参数 `n3` 使用默认值 `3`。返回 `4+2+3 = 9`。
  - `fun1()`: 没有提供任何参数。所有参数都使用默认值：`n1=1`, `n2=2`, `n3=3`。返回 `1+2+3 = 6`。
- `fun2` 的调用:
  - `fun2(4, 5, 6)`: 提供了所有 3 个参数，不使用默认值。返回 `4+5+6 = 15`。
  - `fun2(4, 5)`: 提供了前 2 个参数。第 3 个参数 `n3` 使用默认值 `3`。返回 `4+5+3 = 12`。
  - `// cout << fun2(4) << endl;`: 这行被注释掉了，并且下面的注释解释了原因。你**不能**只提供第一个参数 `4` 来调用 `fun2`。因为 `fun2` 的第二个参数 `n2` **没有**默认值，所以调用时**必须**为它提供一个值。你不能跳过一个没有默认值的参数 (`n2`) 去使用后面参数 (`n3`) 的默认值。这违反了默认参数必须是尾随参数的规则。

default 参数不是绝对必要的。代码可能很难维护。

### 20.4 函数重载

C++ 引入了*函数重载* （或*函数多态性* ，这意味着*多种形式* ），它允许您拥有同一函数名称的多个版本，并通过参数列表（参数的数量、类型或顺序）进行区分。与调用方的参数列表匹配的版本将被选择执行。 例如

```c++
#include <iostream>
using namespace std;
 
void fun(int, int, int);  // Version 1
void fun(double, int);          // Version 2
void fun(int, double);          // Version 3
 
int main() {
   fun(1, 2, 3);   // version 1
   fun(1.0, 2);    // version 2
   fun(1, 2.0);    // version 3
   fun(1.1, 2, 3); // version 1 - double 1.1 casted to int 1 (without warning)
 
   // fun(1, 2, 3, 4);
      // error: no matching function for call to 'fun(int, int, int, int)'
   // fun(1, 2);
      // error: call of overloaded 'fun(int, int)' is ambiguous
      // note: candidates are:
      //    void fun(double, int)
      //    void fun(int, double)
   // fun(1.0, 2.0);
      // error: call of overloaded 'fun(double, double)' is ambiguous
}
 
void fun(int n1, int n2, int n3) {  // version 1
   cout << "version 1" << endl;
}
 
void fun(double n1, int n2) { // version 2
   cout << "version 2" << endl;
}
 
void fun(int n1, double n2) { // version 3
   cout << "version 3" << endl;
}
```

重载函数不能通过返回类型（编译错误）来区分。

#### 名称修饰

为了区分重载函数的不同版本，许多编译器（例如 GNU GCC）采用*名称修饰*或*名称修饰*方案来命名函数。

```
// Compile source into object code FunctionOverloading.o
> g++ -c FunctionOverloading.cpp
 
// List the symbol table
> nm FunctionOverloading.o
......
000000b5 T __Z3fundi
000000ed T __Z3funid
00000089 T __Z3funiii
......
```

每个函数都通过前缀 `__Z` 标识，后跟一个包含函数名称字符数的整数（在本例中为 3 表示“`fun`”），后跟参数类型列表（其中 `i` 表示 `int，d` 表示 `double`）。例如，`di` 表示 `double` 后跟 `int`;`id` 表示 `int` 后跟 `double`;`iii` 表示 3 `个 int`。

您可以通过将关键字 `extern “C”` 附加到函数原型来选择使用 C 的命名协议。C 不支持函数重载。因此，它不需要名称修饰。它只是在函数名称前面附加一个下划线。 例如

```
extern "C" void fun(int, int, int, int);   // Compiled as _fun
```

### 20.5数组和函数

你也可以将数组传递给 function。但是，你还需要将数组的大小传递给函数。这是因为无法从被调用函数内的 array 参数中判断数组的大小。

##### 计算数组和打印数组内容的总和

```c++
#include <iostream>
using namespace std;
 
// Function prototype
int sum(int array[], int size);    // Need to pass the array size too
void print(int array[], int size);
 
// Test Driver
int main() {
   int a1[] = {8, 4, 5, 3, 2};
   print(a1, 5);   // {8,4,5,3,2}
   cout << "sum is " << sum(a1, 5) << endl;  // sum is 22
}
 
// Function definition
// Return the sum of the given array
int sum(int array[], int size) {
   int sum = 0;
   for (int i = 0; i < size; ++i) {
      sum += array[i];
   }
   return sum;
}
 
// Print the contents of the given array
void print(int array[], int size) {
   cout << "{";
   for (int i = 0; i < size; ++i) {
      cout << array[i];
      if (i < size - 1) {
         cout << ",";
      }
   }
   cout << "}" << endl;
}
```

### 20.6 按值传递与按引用传递

有两种方法可以将参数传递到函数中： *按值传递* vs. *按引用传递* 。

#### 按值传递

在按值传递中，创建参数的“副本”并将其传递到函数中。调用的函数适用于“克隆”，无法修改原始副本。在 C/C++ 中，基本类型（如 `int` 和 `double`）按值传递。也就是说，您不能在函数内修改调用方的值 - 没有*副作用* 。

```c++
#include <iostream>
using namespace std;
 
// Function prototypes
int inc(int number);
 
// Test Driver
int main() {
   int n = 8;
   cout << "Before calling function, n is " << n << endl; // 8
   int result = inc(n);
   cout << "After calling function, n is " << n << endl;  // 8
   cout << "result is " << result << endl;                // 9
}
 
// Function definitions
// Return number+1
int inc(int number) {
   ++number;  // Modify parameter, no effect to caller
   return number;
}
```

#### 按引用传递

另一方面，在按引用传递中，调用者变量的*引用*被传递到函数中。换句话说，被调用的函数处理相同的数据。如果被调用的函数修改了参数，则同一调用者的副本也将被修改。

在 C/C++ 中，数组是通过引用传递的。也就是说，您可以在被调用的函数中修改调用方数组的内容 - 将数组传递到函数中可能会产生*副作用* 。

C/C++ 不允许函数返回数组。因此，如果您希望编写一个修改数组内容的函数（例如，对数组的元素进行排序），则需要依靠按引用传递来处理函数内部和外部的同一副本。回想一下，在按值传递中，调用的函数适用于*克隆*副本，并且无法修改原始副本。

#### 递增 Array 的每个元素

```c++
#include <iostream>
using namespace std;
 
// Function prototypes
void inc(int array[], int size);
void print(int array[], int size);
 
// Test Driver
int main() {
   int a1[] = {8, 4, 5, 3, 2};
 
   // Before increment
   print(a1, 5);   // {8,4,5,3,2}
   // Do increment
   inc(a1, 5);     // Array is passed by reference (having side effect)
   // After increment
   print(a1, 5);   // {9,5,6,4,3}
}
 
// Function definitions
 
// Increment each element of the given array
void inc(int array[], int size) {  // array[] is not const
   for (int i = 0; i < size; ++i) {
      array[i]++;  // side-effect
   }
}
 
// Print the contents of the given array
void print(int array[], int size) {
   cout << "{";
   for (int i = 0; i < size; ++i) {
      cout << array[i];
      if (i < size - 1) {
         cout << ",";
      }
   }
   cout << "}" << endl;
}
```

Array 通过引用传递到函数中。也就是说，调用的函数与调用方在数组的同一副本上工作。因此，函数内部数组的变化会反映在函数外部（即副作用）。

#### 为什么数组是按引用传递的？

Array 设计为通过引用传递，而不是使用克隆副本按值传递。这是因为按值传递大型数组效率低下 - 需要克隆大型数组。

### 20.7 const函数参数

按引用传递可能会损坏原始数据。如果您不想修改函数内的数组，则可以在 function 参数中使用 `const` 关键字。不能在函数内部修改 `const` 函数参数。

尽可能使用 `const` 来传递引用，因为它可以防止您无意中修改参数并保护您免受许多编程错误的影响。

##### 使用 Linear Search 搜索数组

在线性搜索中，搜索键与数组中的每个元素进行线性比较。如果匹配，则返回数组在 [0, size-1] 之间的索引；否则，返回 -1 或数组的大小（某些实现仅处理正索引）。线性搜索的复杂度为 O(n)。

```c++
#include <iostream>
using namespace std;
 
int linearSearch(const int a[], int size, int key);
 
int main() {
   const int SIZE = 8;
   int a1[SIZE] = {8, 4, 5, 3, 2, 9, 4, 1};
 
   cout << linearSearch(a1, SIZE, 8) << endl;  // 0
   cout << linearSearch(a1, SIZE, 4) << endl;  // 1
   cout << linearSearch(a1, SIZE, 99) << endl; // 8 (not found)
}
 
// Search the array for the given key
// If found, return array index [0, size-1]; otherwise, return size
int linearSearch(const int a[], int size, int key) {
   for (int i = 0; i < size; ++i) {
      if (a[i] == key) return i;
   }
   return size;
}
```

##### 使用 Bubble Sort 对 Array 进行排序

详细算法和图示请见Wiki 上的“[冒泡排序](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/en.wikipedia.org/wiki/Bubble_sort)” ``。简而言之，我们遍历整个列表，比较两个相邻的元素，如果它们的顺序错误，则交换它们。重复此过程，直到不需要交换为止。例如：

```
{8,4,5,3,2,9,4,1}
PASS 1 ...
{8,4,5,3,2,9,4,1} => {4,8,5,3,2,9,4,1}
{4,8,5,3,2,9,4,1} => {4,5,8,3,2,9,4,1}
{4,5,8,3,2,9,4,1} => {4,5,3,8,2,9,4,1}
{4,5,3,8,2,9,4,1} => {4,5,3,2,8,9,4,1}
{4,5,3,2,8,9,4,1} => {4,5,3,2,8,4,9,1}
{4,5,3,2,8,4,9,1} => {4,5,3,2,8,4,1,9}
PASS 2 ...
{4,5,3,2,8,4,1,9} => {4,3,5,2,8,4,1,9}
{4,3,5,2,8,4,1,9} => {4,3,2,5,8,4,1,9}
{4,3,2,5,8,4,1,9} => {4,3,2,5,4,8,1,9}
{4,3,2,5,4,8,1,9} => {4,3,2,5,4,1,8,9}
PASS 3 ...
{4,3,2,5,4,1,8,9} => {3,4,2,5,4,1,8,9}
{3,4,2,5,4,1,8,9} => {3,2,4,5,4,1,8,9}
{3,2,4,5,4,1,8,9} => {3,2,4,4,5,1,8,9}
{3,2,4,4,5,1,8,9} => {3,2,4,4,1,5,8,9}
PASS 4 ...
{3,2,4,4,1,5,8,9} => {2,3,4,4,1,5,8,9}
{2,3,4,4,1,5,8,9} => {2,3,4,1,4,5,8,9}
PASS 5 ...
{2,3,4,1,4,5,8,9} => {2,3,1,4,4,5,8,9}
PASS 6 ...
{2,3,1,4,4,5,8,9} => {2,1,3,4,4,5,8,9}
PASS 7 ...
{2,1,3,4,4,5,8,9} => {1,2,3,4,4,5,8,9}
PASS 8 ...
{1,2,3,4,4,5,8,9}
```

冒泡排序效率不高，复杂度为 O（n2）。

```c++
#include <iostream>
using namespace std;
 
void insertionSort(int a[], int size);
void print(const int a[], int iMin, int iMax);
 
int main() {
   const int SIZE = 8;
   int a[SIZE] = {8, 4, 5, 3, 2, 9, 4, 1};
 
   print(a, 0, SIZE - 1);
   cout << endl;
   insertionSort(a, SIZE);
   print(a, 0, SIZE - 1);
   cout << endl;
}
 
// Sort the given array of size using insertion sort
void insertionSort(int a[], int size) {
   int temp;   // for shifting elements
   for (int i = 1; i < size; ++i) {
      // for tracing
      print(a, 0, i - 1);    // already sorted
      print(a, i, size - 1); // to be sorted
      cout << endl;
 
      // For element at i, insert into proper position in [0, i-1]
      //  which is already sorted.
      // Shift down the other elements
      for (int prev = 0; prev < i; ++prev) {
         if (a[i] < a[prev]) {
            // insert a[i] at prev, shift the elements down
            temp = a[i];
            for (int shift = i; shift > prev; --shift) {
               a[shift] = a[shift-1];
            }
            a[prev] = temp;
            break;
         }
      }
   }
}
 
// Print the contents of the array in [iMin, iMax]
void print(const int a[], int iMin, int iMax) {
   cout << "{";
   for (int i = iMin; i <= iMax; ++i) {
      cout << a[i];
      if (i < iMax) cout << ",";
   }
   cout << "} ";
}
```

##### “const” 基本型函数参数？

你也可以对基本类型函数参数（例如 int、double）使用 const，以防止参数在函数内部被修改。但是，由于基本类型参数是按值传递的（带有克隆副本），因此永远不会对调用者产生副作用。我们通常不对基本类型使用 const 关键字。换句话说，使用 const 表示不应产生副作用。

### 20.8  通过 “Reference” 参数进行引用传递

如前所述，基本类型的参数（例如 int、double）是按值传递的。也就是说，在函数内部使用克隆副本。在函数中更改克隆的副本不会对调用方的副本产生副作用。

尽管如此，您可以通过 `&` 表示的所谓*引用参数*通过引用传递基本类型参数。例如

```c++
#include <iostream>
using namespace std;
 
int squareByValue (int number);        // Pass-by-value
void squareByReference (int & number); // Pass-by-reference
 
int main() {
   int n1 = 8;
   cout << "Before call, value is " << n1 << endl;  // 8
   cout << squareByValue(n1) << endl;  // no side-effect
   cout << "After call, value is " << n1 << endl;   // 8
 
   int n2 = 9;
   cout << "Before call, value is " << n2 << endl;  // 9
   squareByReference(n2);  // side-effect
   cout << "After call, value is " << n2 << endl;   // 81
}
 
// Pass parameter by value - no side effect
int squareByValue (int number) {
   return number * number;
}
 
// Pass parameter by reference by declaring as reference (&)
// - with side effect to the caller
void squareByReference (int & number) {
   number = number * number;
}
```

在函数 squareByReference() 中，我们将参数 number 声明为 int &（int 的引用），从而通过引用传递。这样，函数内部使用的是调用者的副本（而不是值传递中的克隆副本）。函数内部的更改会产生副作用。

Pass-by-reference 不常用于基本类型（例如 `int`、`double`）——上面的例子纯粹是为了学术说明。但它广泛用于复合类型（例如数组和对象），以避免克隆大量数据以获得更好的性能.

### 20.9数学函数（头文件 <cmath>）

C++ 在库 <cmath>（从 C 的“math.h”移植过来）中提供了许多常用的数学函数。其中一些函数的签名是：

| `sin(x), cos(x), tan(x), asin(x), acos(x), atan(x):   Take argument-type and return-type of float, double, long double.` |
| ------------------------------------------------------------ |
| `atan2(y, x):   Return arc-tan of y/x. Better than atan(x) for handling 90 degree.` |
| `sinh(x), cosh(x), tanh(x):   hyper-trigonometric functions.` |
| `pow(x, y), sqrt(x):   power and square root.`               |
| `ceil(x), floor(x):   returns the ceiling and floor integer of floating point number.` |
| `fabs(x), fmod(x, y):   floating-point absolute and modulus.` |
| `exp(x), log(x), log10(x):   exponent and logarithm functions.` |

### 20.10 生成随机数

`cstdlib` 头文件（从 C 的 `stdlib.h` 移植而来）提供了一个函数 `rand（），` 该函数生成一个介于 0 和 `RAND_MAX`（含）之间的伪随机整数。`RAND_MAX` 是 `cstdlib` 中定义的常量（通常是 16/32 位有符号整数的最大值，例如 32767）。您可以通过 `rand（） % n` 生成 `[0，n）` 之间的随机数。

`rand（）` 在不同的调用中生成相同的伪随机数。`cstblib` 还提供了一个 `srand（）` 函数来*设定*或初始化随机数生成器。我们通常使用通过 `time（0）` 函数获取的当前时间（在 `<ctime>` 标头中）为其设定种子，该函数返回自 1970 年 1 月 1 日以来的秒数。

```c++
#include <iostream>
#include <cstdlib>  // for rand(), srand()
#include <ctime>    // for time()
using namespace std;
 
int main() {
   // rand() generate a random number in [0, RAND_MAX]
   cout << "RAND_MAX is " << RAND_MAX << endl;   // 32767
 
   // Generate 10 pseudo-random numbers between 0 and 99
   //   without seeding the generator.
   // You will get the same sequence, every time you run this program
   for (int i = 0; i < 10; ++i) {
      cout << rand() % 100 << " ";   // need <cstdlib> header
   }
   cout << endl;
 
   // Seed the random number generator with current time
   srand(time(0));   // need <cstdlib> and <ctime> header
   // Generate 10 pseudo-random numbers
   // You will get different sequence on different run,
   //   because the current time is different
   for (int i = 0; i < 10; ++i) {
      cout << rand() % 100 << " ";   // need <cstdlib> header
   }
   cout << endl;
}
```

##### 测试 rand（） 的分布

我们将通过反复掷 6 面骰子来测试 `rand（）` 的分布并计算出现次数。

```c++
#include <iostream>
#include <iomanip>
#include <cstdlib>  // for rand(), srand()
#include <ctime>    // for time()
using namespace std;
 
const int TOTAL_COUNT = 2000000;  // Close to INT_MAX
const int NUM_FACES = 6;
int frequencies[6] = {0}; // frequencies of 0 to 5, init to zero
 
int main() {
   srand(time(0)); // seed random number generator with current time
   // Throw the die and count the frequencies
   for (int i = 0; i < TOTAL_COUNT; ++i) {
      ++frequencies[rand() % 6];
   }
 
   // Print statistics
   cout << fixed << setprecision(2);
   for (int i = 0; i < NUM_FACES; i++) {
      cout << i+1 << ": " << frequencies[i]
           << " (" << 100.0 * frequencies[i] / TOTAL_COUNT << "%)" << endl;
   }
}
```

```
1: 333109 (16.66%)
2: 333113 (16.66%)
3: 333181 (16.66%)
4: 333562 (16.68%)
5: 333601 (16.68%)
6: 333434 (16.67%)
```

## 21 文件输入/输出（头文件<fstream>)

`<fstream>` 标头为文件输入和输出提供 `ifstream` （输入文件流） 和 `ofstream` （输出文件流）。文件输入/输出的步骤是：

- 为 input 创建 `ifstream`，或为 output 创建 `ofstream`。
- 通过 `open（filename）` 将流连接到输入或输出文件。
- 通过流插入运算符 `<<` 执行格式化输出，或通过流提取运算符 `>>` 执行输入，类似于 `cout <<` 和 `cin >>`。
- 关闭文件并释放流。

```c++
#include <iostream>
#include <fstream>   // file stream
#include <cstdlib>
using namespace std;
 
int main() {
   ifstream fin;   // Input stream
   ofstream fout;  // Output stream
 
   // Try opening the input file
   fin.open("in.txt");
   if (!fin.is_open()) {
      cerr << "error: open input file failed" << endl;
      abort();  // Abnormally terminate the program (in <cstdlib>)
   }
 
   int sum = 0, number, count = 0;
   while (!(fin.eof())) {
      // Use >> to read
      fin >> number;
      sum += number;
      ++count;
   }
   double average = double(sum) / count;
   cout << "Count = " << count << " average = " << average << endl;
   fin.close();
 
   // Try opening the output file
   fout.open("out.txt");
   if (!fout.is_open()) {
      cerr << "error: open output file failed" << endl;
      abort();
   }
   // Write the average to the output file using <<
   fout << average;
   fout.close();
   return 0;
}
```

##### 输入文件：in.txt

```
12 15 35 26 68
```

##### 输出文件：out.txt

```
31.20
```

说明

- 打开文件后，您可以使用 `>>` 和 `<<` 进行输入和输出，类似于 `cin >>` 和 `cout <<`。（高级说明：`ifstream` 是 `istream` 的子类，` 其中 cin` 属于其中。`ofstream` 是 `ostream 的`子类，` 其中 cout` 属于其中。
- 同样，IO 纵器（例如 `fixed`、`setprecision（）` 和 `setw（）`）也适用于文件流。


## 22 Namespace

当您使用不同的库模块时，总是存在名称崩溃的可能性，因为不同的库可能会出于不同的目的使用相同的名称。这个问题可以通过在 C++ 中使用 *namespace* 来解决。 *命名空间*是同一命名范围下的标识符的集合。（在 UML 和 Java 中称为 *package*。命名空间下的实体名称由命名空间名称*限定* ，后跟 `：：（` 称为范围解析运算符），格式为 `namespace：：entityName`。

要将实体放置在 namespace 下，请使用关键字 `namespace`，如下所示：

```c++
namespace myNameSpace {  
   int foo;               // variable
   int f() { ...... };    // function
   class Bar { ...... };  // compound type such as class and struct
}
 
// To reference the entities, use
myNameSpace::foo
myNameSpace::f()
myNameSpace::Bar
```

命名空间可以包含变量、函数、数组和复合类型，例如类和结构。

```c++
#include <iostream>
 
namespace a {   // contains variables
   int i1 = 8;
   int i2 = 9;
}
 
namespace b {   // contains function
   int max(int n1, int n2) {
      return (n1 > n2) ? n1 : n2;
   }
}
 
int main() {
   std::cout << a::i1 << std::endl;                // 8
   std::cout << b::max(a::i1, a::i2) << std::endl; // 9
}
```

命名空间已打开。换句话说，您可以使用其他`命名空间`定义将更多名称添加到现有命名空间中。

##### Using Namespace

例如，C++ 标准库中的所有标识符（例如 `cout`、`endl` 和 `string`）都放置在名为 `std` 的命名空间下。要引用命名空间下的标识符，您有三个选项：

使用完全限定的名称，例如 `std：：cout`、`std：：endl`、`std：：setw（）` 和 `std：：string`。例如 缺少 “`std：：`” 会导致 “错误：未在此范围内声明 'xxx'”。

```
std::cout << std::setw(6) << 1234 << std::endl;
```

使用 *using 声明*来声明特定标识符。例如 你可以省略 `cout` 和 `endl` 的 “`std：：`”，但你仍然必须对 `setw` 使用 “`std：：`”。

```
using std::cout;
using std::endl;
......
cout << std::setw(6) << 1234 << endl;
```

使用 *using namespace 指令* 。例如 `using namespace` 指令有效地将指定命名空间中的所有标识符引入全局范围，就像它们在全局范围内可用一样。您可以在没有范围解析运算符的情况下引用它们。请注意，`using namespace` 指令可能会导致 name 崩溃，并且 identifier 位于全局范围内。

```
using namespace std;
......
cout << setw(6) << 1234 << endl;
```

对于长命名空间名称，您可以定义命名空间的简写（或别名），如下所示： 您现在可以将类称为 `shorthand：：entityName`

```
namespace shorthand = namespace-name;
```

如前所述，所有标准 C++ 库组件都打包在一个名为 `std` 的命名空间中。它们包括 `cin`、`cout`、`endl`、`setw（）、setprecision``（）` 和 `string`。因此，我们总是在“`#include <iostream>`”和“`#include <string>`”之后包含一个“`using namespace std;”` 指令。您还可以使用限定名称，例如 `std：：cin`、`std：：cout`、`std：：endl`、`std：：string`，而不是 `using` 指令。您还可以使用选择性 using，例如 “`using std：：cin;`”、“`using std：：cout;`”、“`using std：：endl;`” 和 “`using std：：string;`”。

比较以下两个代码示例：

```c++
#include <iostream>
using namespace std;  // std namespace is available to ALL

int main() { ....... }
```

```c++
#include <iostream>

int main() { 
   using namespace std; // std namespace is available to main() only
   .......
}
```

> [!CAUTION]
>
> 可以使用 C 风格的标头 “`iostream.h`”，它不使用命名空间来替换第一个示例中的前两行。

##### Global Namespace 全局命名空间

在 C++ 中，如果实体（变量、函数或类）未包含在`命名空间`声明中，则它属于*全局命名空间* （由 `：：` 标识，没有命名空间名称）。例如，`main（）` 可以标识为 `：：main（）。`

