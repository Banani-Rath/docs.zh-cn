---
title: "指针比较（C# 编程指南） | Microsoft Docs"
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
  - "指针 [C#], 比较"
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 指针比较（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

可应用下面的运算符比较任意类型的指针：  
  
 **\=\=   \!\=   \<   \>   \<\=   \>\=**  
  
 比较运算符比较两个操作数的地址，就像他们是无符号整数一样。  
  
## 示例  
 [!CODE [csProgGuidePointers#16](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#16)]  
  
 [!CODE [csProgGuidePointers#17](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#17)]  
  
## 示例输出  
 `True`  
  
 `False`  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [指针表达式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [C\# 运算符](../../../csharp/language-reference/operators/index.md)   
 [操作指针](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)   
 [指针类型](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [类型](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)