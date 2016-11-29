---
title: "&gt;&gt;= 运算符（C# 参考） | Microsoft Docs"
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
  - ">>=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">>= 运算符（右移赋值）[C#]"
  - "右移赋值运算符 (>>=) [C#]"
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# &gt;&gt;= 运算符（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

右移赋值运算符。  
  
## 备注  
 下列形式的表达式  
  
```  
x >>= y  
```  
  
 按如下规则计算：  
  
```  
x = x >> y  
```  
  
 不同的是 `x` 只计算一次。  [\>\> 运算符](../../../csharp/language-reference/operators/right-shift-operator.md)根据 `y` 指定的量对 `x` 进行右移位。  
  
 不能直接重载 \>\>\= 运算符，但用户定义的类型可重载 [\>\> 运算符](../../../csharp/language-reference/operators/right-shift-operator.md)（请参见 [operator](../../../csharp/language-reference/keywords/operator.md)）。  
  
## 示例  
 [!CODE [csRefOperators#11](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#11)]  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [C\# 运算符](../../../csharp/language-reference/operators/index.md)