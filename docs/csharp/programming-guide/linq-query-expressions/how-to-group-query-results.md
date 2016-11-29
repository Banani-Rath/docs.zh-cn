---
title: "如何：对查询结果进行分组（C# 编程指南） | Microsoft Docs"
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
  - "group 子句示例 [C# 中的 LINQ]"
  - "分组 [C# 中的 LINQ]"
  - "查询 [C# 中的 LINQ], 分组"
  - "查询表达式 [C# 中的 LINQ], 分组"
ms.assetid: ee981053-3392-4245-a8c2-b3730211da0d
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：对查询结果进行分组（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

分组是 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] 最强大的功能之一。  下面的示例演示如何以各种方式对数据进行分组：  
  
-   按照单个属性。  
  
-   按照字符串属性的首字母。  
  
-   按照计算出的数值范围。  
  
-   按照布尔谓词或其他表达式。  
  
-   按照复合键。  
  
 此外，最后两个查询将它们的结果投影到一个新的匿名类型中，该类型仅包含学生的名字和姓氏。  有关更多信息，请参见 [group 子句](../../../csharp/language-reference/keywords/group-clause.md)。  
  
## 示例  
 本主题中的所有示例都使用下列帮助器类和数据源。  
  
 [!CODE [csProgGuideLINQ#15](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#15)]  
  
## 示例  
 下面的示例演示如何通过使用元素的单个属性作为组键对源元素进行分组。  在这种情况下，键是 `string`，即学生的姓氏。  还可以使用子字符串作为键。  分组操作将对该类型使用默认的相等比较器。  
  
 将下面的方法粘贴到 `StudentClass` 类中。  将 `Main` 方法中的调用语句更改为 `sc.GroupBySingleProperty()`。  
  
 [!CODE [csProgGuideLINQ#17](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#17)]  
  
## 示例  
 下面的示例演示如何通过使用除对象属性以外的某个项作为组键对源元素进行分组。  在此示例中，键是学生姓氏的第一个字母。  
  
 将下面的方法粘贴到 `StudentClass` 类中。  将 `Main` 方法中的调用语句更改为 `sc.GroupBySubstring()`。  
  
 [!CODE [csProgGuideLINQ#18](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#18)]  
  
## 示例  
 下面的示例演示如何通过使用某个数值范围作为组键对源元素进行分组。  然后，查询将结果投影到一个匿名类型中，该类型仅包含学生的名字和姓氏以及该学生所属的百分点范围。  使用匿名类型的原因是没有必要使用完整的 `Student` 对象来显示结果。  `GetPercentile` 是一个 helper 函数，它根据学生的平均分数计算百分比。  该方法返回 0 到 10 之间的整数。  
  
 [!CODE [csProgGuideLINQ#50](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#50)]  
  
 将下面的方法粘贴到 `StudentClass` 类中。  将 `Main` 方法中的调用语句更改为 `sc.GroupByRange()`。  
  
 [!CODE [csProgGuideLINQ#19](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#19)]  
  
## 示例  
 下面的示例演示如何通过使用布尔比较表达式对源元素进行分组。  在此示例中，布尔表达式会测试学生的平均考试分数是否超过 75。  与上述示例一样，结果被投影到一个匿名类型中，因为不需要完整的源元素。  请注意，在执行查询时，该匿名类型中的属性将变成 `Key` 成员上的属性，并且可以通过名称进行访问。  
  
 将下面的方法粘贴到 `StudentClass` 类中。  将 `Main` 方法中的调用语句更改为 `sc.GroupByBoolean()`。  
  
 [!CODE [csProgGuideLINQ#20](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#20)]  
  
## 示例  
 下面的示例演示如何使用匿名类型来封装包含多个值的键。  在此示例中，第一个键值是学生姓氏的第一个字母。  第二个键值是一个布尔值，它指定该学生在第一次考试中的得分是否超过了 85。  可以按照该键中的任何属性对多组值进行排序。  
  
 将下面的方法粘贴到 `StudentClass` 类中。  将 `Main` 方法中的调用语句更改为 `sc.GroupByCompositeKey()`。  
  
 [!CODE [csProgGuideLINQ#21](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideLINQ#21)]  
  
## 编译代码  
 将您想要测试的每种方法都复制并粘贴到 `StudentClass` 类中。  将该方法的调用语句添加到 `Main` 方法中并按 F5。  
  
 在改写这些方法以适合您自己的应用程序时，请记住 LINQ 需要 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 3.5 或 4 版，并且项目必须包含一个对 System.Core.dll 的引用和一条针对 System.Linq 的 using 指令。  LINQ to SQL、LINQ to XML 和 LINQ to DataSet 类型需要其他 using 指令和引用。  有关更多信息，请参见 [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md)。  
  
## 请参阅  
 <xref:System.Linq.Enumerable.GroupBy%2A>   
 <xref:System.Linq.IGrouping%602>   
 [LINQ 查询表达式](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group 子句](../../../csharp/language-reference/keywords/group-clause.md)   
 [匿名类型](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [如何：对分组操作执行子查询](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)   
 [如何：创建嵌套组](../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)   
 [Grouping Data](../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)