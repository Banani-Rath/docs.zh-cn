---
title: "对象和集合初始值设定项（C# 编程指南） | Microsoft Docs"
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
  - "集合初始值设定项 [C#]"
  - "对象初始值设定项 [C#]"
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 对象和集合初始值设定项（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

使用对象初始值设定项，你可以在创建对象时向对象的任何可访问字段或属性分配值，而无需调用后跟赋值语句行的构造函数。  利用对象初始值设定项语法，你可为构造函数指定参数或忽略参数（以及括号语法）。  以下示例演示如何使用具有命名类型 `Cat` 的对象初始值设定项以及如何调用默认构造函数。  请注意，自动实现的属性在 `Cat` 类中的用法。  有关详细信息，请参阅[自动实现的属性](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)。  
  
 [!CODE [csProgGuideLINQ#39](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#39)]  
  
 [!CODE [csProgGuideLINQ#45](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#45)]  
  
## 具有匿名类型的对象初始值设定项  
 尽管对象初始值设定项可用于任何上下文中，但它们在 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] 查询表达式中特别有用。  查询表达式常使用只能通过使用对象初始值设定项进行初始化的[匿名类型](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)，如下面的声明所示。  
  
```  
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 利用匿名类型，`select` 查询表达式中的 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] 子句可以将原始序列的对象转换为其值和形状可能不同于原始序列的对象。  如果你只想存储某个序列中每个对象的部分信息，则这很有用。  在下面的示例中，假定产品对象 \(`p`\) 包含很多字段和方法，而你只想创建包含产品名和单价的对象序列。  
  
 [!CODE [csProgGuideLINQ#40](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#40)]  
  
 执行此查询时，`productInfos` 变量将包含一系列对象，这些对象可以在 `foreach` 语句中进行访问，如下面的示例所示：  
  
```  
foreach(var p in productInfos){...}  
```  
  
 新的匿名类型中的每个对象都具有两个公共属性，这两个属性接收与原始对象中的属性或字段相同的名称。  你还可在创建匿名类型时重命名字段；下面的示例将 `UnitPrice` 字段重命名为 `Price`。  
  
```  
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## 具有可以为 null 的类型的对象初始值设定项  
 使用具有可以为 null 的结构的对象初始值设定项会导致编译时错误。  
  
## 集合初始值设定项  
 集合初始值设定项允许在初始化实现 <xref:System.Collections.IEnumerable> 的集合类或初始化具有 `Add` 扩展方法的类时，指定一个或多个元素初始值设定项。  元素初始值设定项可以是简单的值、表达式或对象初始值设定项。  通过使用集合初始值设定项，你将无需在源代码中指定对该类的 `Add` 方法的多个调用；编译器将添加这些调用。  
  
 下面的示例演示了两个简单的集合初始值设定项：  
  
```  
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 下面的集合初始值设定项使用对象初始值设定项来初始化上一个示例中定义的 `Cat` 类的对象。  请注意，各个对象初始值设定项分别括在大括号中且用逗号隔开。  
  
 [!CODE [csProgGuideLINQ#41](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#41)]  
  
 如果集合的 [null](../../../csharp/language-reference/keywords/null.md) 方法允许，则可以将 `Add` 指定为集合初始值设定项中的一个元素。  
  
 [!CODE [csProgGuideLINQ#42](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#42)]  
  
 如果集合支持索引，可以指定索引元素。  
  
```  
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
  
```  
  
## 示例  
 [!CODE [csProgGuideLINQ#46](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#46)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [LINQ 查询表达式](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [匿名类型](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)