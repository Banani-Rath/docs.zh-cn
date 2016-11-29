---
title: "goto（C# 参考） | Microsoft Docs"
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
  - "goto_CSharpKeyword"
  - "goto"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "goto 关键字 [C#]"
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# goto（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`goto` 语句将程序控制直接传递给标记语句。  
  
 `goto` 的一个通常用法是将控制传递给特定的 switch\-case 标签或 `switch` 语句中的默认标签。  
  
 `goto` 语句还用于跳出深嵌套循环。  
  
## 示例  
 下面的示例演示了 `goto` 在 [switch](../../../csharp/language-reference/keywords/switch.md) 语句中的使用。  
  
 [!CODE [csrefKeywordsJump#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsJump#4)]  
  
## 示例  
 下面的示例演示了使用 `goto` 跳出嵌套循环。  
  
 [!CODE [csrefKeywordsJump#5](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsJump#5)]  
  
## C\# 语言规范  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [C\# 关键字](../../../csharp/language-reference/keywords/index.md)   
 [goto 语句](/visual-cpp/cpp/goto-statement-cpp)   
 [跳转语句](../../../csharp/language-reference/keywords/jump-statements.md)