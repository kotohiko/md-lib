https://learn.microsoft.com/en-us/dotnet/csharp/





# [Get started](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/)



## [Introduction - A tour of the C# language](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/)

文档里竟然提到 C# 是 ***component-oriented*** 的，我暂译「面向组件」的，又是一个全新的概念。根据文档中的解释大概是说 C# 可以通过各种组件来迅速完成项目的交付。

接下来讲的就是 C# 拥有的一些特性，差不多也都是 OOP 编程语言（或者说是 Java）固有的一些特性，如[**垃圾回收（*Garbage collection*）**](https://learn.microsoft.com/en-us/dotnet/standard/garbage-collection/)、**[空类型（*Nullable types*）](https://learn.microsoft.com/en-us/dotnet/csharp/nullable-references)**、[**异常处理（*Exception handling*）**](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/exceptions/)、[**lambda 表达式（*Lambda expressions*）**](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/lambda-expressions)等。*[**LINQ（Language Integrated Query）**](https://learn.microsoft.com/en-us/dotnet/csharp/linq/)*倒是一个没听说过的概念，大概是与数据源打交道的一种语法。C# 中对[**异步操作（*asynchronous operations*）**](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/)提供的支持可以有效地构建分布式系统。C# 有一个[**统一类型系统**](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/types/)（暂译，英文为：*[**unified type system**](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/types/)*）。在 C# 中，所有的类型，如 `int`、`double` 都继承自一个根类型 `object`（又是个似曾相识的东西），这印证了 C# 对数据类型的设计思路上似乎与 Java 有着些许不同。所有类型共用一组通用运算。然后介绍用户自定义[引用类型（*reference types*）](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/reference-types)/[值类型（*value types*）](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/value-types)、泛型方法、迭代器等。其中「值类型」又是一个有点陌生的概念呢。

C# 强调**版控（*versioning*）**——好神奇，这如何强调Σ(⊙▽⊙"a）？随即引出了两个修饰符：`virtual` 与 `override`。只看概念很难理解，交给后续实战开发了再理解也不迟。

### [.NET architecture](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/#net-architecture)

C# 程序运行在 .NET 上，

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



### [Types and variables](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/#types-and-variables)



### [Program structure](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/#program-structure)





## [Types - C# types and members](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/types)



## [Program building blocks - C# program building blocks](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/program-building-blocks)



## [Major language areas - C# major language areas](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/features)



## [C# language strategy - Annotated C# strategy](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/strategy)



## Tutorials



# [Fundamentals](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/program-structure/)



## [Program structure - General Structure of a C# Program](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/program-structure/)



### [Overview - General Structure of a C# Program](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/program-structure/)



### [Main method - `Main()` and command-line arguments](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/program-structure/main-command-line)



### [Top-level statements - programs without `Main` methods](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/program-structure/top-level-statements)



# [What's new in C#](https://learn.microsoft.com/en-us/dotnet/csharp/whats-new/)



## [What's new in C# 12](https://learn.microsoft.com/en-us/dotnet/csharp/whats-new/csharp-12)









# [Tutorials](https://learn.microsoft.com/en-us/dotnet/csharp/tutorials/)



# [Language Integrated Query (LINQ)](https://learn.microsoft.com/en-us/dotnet/csharp/linq/)



## [Overview of LINQ](https://learn.microsoft.com/en-us/dotnet/csharp/linq/)



### [Query expression overview](https://learn.microsoft.com/en-us/dotnet/csharp/linq/#how-to-enable-linq-querying-of-your-data-source)





### [How to enable LINQ querying of your data source](https://learn.microsoft.com/en-us/dotnet/csharp/linq/#how-to-enable-linq-querying-of-your-data-source)



### [`IQueryable` LINQ providers](https://learn.microsoft.com/en-us/dotnet/csharp/linq/#iqueryable-linq-providers)



## [Getting Started with LINQ in C#](https://learn.microsoft.com/en-us/dotnet/csharp/linq/get-started/introduction-to-linq-queries)







### [Introduction to LINQ Queries (C#)](https://learn.microsoft.com/en-us/dotnet/csharp/linq/get-started/introduction-to-linq-queries)

*query* 是一种从数据源中检索数据的表达式。不同的数据源有不同的本地查询语言，例如关系型数据库是 SQL 而 XML 是 XQuery。这也就意味着，开发人员需要为每一种类型的数据源或数据格式去学习新的查询语言。LINQ 通过提供了一种跨越多种数据源或格式，也能始终一致的 C# 语言模型，化解了这一难题。通过使用 LINQ，你可以只与 C# 对象打交道。你可以使用基本的编码方式来查询、转换 XML 文档、SQL 数据库、.NET 集合中的数据以及任何其他格式的数据。



#### Three Parts of a Query Operation



#### The Data Source



#### The Query



#### Query Execution

##### Deferred Execution



# [Asynchronous programming](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/)











# C# concepts









# [How-to C# articles](https://learn.microsoft.com/en-us/dotnet/csharp/how-to/)











# Advanced topics



# [The .NET Compiler Platform SDK (Roslyn APIs)](https://learn.microsoft.com/en-us/dotnet/csharp/roslyn-sdk/)



# [C# programming guide](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/)



# [Language reference](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/)



# [Specifications](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/specifications)