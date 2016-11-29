---
title: "|= 运算符（C# 参考） | Microsoft Docs"
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
  - "|=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "|= 运算符（OR 赋值）[C#]"
  - "OR 赋值运算符 (|=) [C#]"
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# |= 运算符（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

“或”赋值运算符。  
  
## 备注  
 使用 `|=` 赋值运算符的表达式，例如  
  
```  
x |= y  
```  
  
 等效于  
  
```  
x = x | y  
```  
  
 不同的是 `x` 只计算一次。  [&#124; 运算符](../../../csharp/language-reference/operators/or-operator.md)对整型操作数执行按位逻辑“或”运算，对布尔操作数执行逻辑“或”运算。  
  
 不能直接重载 `|=` 运算符，但用户定义的类型可以重载 [&#124; 运算符](../../../csharp/language-reference/operators/or-operator.md)（请参见 [operator](../../../csharp/language-reference/keywords/operator.md)）。  
  
## 示例  
 [!CODE [csRefOperators#10](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#10)]  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [C\# 运算符](../../../csharp/language-reference/operators/index.md)