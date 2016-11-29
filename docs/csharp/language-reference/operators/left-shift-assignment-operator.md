---
title: "&lt;&lt;= 运算符（C# 参考） | Microsoft Docs"
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
  - "<<=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<<= 运算符（左移赋值）[C#]"
  - "左移赋值运算符 (<<=) [C#]"
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;&lt;= 运算符（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

左移赋值运算符。  
  
## 备注  
 下列形式的表达式  
  
```  
x <<= y  
```  
  
 按如下规则计算：  
  
```  
x = x << y  
```  
  
 不同的是 `x` 只计算一次。  [\<\< 运算符](../../../csharp/language-reference/operators/left-shift-operator.md)将 `x` 向左移动 `y` 指定的位数。  
  
 不能直接重载 `<<=` 运算符，但用户定义的类型可重载 [\<\< 运算符](../../../csharp/language-reference/operators/left-shift-operator.md)（请参见 [operator](../../../csharp/language-reference/keywords/operator.md)）。  
  
## 示例  
 [!CODE [csRefOperators#12](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#12)]  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [C\# 运算符](../../../csharp/language-reference/operators/index.md)