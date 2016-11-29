---
title: "where 子句（C# 参考） | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "whereclause_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "where 子句 [C#]"
  - "where 关键字 [C#]"
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# where 子句（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`where` 子句用在查询表达式中，用于指定将在查询表达式中返回数据源中的哪些元素。  它将一个布尔条件（“谓词”）应用于每个源元素（由范围变量引用），并返回满足指定条件的元素。  一个查询表达式可以包含多个 `where` 子句，一个子句可以包含多个谓词子表达式。  
  
## 示例  
 在下面的示例中，`where` 子句筛选出除小于五的数字外的所有数字。  如果移除 `where` 子句，则会返回数据源中的所有数字。  表达式 `num < 5` 是应用于每个元素的谓词。  
  
 [!CODE [cscsrefQueryKeywords#5](../CodeSnippet/VS_Snippets_VBCSharp/CsCsrefQueryKeywords#5)]  
  
## 示例  
 在单一 `where` 子句内，可以使用 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) 和 [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) 运算符根据需要指定任意多个谓词。  在下面的示例中，查询将指定两个谓词，以便只选择小于五的偶数。  
  
 [!CODE [cscsrefQueryKeywords#6](../CodeSnippet/VS_Snippets_VBCSharp/CsCsrefQueryKeywords#6)]  
  
## 示例  
 `where` 子句可以包含一个或多个返回布尔值的方法。  在下面的示例中，`where` 子句使用一个方法来确定范围变量的当前值是偶数还是奇数。  
  
 [!CODE [cscsrefQueryKeywords#7](../CodeSnippet/VS_Snippets_VBCSharp/CsCsrefQueryKeywords#7)]  
  
## 备注  
 `where` 子句是一种筛选机制。  除了不能是第一个或最后一个子句外，它几乎可以放在查询表达式中的任何位置。  `where` 子句可以出现在 [group](../../../csharp/language-reference/keywords/group-clause.md) 子句的前面或后面，具体情况取决于是必须在对源元素进行分组之前还是之后来筛选源元素。  
  
 如果指定的谓词对于数据源中的元素无效，则会发生编译时错误。  这是 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] 提供的强类型检查的一个优点。  
  
 编译时，`where` 关键字会被转换为对 <xref:System.Linq.Enumerable.Where%2A> 标准查询运算符方法的调用。  
  
## 请参阅  
 [查询关键字 \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [from 子句](../../../csharp/language-reference/keywords/from-clause.md)   
 [select 子句](../../../csharp/language-reference/keywords/select-clause.md)   
 [Filtering Data](../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)   
 [LINQ 查询表达式](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)