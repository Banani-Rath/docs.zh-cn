---
title: "语句不能在“If”语句行之外结束块 | Microsoft Docs"
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
  - "vbc32005"
  - "bc32005"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32005"
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 语句不能在“If”语句行之外结束块
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

单行 `If` 语句包含由冒号 \(:\) 分隔的几个语句，其中一个语句是单行 `If` 语句外的控制块的 `End` 语句。  单行 `If` 语句不使用 `End If` 语句。  
  
 **错误 ID：**BC32005  
  
### 更正此错误  
  
-   将单行 `If` 语句移到包含 `End If` 语句的控制块之外。  
  
## 请参阅  
 [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)