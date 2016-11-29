---
title: "Nothing 和字符串 (Visual Basic) | Microsoft Docs"
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
  - "字符串 [Visual Basic], Nothing"
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Nothing 和字符串 (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 运行时和 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 在处理字符串时以不同的方式计算 `Nothing`。  
  
## Visual Basic 运行时与 .NET Framework  
 请看下面的示例：  
  
 [!CODE [VbVbalrStrings#47](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#47)]  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 运行时通常将 `Nothing` 作为空字符串 \(""\) 计算。  但是 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 则不同，每当尝试对 `Nothing` 执行字符串操作时都将引发异常。  
  
## 请参阅  
 [字符串介绍 \(Visual Basic\)](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)