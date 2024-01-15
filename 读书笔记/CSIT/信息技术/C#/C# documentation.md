https://learn.microsoft.com/en-us/dotnet/csharp/





# Get started



## [Introduction - A tour of the C# language](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/)

文档里竟然提到 C# 是 ***component-oriented*** 的，我暂译「面向组件」的，又是一个全新的概念。根据文档中的解释大概是说 C# 可以通过各种组件来迅速完成项目的交付。

接下来讲的就是 C# 拥有的一些特性，差不多也都是 OOP 编程语言（或者说是 Java）固有的一些特性，如[**垃圾回收（*Garbage collection*）**](https://learn.microsoft.com/en-us/dotnet/standard/garbage-collection/)、**[空类型（*Nullable types*）](https://learn.microsoft.com/en-us/dotnet/csharp/nullable-references)**、[**异常处理（*Exception handling*）**](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/exceptions/)、[**lambda 表达式（*Lambda expressions*）**](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/lambda-expressions)等。*[**LINQ（Language Integrated Query）**](https://learn.microsoft.com/en-us/dotnet/csharp/linq/)*倒是一个没听说过的概念，大概是与数据源打交道的一种语法。C# 中对[**异步操作（*asynchronous operations*）**](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/)提供的支持可以有效地构建分布式系统。C# 有一个[**统一类型系统**](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/types/)（暂译，英文为：*[**unified type system**](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/types/)*）。在 C# 中，所有的类型，如 `int`、`double` 都继承自一个根类型 `object`（又是个似曾相识的东西），这印证了 C# 对数据类型的设计思路上似乎与 Java 有着些许不同。所有类型共用一组通用运算。然后介绍用户自定义[引用类型（*reference types*）](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/reference-types)/[值类型（*value types*）](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/value-types)、泛型方法、迭代器等。其中「值类型」又是一个有点陌生的概念呢。

C# 强调**版控（*versioning*）**——好神奇，这如何强调Σ(⊙▽⊙"a）？随即引出了两个修饰符：`virtual` 与 `override`。只看概念很难理解，交给后续实战开发了再理解也不迟。

### [.NET architecture](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/#net-architecture)

C# 程序运行在 .NET 上，所谓 .NET 是一种名为**公共语言运行库（common language runtime，CLR）**的虚拟运行系统，并包含一系列类库。而 CLR 是 Microsoft 对公共语言基础结构（CLI）国际标准的实现。CLI 是创建执行和开发环境的基础，并且语言和库可以在其中无缝协同运转。





> 

### [Hello world](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/#hello-world)

```c#
using System;

class Hello
{
    static void Main()
    {
        // This line prints "Hello, World" 
        Console.WriteLine("Hello, World");
    }
}
```

`using` 指令表示引用了一个叫 `System` 的**命名空间（*namespace*）**。所谓「命名空间」提供了一种将 C# 程序和库整合起来的分层方法。命名空间包含了类型和其他命名空间——举个例子，`System` 命名空间包含了一些类型，比如程序中引用到的 `Console` 类，以及其他命名空间如 `IO`、`Collections`。

程序第一行使用了 `using` 指令，意味着 `Console.WriteLine()` 就毋须写成 `System.Console.WriteLine()`。

本程序中，`Hello` 类只有一个「成员」，也就是 `Main` 方法。与 Java 一样，`Main` 方法也是使用 `static` 来修饰。实例方法可以通过使用关键字 `this` 引用特定的封闭对象实例，而静态方法则可以在不引用特定对象的情况下运行。按照约定，`Main` 静态方法是 C# 程序的入口点。

### [Types and variables](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/#types-and-variables)

类型（*type*）可以定义 C# 中的任何数据的结构和行为。

