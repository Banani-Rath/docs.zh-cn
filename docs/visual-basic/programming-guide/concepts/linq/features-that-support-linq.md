---
title: "Visual Basic Features That Support LINQ | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic, LINQ features"
  - "LINQ [Visual Basic], features supporting LINQ"
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
caps.latest.revision: 51
caps.handback.revision: 49
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Visual Basic Features That Support LINQ
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

名称[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] 是指 Visual Basic 中的技术，该技术直接在语言中支持查询语法和其他语言结构。  利用 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]，您不必学习新语言即可针对外部数据源进行查询。  您可以使用 Visual Basic 对关系数据库、XML 存储区或对象中的数据进行查询。  由于将查询功能集成到了语言中，因此能够在编译时检查语法错误和类型安全。  同时，这种集成还确保您已经了解在 Visual Basic 中编写各种各样丰富的查询所必须了解的知识。  
  
 以下各节详细描述了支持 LINQ 的语言结构，以使您能够开始阅读介绍性文档、代码示例和示例应用程序。  您还可以单击链接，以了解有关语言功能如何整合在一起从而实现语言集成查询的更详细说明。  [演练：用 Visual Basic 编写查询](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)是一个好的起点。  
  
## 查询表达式  
 Visual Basic 中的查询表达式可以采用类似于 SQL 或 XQuery 的声明性语法来表示。  在编译时，查询语法转换为对 LINQ 提供程序的标准查询运算符扩展方法实现的方法调用。  应用程序通过使用 `Imports` 语句指定适当的命名空间来控制哪些标准查询运算符位于范围内。  Visual Basic 查询表达式的语法如下所示：  
  
 [!CODE [VbLINQVbFeatures#1](../CodeSnippet/VS_Snippets_VBCSharp/VbLINQVbFeatures#1)]  
  
 有关更多信息，请参见 [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)。  
  
## 隐式类型化变量  
 不必在声明并初始化变量时显式指定类型，即可使编译器推断并分配类型。  这称为“局部类型推理”。  
  
 推断其类型的变量是强类型变量，就像您显式指定其类型的变量一样。  只有当您在方法体内定义局部变量时，局部类型推断才起作用。  有关更多信息，请参见[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)和[局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。  
  
 下面的示例阐释了局部类型推断。  要使用此示例，必须将 `Option Infer` 设置为 `On`。  
  
 [!CODE [VbLINQVbFeatures#2](../CodeSnippet/VS_Snippets_VBCSharp/VbLINQVbFeatures#2)]  
  
 局部类型推理还可以创建匿名类型，本节后面将介绍这些类型是 LINQ 查询所必需的。  
  
 在下面的 LINQ 示例中，如果 `Option Infer` 为 `On` 或 `Off`，则会进行类型推断。  如果 `Option Infer` 为 `Off`，并且 `Option Strict` 为 `On`，将产生编译时错误。  
  
 [!CODE [VbLINQVbFeatures#3](../CodeSnippet/VS_Snippets_VBCSharp/VbLINQVbFeatures#3)]  
  
## 对象初始值设定项  
 当您必须创建匿名类型来容纳查询的结果时，将在查询表达式中使用对象初始值设定项。  它们还可以用于在查询外部初始化命名类型的对象。  使用对象初始值设定项，可以在单独一行中初始化对象，而无需显式调用构造函数。  假定有一个名为 `Customer` 的类，该类具有公共 `Name` 和 `Phone` 属性以及其他属性，则可以采用此方式使用对象初始值设定项：  
  
 [!CODE [VbLINQVbFeatures#4](../CodeSnippet/VS_Snippets_VBCSharp/VbLINQVbFeatures#4)]  
  
 有关更多信息，请参见[对象初始值设定项：命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)。  
  
## 匿名类型  
 利用匿名类型，可以方便地将一组属性临时分组为想要包括在查询结果中的元素。  这样，您将能够在查询中按任何顺序选择可用字段的任意组合，而无需为元素定义命名数据类型。  
  
 “匿名类型”由编译器动态构建。  类型的名称由编译器分配，并且可能随着每次新编译发生更改。  因此，不能直接使用该名称。  匿名类型采用以下方式初始化：  
  
 [!CODE [VbLINQVbFeatures#5](../CodeSnippet/VS_Snippets_VBCSharp/VbLINQVbFeatures#5)]  
  
 有关更多信息，请参见[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。  
  
## 扩展方法  
 使用扩展方法，可以从定义外部向数据类型或接口中添加方法。  实际上，此功能使您能够将新方法添加到现有类型，而不会实际修改该类型。  标准查询运算符本身是一组扩展方法，它们为实现 <xref:System.Collections.Generic.IEnumerable%601> 的任何类型提供 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 查询功能。其他 <xref:System.Collections.Generic.IEnumerable%601> 扩展包括 <xref:System.Linq.Enumerable.Count%2A>、<xref:System.Linq.Enumerable.Union%2A> 和 <xref:System.Linq.Enumerable.Intersect%2A>。  
  
 以下扩展方法将一个 print 方法添加到 <xref:System.String> 类。  
  
 [!CODE [VbLINQVbFeatures#6](../CodeSnippet/VS_Snippets_VBCSharp/VbLINQVbFeatures#6)]  
  
 调用该方法就像调用 <xref:System.String> 的普通实例方法一样。  
  
 [!CODE [VbLINQVbFeatures#7](../CodeSnippet/VS_Snippets_VBCSharp/VbLINQVbFeatures#7)]  
  
 有关更多信息，请参见[扩展方法](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)。  
  
## Lambda 表达式  
 Lambda 表达式是一种无名函数，用于计算并返回单个值。  与命名函数不同，Lambda 表达式可以在同时定义和执行。  下面的示例显示 4。  
  
 [!CODE [VbLINQVbFeatures#8](../CodeSnippet/VS_Snippets_VBCSharp/VbLINQVbFeatures#8)]  
  
 可以将 Lambda 表达式定义赋给变量名称，然后使用该名称来调用函数。  下面的示例也显示 4。  
  
 [!CODE [VbLINQVbFeatures#12](../CodeSnippet/VS_Snippets_VBCSharp/VbLINQVbFeatures#12)]  
  
 在 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 中，Lambda 表达式成为许多标准查询运算符的基础。  编译器创建 Lambda 表达式以捕获在基础查询方法（比如 `Where`、`Select`、`Order By`、`Take While` 以及其他方法）中定义的计算。  
  
 例如，下面的代码定义一个从学员列表中返回所有高级学员的查询。  
  
 [!CODE [VbLINQVbFeatures#9](../CodeSnippet/VS_Snippets_VBCSharp/VbLINQVbFeatures#9)]  
  
 查询定义将编译为与下面的示例类似的代码，该示例使用两个 Lambda 表达式为 `Where` 和 `Select` 指定参数。  
  
 [!CODE [VbLINQVbFeatures#10](../CodeSnippet/VS_Snippets_VBCSharp/VbLINQVbFeatures#10)]  
  
 可以使用 `For Each` 循环运行任一版本：  
  
 [!CODE [VbLINQVbFeatures#11](../CodeSnippet/VS_Snippets_VBCSharp/VbLINQVbFeatures#11)]  
  
 有关更多信息，请参见 [lambda 表达式](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。  
  
## 请参阅  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ 和字符串](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [C\# Features That Support LINQ](../../../../csharp/programming-guide/concepts/linq/features-that-support-linq.md)   
 [Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)