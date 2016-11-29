---
title: "指针转换（C# 编程指南） | Microsoft Docs"
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
  - "指针 [C#], 转换"
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 指针转换（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

下表显示了预定义的隐式指针转换。  隐式转换可能在多种情形下发生，包括调用方法时和在赋值语句中。  
  
## 隐式指针转换  
  
|发件人|若要|  
|---------|--------|  
|任何指针类型|void\*|  
|null|任何指针类型|  
  
 显式指针转换用于在不存在隐式转换时通过使用强制转换表达式来执行转换。  下表显示了这些转换。  
  
## 显式指针转换  
  
|发件人|若要|  
|---------|--------|  
|任何指针类型|所有其他指针类型|  
|sbyte、byte、short、ushort、int、uint、long 或 ulong|任何指针类型|  
|任何指针类型|sbyte、byte、short、ushort、int、uint、long 或 ulong|  
  
## 示例  
 在下面的示例中，一个指向 `int` 的指针被转换为指向 `byte` 的指针。  注意，该指针指向变量的最低地址字节。  连续递增该结果直到达到 `int` 的大小（4 字节），即可显示变量的剩余字节。  
  
 [!CODE [csProgGuidePointers#3](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#3)]  
  
 [!CODE [csProgGuidePointers#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#4)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [指针表达式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [类型](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)