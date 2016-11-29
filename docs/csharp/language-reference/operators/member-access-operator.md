---
title: ". 运算符（C# 参考） | Microsoft Docs"
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
  - "._CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ". 运算符 [C#]"
  - "点运算符 (.)[C#]"
  - "成员访问运算符 (.)[C#]"
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# . 运算符（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

点运算符 \(`.`\) 用于成员访问。  点运算符指定类型或命名空间的成员。  例如，点运算符用于访问 .NET Framework 类库中的特定方法：  
  
 [!CODE [csRefOperators#16](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#16)]  
  
 例如，请考虑以下类：  
  
 [!CODE [csRefOperators#17](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#17)]  
  
 [!CODE [csRefOperators#18](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#18)]  
  
 变量 `s` 有两个成员 `a` 和 `b`；若要访问这两个成员，请使用点运算符：  
  
 [!CODE [csRefOperators#19](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#19)]  
  
 点还用于构造限定名，即指定其所属的命名空间或接口的名称。  
  
 [!CODE [csRefOperators#20](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#20)]  
  
 using 指令使某些名称限定可选：  
  
 [!CODE [csRefOperators#21](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#21)]  
  
 但是当某一标识符不确定时，必须限定它：  
  
 [!CODE [csRefOperators#22](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#22)]  
  
## C\# 语言规范  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [C\# 运算符](../../../csharp/language-reference/operators/index.md)