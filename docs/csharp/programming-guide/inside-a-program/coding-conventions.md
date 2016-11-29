---
title: "C# 编码约定（C# 编程指南） | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 语言, 编码约定"
  - "编码约定, C#"
  - "Visual C#, 编码约定"
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 32
caps.handback.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# C# 编码约定（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[C\# 语言规范](http://go.microsoft.com/fwlink/?LinkId=199552) 未定义编码标准。  但是，Microsoft 根据本主题中的准则来开发样本和文档。  
  
 编码约定可实现以下目的：  
  
-   它们为代码创建一致的外观，以确保读取器专注于内容而非布局。  
  
-   它们使得读取器可以通过基于之前的经验进行的假设更快地理解代码。  
  
-   它们便于复制、更改和维护代码。  
  
-   它们展示 C\# 最佳做法。  
  
## 命名约定  
  
-   在不包括 [using 指令](../../../csharp/language-reference/keywords/using-directive.md)的短示例中，使用命名空间限定。  如果你知道命名空间默认导入项目中，则不必完全限定来自该命名空间的名称。  如果对于单行来说过长，则可以在点 \(.\) 后中断限定名称，如下面的示例所示。  
  
     [!CODE [csProgGuideCodingConventions#1](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#1)]  
  
-   你不必更改通过使用 Visual Studio 设计器工具创建的对象的名称以使它们适合其他准则。  
  
## 布局约定  
 好的布局利用格式设置来强调代码的结构并使代码更便于阅读。  Microsoft 示例和样本符合以下约定：  
  
-   使用默认的代码编辑器设置（智能缩进、4 字符缩进、制表符保存为空格）。  有关详细信息，请参阅[选项、文本编辑器、C\#、格式设置](/visual-studio/ide/reference/options-text-editor-csharp-formatting)。  
  
-   每行只写一条语句。  
  
-   每行只写一个声明。  
  
-   如果连续行未自动缩进，请将它们缩进一个制表符位（四个空格）。  
  
-   在方法定义与属性定义之间添加至少一个空白行。  
  
-   使用括号突出表达式中的子句，如下面的代码所示。  
  
     [!CODE [csProgGuideCodingConventions#2](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#2)]  
  
## 注释约定  
  
-   将注释放在单独的行上，而非代码行的末尾。  
  
-   以大写字母开始注释文本。  
  
-   以句点结束注释文本。  
  
-   在注释分隔符 \(\/\/\) 与注释文本之间插入一个空格，如下面的示例所示。  
  
     [!CODE [csProgGuideCodingConventions#3](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#3)]  
  
-   不要在注释周围创建格式化的星号块。  
  
## 语言准则  
 以下各节介绍 C\# 遵循以准备代码示例和样本的做法。  
  
### String 数据类型  
  
-   使用 `+` 运算符来连接短字符串，如下面的代码所示。  
  
     [!CODE [csProgGuideCodingConventions#6](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#6)]  
  
-   若要在循环中追加字符串，尤其是在使用大量文本时，请使用 <xref:System.Text.StringBuilder> 对象。  
  
     [!CODE [csProgGuideCodingConventions#7](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#7)]  
  
### 隐式类型的局部变量  
  
-   当变量类型明显来自赋值的右侧时，或者当精度类型不重要时，请对本地变量进行[隐式类型化](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)。  
  
     [!CODE [csProgGuideCodingConventions#8](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#8)]  
  
-   当类型并非明显来自赋值的右侧时，请勿使用 [var](../../../csharp/language-reference/keywords/var.md)。  
  
     [!CODE [csProgGuideCodingConventions#9](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#9)]  
  
-   请勿依靠变量名称来指定变量的类型。  它可能不正确。  
  
     [!CODE [csProgGuideCodingConventions#10](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#10)]  
  
-   避免使用 `var` 来代替 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)。  
  
-   使用隐式类型化来确定 [for](../../../csharp/language-reference/keywords/for.md) 和 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 循环中循环变量的类型。  
  
     下面的示例在 `for` 语句中使用隐式类型化。  
  
     [!CODE [csProgGuideCodingConventions#11](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#11)]  
  
     下面的示例在 `foreach` 语句中使用隐式类型化。  
  
     [!CODE [csProgGuideCodingConventions#12](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#12)]  
  
### 无符号数据类型  
  
-   通常，使用 `int` 而非无符号类型。  `int` 的使用在整个 C\# 中都很常见，并且当你使用 `int` 时，更易于与其他库交互。  
  
### 数组  
  
-   当在声明行上初始化数组时，请使用简洁的语法。  
  
     [!CODE [csProgGuideCodingConventions#13](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#13)]  
  
### 委托  
  
-   使用简洁的语法来创建委托类型的实例。  
  
     [!CODE [csProgGuideCodingConventions#14](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#14)]  
  
     [!CODE [csProgGuideCodingConventions#15](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#15)]  
  
### 异常处理中的 try\-catch 和 using 语句  
  
-   对大多数异常处理使用 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) 语句。  
  
     [!CODE [csProgGuideCodingConventions#16](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#16)]  
  
-   通过使用 C\# [using 语句](../../../csharp/language-reference/keywords/using-statement.md)简化你的代码。  如果你具有 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md) 语句（该语句中 `finally` 块的唯一代码是对 <xref:System.IDisposable.Dispose%2A> 方法的调用），请使用 `using` 语句代替。  
  
     [!CODE [csProgGuideCodingConventions#17](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#17)]  
  
### && 和 &#124;&#124; 运算符  
  
-   若要通过跳过必要的比较来避免异常和提高性能，请在执行比较时使用 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) 来代替 [&](../../../csharp/language-reference/operators/and-operator.md)，使用 [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) 来代替                                        [&#124;](../../../csharp/language-reference/operators/or-operator.md) ，如下面的示例所示。  
  
     [!CODE [csProgGuideCodingConventions#18](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#18)]  
  
### New 运算符  
  
-   隐式类型化时，请使用对象实例化的简洁形式，如下面的声明所示。  
  
     [!CODE [csProgGuideCodingConventions#19](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#19)]  
  
     上一行等同于下面的声明。  
  
     [!CODE [csProgGuideCodingConventions#20](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#20)]  
  
-   使用对象初始值设定项来简化对象创建。  
  
     [!CODE [csProgGuideCodingConventions#21](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#21)]  
  
### 事件处理  
  
-   如果你正定义一个稍后不需要删除的事件处理程序，请使用 lambda 表达式。  
  
     [!CODE [csProgGuideCodingConventions#22](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#22)]  
  
     [!CODE [csProgGuideCodingConventions#23](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#23)]  
  
### 静态成员  
  
-   通过使用类名称调用[静态](../../../csharp/language-reference/keywords/static.md)成员：*ClassName.StaticMember*。  这种做法通过明确静态访问使代码更易于阅读。  请勿使用派生类的名称限定基类中定义的静态成员。  编译该代码时，代码可读性具有误导性，如果向派生类添加具有相同名称的静态成员，代码可能会被破坏。  
  
### LINQ 查询  
  
-   对查询变量使用有意义的名称。  下面的示例为位于西雅图的客户使用 `seattleCustomers`。  
  
     [!CODE [csProgGuideCodingConventions#25](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#25)]  
  
-   使用别名确保匿名类型的属性名称都使用 Pascal 大小写格式正确大写。  
  
     [!CODE [csProgGuideCodingConventions#26](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#26)]  
  
-   如果结果中的属性名称模棱两可，请对属性重命名。  例如，如果你的查询返回客户名称和分销商 ID，而不是在结果中将它们保留为 `Name` 和 `ID`，请对它们进行重命名以明确 `Name` 是客户的名称，`ID` 是分销商的 ID。  
  
     [!CODE [csProgGuideCodingConventions#27](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#27)]  
  
-   在查询变量和范围变量的声明中使用隐式类型化。  
  
     [!CODE [csProgGuideCodingConventions#25](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#25)]  
  
-   对齐 [from](../../../csharp/language-reference/keywords/from-clause.md) 子句下的查询子句，如上面的示例所示。  
  
-   在其他查询子句之前使用 [where](../../../csharp/language-reference/keywords/where-clause.md) 子句，以确保后面的查询子句作用于经过减少和筛选的数据集。  
  
     [!CODE [csProgGuideCodingConventions#29](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#29)]  
  
-   使用多行 `from` 子句代替 [join](../../../csharp/language-reference/keywords/join-clause.md) 子句以访问内部集合。  例如，`Student` 对象的集合可能包含测验分数的集合。  当执行以下查询时，它返回高于 90 的分数，并返回得到该分数的学生的姓氏。  
  
     [!CODE [csProgGuideCodingConventions#30](../CodeSnippet/VS_Snippets_VBCSharp/csprogguidecodingconventions#30)]  
  
## 安全性  
 请遵循[代码安全维护指南](../Topic/Secure%20Coding%20Guidelines.md)中的准则。  
  
## 请参阅  
 [Visual Basic 编码约定](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)   
 [代码安全维护指南](../Topic/Secure%20Coding%20Guidelines.md)