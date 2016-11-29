---
title: "显式接口实现（C# 编程指南） | Microsoft Docs"
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
  - "显式接口 [C#]"
  - "接口 [C#], 显式"
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 显式接口实现（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

如果[类](../../../csharp/language-reference/keywords/class.md)实现两个接口，并且这两个接口包含具有相同签名的成员，那么在类中实现该成员将导致两个接口都使用该成员作为它们的实现。  在下面的示例中，所有对 `Paint` 调用方法相同。  
  
 [!CODE [csProgGuideInheritance#39](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#39)]  
  
 然而，如果两个[接口](../../../csharp/language-reference/keywords/interface.md)成员执行不同的函数，那么这可能会导致其中一个接口的实现不正确或两个接口的实现都不正确。  可以显式地实现接口成员 \-\- 即创建一个仅通过该接口调用并且特定于该接口的类成员。  这是使用接口名称和一个句点命名该类成员来实现的。  例如：  
  
 [!CODE [csProgGuideInheritance#40](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#40)]  
  
 类成员 `IControl.Paint` 只能通过 `IControl` 接口使用，`ISurface.Paint` 只能通过 `ISurface` 使用。  两个方法实现都是分离的，都不可以直接在类中使用。  例如：  
  
 [!CODE [csProgGuideInheritance#41](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#41)]  
  
 显式实现还用于解决两个接口分别声明具有相同名称的不同成员（如属性和方法）的情况：  
  
 [!CODE [csProgGuideInheritance#42](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#42)]  
  
 为了同时实现两个接口，类必须对属性 P 和\/或方法 P 使用显式实现以避免编译器错误。  例如：  
  
 [!CODE [csProgGuideInheritance#43](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#43)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [类和结构](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [接口](../../../csharp/programming-guide/interfaces/index.md)   
 [继承](../../../csharp/programming-guide/classes-and-structs/inheritance.md)