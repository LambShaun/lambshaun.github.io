# 为什么要选择面向对象编程（OOP）



假设你想组装自己的 PC，你去一家硬件商店，挑选了一块主板、一个处理器、一些 RAM、一个硬盘、一个机箱、一个电源，然后把它们组装在一起。你打开电源，PC 就运行了。你不需要担心主板是 4 层还是 6 层板，硬盘有 4 个还是 6 个盘片；直径是 3 英寸还是 5 英寸，RAM 是日本制造还是韩国制造，等等。你只需将硬件组件组装在一起，并期望机器能运行。当然，你必须确保接口正确，例如，如果你的主板只支持 IDE，你就得选择 IDE 硬盘而不是 SCSI 硬盘；你必须选择具有正确速度等级的 RAM，等等。然而，从硬件组件设置一台机器并不难。

同样，汽车是由零件和组件组装而成的，例如底盘、车门、发动机、车轮、刹车和变速器。这些组件是可重复使用的，例如，一个车轮可以用于多辆汽车（具有相同规格）。

软件怎么样？你能通过这里选一个程序，那里选一个程序来“组装”一个软件应用程序，并期望程序能运行吗？答案显然是否定的！与硬件不同，从软件组件中“组装”一个应用程序是非常困难的。自从 60 年前计算机出现以来，我们已经编写了无数的程序。然而，对于每个新的应用程序，我们都不得不重新发明轮子，从头开始编写程序。

为什么要重新发明轮子？

## 1关于面向对象编程

### 1.1 传统的面向过程语言

我们能否在传统的面向过程的编程语言，如C、Fortran、Cobol或Pascal中做这件事？

![OOP_CFunction](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/OOP_CFunction.png)

传统的面向过程的语言（如 C 和 Pascal）在创建可重用的软件组件方面存在一些显著的缺点：

- 程序由函数组成。函数往往不可重用。从一个程序中复制一个函数并在另一个程序中重用非常困难，因为该函数很可能会引用头文件、全局变量和其他函数。换句话说，函数并没有很好地封装成一个独立的可重用单元。
- 程序语言不适合用于解决现实生活问题的高层次抽象。例如，C 程序使用诸如 if-else、for-loop、array、function、pointer 等构造，这些都是低层次的，很难抽象出真实问题，如客户关系管理（CRM）系统或电脑足球游戏。（想象一下使用汇编代码，这是一种非常低层次的代码，来编写一个电脑足球游戏。C 语言要好一些，但也好不了多少。）

简而言之，传统的程序语言将软件实体的数据结构和算法分开。



在 1970 年代早期，美国国防部（DoD）委托一个特别工作组调查其 IT 预算为何总是失控，但却没有太多成果。调查结果如下：

- 80%的预算用于软件（剩余的 20%用于硬件）。
- 超过 80%的软件预算用于维护（仅剩 20%用于新软件开发）。
- 硬件组件可以应用于各种产品，其完整性通常不会影响其他产品。（硬件可以共享和重复使用！硬件故障是隔离的！）
- 软件程序往往不可共享且不可重用。软件故障可能会影响计算机中运行的其他程序。

任务小组提议让软件表现得像硬件 OBJECT。随后，国防部（DoD）用一种名为 Ada 的面向对象语言替换了超过 450 种计算机语言，这些语言当时用于构建 DoD 系统。



### 1.2面向对象编程语言

![OOP_Objects](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/OOP_Objects.png)

面向对象编程（OOP）语言旨在解决这些问题。

- 面向对象编程的基本单位是类，它将静态属性和动态行为封装在一个“盒子”中，并指定了使用这些盒子的公共接口。由于类是良好封装的（与函数相比），因此更容易重用这些类。换句话说，面向对象编程将软件实体的数据结构和算法组合在同一个盒子中。
- OOP 语言允许更高层次的抽象来解决现实生活中的问题。传统的过程式语言（如 C 和 Pascal）迫使你从计算机结构的角度思考（例如内存位和字节、数组、决策、循环），而不是从你试图解决的问题的角度思考。OOP 语言（如 Java、C++、C#）让你在问题空间中思考，并使用软件对象来表示和抽象问题空间中的实体来解决问题。

![OOP_SoccerGame](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/OOP_SoccerGame.png)

举个例子，假设你想编写一个电脑足球游戏（我认为这是一个复杂的应用程序）。在面向过程的语言中建模这个游戏是相当困难的。但使用 OOP 语言，你可以轻松地根据足球游戏中出现的“真实事物”来相应地建模程序。

- 玩家：属性包括姓名、号码、场上位置等；操作包括跑、跳、踢球等。
- Ball：球：
- Reference: 参考：
- Field: 字段：
- Audience: 受众：
- Weather: 天气：

最重要的是，其中一些类（例如 `Ball` 和 `Audience` ）可以在另一个应用程序中重复使用，例如电脑篮球游戏，几乎不需要或完全不需要修改。

### 1.3 OPP的优势

面向过程的语言以过程为中心，以函数为基本单位。你需要先弄清楚所有的函数，然后再考虑如何表示数据。

面向对象语言关注用户感知的组件，以对象作为基本单位。你通过将所有描述用户与数据交互的数据和操作整合在一起，来确定所有对象。

面向对象技术有很多好处：

- 在软件设计中更加轻松，因为你可以从问题的角度思考，而不必考虑机器的位和字节。你处理的是高层次的概念和抽象。设计的轻松导致更高效的软件开发。
- 软件维护的便利性：面向对象的软件更容易理解，因此更容易测试、调试和维护。
- 可重用软件：您不需要反复重新发明轮子，也不需要为不同情况重写相同的功能。开发新应用程序最快、最安全的方法是重用现有代码——经过充分测试和验证的代码。

## 2 OPP基础

### 2.1 类与实例 Classes & Instances 

Class: 类是同类对象的定义。换句话说，类是一个蓝图、模板或原型，它定义并描述了同类所有对象共有的静态属性和动态行为。

Instance :实例是类中特定项目的实现。换句话说，实例是类的实例化。类的所有实例都具有相似的属性，如类定义中所描述。例如，你可以定义一个名为“ `Student` ”的类，并为“ `Peter` ”、“ `Paul` ”和“ `Pauline` ”创建类“ `Student` ”的三个实例。

“object”这个术语通常指的是实例。但它常常被用得比较宽泛，可能指代一个类或一个实例。

### 2.2 一个类是一个封装数据和函数的三格盒子



![OOP_ThreeCompartment](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/OOP_ThreeCompartment.png)

1. ***Classname*** (or identifier): identifies the class.
   Classname (或标识符)：标识类。
2. ***Data Members*** or ***Variables*** (or *attributes*, *states*, *fields*): contains the *static attributes* of the class.
   数据成员或变量（或属性、状态、字段）：包含类的静态属性。
3. ***Member Functions*** (or *methods*, *behaviors*, *operations*): contains the *dynamic operations* of the class.
   成员函数（或方法、行为、操作）：包含类的动态操作。

换句话说，一个类将静态属性（数据）和动态行为（对数据进行操作的操作）封装在一个盒子里。

**Class Members**: The *data members* and *member functions* are collectively called *class members*.
类成员：数据成员和成员函数统称为类成员。

下图展示了一些类的示例：

![OOP_ClassExamples](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/OOP_ClassExamples.png)

下图显示了类 `Student` 的两个实例，分别标识为“ `paul` ”和“ `peter` ”。

![OOP_InstanceExamples](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/OOP_InstanceExamples.png)

统一建模语言（UML）类图和实例图：上述类图是根据 UML 符号绘制的。一个类被表示为一个包含三个部分的框，分别包含名称、数据成员（变量）和成员函数。类名以粗体显示并居中。一个实例（对象）也被表示为一个包含三个部分的框，实例名称显示为 `instanceName:Classname` 并带有下划线。

##### 简要概述

- 一个类是由程序员定义的、抽象的、自包含的、可重用的软件实体，它模仿现实世界中的事物。
- 一个类是一个包含名称、数据成员（变量）和成员函数的 3 个分区的盒子。
- 一个类封装了数据结构（在数据成员中）和算法（成员函数）。数据成员的值构成了它的状态。成员函数构成了它的行为。

- 一个实例是一个类的特定项目的实例化（或实现）。

### 2.3 Class Definition 类定义

在 C++ 中，我们使用关键字 `class` 来定义一个类。类声明中有两个部分： `private` 和 `public` ，稍后会进行解释。例如，

```c++
class Circle {         // classname
private:
   double radius;      // Data members (variables)
   string color;
public:   
   double getRadius(); // Member functions
   double getArea();
}
```

```c++
class SoccerPlayer {   // classname
private:
   int number;         // Data members (variables)
   string name;
   int x, y;
public:   
   void run();         // Member functions
   void kickBall();
}
```

类命名规范：类名应为名词或由多个词组成的名词短语。所有词的首字母应大写（驼峰式）。类名使用单数名词。选择有意义且自描述的类名。例如， `SoccerPlayer` ， `HttpProxyServer` ， `FileInputStream` ， `PrintStream` 和 `SocketFactory` 。

### 2.4 创建类的实例

要创建一个类的实例，必须要满足：

- 声明特定类的一个实例标识符（名称）
- 调用构造函数来构建实例（即为实例分配储存空间并初始化变量）

例如，假设我们有一个名为 `Circle` 的类，我们可以如下创建 `Circle` 的实例：

```c++
// Construct 3 instances of the class Circle: c1, c2, and c3
Circle c1(1.2, "red");  // radius, color
Circle c2(3.4);         // radius, default color
Circle c3;              // default radius and color
```

或者，可以使用以下语法显式调用构造函数：

```c++
Circle c1 = Circle(1.2, "red");  // radius, color
Circle c2 = Circle(3.4);         // radius, default color
Circle c3 = Circle();            // default radius and color
```

### 2.5Dot (.) Operator 点号 (.) 运算符

要引用对象的成员（数据成员或成员函数），必须：

- 首先确定感兴趣的实例。然后
- 使用点运算符（` .`）来引用成员，使用为`instanceName.memberName` 

例如，假设我们有一个名为 `Circle` 的类，包含两个数据成员（ `radius` 和 `color` ）以及两个函数（ `getRadius()` 和 `getArea()` ）。我们已经创建了类 `Circle` 的三个实例，分别是 `c1` 、 `c2` 和 `c3` 。要调用函数 `getArea()` ，你必须首先确定感兴趣的实例，比如 `c2` ，然后使用点运算符，以 `c2.getArea()` 的形式调用实例 `c2` 的 `getArea()` 函数。

For example, 例如，

```c++
// Declare and construct instances c1 and c2 of the class Circle
Circle c1(1.2, "blue");
Circle c2(3.4, "green");
// Invoke member function via dot operator
cout << c1.getArea() << endl;
cout << c2.getArea() << endl;
// Reference data members via dot operator
c1.radius = 5.5;
c2.radius = 6.6;
```

调用 `getArea()` 而不指定实例是毫无意义的，因为半径是未知的（可能有多个 `Circle` 实例 - 每个实例都维护自己的半径）。

一般来说，假设有一个名为 `AClass` 的类，包含一个名为 `aData` 的数据成员和一个名为 `aFunction()` 的成员函数。为 `AClass` 构造了一个名为 `anInstance` 的实例。你使用了 `anInstance.aData` 和 `anInstance.aFunction()` 。

### 2.6数据成员（变量）Data Members (Variables) 

数据成员（变量）有一个名称（或标识符）和一个类型；并且持有该特定类型的值（如前一章所述）。数据成员也可以是某个类的实例（将在后面讨论）。

数据成员命名约定：数据成员名称应为名词或由多个词组成的名词短语。第一个词小写，其余词的首字母大写（驼峰式），例如： `fontSize` ， `roomNumber` ， `xMax` ， `yMin` 和 `xTopLeft` 。请注意，变量名以小写字母开头，而类名以大写字母开头。

### 2.7 成员函数

成员函数（如前一章所述）：

- 从调用者接受参数
- 执行函数体中定义的操作，并且
- 返回一个结果片段（`或void`)给调用者

成员函数命名规范：函数名应为动词，或由多个词组成的动词短语。第一个词小写，其余词的首字母大写（驼峰式）。例如， `getRadius()` ， `getParameterValues()` 。