- 值类型

    - 简单类型
        - [有符号整型](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types)：`sbyte`、`short`、`int`、`long`
        - 无符号类型
        - [Unicode 字符](https://learn.microsoft.com/en-us/dotnet/standard/base-types/character-encoding-introduction)：
        - IEEE 二进制浮点：
        - 高精度十进制浮点数：
        - 布尔值
    - 枚举类型
    - 结构类型
    - 可以为 null 的值类型
    - 元组值类型

- 引用类型

    - 类类型
    - 接口类型
        - 
    - 数组类型
        - 一维、多维与交错。例如：`int[]`、`int[,]` 和 `int[][]`
    - 委托类型
        - 格式为 `delegate int D(...)` 的用户定义类型

    

### [Program structure](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/#program-structure)





## [Types - C# types and members](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/types)

作为 OOP 语言，C#（同样地，也）具有封装、继承与多态的特性。

在 C# 中，struct 是一种轻量级的类；也是「栈分配」类型，可以实现接口，但不支持继承。C# 提供了 `record class` 与 `record struct` 类型，它们的用途主要在于存储数据值。

### Classes and objects

#### Type parameters

#### Base classes

### Structs

### Interfaces

### Enums

### Nullable types

### Tuples

C# 支持[元组（*tuples*）](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/value-tuples)，



## [Program building blocks - C# program building blocks](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/program-building-blocks)



## [Major language areas - C# major language areas](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/features)



## [C# language strategy - Annotated C# strategy](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/strategy)



## Tutorials



# Fundamentals



## Program structure - General Structure of a C# Program



## Type system



## Object-oriented programming



## Functional techniques



## Exceptions and errors



## Coding style

### [C# identifier names - C# identifier naming rules and conventions](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/identifier-names)

在 C# 中，标识符意味着可以给类型（包括类（class）、接口（interface）、结构（struct）、委托（delegate）、枚举（enum））、成员、变量或命名空间自定义名称。

#### Naming rules



#### Naming conventions





### C# coding conventions









### [Overview - General Structure of a C# Program](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/program-structure/)



### [Main method - `Main()` and command-line arguments](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/program-structure/main-command-line)



### [Top-level statements - programs without `Main` methods](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/program-structure/top-level-statements)











# What's new in C#



## [What's new in C# 12](https://learn.microsoft.com/en-us/dotnet/csharp/whats-new/csharp-12)









# Tutorials



# Language Integrated Query (LINQ)



### [Query expression overview](https://learn.microsoft.com/en-us/dotnet/csharp/linq/#how-to-enable-linq-querying-of-your-data-source)



## [Overview of LINQ](https://learn.microsoft.com/en-us/dotnet/csharp/linq/)



### [How to enable LINQ querying of your data source](https://learn.microsoft.com/en-us/dotnet/csharp/linq/#how-to-enable-linq-querying-of-your-data-source)



### [`IQueryable` LINQ providers](https://learn.microsoft.com/en-us/dotnet/csharp/linq/#iqueryable-linq-providers)





## Getting Started with LINQ in C#



### [Introduction to LINQ queries](https://learn.microsoft.com/en-us/dotnet/csharp/linq/get-started/introduction-to-linq-queries)



## Standard query operators

### [Overview](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/standard-query-operators-overview)





### [Introduction to LINQ Queries (C#)](https://learn.microsoft.com/en-us/dotnet/csharp/linq/get-started/introduction-to-linq-queries)

*query* 是一种从数据源中检索数据的表达式。在实际开发中，不同的数据源有不同的本地查询语言，例如关系型数据库是 SQL 而 XML 是 XQuery。这也就意味着，开发人员需要为每一种类型的数据源或数据格式去学习新的查询语言。

LINQ 通过提供了一种跨越多种数据源或格式，也能始终一致的 C# 语言模型，化解了这一难题。通过使用 LINQ，你可以只与 C# 对象打交道。你可以使用基本的编码方式来查询、转换 XML 文档、SQL 数据库、.NET 集合中的数据以及任何其他格式的数据。

#### Three Parts of a Query Operation

所有的 LINQ 查询操作由以下三种操作组成：

1. 获取数据源。
2. 创建查询。
3. 执行查询。

以下示例给我们展现了这三个部分在源代码中的具体表现形式。为了便捷，示例中使用了整数数组作为数据源；然而实际上，对其他数据源也是同样的概念。此案例将会贯穿本文余下内容。

```c#
// The Three Parts of a LINQ Query:
// 1. Data source.
int[] numbers = [ 0, 1, 2, 3, 4, 5, 6 ];

// 2. Query creation.
// numQuery is an IEnumerable<int>
var numQuery =
    from num in numbers
    where (num % 2) == 0
    select num;

// 3. Query execution.
foreach (int num in numQuery)
{
    Console.Write("{0,1} ", num);
}
```



#### The Data Source



#### The Query



#### Query Execution

##### Deferred Execution



# [Asynchronous programming](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/)



## [Overview - Asynchronous programming with async and await](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/)



```c#
using System;
using System.Threading.Tasks;

namespace AsyncBreakfast
{
    // These classes are intentionally empty for the purpose of this example. They are simply marker classes for the purpose of demonstration, contain no properties, and serve no other purpose.
    internal class Bacon { }
    internal class Coffee { }
    internal class Egg { }
    internal class Juice { }
    internal class Toast { }

    class Program
    {
        static void Main(string[] args)
        {
            Coffee cup = PourCoffee();
            Console.WriteLine("coffee is ready");

            Egg eggs = FryEggs(2);
            Console.WriteLine("eggs are ready");

            Bacon bacon = FryBacon(3);
            Console.WriteLine("bacon is ready");

            Toast toast = ToastBread(2);
            ApplyButter(toast);
            ApplyJam(toast);
            Console.WriteLine("toast is ready");

            Juice oj = PourOJ();
            Console.WriteLine("oj is ready");
            Console.WriteLine("Breakfast is ready!");
        }

        private static Juice PourOJ()
        {
            Console.WriteLine("Pouring orange juice");
            return new Juice();
        }

        private static void ApplyJam(Toast toast) =>
            Console.WriteLine("Putting jam on the toast");

        private static void ApplyButter(Toast toast) =>
            Console.WriteLine("Putting butter on the toast");

        private static Toast ToastBread(int slices)
        {
            for (int slice = 0; slice < slices; slice++)
            {
                Console.WriteLine("Putting a slice of bread in the toaster");
            }
            Console.WriteLine("Start toasting...");
            Task.Delay(3000).Wait();
            Console.WriteLine("Remove toast from toaster");

            return new Toast();
        }

        private static Bacon FryBacon(int slices)
        {
            Console.WriteLine($"putting {slices} slices of bacon in the pan");
            Console.WriteLine("cooking first side of bacon...");
            Task.Delay(3000).Wait();
            for (int slice = 0; slice < slices; slice++)
            {
                Console.WriteLine("flipping a slice of bacon");
            }
            Console.WriteLine("cooking the second side of bacon...");
            Task.Delay(3000).Wait();
            Console.WriteLine("Put bacon on plate");

            return new Bacon();
        }

        private static Egg FryEggs(int howMany)
        {
            Console.WriteLine("Warming the egg pan...");
            Task.Delay(3000).Wait();
            Console.WriteLine($"cracking {howMany} eggs");
            Console.WriteLine("cooking the eggs ...");
            Task.Delay(3000).Wait();
            Console.WriteLine("Put eggs on plate");

            return new Egg();
        }

        private static Coffee PourCoffee()
        {
            Console.WriteLine("Pouring coffee");
            return new Coffee();
        }
    }
}
```



## [Asynchronous programming scenarios](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/async-scenarios)





# C# concepts









# How-to C# articles











# Advanced topics



# The .NET Compiler Platform SDK (Roslyn APIs)



# C# programming guide



# Language reference



# Specifications