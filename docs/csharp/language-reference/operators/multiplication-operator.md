---
title: "* 运算符（C# 参考） | Microsoft Docs"
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
  - "*_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "* 运算符 [C#]"
  - "乘法运算符 (*) [C#]"
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# * 运算符（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

乘法运算符 \(`*`\)，用于计算操作数的积。  另外还用作取消引用运算符，允许读取和写入指针。  
  
## 备注  
 所有数值类型都具有预定义的乘法运算符。  
  
 `*` 运算符还用来声明指针类型和取消引用指针。  该运算符只能在不安全的上下文中使用，通过 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 关键字的使用来表示，并且需要 [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 编译器选项。  取消引用运算符也称为间接寻址运算符。  
  
 用户定义的类型可重载二元 `*` 运算符（请参见 [operator](../../../csharp/language-reference/keywords/operator.md)）。  重载二元运算符时，也会隐式重载相应的赋值运算符（如果有）。  
  
## 示例  
 [!CODE [csRefOperators#50](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#50)]  
  
## 示例  
 [!CODE [csRefOperators#51](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#51)]  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [不安全代码和指针](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [C\# 运算符](../../../csharp/language-reference/operators/index.md)