---
title: "如何：使用运算符重载创建复数类（C# 编程指南） | Microsoft Docs"
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
  - "类 [C#], 运算符重载"
  - "复数 [C#]"
  - "运算符重载 [C#], 复数"
  - "运算符重载 [C#], 用于创建类"
  - "运算符 [C#], 重载以创建复数类"
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：使用运算符重载创建复数类（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

本示例展示如何使用运算符重载创建定义复数加法的复数类 `Complex`。  本程序使用 `ToString` 方法的重载显示数字的虚部和实部以及加法结果。  
  
## 示例  
 [!CODE [csProgGuideStatements#16](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#16)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [C\# 运算符](../../../csharp/language-reference/operators/index.md)   
 [运算符](../../../csharp/language-reference/keywords/operator.md)   
 [Why are overloaded operators always static in C\#?（在 C\# 中，为什么重载的运算符始终是静态的？）](http://go.microsoft.com/fwlink/?LinkId=112383)