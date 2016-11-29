---
title: "Alias 子句 (Visual Basic) | Microsoft Docs"
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
  - "vb.Alias"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Alias 关键字"
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Alias 子句 (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

指示外部过程在其 DLL 中具有另一个名称。  
  
## 备注  
 `Alias` 关键字可用于下面的上下文中：  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 在下面的示例中，使用 `Alias` 关键字提供 advapi32.dll 中函数 `GetUserNameA`（在本例中改用 `getUserName`）的名称。  在 sub `getUser` 中，调用了函数 `getUserName`，该函数显示当前用户的名称。  
  
 [!CODE [VbVbalrStatements#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#15)]  
  
## 请参阅  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)