---
title: "分部（类型）（C# 参考） | Microsoft Docs"
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
  - "partialtype"
  - "partialtype_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "分部类型 [C#]"
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 分部（类型）（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

分部类型定义允许将类、结构或接口的定义拆分到多个文件中。  
  
 在 File1.cs 中：  
  
 [!CODE [csrefKeywordsContextual#3](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsContextual#3)]  
  
 在 File2.cs 中，声明：  
  
 [!CODE [csrefKeywordsContextual#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsContextual#4)]  
  
## 备注  
 当使用大项目或自动生成的代码（如由 [Windows Forms Designer](http://msdn.microsoft.com/zh-cn/3c3d61f8-f36c-4d41-b9c3-398376fabb15)提供的代码）时，将一个类、结构或接口类型拆分到多个文件中的做法就很有用。  分部类型可能包含[分部方法](../../../csharp/language-reference/keywords/partial-method.md)。  有关更多信息，请参见 [分部类和方法](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)。  
  
## C\# 语言规范  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [修饰符](../../../csharp/language-reference/keywords/modifiers.md)   
 [泛型介绍](../../../csharp/programming-guide/generics/introduction-to-generics.md)