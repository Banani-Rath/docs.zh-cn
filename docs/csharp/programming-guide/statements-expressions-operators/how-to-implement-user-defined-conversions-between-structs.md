---
title: "如何：在结构间实现用户定义的转换（C# 编程指南） | Microsoft Docs"
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
  - "用户定义的转换 [C#]"
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：在结构间实现用户定义的转换（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

本示例定义 `RomanNumeral` 和 `BinaryNumeral` 两个结构，并演示二者之间的转换。  
  
## 示例  
 [!CODE [csProgGuideStatements#13](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#13)]  
  
## 可靠编程  
  
-   在上面的示例中，语句：  
  
     [!CODE [csProgGuideStatements#14](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#14)]  
  
     执行从 `RomanNumeral` 到 `BinaryNumeral` 的转换。  由于没有从 `RomanNumeral` 到 `BinaryNumeral` 的直接转换，所以使用一个转换将 `RomanNumeral` 转换为 `int`，并使用另一个转换将 `int` 转换为 `BinaryNumeral`。  
  
-   另外，语句  
  
     [!CODE [csProgGuideStatements#15](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#15)]  
  
     执行从 `BinaryNumeral` 到 `RomanNumeral` 的转换。  由于 `RomanNumeral` 定义了从 `BinaryNumeral` 的隐式转换，所以不需要转换。  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [转换运算符](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)