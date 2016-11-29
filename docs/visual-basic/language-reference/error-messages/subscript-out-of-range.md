---
title: "下标超出范围 (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID9"
dev_langs: 
  - "VB"
ms.assetid: d0344a65-ec02-4caf-8d3c-9977392ca353
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 下标超出范围 (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

数组下标无效，因为它不在允许的范围内。  维度的最小下标值始终是 0，最大下标值是由该维的 `GetUpperBound` 方法返回的。  
  
### 更正此错误  
  
-   更改下标，使其在有效的范围内。  
  
## 请参阅  
 <xref:System.Array.GetUpperBound%2A?displayProperty=fullName>   
 [数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)