---
title: "continue（C# 参考） | Microsoft Docs"
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
  - "continue_CSharpKeyword"
  - "continue"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "continue 关键字 [C#]"
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# continue（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`continue` 语句将控制传递到封闭 [while](../../../csharp/language-reference/keywords/while.md)、[](../../../csharp/language-reference/keywords/do.md "do (C# Reference)")、[为](../../../csharp/language-reference/keywords/for.md)或显示的 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 语句下一次迭代。  
  
## 示例  
 在本示例中，计数器最初是从 1 到 10 进行计数。  通过使用该表达式 `(i < 9)`一起的 `continue` 语句，在 `continue` 和 `for` 主体结束的语句跳过。  
  
 [!CODE [csrefKeywordsJump#3](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsJump#3)]  
  
## C\# 语言规范  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [C\# 关键字](../../../csharp/language-reference/keywords/index.md)   
 [break 语句](/visual-cpp/cpp/break-statement-cpp)   
 [跳转语句](../../../csharp/language-reference/keywords/jump-statements.md)