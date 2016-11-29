---
title: "泛型和特性（C# 编程指南） | Microsoft Docs"
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
  - "特性 [C#], 具有泛型"
  - "泛型 [C#], 特性"
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 泛型和特性（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

特性可以应用于泛型类型中，方式与应用于非泛型类型相同。  有关应用特性的更多信息，请参见 [特性](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)。  
  
 自定义特性只允许引用开放泛型类型（未提供类型参数的泛型类型）和封闭构造泛型类型（为所有类型参数提供参数）。  
  
 下面的示例使用此自定义特性：  
  
 [!CODE [csProgGuideGenerics#48](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#48)]  
  
 特性可以引用开放式泛型类型：  
  
 [!CODE [csProgGuideGenerics#49](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#49)]  
  
 使用数目适当的若干个逗号指定多个类型参数。  在此示例中，`GenericClass2` 有两个类型参数：  
  
 [!CODE [csProgGuideGenerics#50](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#50)]  
  
 特性可以引用封闭式构造泛型类型：  
  
 [!CODE [csProgGuideGenerics#51](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#51)]  
  
 引用泛型类型参数的特性将导致编译时错误：  
  
 [!CODE [csProgGuideGenerics#52](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#52)]  
  
 不能从 <xref:System.Attribute> 继承泛型类型：  
  
 [!CODE [csProgGuideGenerics#53](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideGenerics#53)]  
  
 若要在运行时获得有关泛型类型或类型参数的信息，可以使用 <xref:System.Reflection> 的方法。  有关更多信息，请参见[泛型和反射](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [泛型](../../../csharp/programming-guide/generics/index.md)   
 [特性](../Topic/Extending%20Metadata%20Using%20Attributes.md)