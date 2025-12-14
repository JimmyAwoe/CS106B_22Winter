View what I learned from CS106B.

---

##### 零碎知识点

- **C++程序的编译过程** C++代码文件称为 source file，要想使其可以运行，实现需要编译器将其转换为 Object file，这些 object file 在经过一个 Linking 阶段，和其他 object file 进行链接后生成最后的可执行文件。

- **NameSpace** C++给库作者提供一种选择，NameSpace，库作者可以选做使用特定的 NameSpace 封装整个库，使得其在被导入时更安全。例如 iostream 的 NameSpace 就是 std。如果没有设置 NameSpace，那么可以直接在全局作用域下，即`::`进行调用。

- **main** C++从 main 函数开始执行，main()函数执行完成后退出。

- **precedence and associativity** 对于同一个操作数，若其参与了不同的运算符的运算，将先由高 precedence 的运算符使用，如果两个运算符的优先级一样，那么则有他们的 associativity 来决定是从左向右运算还是从右向左运算。

- **>>操作符** >>操作符一旦遇到空白符就会结束，空白操作符包括空格,tab，回车。

##### 数据类型

- 一个数据类型包含两方面，数据范围和操作集合。

- C++的基础数据类型包含五类，integer，floating-point，Boolean, character, enumerated.他们被称为 atomic 或 primitive types。C++中允许自定义数据类型。

- const 会使一个变量变成只读

##### Expression

- **类型转换** 如果一个表达式中包含不同类型的数据，那么会进行类型转换。C++内置了一个类型阶梯，位于低位的数据类型会被转换为高位的数据类型。

- **Type Cast** 可以使用 double(variable)，int(variable)，这样来直接进行类型转换

- **?:判别式** `(condition)?exp1:exp2`当 condition 满足时执行 exp1 否则 exp2。

- **switch** 判断 e 表达式的结果是否匹配 c1，...其中 c1 这些通常是常数

```c++
switch (e) {
    case c1:
    statements
    break;
    case c2:
    statements
    break;
    ...
    default:
    statements
    break;
}
```

##### function

- **Basic** ①C++的函数只允许一个返回值

- **function prototype**在 C++中，代码是逐行编译的，因此如果函数的定义写到函数调用之后了，那么就需要在前面进行函数断言，函数断言由函数的第一行加上分号组成。

- **function overloading** 同样的函数名称，但是参数的数量/类型有不同这在 C++中是允许的，这被称为函数重载，一般用来对不同的参数执行类似的操作。

- **default parameter** 和 python 一样，C++也允许设置默认参数，但是 C++的默认参数只需要在函数断言中设置，而不需要在函数定义中设置。

- **pass-by-value or pass-by-reference** C++允许手动设定函数传入的变量是在函数域内构建一个新变量(pass-by-value)还是直接引用地址(pass-by-reference)。他的实现方式是在函数的参数类型声明中加&，例如

```c++
void foo(int& n)
{
   n++;
}
```

##### String

- **Basic** ①String 实际上就是一个数组，包含一系列的 char② 可以使用+来连接两个 String 或 String 和 char③String 可以通过索引调用，且在 C++中 String 是可变的，即可以修改其单个元素

- **特殊的 loop 方式**

```C++
for (char ch: s){
    cout << ch;
}
```

- **两种字符串** string literal 其实是 C 风格的字符串，而使用 string var = xxx 得到的是 C++风格的字符串。任何字符串的操作，当操作数的某一方是 C++风格的字符串时，是安全的。
