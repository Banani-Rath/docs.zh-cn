---
title: "字符串操作方法的类型 (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "字符串操作"
  - "字符串 [Visual Basic], 操作 [Visual Basic]"
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 字符串操作方法的类型 (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

可使用几种不同的方法来分析和操作字符串。  一些方法是 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 语言的一部分，另外一些是 `String` 类中所固有的。  
  
## Visual Basic 语言与 .NET Framework  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 方法被用作该语言的固有函数。  它们可无限制地在代码中使用。  下面的示例演示了一个 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 字符串操作命令的典型用法：  
  
 [!CODE [VbVbalrStrings#44](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#44)]  
  
 在此示例中，`Mid` 函数对 `aString` 执行直接操作，并将值赋予 `bString`。  
  
 有关 Visual Basic 字符串操作方法的列表，请参见[字符串操作摘要](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)。  
  
### 共享方法和实例方法  
 还可以使用 `String` 类的方法操作字符串。  `String` 中有两类方法：共享方法和实例方法。  
  
#### 共享方法  
 共享方法是起源于 `String` 类本身的方法，不要求该类的实例起作用。  可以用类名 \(`String`\) 限定这些方法，而不使用 `String` 类的实例限定。  例如：  
  
 [!CODE [VbVbalrStrings#45](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#45)]  
  
 在前面的示例中，<xref:System.String.Copy%2A?displayProperty=fullName> 方法是静态方法，它处理给予它的表达式，并将结果值赋予 `bString`。  
  
#### 实例方法  
 相反，实例方法起源于 `String` 的特定实例，而且必须用该实例名限定。  例如：  
  
 [!CODE [VbVbalrStrings#46](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#46)]  
  
 在此示例中，<xref:System.String.Substring%2A?displayProperty=fullName> 方法是 `String` 实例（即 `aString`）的方法。  它对 `aString` 执行操作，并将该值赋予 `bString`。  
  
 有关更多信息，请参见 <xref:System.String> 类的文档。  
  
## 请参阅  
 [字符串介绍 \(Visual Basic\)](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)