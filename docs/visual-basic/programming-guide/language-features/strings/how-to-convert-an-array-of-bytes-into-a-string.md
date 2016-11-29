---
title: "如何：在 Visual Basic 中将字节数组转换为字符串 | Microsoft Docs"
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
  - "数组 [Visual Basic], 转换为字符串"
  - "字节数组, 转换为字符串"
  - "示例 [Visual Basic], 字符串"
  - "字符串转换, 数组"
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：在 Visual Basic 中将字节数组转换为字符串
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

本主题演示如何将字节从字节数组转换为字符串。  
  
## 示例  
 本示例使用 <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName> 编码类的 <xref:System.Text.Encoding.GetString%2A> 方法将所有字节从字节数组转换为字符串。  
  
 [!CODE [VbVbalrStrings#72](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStrings#72)]  
  
 可以从多个编码选项中选择一种以将字节数组转换为字符串：  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName>：获取 ASCII（7 位）字符集的编码。  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=fullName>：使用 Big\-Endian 字节顺序获取 UTF\-16 格式的编码。  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=fullName>：获取系统当前 ANSI 代码页的编码。  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=fullName>：使用 Little\-Endian 字节顺序获取 UTF\-16 格式的编码。  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=fullName>：使用 Little\-Endian 字节顺序获取 UTF\-32 格式的编码。  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=fullName>：获取 UTF\-7 格式的编码。  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=fullName>：获取 UTF\-8 格式的编码。  
  
## 请参阅  
 <xref:System.Text.Encoding?displayProperty=fullName>   
 <xref:System.Text.Encoding.GetString%2A>   
 [如何：在 Visual Basic 中将字符串转换为字节数组](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)