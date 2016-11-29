---
title: "接口属性（C# 编程指南） | Microsoft Docs"
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
  - "接口 [C#], 属性"
  - "属性 [C#], 在接口上"
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 接口属性（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

可以在[interface](../../../csharp/language-reference/keywords/interface.md)上声明属性。  以下是接口索引器访问器的示例：  
  
 [!CODE [csProgGuideProperties#14](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideProperties#14)]  
  
 接口属性的访问器不具有体。  因此，访问器的用途是指示属性是否为读写、只读或只写。  
  
## 示例  
 在此例中，接口 `IEmployee` 具有读写属性 `Name` 和只读属性 `Counter`。  `Employee` 类实现 `IEmployee` 接口并使用这两种属性。  程序读取新雇员的姓名和雇员的当前编号，并显示雇员姓名和计算所得的雇员编号。  
  
 可以使用属性的完全限定名，它引用声明成员的接口。  例如：  
  
 [!CODE [csProgGuideProperties#16](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideProperties#16)]  
  
 这称为[显式接口实现](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)。  例如，如果 `Employee` 类实现两个接口 `ICitizen` 和 `IEmployee`，并且两个接口都具有 `Name` 属性，则需要显式接口成员实现。  即，如下属性声明：  
  
 [!CODE [csProgGuideProperties#16](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideProperties#16)]  
  
 在 `IEmployee` 接口上实现 `Name` 属性，而下面的声明：  
  
 [!CODE [csProgGuideProperties#17](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideProperties#17)]  
  
 在 `ICitizen` 接口上实现 `Name` 属性。  
  
 [!CODE [csProgGuideProperties#15](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideProperties#15)]  
  
  **`210 Hazem Abolrous`**    
## 示例输出  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [属性](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [使用属性](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [属性和索引器之间的比较](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)   
 [索引器](../../../csharp/programming-guide/indexers/index.md)   
 [接口](../../../csharp/programming-guide/interfaces/index.md)