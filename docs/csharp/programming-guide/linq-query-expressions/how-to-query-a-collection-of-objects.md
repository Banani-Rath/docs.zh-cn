---
title: "如何：查询对象集合（C# 编程指南） | Microsoft Docs"
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
  - "对象集合查询 [C#]"
  - "查询 [C# 中的 LINQ], 对象集合"
  - "查询表达式 [C# 中的 LINQ], 对象集合"
ms.assetid: 122d1e3b-1604-4add-b6b4-b84530a77b6b
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：查询对象集合（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

此示例演示如何对一个 `Student` 对象列表执行简单查询。  每个 `Student` 对象都包含一些有关该学生的基本信息，以及一个表示该学生的四次考试得分的列表。  
  
 此应用程序充当此部分中其他很多示例的框架，这些示例都使用相同的 `students` 数据源。  
  
## 示例  
 下面的查询返回那些在其第一次考试中得分为 90 分或更高的学生。  
  
 [!CODE [csProgGuideLINQ#15](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#15)]  
  
 我们特意将此查询编写得非常简单，以使您能够进行试验。  例如，您可以在 `where` 子句中尝试使用更多的谓词，也可以使用 `orderby` 子句对结果进行排序。  
  
## 编译代码  
  
-   创建面向 .NET Framework 3.5 版的 [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)] 项目。  默认情况下，该项目具有一个对 System.Core.dll 的引用以及一条针对 System.Linq 命名空间的 `using` 指令。  
  
-   将代码复制到项目中。  
  
-   按 F5 编译并运行程序。  
  
-   按任意键退出控制台窗口。  
  
## 请参阅  
 [LINQ 查询表达式](../../../csharp/programming-guide/linq-query-expressions/index.md)