请注意，数据成员名称是名词（表示静态属性），而函数名称是动词（表示动作）。它们具有相同的命名约定。尽管如此，您可以轻松地从上下文中区分它们。函数在括号中接受参数（可能有零个参数，括号为空），但变量没有。在本文中，函数用一对括号表示，例如 `println()` ， `getArea()` 以便清晰。

### 2.8 将它们组合在一起： 一个OPP实例

![OOP_Circle](https://www3.ntu.edu.sg/home/ehchua/programming/java/images/OOP_Circle.png)

一个名为 `Circle` 的类将按照类图所示进行定义。它包含两个数据成员： `radius` （类型为 `double` ）和 `color` （类型为 `String` ）；以及三个成员函数： `getRadius()` 、 `getColor()` 和 `getArea()` 。

三个 `Circle` 的实例，分别称为 `c1` 、 `c2` 和 `c3` ，随后将被构建，并带有各自的数据成员，如实例图所示。

在这个例子中，我们将所有代码保存在一个名为 `CircleAIO.cpp` 的单一源文件中。

```c++
/* The Circle class (All source codes in one file) (CircleAIO.cpp) */
#include <iostream>    // using IO functions
#include <string>      // using string
using namespace std;
 
class Circle {
private:
   double radius;      // Data member (Variable)
   string color;       // Data member (Variable)
 
public:
   // Constructor with default values for data members
   Circle(double r = 1.0, string c = "red") {
      radius = r;
      color = c;
   }
 
   double getRadius() {  // Member function (Getter)
      return radius;
   }
 
   string getColor() {   // Member function (Getter)
      return color;
   }
 
   double getArea() {    // Member function
      return radius*radius*3.1416;
   }
};   // need to end the class declaration with a semi-colon
 
// Test driver function
int main() {
   // Construct a Circle instance
   Circle c1(1.2, "blue");
   cout << "Radius=" << c1.getRadius() << " Area=" << c1.getArea()
        << " Color=" << c1.getColor() << endl;
 
   // Construct another Circle instance
   Circle c2(3.4); // default color
   cout << "Radius=" << c2.getRadius() << " Area=" << c2.getArea()
        << " Color=" << c2.getColor() << endl;
 
   // Construct a Circle instance using default no-arg constructor
   Circle c3;      // default radius and color
   cout << "Radius=" << c3.getRadius() << " Area=" << c3.getArea()
        << " Color=" << c3.getColor() << endl;
   return 0;
}
```

````
Radius=1.2 Area=4.5239 Color=blue
Radius=3.4 Area=36.3169 Color=red
Radius=1 Area=3.1416 Color=red
````

### 2.9 Constructors 构造函数

构造函数是一种特殊函数，其函数名与类名相同。在上面的 `Circle` 类中，我们定义了一个构造函数如下：

```c++
// Constructor has the same name as the class
Circle(double r = 1.0, string c = "red") {
   radius = r;
   color = c;
}
```

构造函数用于构建和初始化所有数据成员。要创建类的新实例，您需要声明实例的名称并调用构造函数。例如，

```c++
Circle c1(1.2, "blue");
Circle c2(3.4);      // default color
Circle c3;           // default radius and color
                     // Take note that there is no empty bracket ()
```

构造函数与普通函数在以下方面有所不同：

- 构造函数的名称与类名相同。
- 构造函数没有返回类型（或隐式返回 `void` ）。因此，构造函数体内不允许有 `return` 语句。
- 构造函数只能被调用一次来初始化构建的实例。你不能在程序中之后再次调用构造函数。
- 构造函数不会被继承。

### 2.10 函数的默认参数

在 C++ 中，你可以在函数头中为函数（包括构造函数）的尾部参数指定默认值。例如，

```c++
/* Test function default arguments (TestFnDefault.cpp) */
#include <iostream>
using namespace std;
 
// Function prototype
int sum(int n1, int n2, int n3 = 0, int n4 = 0, int n5 = 0);
 
int main() {
   cout << sum(1, 1, 1, 1, 1) << endl; // 5
   cout << sum(1, 1, 1, 1) << endl;    // 4
   cout << sum(1, 1, 1) << endl;       // 3
   cout << sum(1, 1) << endl;          // 2
// cout << sum(1) << endl;  // error: too few arguments
}
 
// Function definition
// The default values shall be specified in function prototype,
//   not the function implementation
int sum(int n1, int n2, int n3, int n4, int n5) {
   return n1 + n2 + n3 + n4 + n5;
}
```

### 2.11 "public" 与 "private" 访问控制修饰符

访问控制修饰符可用于控制类数据成员或函数成员的可见性，从以下俩个控制访问修饰符开始：

- 1. **public**:该成员（数据或函数）**在系统中对所有人可访问和使用的。**比如类之外`main`函数里
- 2. **private**:该成员（数据或函数）**仅在此类中(类的内部)可以访问和使用。**`main`函数不可访问

例如，在上面的 `Circle` 定义中，数据成员 `radius` 被声明为 `private` 。因此， `radius` 在 `Circle` 类内部是可访问的，但在 `类外部不可访问。换句话说，你不能使用“ c1.radius ”来引用 main()中 c1 的 `radius` 。尝试在 `main()` 中插入语句“ `cout << c1.radius; ”，并观察错误消息：

````c++
CircleAIO.cpp:8:11: error: 'double Circle::radius' is private
````

尝试将 `radius` 移动到 `public` 部分，然后重新运行该语句。

另一方面，函数 `getRadius()` 在 `Circle` 类中被声明为 `public` 。因此，它可以在 `main()` 中被调用。

**UML Notation:** In UML notation, `public` members are denoted with a "`+`", while `private` members with a "`-`" in the class diagram.
UML 表示法：在 UML 表示法中， `public` 成员用 " `+` " 表示，而 `private` 成员在类图中用 " `-` " 表示。

### 2.12 信息隐藏和封装

一个类将静态属性和动态行为封装到一个“3 个隔间的盒子”中。一旦定义了类，你可以封好这个“盒子”，并将其放在架子上供他人使用和重复使用。任何人都可以拿起这个“盒子”，并在他们的应用程序中使用它。这在传统的面向过程的语言如 C 中是无法实现的，因为静态属性（或变量）分散在整个程序和头文件中。你无法“剪切”出一部分 C 程序，插入到另一个程序中，并期望程序在没有大量修改的情况下运行。

类的成员数据通常对外部世界隐藏，使用 `private` 访问控制修饰符。通过 `public` 访问器函数提供对私有数据成员的访问，例如 `getRadius()` 和 `getColor()` 。

这遵循了信息隐藏的原则。也就是说，对象之间通过明确定义的接口（公共函数）进行通信。对象不允许了解其他对象的实现细节。实现细节被隐藏或封装在类中。信息隐藏有助于类的重用。

经验法则：除非有充分理由，否则不要将任何数据成员设为 `public` 。

### 2.13 获取器和设置器 Getter and Setters

为了让其他人能够读取 `private` 数据成员的值（称为 `xxx` ），你应当提供一个名为 `getXxx()` 的 get 函数（或 getter 或访问器函数）。getter 不必以原始格式暴露数据。它可以处理数据并限制其他人看到的数据视图。getter 不应修改数据成员。

为了允许其他类修改 `private` 数据成员的值，即 `xxx` ，你应该提供一个名为 `setXxx()` 的设置函数（或 setter 或 mutator 函数）。setter 可以提供数据验证（例如范围检查），并将原始数据转换为内部表示形式。

例如，在我们的 `Circle` 类中，数据成员 `radius` 和 `color` 被声明为 `private` 。也就是说，它们只能在 `Circle` 类内部使用，而在 `Circle` 类外部不可见——包括 `main()` 。你无法直接从 `main()` 访问 `private` 数据成员 `radius` 和 `color` ——通过 `c1.radius` 或 `c1.color` 所说的。 `Circle` 类提供了两个公共访问函数，即 `getRadius()` 和 `getColor()` 。这些函数被声明为 `public` 。 `main()` 可以调用这些公共访问函数来获取 `Circle` 对象的 `radius` 和 `color` ，通过 `c1.getRadius()` 和 `c1.getColor()` 所说的。

没有办法在 `main()` 中构造后更改 `Circle` 对象的 `radius` 或 `color` 。你不能发出像 `c1.radius = 5.0` 这样的语句来更改实例 `c1` 的 `radius` ，因为 `radius` 在 `Circle` 类中被声明为 `private` ，并且对包括 `main()` 在内的其他对象不可见。

如果 `Circle` 类的设计者允许在 `Circle` 对象构建后更改 `radius` 和 `color` ，他必须提供相应的 setter，例如：

```c++
// Setter for color
void setColor(string c) {
   color = c;
}
   
// Setter for radius
void setRadius(double r) {
   radius = r;
}
```

通过适当实现信息隐藏，类的设计者可以完全控制类的用户能做什么和不能做什么。

### 2.14关键字`this`

可以在类定义中用`this`来引用这个实例

关键字`this`的主要用途之一是解决数据成员名称和函数名称之间的歧义。例如

```c++
class Circle {
private:
   double radius;                 // Member variable called "radius"
   ......
public:
   void setRadius(double radius) { // Function's argument also called "radius"
      this->radius = radius;
         // "this.radius" refers to this instance's member variable
         // "radius" resolved to the function's argument.
   }
   ......
}
```

在上述代码中，有两个标识符称为 `radius` - 一个是数据成员，另一个是函数参数。这导致了命名冲突。为了解决命名冲突，你可以将函数参数命名为 `r` 而不是 `radius` 。然而，在此上下文中， `radius` 更接近且有意义。你可以使用关键字 `this` 来解决这个命名冲突。" `this->radius` " 指的是数据成员；而 " `radius` " 解析为函数参数。

" `this` " 实际上是指向这个对象的指针。我稍后会解释指针和 " `->` " 运算符的含义。

或者，您可以使用前缀（例如 `m_` ）或后缀（例如 `_` ）来命名数据成员，以避免名称冲突。例如，

```c++
class Circle {
private:
   double m_radius;  // or radius_
   ......
public:
   void setRadius(double radius) {
      m_radius = radius;  // or radius_ = radius
   }
   ......
}
```

C++ 编译器内部会以一个前导下划线（ `e.g., _xxx` ）开始命名其数据成员，并以两个前导下划线（例如， `__xxx` ）开始命名局部变量。因此，在你的程序中避免使用以下划线开头的名称。

### 2.15 "`const`"成员函数

一个 `const` 成员函数，由成员函数头部的 `const` 关键字标识，不能修改此对象的任何数据成员。例如，

```c++
double getRadius() const {  // const member function
   radius = 0;  
      // error: assignment of data-member 'Circle::radius' in read-only structure
   return radius;
}
```

### 2.16 Getters/Setters和构造函数的约定

`Aaa` 类中名为 `xxx` 的 `private` 数据成员的构造函数、getter 和 setter 函数具有以下约定，其类型为 `T` ：

```c++
class Aaa {
private:
   // A private variable named xxx of type T
   T xxx;
public:
   // Constructor
   Aaa(T x) { xxx = x; }
   // OR
   Aaa(T xxx) { this->xxx = xxx; }
   // OR using member initializer list (to be explained later)
   Aaa(T xxx) : xxx(xxx) { }
 
   // A getter for variable xxx of type T receives no argument and return a value of type T
   T getXxx() const { return xxx; }
 
   // A setter for variable xxx of type T receives a parameter of type T and return void
   void setXxx(T x) { xxx = x; }
   // OR
   void setXxx(T xxx) { this->xxx = xxx; }
}
```

对于 `bool` 变量 `xxx` ，getter 应命名为 `isXxx()` ，而不是 `getXxx()` ，如下所示：

```c++
private:
   // Private boolean variable
   bool xxx;
public: 
   // Getter
   bool isXxx() const { return xxx; }
 
   // Setter
   void setXxx(bool x) { xxx = x; }
   // OR
   void setXxx(bool xxx) { this->xxx = xxx; }
```

### 2.17 默认构造函数

默认构造函数是一个没有参数的构造函数，或者所有参数都有默认值的构造函数。例如，上面的`Circle`的构造函数可以作为默认构造函数，所有参数都有默认值。

```c++
Circle c1;   // Declare c1 as an instance of Circle, and invoke the default constructor
Circle c1(); // Error!
             // (This declares c1 as a function that takes no parameter and returns a Circle instance)
```

如果是 C++，如果你没有提供任何构造函数，编译器会自动提供一个默认构造函数，这个构造函数什么也不做。也就是说，

```c++
ClassName::ClassName() { }  // Take no argument and do nothing
```

如果你定义了任何构造函数，编译器不会提供默认构造函数。如果你定义的构造函数都需要参数，那么调用无参数的默认构造函数会导致错误。这是为了允许设计者通过不提供显式的默认构造函数来确保无法创建未初始化的实例。

### 2.18 构造函数的成员初始化列表

不要想下面这样在构造函数的主体内初始化私有数据成员：

```c++
Circle(double r = 1.0, string c = "red") {
   radius = r;//error
   color = c;//error
}
```

我们可以使用一种称为成员初始化列表的替代语法，如下所示：

```c++
Circle(double r = 1.0, string c = "red") : radius(r), color(c) { }
// 构造函数头部  : 初始化列表             { 构造函数体 }
Circle(double r, string c) : radius(r), color(c) { /* 函数体可以为空 */ }
```

成员初始化列表放在构造函数的头部之后，用冒号（ `:` ）分隔。每个初始化器采用 `data_member_name(parameter_name)` 的形式。对于基本类型，它等同于 `data_member_name = parameter_name` 。对于对象，将调用构造函数来构建对象。构造函数的主体（在此情况下为空）将在成员初始化列表完成后运行。

建议使用成员初始化列表来初始化所有数据成员，因为这通常比在构造函数体内进行赋值更高效。

### 2.19 *Destructor 析构函数

析构函数与构造函数类似，是一种特殊函数，其名称与类名相同，带有前缀 `~` ，例如 `~Circle()` 。当对象被销毁时，析构函数会被隐式调用。

- **是什么**: 一个特殊的成员函数，用于在对象**被销毁时**执行清理工作。
- **命名**: 名称与类名相同，但在前面加一个波浪号 `~` (例如 `~Circle()`)。
- **特性**: 没有返回值，没有参数。
- **调用**: 当对象生命周期结束时（例如，函数内的局部对象离开其作用域，或者 `delete` 一个通过 `new` 创建的对象指针时），析构函数会被**自动隐式调用**。
- **默认析构函数**: 如果你不定义析构函数，编译器会提供一个默认的，它什么也不做。
- **何时需要自定义**: 当你的类在构造时**动态分配了资源**（最常见的是使用 `new` 或 `new[]` 分配的内存），你**必须**在析构函数中使用 `delete` 或 `delete[]` 来**释放这些资源**，否则会发生内存泄漏。

如果你没有定义析构函数，编译器会提供一个默认的析构函数，它什么也不做。

```c++
class MyClass {
public:
   // The default destructor that does nothing
   ~MyClass() { }
......
}
```

##### Advanced Notes 高级笔记

- If your class contains data member which is dynamically allocated (via `new` or `new[]` operator), you need to free the storage via `delete` or `delete[]`.
  如果你的类包含通过 `new` 或 `new[]` 运算符动态分配的数据成员，你需要通过 `delete` 或 `delete[]` 释放存储空间。

### 2.20 *Copy Constructor 拷贝构造函数

- **是什么**: 一个特殊的构造函数，它的作用是**创建一个新对象，作为同一类型的另一个现有对象的副本**。

- **签名 (Signature)**: 通常形式为 `ClassName(const ClassName& other)`。它接受一个对同类对象的 `const` 引用作为参数。

- 何时调用

  1. **显式调用**: `ClassName obj2(obj1);` 或 `ClassName obj3 = obj1;` (注意 `=` 在这里是初始化，不是赋值)。
  2. 隐式调用
     - 当对象按**值传递 (pass-by-value)** 给函数时，会调用拷贝构造函数创建函数参数副本。
     - 当函数按**值返回 (return-by-value)** 一个对象时，可能调用拷贝构造函数（尽管编译器优化 RVO/NRVO 可能避免）。

- 默认拷贝构造函数

  如果你不定义拷贝构造函数，编译器会提供一个默认的。

  - **行为**: 它执行**成员逐一拷贝 (memberwise copy)**，简单地将源对象的每个成员的值复制到新对象的对应成员中。

- 浅拷贝 (Shallow Copy) 问题

  - 默认拷贝构造函数执行的是**浅拷贝**。如果类中有指针成员指向动态分配的内存，浅拷贝只会复制指针的值（内存地址），而**不会**复制指针指向的内存内容。
  - **后果**: 这导致原对象和副本对象的指针指向**同一块**内存。当其中一个对象被销毁并释放该内存时，另一个对象的指针就变成了悬空指针。如果两个对象都试图释放同一块内存（比如在析构函数中），会导致程序崩溃（double free）。修改一个对象指向的数据也会影响另一个。

- **深拷贝 (Deep Copy)**: 当类管理动态资源（如内存指针）时，通常需要**自定义拷贝构造函数**来执行**深拷贝**：为新对象分配**新的**内存，并将源对象指向的内存**内容**复制过来。

- **按引用传递 `const`**: 为了避免按值传递对象时调用拷贝构造函数的开销和潜在的浅拷贝问题，通常推荐使用**按常量引用传递 (pass-by-reference-to-const)**，即 `void myFunction(const ClassName& obj)`。这样既高效，又保证函数不会修改传入的对象。





拷贝构造函数通过复制同一类型的现有对象来构造一个新对象。换句话说，拷贝构造函数接受一个参数，该参数是同一类的对象。

如果你没有定义拷贝构造函数，编译器会提供一个默认的构造函数，它会复制给定对象的所有数据成员。例如，

```c++
Circle c4(7.8, "blue");
cout << "Radius=" << c4.getRadius() << " Area=" << c4.getArea()
     << " Color=" << c4.getColor() << endl;
                // Radius=7.8 Area=191.135 Color=blue
 
// Construct a new object by copying an existing object
// via the so-called default copy constructor
Circle c5(c4);
cout << "Radius=" << c5.getRadius() << " Area=" << c5.getArea()
     << " Color=" << c5.getColor() << endl;
                // Radius=7.8 Area=191.135 Color=blue
```

复制构造函数尤为重要。当一个对象以值的方式传递给函数时，复制构造函数将被用来创建一个参数的克隆副本。

##### Advanced Notes 高级笔记

- Pass-by-value for object means calling the copy constructor. To avoid the overhead of creating a clone copy, it is usually better to pass-by-reference-to-`const`, which will not have side effect on modifying the caller's object.
  对象的按值传递意味着调用复制构造函数。为了避免创建克隆副本的开销，通常最好使用按引用传递到 `const` ，这样不会对修改调用者的对象产生副作用。

- The copy constructor has the following signature:

  
  拷贝构造函数具有以下签名：

  ```c++
  class MyClass {
  private:
     T1 member1;
     T2 member2;
  public:
     // The default copy constructor which constructs an object via memberwise copy
     MyClass(const MyClass & rhs) {
        member1 = rhs.member1;
        member2 = rhs.member2;
     }
  ......
  }
  ```

- The default copy constructor performs *shadow copy*. It does not copy the dynamically allocated data members created via `new` or `new[]` operator.
  默认的拷贝构造函数执行浅拷贝。它不会拷贝通过 `new` 或 `new[]` 运算符创建的动态分配的数据成员。

### 2.21 *Copy Assiginment Operator ( = ) 拷贝赋值运算符

编译器还提供了一个默认的赋值运算符 ( `=` )，可用于通过逐成员复制将一个对象赋值给同一类的另一个对象。例如，使用之前定义的 `Circle` 类，

```c++
Circle c6(5.6, "orange"), c7;
cout << "Radius=" << c6.getRadius() << " Area=" << c6.getArea()
     << " Color=" << c6.getColor() << endl;
                // Radius=5.6 Area=98.5206 Color=orange
cout << "Radius=" << c7.getRadius() << " Area=" << c7.getArea()
     << " Color=" << c7.getColor() << endl;
                // Radius=1 Area=3.1416 Color=red (default constructor)
 
c7 = c6; // memberwise copy assignment
cout << "Radius=" << c7.getRadius() << " Area=" << c7.getArea()
     << " Color=" << c7.getColor() << endl;
                // Radius=5.6 Area=98.5206 Color=orange
```

##### Advanced Notes 高级笔记

- You could overload the assignment operator to override the default.
  你可以重载赋值运算符来覆盖默认设置。

- The copy constructor, instead of copy assignment operator, is used in declaration:

  
  在声明中使用了拷贝构造函数，而不是拷贝赋值运算符：

  ```c++
  Circle c8 = c6;  // Invoke the copy constructor, NOT copy assignment operator
                   // Same as Circle c8(c6)
  ```

  

- The default copy assignment operator performs *shadow copy*. It does not copy the dynamically allocated data members created via `new` or `new[]` operator.
  默认的拷贝赋值运算符执行浅拷贝。它不会复制通过 `new` 或 `new[]` 运算符创建的动态分配的数据成员。

- The copy assignment operator has the following signature:

  
  拷贝赋值运算符具有以下签名：

  ```c++
  class MyClass {
  private:
     T1 member1;
     T2 member2;
  public:
     // The default copy assignment operator which assigns an object via memberwise copy
     MyClass & operator=(const MyClass & rhs) {
        member1 = rhs.member1;
        member2 = rhs.member2;
        return *this;
     }
  ......
  }
  ```

- The copy assignment operator differs from the copy constructor in that it must release the dynamically allocated contents of the target and prevent self assignment. The assignment operator shall return a reference of this object to allow chaining operation (such as `x = y = z`).
  复制赋值运算符与复制构造函数的不同之处在于，它必须释放目标的动态分配内容并防止自赋值。赋值运算符应返回此对象的引用以允许链式操作（例如 `x = y = z` ）。

- The default constructor, default destructor, default copy constructor, default copy assignment operators are known as *special member functions*, in which the compiler will automatically generate a copy if they are used in the program and not explicitly defined.
  默认构造函数、默认析构函数、默认拷贝构造函数、默认拷贝赋值运算符被称为特殊成员函数，如果在程序中使用且未明确定义，编译器将自动生成副本。

## 3.分离头文件实现

为了更好的软件工程，建议将类声明和实现分别保存在两个独立的文件中：声明放在头文件“ `.h` ”中；而实现在“ `.cpp` ”中。这被称为分离公共接口（头文件声明）和实现。接口由设计者定义，实现可以由其他人提供。虽然接口是固定的，但不同供应商可以提供不同的实现。此外，只有头文件会暴露给用户，实现可以以对象文件“ `.o` ”（或库）的形式提供。源代码无需提供给用户。

**核心思想：**

- 声明 (Interface - 接口):放在头文件 (`.h` 或 `.hpp`)中。它告诉使用者这个类“长什么样”以及“能做什么”。这包括：
  - 类的定义框架 (`class ClassName { ... };`)。
  - 数据成员的声明。
  - 成员函数的**声明**（函数原型，只有函数名、参数列表、返回类型，没有函数体 `{}`）。
- 实现 (Implementation - 实现):放在源文件 (`.cpp`)中。它具体说明类的成员函数“如何工作”。这包括：
  - 成员函数的**定义**（包含函数体 `{}` 的完整代码）。

**为什么这样做（好处）？**

1. 接口与实现分离 (Separation of Interface and Implementation):
   - 用户（其他使用这个类的代码）只需要关心**接口**（头文件 `.h`），知道如何使用这个类即可。
   - 类的内部**实现**（源文件 `.cpp`）可以独立修改，只要不改变头文件中声明的公共接口，就不会影响到使用该类的其他代码。这提高了代码的**模块化**和**灵活性**。
2. 信息隐藏 (Information Hiding):
   - 可以将实现细节隐藏在 `.cpp` 文件中。如果发布库，可以只提供头文件和编译好的目标文件 (`.o` 或库文件 `.lib`, `.a`, `.dll`, `.so`)，而不需要提供实现部分的源代码，保护知识产权。
3. 提高编译效率 (Improved Compilation Speed):
   - 当 `.cpp` 文件中的实现代码被修改时，只需要重新编译这个 `.cpp` 文件即可。
   - 如果所有实现都放在头文件中，那么任何包含了该头文件的 `.cpp` 文件，在头文件有任何（即使是实现部分的）改动时，**都**需要重新编译，这在大型项目中会大大增加编译时间。
4. 便于团队协作 (Easier Teamwork):
   - 团队成员可以根据定义好的头文件接口，并行地去实现不同类的 `.cpp` 文件。

**例子与讲解：**

我们用之前的 `Circle` 类来演示：

**第 1 步：创建头文件 `Circle.h`**

C++

```c++
// Circle.h - Header file for the Circle class

#ifndef CIRCLE_H   // Header Guard - 防止头文件被重复包含
#define CIRCLE_H

#include <string> // 需要用到 std::string

class Circle {
private: // 数据成员声明
    double radius;
    std::string color;

public: // 公共成员函数声明 (只有原型，没有函数体)
    // Constructor declaration
    Circle(double r = 1.0, std::string c = "red");

    // Getter declarations (const because they don't modify the object)
    double getRadius() const;
    std::string getColor() const;
    double getArea() const;

    // Setter declarations
    void setRadius(double r);
    void setColor(std::string c);

    // Destructor declaration (optional if simple, but good practice)
    ~Circle();
};

#endif // CIRCLE_H
```

- **`#ifndef CIRCLE_H ... #endif`**: 这是**头文件保护符 (Header Guard)**。它确保即使这个头文件在编译过程中被多次 `#include`（直接或间接），其内容也只会被处理一次，防止重复定义错误。
- **`#include <string>`**: 因为类中用到了 `std::string`，所以需要包含相应的标准库头文件。
- **类定义**: 包含了 `private` 数据成员 `radius` 和 `color` 的声明。
- **函数声明**: 包含了所有 `public` 成员函数（构造函数、Getters、Setters、`getArea`、析构函数）的**声明**。注意，这些声明后面是分号 `;`，**没有 `{}` 函数体**。`const` 成员函数在这里也要标记 `const`。

**第 2 步：创建源文件 `Circle.cpp`**

```c++
// Circle.cpp - Implementation file for the Circle class

#include "Circle.h" // 必须包含对应的头文件，以获取类的声明
#include <iostream> // 例子：可能在析构函数等地方用到输出
#include <cmath>    // 需要 M_PI (或者自己定义 PI) 来计算面积

// Constructor definition
// 注意：使用作用域解析运算符 Circle:: 来指明这是 Circle 类的成员
Circle::Circle(double r, std::string c) : radius(r), color(c) {
    // 构造函数体，这里为空，因为初始化已在初始化列表中完成
    std::cout << "Circle object created - Radius: " << radius << ", Color: " << color << std::endl;
}

// Getter definitions
double Circle::getRadius() const {
    return radius;
}

std::string Circle::getColor() const {
    return color;
}

double Circle::getArea() const {
    // M_PI 通常在 <cmath> 或 <math.h> 中定义，或者可以自己定义 const double PI = 3.14159;
    #ifndef M_PI
    const double M_PI = 3.14159265358979323846;
    #endif
    return radius * radius * M_PI;
}

// Setter definitions
void Circle::setRadius(double r) {
    // 可以加入验证逻辑
    if (r >= 0) {
        radius = r;
    } else {
        std::cerr << "Error: Radius cannot be negative." << std::endl;
    }
}

void Circle::setColor(std::string c) {
    // 可以加入验证逻辑
    color = c;
}

// Destructor definition
Circle::~Circle() {
    // 在这里执行清理工作，例如释放动态分配的内存
    // 这个简单的例子中不需要做什么
    std::cout << "Circle object destroyed - Radius: " << radius << ", Color: " << color << std::endl;
}
```

- **`#include "Circle.h"`**: **必须**首先包含对应的头文件 `Circle.h`。注意这里用的是**双引号 `""`**，通常表示包含项目内的本地文件，而不是尖括号 `<>`（用于标准库或系统库）。
- **作用域解析运算符 `::`**: 在定义类的成员函数时，必须在函数名前加上 `类名::` (例如 `Circle::getRadius`)，以告诉编译器这个函数是属于 `Circle` 类的。
- **函数体**: 这里提供了在 `Circle.h` 中声明的所有函数的**完整实现**（带有 `{}` 函数体）。

**第 3 步：在其他地方使用 `Circle` 类 (例如 `main.cpp`)**

```c++
// main.cpp - Example usage of the Circle class

#include "Circle.h" // 只需要包含头文件即可
#include <iostream>

int main() {
    // 创建 Circle 对象，调用构造函数
    Circle c1(2.5, "blue");
    Circle c2; // 使用默认参数调用构造函数 (radius=1.0, color="red")

    // 使用 public getter 方法
    std::cout << "Circle 1 - Radius: " << c1.getRadius() << ", Color: " << c1.getColor() << ", Area: " << c1.getArea() << std::endl;
    std::cout << "Circle 2 - Radius: " << c2.getRadius() << ", Color: " << c2.getColor() << ", Area: " << c2.getArea() << std::endl;

    // 使用 public setter 方法
    c1.setRadius(3.0);
    c1.setColor("yellow");
    std::cout << "Circle 1 (modified) - Radius: " << c1.getRadius() << ", Color: " << c1.getColor() << ", Area: " << c1.getArea() << std::endl;

    // 对象 c1 和 c2 在 main 函数结束时会自动销毁，调用析构函数
    return 0;
}
```

- **`#include "Circle.h"`**: `main.cpp` 只需要包含 `Circle.h` 头文件。它不需要知道 `Circle.cpp` 中的实现细节，只需要知道 `Circle` 类的接口（有哪些公有成员和函数）。

- 编译和链接

  :

  1. 编译器会分别编译 `Circle.cpp` 生成 `Circle.o` (目标文件)。
  2. 编译器会编译 `main.cpp` 生成 `main.o` (目标文件)。`main.o` 知道要调用 `Circle` 的函数，但不知道它们的具体实现在哪里。
  3. **链接器 (Linker)** 会将 `Circle.o` 和 `main.o` (以及其他需要的库) 连接起来，生成最终的可执行文件。链接器负责找到 `main.o` 中调用的 `Circle` 函数在 `Circle.o` 中的具体实现地址。

## 4 示例：`Circle`类

![ClassDiagramCircle](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/ClassDiagramCircle.png)

不要将所有代码放在一个文件中。我们应该通过将代码放在 3 个文件中来“分离接口和实现”。

- `Circle.h` : 定义了 `Circle` 类的公共接口。
- `Circle.cpp` : 提供了 `Circle` 类的实现。
- `TestCircle.cpp` : `Circle` 类的测试驱动程序。

#### Circle.h - 头文件

```c++
#include <string>   // using string
using namespace std;
 
// Circle class declaration
class Circle {
private:   // Accessible by members of this class only
   // private data members (variables)
   double radius;
   string color;
 
public:    // Accessible by ALL
   // Declare prototype of member functions
   // Constructor with default values
   Circle(double radius = 1.0, string color = "red");
 
   // Public getters & setters for private data members
   double getRadius() const;
   void setRadius(double radius);
   string getColor() const;
   void setColor(string color);
 
   // Public member Function
   double getArea() const;
};
```

头文件包含声明语句，告诉编译器有关名称和类型的信息，以及函数原型，但不包含实现细节。

你可以在函数头中为函数参数提供默认值。例如，

````c++
Circle(double radius = 1.0, string color = "red");
````

Header 包含函数原型，参数名称会被编译器忽略，但作为文档很有用。例如，你可以在原型中省略参数名称，如下所示

````c++
Circle(double = 1.0, string = "red");   // without identifiers
   // Identifiers not needed in prototype but good to serve as documentation
````

头文件应包含常量、函数原型、类/结构声明。

#### Circle.cpp - 实现

```c++
#include "Circle.h" // user-defined header in the same directory
 
// Constructor
// default values shall only be specified in the declaration,
// cannot be repeated in definition
Circle::Circle(double r, string c) {
   radius = r;
   color = c;
}
 
// Public getter for private data member radius
double Circle::getRadius() const {
   return radius;
}
 
// Public setter for private data member radius
void Circle::setRadius(double r) {
   radius = r;
}
 
// Public getter for private data member color
string Circle::getColor() const {
   return color;
}
 
// Public setter for private data member color
void Circle::setColor(string c) {
   color = c;
}
 
// A public member function
double Circle::getArea() const {
   return radius*radius*3.14159265;
}
```

实现文件提供了函数的定义，这些定义在头文件中被省略。

编译器首先在当前目录中搜索双引号中的头文件（例如 `"Circle.h"` ），然后搜索系统的包含目录。对于尖括号中的头文件（例如 `<iostream>` ），编译器不会搜索当前目录，而只会搜索系统的包含目录。因此，对于用户定义的头文件，请使用双引号。

您需要在所有成员名称前加上 `className::` （称为类作用域解析运算符），以便告知编译器该成员属于特定类。

（类作用域：在类内部定义的名称具有所谓的类作用域。它们仅在类内部可见。因此，你可以在两个不同的类中使用相同的名称。要在类外部使用这些名称，需要使用类作用域解析运算符 `className::` 。）

你不能在实现中放置默认参数（它们应该放在头文件中）。例如，

````c++
Circle::Circle(double r = 1.0, string c = "red") {   // error!
````

#### 编译 Circle 类

您可以使用 GNU GCC 中的选项 `-c` （仅编译）将 `Circle.cpp` 编译成名为 `Circle.o` 的目标文件：

要使用 `Circle` 类，用户需要 `Circle.h` 和 `Circle.o` 。他不需要 `Circle.cpp` 。换句话说，你不需要提供你的源代码，而只需要提供公共声明和目标代码。

#### TestCircle.cpp - 测试驱动程序

```c++
/* A test driver for the Circle class (TestCircle.cpp) */
#include <iostream>
#include "Circle.h"   // using Circle class
using namespace std;
 
int main() {
   // Construct an instance of Circle c1
   Circle c1(1.2, "red");
   cout << "Radius=" << c1.getRadius() << " Area=" << c1.getArea()
        << " Color=" << c1.getColor() << endl;
 
   c1.setRadius(2.1);   // Change radius and color of c1
   c1.setColor("blue");
   cout << "Radius=" << c1.getRadius() << " Area=" << c1.getArea()
        << " Color=" << c1.getColor() << endl;
 
   // Construct another instance using the default constructor
   Circle c2;
   cout << "Radius=" << c2.getRadius() << " Area=" << c2.getArea()
        << " Color=" << c2.getColor()  << endl;
   return 0;
}
```

#### 链接

````c++
g++ -c circle.cpp -o circle.o
g++ TestCircle.cpp Circle.o -o TestCircle
./TestCircle
````

#### 输出

````
Radius=1.2 Area=4.52389 Color=red
Radius=2.1 Area=13.8544 Color=blue
Radius=1 Area=3.14159 Color=red
````



## 5 示例：`Time`类

![ClassDiagramTime](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/ClassDiagramTime.png)

让我们编写一个名为 `Time` 的类，它模拟时间的特定实例，具有小时、分钟和秒的值，如类图所示。

类 `Time` 包含以下成员：

- 三个 `private` 数据成员： `hour` (0-23)、 `minute` (0-59) 和 `second` (0-59)，默认值为 0。
- 一个 `public` 构造函数 `Time()` ，它初始化数据成员 `hour` 、 `minute` 和 `second` ，使用调用者提供的值。
- `public` 私有数据成员的 getter 和 setter 方法： `getHour()` ， `getMinute()` ， `getSecond()` ， `setHour()` ， `setMinute()` 和 `setSecond()` 。
- 一个 `public` 成员函数 `setTime()` 用于设置调用者提供的 `hour` 、 `minute` 和 `second` 的值。
- 一个 `public` 成员函数 ```print()` 用于以格式 " `hh:mm:ss` " 打印此 `Time` 实例，零填充，例如 `01:30:04` 。
- 一个 `public` 成员函数 `nextSecond()` ，它将此实例增加一秒。 `nextSecond()` 的 `23:59:59` 应为 `00:00:00` 。

让我们为 `Time` 类编写代码，将头文件和实现分开在两个文件中： `Time.h` 和 `Time.cpp` 。

##### Header - Time.h 

```c++
/* Header for the Time class (Time.h) */
#ifndef TIME_H   // Include this "block" only if TIME_H is NOT defined
#define TIME_H   // Upon the first inclusion, define TIME_H so that
                 //  this header will not get included more than once
class Time {
private:  // private section
   // private data members
   int hour;     // 0 - 23
   int minute;   // 0 - 59
   int second;   // 0 - 59
 
public:   // public section
   // public member function prototypes
   Time(int h = 0, int m = 0, int s = 0); 
  // Constructor with default values
   int getHour() const;   
  // public getter for private data member hour
   void setHour(int h);   
  // public setter for private data member hour
   int getMinute() const; 
  // public getter for private data member minute
   void setMinute(int m); 
  // public setter for private data member minute
   int getSecond() const; 
  // public getter for private data member second
   void setSecond(int s); 
  // public setter for private data member second
   void setTime(int h, int m, int s);  
  // set hour, minute and second
   void print() const; 
  // Print a description of this instance in "hh:mm:ss"
   void nextSecond();  
  // Increase this instance by one second
};  // need to terminate the class declaration with a semicolon
 
#endif  // end of "#ifndef" block
```

##### 解析 Time.h

`#ifndef TIME_H`
`#define TIME_H`
......
`#endif`

为了防止头文件被多次包含到源文件中（如果某个实体被声明两次，可能会导致编译错误，例如 `int i` ），我们将头文件代码包裹在一对预处理器指令 `#ifndef` （如果未定义）和 `#endif` 中。如果标识符 `TIME_H` 尚未被定义，则 if 块内的代码才会被包含。第一次包含时是这样的情况，同时也会定义标识符 `TIME_H` （if 块体内的第一个指令）。后续的包含是不可能的，因为 `TIME_H` 在第一次包含时已被定义。按照惯例，对于头文件 `Xxx.h` ，使用标识符 `XXX_H` （或 `XXX_H_INCLUDED` ）。

````c++
class Time {
private:  私有：
......
public:  公共:
......
};

````

头文件 `Time.h` 包含类 `Time` 的类声明。它分为两个部分： `private` 和 `public` 。 `private` 成员（数据或函数）只能被该类的成员访问，而 `public` 成员对所有人可见（例如类外的 `main()` 函数）。类声明必须以分号结束。

````c++
private:  私有：
   int hour;
   int minute;
   int second;
public:  公共:
   ......

````

我们声明了三个私有数据成员，分别名为 `hour` 、 `minute` 和 `second` 。在 C++98/C++03 中，你**不允许在类声明中初始化数据成员**（除了 `const` `static` `int` 数据成员）。例如，设置 `hour = 0` 会导致编译错误。相反，数据成员应在构造函数中初始化（稍后会展示）。较新的 C++11 允许初始化数据成员。

在类声明中仅列出成员函数原型。函数原型由返回类型、函数名称和参数类型组成。

````c++
Time(int h = 0, int m = 0, int s = 0);
````

声明了所谓的构造函数。构造函数是一个特殊函数，其名称与类名相同。构造函数没有返回类型，或者隐式返回 `void` 。构造函数体内不允许有 `return` 语句。构造函数只能在实例声明期间使用，以初始化实例的数据成员。此后不能再调用它。

在头文件的函数原型中，我们可以使用“ `= default-value` ”为任何函数成员设置函数参数的默认值。在这种情况下，此构造函数可以被调用时传入 0 到 3 个参数，省略的尾随参数将被设置为它们的默认值，例如，

```c++
Time t1(1, 2, 3); // no default used
Time t2(1, 2);    // s = 0 (default)
Time t3(1);       // m = 0, s = 0 (defaults)
Time t4;          // h = 0, m = 0, s = 0 (all defaults) - no empty parentheses ()
```

标识符 `h` 、 `m` 和 `s` 在函数原型中不是必需的 - 您只需要指定参数的类型。但它们作为适当的文档非常有用，强烈推荐使用。

````c++
int getHour() const;
void setHour(int h);
int getHour() const;
void setHour(int h);
int getHour() const;
void setHour(int h);
````

声明私有数据成员 `hour` 、 `minute` 和 `second` 的所谓 getter 和 setter。由于数据成员是 `private` ，在类外部无法访问，因此通常提供 `public` getter 和 setter 来读取和修改 `private` 数据成员。按照惯例，getter 不从调用者接收任何内容（ `void` ），并返回数据成员类型的值；setter 接收一个数据成员类型的值，并返回 `void` 。Setter 可能会在设置数据成员的值之前验证输入。

我们通过在函数参数列表后放置关键字 `const` ，将 getter 函数 ``声明为常量。 `const` 成员函数不能修改此对象的任何数据成员。**Getter 不需要修改任何数据成员**。

````c++
void setTime(int h, int m, int s);
````

声明一个公共成员函数，用于在一次调用中设置此实例的 `hour` 、 `minute` 和 `second` 。

````c++
void print() const;
````

声明一个公共成员函数以打印此实例，格式为 `HH:MM:SS` ，用零填充，例如 `01:56:09` 。函数 `print()` 返回 `void` 。

````c++
void nextSecond();
````

声明一个公共成员函数，将此实例增加一秒。例如， `23:59:59` 变成 `00:00:00` 。函数 `nextSecond()` 返回 `void` 。

##### 解析运算符 ( `::` )

所有成员的标识符前都带有类名和作用域解析运算符 ( `::` )，例如 `Time::Time` 和 `Time::getHour` ，这样编译器就能辨识这些标识符属于特定类

##### 实现 - Time.cpp

```c++
/* Implementation for the Time Class (Time.cpp) */
#include <iostream>
#include <iomanip>
#include "Time.h"    // include header of Time class
using namespace std;
 
// Constructor with default values. No input validation
Time::Time(int h, int m, int s) {
   hour = h;
   minute = m;
   second = s;
}
 
// public getter for private data member hour
int Time::getHour() const {
   return hour;
}
 
// public setter for private data member hour. No input validation
void Time::setHour(int h) {
   hour = h;
}
 
// public getter for private data member minute
int Time::getMinute() const {
   return minute;
}
 
// public setter for private data member minute. No input validation
void Time::setMinute(int m) {
   minute = m;
}
 
// public getter for private data member second
int Time::getSecond() const {
   return second;
}
 
// public setter for private data member second. No input validation
void Time::setSecond(int s) {
   second = s;
}
 
// Set hour, minute and second. No input validation
void Time::setTime(int h, int m, int s) {
   hour = h;
   minute = m;
   second = s;
}
 
// Print this Time instance in the format of "hh:mm:ss", zero filled
void Time::print() const {
   cout << setfill('0');    // zero-filled, need <iomanip>, sticky
   cout << setw(2) << hour  // set width to 2 spaces, need <iomanip>, non-sticky
        << ":" << setw(2) << minute
        << ":" << setw(2) << second << endl;
}
 
// Increase this instance by one second
void Time::nextSecond() {
   ++second;
   if (second >= 60) {
      second = 0;
      ++minute;
   }
   if (minute >= 60) {
      minute = 0;
      ++hour;
   }
   if (hour >= 24) {
      hour = 0;
   }
}/* Time 类的实现 (Time.cpp) */
#include <iostream>  // 用于 cout
#include <iomanip>   // 用于 setfill, setw (格式化输出)
#include "Time.h"    // 包含 Time 类的头文件定义
using namespace std;

// 构造函数，带有默认值。没有进行输入验证。
Time::Time(int h = 0, int m = 0, int s = 0) { // 构造函数实现，如果创建对象时不提供参数，则默认为0
   hour = h;
   minute = m;
   second = s;
}

// 公有的 getter 函数，用于获取私有数据成员 hour 的值
int Time::getHour() const { // const 表示此函数不会修改对象的状态
   return hour;
}

// 公有的 setter 函数，用于设置私有数据成员 hour 的值。没有进行输入验证。
void Time::setHour(int h) {
   hour = h;
}

// 公有的 getter 函数，用于获取私有数据成员 minute 的值
int Time::getMinute() const { // const 表示此函数不会修改对象的状态
   return minute;
}

// 公有的 setter 函数，用于设置私有数据成员 minute 的值。没有进行输入验证。
void Time::setMinute(int m) {
   minute = m;
}

// 公有的 getter 函数，用于获取私有数据成员 second 的值
int Time::getSecond() const { // const 表示此函数不会修改对象的状态
   return second;
}

// 公有的 setter 函数，用于设置私有数据成员 second 的值。没有进行输入验证。
void Time::setSecond(int s) {
   second = s;
}

// 设置 时、分、秒。没有进行输入验证。
void Time::setTime(int h, int m, int s) {
   hour = h;
   minute = m;
   second = s;
}

// 以 "hh:mm:ss" 的格式打印当前 Time 实例，不足两位的前面补零
void Time::print() const { // const 表示此函数不会修改对象的状态
   cout << setfill('0');    // 设置填充字符为 '0' (需要 <iomanip>), 这是粘性的 (sticky)，会影响后续输出直到被改变
   cout << setw(2) << hour  // 设置字段宽度为 2 (需要 <iomanip>), 这是非粘性的 (non-sticky)，只影响紧随其后的输出项
        << ":" << setw(2) << minute
        << ":" << setw(2) << second << endl;
}

// 将当前时间实例增加一秒
void Time::nextSecond() {
   ++second; // 秒数加 1
   if (second >= 60) { // 如果秒数达到或超过 60
      second = 0;      // 秒数归零
      ++minute;        // 分钟数加 1
   }
   if (minute >= 60) { // 如果分钟数达到或超过 60
      minute = 0;      // 分钟数归零
      ++hour;          // 小时数加 1
   }
   if (hour >= 24) {   // 如果小时数达到或超过 24
      hour = 0;        // 小时数归零 (回到午夜)
   }
}
```

##### 解析 Time.cpp

实现文件 `Time.cpp` 包含成员的定义（而头文件包含声明），特别是成员函数。

实现中所有成员的标识符前都带有类名和作用域解析运算符 ( `::` )，例如 `Time::Time` 和 `Time::getHour` ，这样编译器就能辨识这些标识符属于特定类，在本例中为 `Time` 。

````c++
Time::Time(int h, int m, int s) {
   hour = h;
   minute = m;
   second = s; 
}
````

在构造函数中，我们根据调用者提供的输入初始化 `private` 数据成员 `hour` 、 `minute` 和 `second` 。C++ 不会初始化基本类型（例如 `int` 、 `double` ）的数据成员。如果在使用数据成员之前未对其进行初始化，C++ 也不会发出错误消息。因此，强烈建议在构造函数中初始化所有数据成员，这样构造的实例就是完整的，而不是依赖用户在构造后设置数据成员的值。

参数的默认值在类声明（在头文件中）中指定，而不是在函数定义中指定。在函数定义中放置默认值（例如， `h = 0` ）会导致编译错误。

请注意，我们在构造函数（以及 setters）中没有包含输入验证（例如，小时应在 0 到 23 之间）。我们将在后面的示例中进行此操作。

````c++
int Time::getHour() const {
   return hour;
}
````

私有数据成员 `hour` 的公共 getter 简单地返回数据成员 `hour` 的值。

````c++
void Time::setHour(int h) {
   hour = h;
}
````

私有数据成员 `hour` 的公共设置器将数据成员 `hour` 设置为给定的值 `h` 。同样，对于 h 没有输入验证（应在 0 到 23 之间）。

#####  "this" 指针

我们不希望将函数参数命名为 `h` 、 `m` 和 `s` ，而是希望将参数命名为 `hour` 、 `minute` 和 `second` ，这些名称在语义上更有意义。然而，这些名称与私有数据成员的名称冲突。C++ 提供了一个关键字 `this` （这是一个指向当前实例的指针——稍后讨论），用于区分数据成员和函数参数。 `this->hour` 、 `this->minute` 和 `this->second` 指的是数据成员；而 `hour` 、 `minute` 和 `second` 指的是函数参数。我们可以按如下方式重写构造函数和 setter：

```c++
Time::Time(int hour, int minute, int second) {  // Constructor
   this->hour = hour;
   this->minute = minute;
   this->second = second;
}
 
Time::setHour(int hour) {   // Setter for hour
   this->hour = hour;
}
 
Time::getHour() const {  // Getter for hour
   return this->hour;    // this-> is the default, and hence optional
}
```

##### Member Initializer List 成员初始化列表

C++ 提供了一种替代语法来在构造函数中初始化数据成员，称为成员初始化列表。例如，

```c++
Time::Time(int h, int m, int s) : hour(h), minute(m), second(s) { 
   // The body runs after the member initializer list
   // empty in this case
}
```

成员初始化列表放在函数参数列表之后，用冒号分隔，形式为 `dataMemberName(parameters)` 。对于基本类型的数据成员（例如， `int` ， `double` ）， `hour(h)` 与 `hour = h` 相同。对于对象数据成员（稍后讨论），将调用拷贝构造函数。函数体将在成员初始化列表之后执行，在本例中为空。

初始化列表中的数据成员按照类声明中它们的声明顺序进行初始化，而不是初始化列表中的顺序。

##### 测试驱动程序 - TestTime.cpp

````c++
/* Test Driver for the Time class (TestTime.cpp) */
#include <iostream>
#include "Time.h"    // include header of Time class
using namespace std;
 
int main() {
   Time t1(23, 59, 59);   // Test constructor
 
   // Test all public member functions
   t1.print();       // 23:59:59
   t1.setHour(12);
   t1.setMinute(30);
   t1.setSecond(15);
   t1.print();       // 12:30:15
   cout << "Hour is "   << t1.getHour()   << endl;
   cout << "Minute is " << t1.getMinute() << endl;
   cout << "Second is " << t1.getSecond() << endl;
 
   Time t2;     // Test constructor with default values for hour, minute and second
   t2.print();  // 00:00:00
   t2.setTime(1, 2, 3);
   t2.print();  // 01:02:03
 
   Time t3(12); // Use default values for minute and second
   t3.print();  // 12:00:00
 
   // Test nextSecond()
   Time t4(23, 59, 58);
   t4.print();
   t4.nextSecond();
   t4.print();
   t4.nextSecond();
   t4.print();
 
   // No input validation
   Time t5(25, 61, 99); // values out of range
   t5.print();  // 25:61:99
}
````



````c++
23 : 59 : 59
22 : 30 : 15
Hour is 22
Minute is 30
Second is 15
00 : 00 : 00
01 : 02 : 03
12 : 00 : 00
23 : 59 : 58
23 : 59 : 59
24 : 00 : 00
25 : 61 : 99
````

##### 解析 TestTime.cpp

测试驱动程序测试构造函数（包括和不包括默认值）以及所有公共成员函数。显然，没有进行输入验证，如实例 `t5` 中所反映的。

##### Exercise 练习

将成员函数 `previousSecond()` 、 `nextMinute()` 、 `previousMinute()` 、 `nextHour()` 、 `previousHour()` 添加到 `Time` 类中。

头文件

````c++
#ifndef TIME_H
#define TIME_H

class Time{
  private:
    int hour;
    int minute;
    int second;
  public:
    Time(int h=0,int m =0,int s=0);
    int getHour()const;
    void setHour(int h);
    int getMinute()const;
    void setMinute(int m);
    int getSecond()const;
    void setSecond(int s);
    void setTime(int h,int m ,int s);
    void print()const;
    void nextSecond();
    //new menber function
    void previousSecond();
    void nextMinute();
    void previousMinute();
    void nextHour();
    void previousHour();
};
#endif
````

实现文件

````c++
#include<iostream>
#include"Time.h"
#include<iomanip>
using namespace std;

Time :: Time(int h, int m ,int s){
    hour = h;
    minute = m;
    second = s;
}
int Time::getHour()const{
    return hour;
}
void Time::setHour(int h){
    hour=h;
}
int Time::getMinute()const{
    return minute;
}
void Time::setMinute(int m){
    minute =m;
}
int Time::getSecond()const{
    return second;
}
void Time::setSecond(int s){
    second=s;
}
void Time::setTime(int h,int m,int s){
    hour =h;
    minute =m;
    second =s;
}
void Time::print()const{
    if(hour>=25||minute>=61||second>=61){
        cout <<"Error"<<endl;
    } else {cout<<setfill('0');
          cout<<setw(2)<<hour
           <<" : "<<setw(2)<<minute
           <<" : "<<setw(2)<<second<<endl;
    }
}
void Time::nextSecond(){
    ++second;
    if(second>=60){
        second = 0;
        ++minute;
    }
    if(minute>=60){
        minute = 0;
        ++hour;
    }
    if(hour>=24){
        hour =0;
    }
}
void Time::previousSecond(){
    -- second;
    if(second < 0){
        second =59;
        --minute; 
        if(minute<0){
            minute = 59;
            -- hour ;
            if(hour <0){
                hour =23;
            }
        }
        
    }
    
}
void Time::nextMinute(){
    ++ minute;
    if(minute>=60){
        minute=0;
        ++hour;
    }
    if(hour>=24){
        hour =0;
    }
}
void Time::previousMinute(){
    --minute;
    if(minute<0){
        minute =59;
        --hour;
        if(hour <0){
            hour =23;
        }
    }
}
void Time::nextHour(){
    ++hour;
    if(hour>=24){
        hour =0;
    }
}
void Time::previousHour(){
    --hour;
    if(hour <0){
        hour =23;
    }
}
````

测试文件

````c++
#include<iostream>
#include"Time.h"
using namespace std;

int main(){
    Time t1 (23,59,59);
    t1. print();
    t1.setHour(22);
    t1.setMinute(30);
    t1.setSecond(15);
    t1.print();
    t1.previousHour();
    t1.print();
    t1.nextHour();
    t1.print();
    t1.previousMinute();
    t1.print();
    t1.nextMinute();
    t1.print();
    t1.previousSecond();
    t1.print();
    cout<<"Hour is "<<t1.getHour()<<endl;
    cout<<"Minute is "<<t1.getMinute()<<endl;
    cout<<"Second is "<<t1.getSecond()<<endl;
    Time t2;
    t2.print();
    t2.setTime(1,2,3);
    t2.print();

    Time t3(12);
    t3.print();

    Time t4(23,59,58);
    t4.print();
    t4.nextSecond();
    t4.print();
    t4.nextSecond();
    t4.print();
    t4.previousSecond();
    t4.print();
    
    Time t5 (25,61,99);
    t5.print();
    
    Time t6;
    t6.previousMinute();
    t6.print();

    Time t7;
    t7.previousHour();
    t7.print();
    
    Time t8(23,59,00);
    t8.print();
    t8.nextMinute();
    t8.print();

    Time t9(24,59,00);
    t9.print();
    t9.nextHour();
    t9.print();
    t9.nextMinute();
    t9.print();

}
````

输出

````
23 : 59 : 59
22 : 30 : 15
21 : 30 : 15
22 : 30 : 15
22 : 29 : 15
22 : 30 : 15
22 : 30 : 14
Hour is 22
Minute is 30
Second is 14
00 : 00 : 00
01 : 02 : 03
12 : 00 : 00
23 : 59 : 58
23 : 59 : 59
00 : 00 : 00
23 : 59 : 59
Error
23 : 59 : 00
23 : 00 : 00
23 : 59 : 00
00 : 00 : 00
24 : 59 : 00
00 : 59 : 00
01 : 00 : 00
````

编译方式

````c++
windows:
g++ -o TestTime.exe Time.cpp TestTime.cpp  
macos:
g++ -o TestTime Time.cpp TestTime.cpp  
````

```c++
windows
// Compile Time.cpp into object file Time.o, with -c option
> g++ -c Time.cpp
// Compile test driver with object file
> g++ -o TestTime.exe TestTime.cpp Time.o
// Execute the test driver
> TestTime
macos
 > g++ -c Time.cpp
 > g++ -o TestTime TestTime.cpp Time.o
  
```

## 6. 示例：Point 类

![ClassDiagramPoint](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/ClassDiagramPoint.png)

`Point` 类，如类图所示，建模具有 x 和 y 坐标的 2D 点。

在类图中，“ `-` ”表示 `private` 成员；“ `+` ”表示 `public` 成员。“ `= xxx` ”指定数据成员的默认值。

`Point` 类包含以下内容：

- 私有数据成员 `x` 和 `y` （类型为 `int` ），默认值为 0。
- 一个构造函数，私有数据成员 `x` 和 `y` 的 getter 和 setter 方法。
- 一个 setXY() 函数，用于设置 `Point` 的 `x` 和 `y` 坐标。
- 一个函数 `getMagnitude()` ，它返回 `√(x2+y2)` 。你可以在 `<cmath>` 中使用内置的 `sqrt()` 函数来计算平方根。
- 一个函数 `getArgument()` ，它返回 `tan-1(y/x)` 。你可以在 `<cmath>` 中使用内置的 `atan2(y, x)` 函数来计算以弧度为单位的梯度。
- 一个函数 `print()` ，用于打印此实例的“ `(x,y)` ”。

##### Point.h - 头文件

```c++
/* The Point class Header (Point.h) */
#ifndef POINT_H
#define POINT_H
 
// Point class declaration
class Point {
private:
   // private data members (variables)
   int x;
   int y;
 
public:
   // Declare member function prototypes
   Point(int x = 0, int y = 0);  // Constructor with default values
   int getX() const;
   void setX(int x);
   int getY() const;
   void setY(int y);
   void setXY(int x, int y);
   double getMagnitude() const;
   double getArgument() const;
   void print() const;
};
 
#endif
```

##### Point.cpp - 实现

```c++
/* The Point class Implementation (Point.cpp) */
#include "Point.h" // user-defined header in the same directory
#include <iostream>
#include <cmath>
using namespace std;
 
// Constructor (default values can only be specified in the declaration)
Point::Point(int x, int y) : x(x), y(y) { }  // Use member initializer list
 
// Public getter for private data member x
int Point::getX() const {
   return x;
}
 
// Public setter for private data member x
void Point::setX(int x) {
   this->x = x;
}
 
// Public getter for private data member y
int Point::getY() const {
   return y;
}
 
// Public setter for private data member y
void Point::setY(int y) {
   this->y = y;
}
 
// Public member function to set both x and y
void Point::setXY(int x, int y) {
   this->x = x;
   this->y = y;
}
 
// Public member function to return the magnitude
double Point::getMagnitude() const {
   return sqrt(x*x + y*y);    // sqrt in <cmath>
}
 
// Public member function to return the argument
double Point::getArgument() const {
   return atan2(y, x);    // atan2 in <cmath>
}
 
// Public member function to print description about this point
void Point::print() const {
   cout << "(" << x << "," << y << ")" << endl;
}
```

##### TestPoint.cpp - 测试驱动程序

```c++
/* A test driver for the Point class (TestPoint.cpp) */
#include <iostream>
#include <iomanip>
#include "Point.h"   // using Point class
using namespace std;
 
int main() {
   // Construct an instance of Point p1
   Point p1(3, 4);
   p1.print();
   cout << "x = " << p1.getX() << endl;
   cout << "y = " << p1.getY() << endl;
   cout << fixed << setprecision(2);
   cout << "mag = " << p1.getMagnitude() << endl;
   cout << "arg = " << p1.getArgument() << endl;
   p1.setX(6);
   p1.setY(8);
   p1.print();
   p1.setXY(1, 2);
   p1.print();
 
   // Construct an instance of Point using default constructor
   Point p2;
   p2.print();
}
```

## 7. 示例：Account 类

![ClassDiagramAccount](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/ClassDiagramAccount.png)

一个名为 `Account` 的类，模拟银行账户，其设计如类图所示。它包含：

- 两个私有数据成员： `accountNumber` ( `int` ) 和 `balance` ( `double` )，用于维护当前账户余额。
- 公共函数 `credit()` 和 `debit()` ，分别用于从余额中增加或减少给定金额。如果 `amount` 大于 `balance` ，则 `debit()` 函数应打印“取款金额超过当前余额！”
- 一个公共函数 `print()` ，它应打印 "A/C no: xxx Balance=xxx"（例如，A/C no: 991234 Balance=$88.88），其中 `balance` 保留两位小数。

##### 头文件 - Account.h

```c++
/* Header for Account class (Account.h) */
#ifndef ACCOUNT_H
#define ACCOUNT_H
 
class Account {
private:
   int accountNumber;
   double balance;
 
public:
   Account(int accountNumber, double balance = 0.0);
   int getAccountNumber() const;
   double getBalance() const;
   void setBalance(double balance);
   void credit(double amount);
   void debit(double amount);
   void print() const;
};
 
#endif
```

##### 实现文件 - Account.cpp

```c++
/* Implementation for the Account class (Account.cpp) */
#include <iostream>
#include <iomanip>
#include "Account.h"
using namespace std;
 
// Constructor
Account::Account(int no, double b) : accountNumber(no), balance(b) { }
 
// Public getter for private data member accountNumber
int Account::getAccountNumber() const {
   return accountNumber;
}
 
// Public getter for private data member balance
double Account::getBalance() const {
   return balance;
}
 
// Public setter for private data member balance
void Account::setBalance(double b) {
   balance = b;
}
 
// Adds the given amount to the balance
void Account::credit(double amount) {
   balance += amount;
}
 
// Subtract the given amount from the balance
void Account::debit(double amount) {
   if (amount <= balance) {
      balance -= amount;
   } else {
      cout << "Amount withdrawn exceeds the current balance!" << endl;
   }
}
 
// Print description for this Account instance
void Account::print() const {
   cout << fixed << setprecision(2);
   cout << "A/C no: " << accountNumber << " Balance=$" << balance << endl;
}
```

##### 测试驱动程序 - TestAccount.cpp

```c++
/* Test Driver for Account class (TestAccount.cpp) */
#include <iostream>
#include "Account.h"
 
using namespace std;
 
int main() {
    Account a1(8111, 99.99);
    a1.print();     // A/C no: 8111 Balance=$99.99
    a1.credit(20);
    a1.debit(10);
    a1.print();     // A/C no: 8111 Balance=$109.99
 
    Account a2(8222);  // default balance
    a2.print();        // A/C no: 8222 Balance=$0.00
    a2.setBalance(100);
    a2.credit(20);
    a2.debit(200);  // Amount withdrawn exceeds the current balance!
    a2.print();     // A/C no: 8222 Balance=$120.00
    return 0;
}
```

## 8. 示例：Ball 类

![ClassDiagramBall](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/ClassDiagramBall.png)

一个 `Ball` 类模拟一个移动的球，按照类图所示设计，包含以下成员：

- 四个 `private` 数据成员 `x` 、 `y` 、 `xSpeed` 和 `ySpeed` 用于维护球的位置和速度。
- 一个构造函数，以及私有数据成员的公共 getter 和 setter 方法。
- 一个函数 `setXY()` ，用于设置球的位置，以及 `setXYSpeed()` 用于设置球的速度。
- 一个函数 `move()` ，它分别将 `x` 和 `y` 增加 `xSpeed` 和 `ySpeed` 。
- 一个函数 `print()` ，它打印 " `Ball @ (x,y) with speed (xSpeed,ySpeed)` "，保留 2 位小数。

##### 头文件 - Ball.h

```c++
/* Header for the Ball class (Ball.h) */
#ifndef BALL_H
#define BALL_H
 
class Ball {
private:
   double x, y;           // Position of the ball
   double xSpeed, ySpeed; // Speed of the ball
 
public:
   Ball(double x = 0.0, double y = 0.0,  // Constructor with default values
        double xSpeed = 0.0, double ySpeed = 0.0);
   double getX() const;
   void setX(double x);
   double getY() const;
   void setY(double y);
   double getXSpeed() const;
   void setXSpeed(double xSpeed);
   double getYSpeed() const;
   void setYSpeed(double ySpeed);
   void setXY(double x, double y);
   void setXYSpeed(double xSpeed, double ySpeed);
   void move();
   void print() const;
};
 
#endif
```

##### 实现文件 - Ball.cpp

```c++
/* Implementation for the Ball Class (Ball.cpp) */
#include <iostream>
#include <iomanip>
#include "Ball.h"    // include header of Ball class
using namespace std;
 
// Constructor with default values. No input validation
Ball::Ball(double x, double y, double xSpeed, double ySpeed)
      : x(x), y(y), xSpeed(xSpeed), ySpeed(ySpeed) { }  // use member initializer list
 
// public getters/setters for private data members
double Ball::getX() const {
   return x;
}
double Ball::getY() const {
   return y;
}
void Ball::setX(double x) {
   this->x = x;
}
void Ball::setY(double y) {
   this->y = y;
}
double Ball::getXSpeed() const {
   return xSpeed;
}
double Ball::getYSpeed() const {
   return ySpeed;
}
void Ball::setXSpeed(double xSpeed) {
   this->xSpeed = xSpeed;
}
void Ball::setYSpeed(double ySpeed) {
   this->ySpeed = ySpeed;
}
 
// Set position (x,y)
void Ball::setXY(double x, double y) {
   this->x = x;
   this->y = y;
}
 
// Set speed (xSpeed,ySpeed)
void Ball::setXYSpeed(double xSpeed, double ySpeed) {
   this->xSpeed = xSpeed;
   this->ySpeed = ySpeed;
}
 
// Move the ball by increases x and y by xSpeed and ySpeed
void Ball::move() {
   x += xSpeed;   // increment x by xSpeed
   y += ySpeed;   // increment y by ySpeed
}
 
// Print a description about this Ball instance
void Ball::print() const {
   cout << fixed << setprecision(2);
   cout << "Ball @ (" << x << ',' << y << ") with speed ("
        << xSpeed << ',' << ySpeed << ')' << endl;
}
```

##### 测试驱动程序 - TestBall.cpp

```c++
/* Test Driver for the Ball class (TestBall.cpp) */
#include <iostream>
#include "Ball.h"    // include header of Ball class
using namespace std;
 
int main() {
   Ball ball;
   ball.print();    // Ball @ (0.00,0.00) with speed (0.00,0.00)
   ball.setXY(1.1, 2.2);
   ball.setXYSpeed(3.3, 4.4);
   ball.print();    // Ball @ (1.10,2.20) with speed (3.30,4.40)
   ball.setX(5.5);
   ball.setY(6.6);
   cout << "x is " << ball.getX() << endl;  // x is 5.50
   cout << "y is " << ball.getY() << endl;  // y is 6.60
   ball.move();
   ball.print();    // Ball @ (8.80,11.00) with speed (3.30,4.40)
}
```

## 9. 示例：作者和书籍类（用于书店）

### 9.1 让我们从 Author 类开始![ClassDiagramAuthor](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/ClassDiagramAuthor.png)

让我们从一个名为 `Author` 的类开始，其设计如类图所示。它包含：

- 三个 `private` 数据成员： `name` ( `string` )， `email` ( `string` )，以及 `gender` ( `char` 的 `'m'` ， `'f'` 或 `'u'` 表示未知)。
- 一个构造函数，用于初始化 `name` 、 `email` 和 `gender` ，并使用给定的值。数据成员没有默认值。
- 获取 `name` 、 `email` 和 `gender` 的 getter，以及 `email` 的 setter。没有 `name` 和 `gender` 的 setter，因为我们假设这些属性无法更改。
- 一个 `print()` 成员函数，打印“name (gender) at email”，例如，“Peter Jones (m) at peter@somewhere.com”。

##### 头文件 - Author.h

```c++
/* Header for the Author class (Author.h) */
#ifndef AUTHOR_H
#define AUTHOR_H
 
#include <string>
using namespace std;
 
class Author {
private:
   string name;
   string email;
   char gender;   // 'm', 'f', or 'u' for unknown
 
public:
   Author(string name, string email, char gender);
   string getName() const;
   string getEmail() const;
   void setEmail(string email);
   char getGender() const;
   void print() const;
};
 
#endif
```

##### Author.cpp

```c++
/* Implementation for the Author class (Author.cpp) */
#include <iostream>
#include "Author.h"
using namespace std;
 
// Constructor, with input validation
Author::Author(string name, string email, char gender) {
   this->name = name;
   setEmail(email);  // Call setter to check for valid email
   if (gender == 'm' || gender == 'f') {
      this->gender = gender;
   } else {
      cout << "Invalid gender! Set to 'u' (unknown)." << endl;
      this->gender = 'u';
   }
}
 
string Author::getName() const {
   return name;
}
 
string Author::getEmail() const {
   return email;
}
 
void Author::setEmail(string email) {
   // Check for valid email. Assume that a valid email contains
   //  a '@' that is not the first nor last character.
   size_t atIndex = email.find('@');
   if (atIndex != string::npos && atIndex != 0 && atIndex != email.length()-1) {
      this->email = email;
   } else {
      cout << "Invalid email! Set to empty string." << endl;
      this->email = "";
   }
}
 
char Author::getGender() const {
   return gender;
}
 
// print in the format "name (gender) at email"
void Author::print() const {
   cout << name << " (" << gender << ") at " << email << endl;
}
```

##### 解析 Author.cpp

````c++
Author::Author(string name, string email, char gender) {
   this->name = name;
   setEmail(email);
````

在这个例子中，我们在函数参数中使用标识符 `name` ，它与数据成员的标识符 `name` 发生冲突。为了区分这两个标识符，我们使用关键字 `this` ，它是指向此实例的指针。 `this->name` 指的是数据成员；而 `name` 指的是函数参数。

参数 `name` 没有进行输入验证。另一方面，对于 `email` ，我们调用了执行输入验证的 setter `setEmail()` 。

````c++
void Author::setEmail(string email) {
   size_t found = email.find('@');
   if (found != string::npos && found != 0 && found != email.length()-1) {
      this->email = email;
   } else {
      cout << "Invalid email! Set to empty string." << endl;
      this->email = "";
   }
````

为了验证 `email` ，我们假设有一个 `'@'` ，它不是第一个或最后一个字符（还有其他更严格的电子邮件验证标准）。我们使用 `string` 类的函数 `find()` 来查找字符 `'@'` 的位置，该函数返回类型为 `size_t` 的值（通常与 `unsigned int` 相同）。函数 `find()` 返回一个特殊常量 `string::npos` （通常设置为 -1）以表示“未找到”；0 表示第一个字符， `length()-1` 表示最后一个字符（其中 `string` 的函数 `length()` 返回字符串的长度）。

##### TestAuthor.cpp

```c++
/* Test Driver for the Author class (TestAuthor.cpp) */
#include "Author.h"
 
int main() {
   // Declare and construct an instance of Author
   Author peter("Peter Jones", "peter@somewhere.com", 'm');
   peter.print();
      // Peter Jones (m) at peter@somewhere.com
   peter.setEmail("peter@xyz.com");
   peter.print();
      // Peter Jones (m) at peter@xyz.com
 
   Author paul("Paul Jones", "@somewhere.com", 'n');
      // Invalid email! Set to empty string.
      // Invalid gender! Set to 'u' (unknown).
   paul.setEmail("paul@");
      // Invalid email! Set to empty string.
   paul.print();
      // Paul Jones (u) at
}
```

### 9.2 一本书由作者编写 - 使用“对象”数据成员

![ClassDiagramBook](https://www3.ntu.edu.sg/home/ehchua/programming/cpp/images/ClassDiagramBook.png)

让我们设计一个 `Book` 类。假设一本书只能由一个作者编写。 `Book` 类（如类图所示）包含以下成员：

- 四个 `private` 数据成员： `name` ( `string` )， `author` (我们之前创建的类 `Author` 的一个实例)， `price` ( `double` )，以及 `qtyInStock` ( `int` ，默认值为 0)。 `price` 应为正数， `qtyInStock` 应为零或正数。
- 四个 `private` 数据成员： `name` ( `string` )， `author` (我们之前创建的类 `Author` 的一个实例)， `price` ( `double` )，以及 `qtyInStock` ( `int` ，默认值为 0)。 `price` 应为正数， `qtyInStock` 应为零或正数。
- `public` 的 getter 和 setter 用于 `private` 数据成员。请注意， `getAuthor()` 返回一个对象（ `Author` 类的实例）。
- 一个 `public` 成员函数 `print()` ，它会打印“'book-name' by author-name (gender) @ email”。
- 一个 `public` 成员函数 `getAuthorName()` ，它返回此 `Book` 实例的作者的 `name` 。

图中的空心菱形表示聚合（或 has-a）关联关系。也就是说，一个 `Book` 实例拥有一个（且仅一个） `Author` 实例作为其组成部分。

##### 头文件 - Book.h

```c++
/* Header for the class Book (Book.h) */
#ifndef BOOK_H
#define BOOK_H
 
#include <string>
#include "Author.h"   // Use the Author class
using namespace std;
 
class Book {
private:
   string name;
   Author author; // data member author is an instance of class Author
   double price;
   int qtyInStock;
 
public:
   Book(string name, Author author, double price, int qtyInStock = 0);
      // To recieve an instance of class Author as argument
   string getName() const;
   Author getAuthor() const;  // Returns an instance of the class Author
   double getPrice() const;
   void setPrice(double price);
   int getQtyInStock() const;
   void setQtyInStock(int qtyInStock);
   void print() const;
   string getAuthorName() const;
};
 
#endif
```

````c++
#include "Author.h"
````

我们需要包含“ `Author.h` ”头文件，因为我们在当前类 `Book` 中使用了 `Author` 类。

````c++
private:
   Author author;
````

我们声明一个 `private` 数据成员 `author` 作为类 `Author` 的实例，该类之前已定义。

##### 实现文件 - Book.cpp

```c++
/* Implementation for the class Book (Book.cpp) */
#include <iostream>
#include "Book.h"
using namespace std;
 
// Constructor, with member initializer list to initialize the
//  component Author instance
Book::Book(string name, Author author, double price, int qtyInStock)
      : name(name), author(author) {   // Must use member initializer list to construct object
   // Call setters to validate price and qtyInStock
   setPrice(price);
   setQtyInStock(qtyInStock);
}
 
string Book::getName() const {
   return name;
}
 
Author Book::getAuthor() const {
   return author;
}
 
double Book::getPrice() const {
   return price;
}
 
// Validate price, which shall be positive
void Book::setPrice(double price) {
   if (price > 0) {
      this->price = price;
   } else {
      cout << "price should be positive! Set to 0" << endl;
      this->price = 0;
   }
}
 
int Book::getQtyInStock() const {
   return qtyInStock;
}
 
// Validate qtyInStock, which cannot be negative
void Book::setQtyInStock(int qtyInStock) {
   if (qtyInStock >= 0) {
      this->qtyInStock = qtyInStock;
   } else {
      cout << "qtyInStock cannot be negative! Set to 0" << endl;
      this->qtyInStock = 0;
   }
}
 
// print in the format ""Book-name" by author-name (gender) at email"
void Book::print() const {
   cout << "'" << name << "' by ";
   author.print();
}
 
// Return the author' name for this Book
string Book::getAuthorName() const {
   return author.getName();   // invoke the getName() on instance author
}
```

````c++
Book::Book(string name, Author author, double price, int qtyInStock)
      : name(name), author(author) {
   setPrice(price);
   setQtyInStock(qtyInStock);
}
````

在构造函数中，调用者应该创建一个 `Author` 的实例，并将该实例传递给构造函数。我们使用成员初始化列表来初始化数据成员 `name` 和 `author` 。我们在函数体中调用 setters，这些 setters 会执行输入验证来设置 `price` 和 `qtyInStock` 。函数体在成员初始化列表之后运行。 `author(author)` 调用 `Author` 类的默认拷贝构造函数，该构造函数会对所有数据成员执行逐成员拷贝。对象数据成员应通过成员初始化列表构造，而不应在函数体中构造。否则，将调用默认构造函数来构造对象。

````c++
void Book::setPrice(double price) {
   if (price > 0) {
      this->price = price;
   } else {
      cout << "price should be positive! Set to 0" << endl;
      this->price = 0;
   }
}
````

`price` 的 setter 会验证给定的输入。

````c++
string Book::getAuthorName() const {
   return author.getName();
}
````

调用数据成员 `author` 的 `getName()` ，它返回此 `Book` 实例的作者姓名。

##### TestBook.cpp

```c++
/* Test Driver for the Book class (TestBook.cpp) */
#include <iostream>
#include "Book.h"
using namespace std;
 
int main() {
   // Declare and construct an instance of Author
   Author peter("Peter Jones", "peter@somewhere.com", 'm');
   peter.print();  // Peter Jones (m) at peter@somewhere.com
 
   // Declare and construct an instance of Book
   Book cppDummy("C++ for Dummies", peter, 19.99,1);
   cppDummy.setQtyInStock(88);
   cppDummy.print();
      // 'C++ for Dummies' by Peter Jones (m) at peter@somewhere.com
 
   cout << cppDummy.getQtyInStock() << endl;  // 88
   cout << cppDummy.getPrice() << endl;       // 19.99
   cout << cppDummy.getAuthor().getName() << endl;  // "Peter Jones"
   cout << cppDummy.getAuthor().getEmail() << endl; // "peter@somewhere.com"
   cout << cppDummy.getAuthorName() << endl;        // "Peter Jones"
 
   Book moreCpp("More C++ for Dummies", peter, -19.99,1);
      // price should be positive! Set to 0
   cout << moreCpp.getPrice() << endl;   // 0
}
```

````
Peter Jones (m) at peter@somewhere.com
 ' C++ for Dummies ' by Peter Jones (m) at peter@somewhere.com
88
3.03226e-314
Peter Jones
peter@somewhere.com
Peter Jones
price should be positive! Set to 0
0
````

##### The Default Copy Constructor 默认拷贝构造函数

构造函数中的初始化器 `author(author)` 调用了所谓的拷贝构造函数。拷贝构造函数通过复制同一类的给定实例来创建一个新实例。如果您在类中没有提供拷贝构造函数，C++ 会提供一个默认的拷贝构造函数，它通过逐个成员复制来构造一个新对象。例如，对于 `Author` 类，编译器提供的默认拷贝构造函数如下：

```c++
// Default copy constructor of Author class provided by C++
Author::Author(const Author& other)
      : name(other.name), email(other.email), gender(other.gender) { }  // memberwise copy
```

## 9.3对象的引用传递作为函数参数 Author 和 string

默认情况下，对象是以值传递的方式传入函数的。也就是说，会创建一个克隆副本并传入函数，而不是原始副本。对于大型对象，值传递会因为创建克隆副本的开销而影响性能。

相反，我们可以通过引用将对象传入函数，使用参数列表中的引用（ `&` ）声明。如果我们不打算在函数内部修改对象（对原始副本产生副作用），我们将其设置为 `const` 。

在 `Book` 类中， `string` 和 `Author` 的数据成员是对象。 `Author` 类之前已定义； `string` 是 C++ 头文件 `<string>` 中提供的一个类，属于命名空间 `std` 。我们不应该在头文件中包含“ `using namespace std;` ”（因为这种做法不好，该语句会被包含在使用此头文件的所有文件中），而是应当使用作用域解析运算符，并将其称为 `std::string` 。

让我们修改我们的 `Book` 类来展示按引用传递（为了性能）。

```c++
/* Header for Author class (Author.h) */
#ifndef AUTHOR_H
#define AUTHOR_H
 
#include <string>
 
class Author {
private:
   std::string name;
   std::string email;
   char gender;   // 'm', 'f', or 'u' for unknown
 
public:
   Author(const std::string & name, const std::string & email, char gender);
          // & specifies pass by reference, const for non-mutable
   std::string getName() const;
   std::string getEmail() const;
   void setEmail(const std::string & email);
   char getGender() const;
   void print() const;
};
 
#endif
```

- 在 C++ 中， `string` 是标准库中的一个类（在头文件 中，属于命名空间 `std` ），就像我们定义的 `Point` 、 `Circle` 类一样。
- 而不是包含“using namespace std;”，因为这会是一个不好的做法，因为这个语句将会被包含在所有使用此头文件的文件中，我们使用完全限定的名称std::string。
- 不是通过值传递 `string` 对象到函数中，因为这会影响性能，需要创建克隆副本。我们通过引用传递 `string` 对象（由 `&` 表示）。
- 然而，在按引用传递中，函数内部的更改会影响函数外部调用者的副本。
- 如果我们不打算在函数内部更改对象，可以使用关键字 `const` 来表示不可变性。如果在函数内部无意中更改了对象，编译器会报错。

##### Author.cpp

```c++
/* Implementation for the Author class (Author.cpp) */
#include <iostream>
#include "Author.h"
using namespace std;
 
// Constructor, with input validation
Author::Author(const string & name, const string & email, char gender) : name(name) {
   setEmail(email);  // Call setter to check for valid email
   if (gender == 'm' || gender == 'f') {
      this->gender = gender;
   } else {
      cout << "Invalid gender! Set to 'u' (unknown)." << endl;
      this->gender = 'u';
   }
}
 
string Author::getName() const {
   return name;
}
 
string Author::getEmail() const {
   return email;
}
 
void Author::setEmail(const string & email) {
   // Check for valid email. Assume that a valid email contains
   //  a '@' that is not the first nor last character.
   size_t atIndex = email.find('@');
   if (atIndex != string::npos && atIndex != 0 && atIndex != email.length()-1) {
      this->email = email;
   } else {
      cout << "Invalid email! Set to empty string." << endl;
      this->email = "";
   }
}
 
char Author::getGender() const {
   return gender;
}
 
// print in the format "name (gender) at email"
void Author::print() const {
   cout << name << " (" << gender << ") at " << email << endl;
}
```

Program Notes: 程序说明：

````c++
Author::Author(const string & name, const string & email, char gender) { ...... }
````

在构造函数中， `string` 对象通过引用传递。这提高了性能，因为它消除了创建临时（克隆）对象的需要。然后构造函数调用 `string` 类的拷贝构造函数，将参数逐个成员复制到其数据成员 `name` 和 `email` 中。

我们将参数设置为 `const` ，以防止它们在函数内部被修改（从而对原始副本产生副作用）。

````c++
Book(const string & name, const Author & author, double price, int qtyInStock = 0);
````

`string` 和 `Author` 对象 ``通过引用传递到构造函数中。这提高了性能，因为它避免了在按值传递中创建临时克隆副本。参数被标记为 `const` ，因为我们不打算在函数内部修改它们（对原始副本产生副作用）。

````c++
Author getAuthor() const;
````

该 getter 返回数据成员 `author` 的副本。

##### Book.cpp

```c++
/* Implementation for the class Book (Book.cpp) */
#include <iostream>
#include "Book.h"
using namespace std;
 
// Constructor, with member initializer list to initialize the
//  component Author instance
Book::Book(const string & name, const Author & author, double price, int qtyInStock)
      : name(name), author(author) { // Init object reference in member initializer list
   // Call setters to validate price and qtyInStock
   setPrice(price);
   setQtyInStock(qtyInStock);
}
 
string Book::getName() const {
   return name;
}
 
Author Book::getAuthor() {
   return author;
}
 
double Book::getPrice() const {
   return price;
}
 
// Validate price, which shall be positive
void Book::setPrice(double price) {
   if (price > 0) {
      this->price = price;
   } else {
      cout << "price should be positive! Set to 0" << endl;
      this->price = 0;
   }
}
 
int Book::getQtyInStock() const {
   return qtyInStock;
}
 
// Validate qtyInStock, which cannot be negative
void Book::setQtyInStock(int qtyInStock) {
   if (qtyInStock >= 0) {
      this->qtyInStock = qtyInStock;
   } else {
      cout << "qtyInStock cannot be negative! Set to 0" << endl;
      this->qtyInStock = 0;
   }
}
 
// print in the format ""Book-name" by author-name (gender) at email"
void Book::print() const {
   cout << "'" << name << "' by ";
   author.print();
}
 
// Return the author' name for this Book
string Book::getAuthorName() const {
   return author.getName();   // invoke the getName() on instance author
}
```

````c++
Book::Book(const string & name, Author & author, double price, int qtyInStock)
      : name(name), author(author) { ...... }
````

`name(name)` 和 `author(author)` 调用默认拷贝构造函数，通过逐成员拷贝参数来构造 `string` 和 `Author` 的新实例。

````c++
Author Book::getAuthor() { return author; }
````

数据成员 `author` 的副本被返回给调用者。

你应该避免将私有数据成员的引用返回给调用者（例如， `Author & Book::getAuthor() { return author; }` ），因为调用者可以通过引用更改私有数据成员，这破坏了“信息隐藏和封装”的概念。

##### 测试驱动程序 - TestBook.cpp

````c++
/* Test Driver for the Book class (TestBook.cpp) */
#include <iostream>
#include "Book.h"
using namespace std;
 
int main() {
   // Declare and construct an instance of Author
   Author peter("Peter Jones", "peter@somewhere.com", 'm');
   peter.print();  // Peter Jones (m) at peter@somewhere.com
 
   // Declare and construct an instance of Book
   Book cppDummy("C++ for Dummies", peter, 19.99);
   cppDummy.print();
      // 'C++ for Dummies' by Peter Jones (m) at peter@somewhere.com
 
   peter.setEmail("peter@xyz.com");
   peter.print();   // Peter Jones (m) at peter@xyz.com
   cppDummy.print();
      // 'C++ for Dummies' by Peter Jones (m) at peter@somewhere.com
 
   cppDummy.getAuthor().setEmail("peter@abc.com");
   cppDummy.print();
      // 'C++ for Dummies' by Peter Jones (m) at peter@somewhere.com
}
````

在上述测试程序中，构造了一个名为 `peter` 的 `Author` 实例（在第 8 行）。此实例通过引用传递到 `Book` 的构造函数中（第 12 行），以创建 `Book` 的实例 `cppDummy` 。
