---
title: "“Custom”修饰符在未用显式委托类型声明的事件上无效 | Microsoft Docs"
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
  - "vbc31122"
  - "bc31122"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31122"
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# “Custom”修饰符在未用显式委托类型声明的事件上无效
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

与非自定义事件不同，`Custom Event` 声明需要一个跟在事件名称后面的 `As` 子句，该子句显式指定事件的委托类型。  
  
 定义的非自定义事件可带有 `As` 子句和显式委托类型，或在事件名称后面紧跟一个参数列表。  
  
 **错误 ID：**BC31122  
  
### 更正此错误  
  
1.  使用与自定义事件相同的参数列表定义一个委托。  
  
     例如，如果 `Custom Event` 是由 `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` 定义的，则对应的委托将如下所示。  
  
     [!CODE [VbVbalrEventError#18](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#18)]  
  
2.  将自定义事件的参数列表替换为指定委托类型的 `As` 子句。  
  
     接上例，将按如下方式重写 `Custom Event` 声明。  
  
     [!CODE [VbVbalrEventError#19](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#19)]  
  
## 示例  
 此示例声明 `Custom Event`，并指定带有委托类型的必需 `As` 子句。  
  
 [!CODE [VbVbalrEventError#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#2)]  
  
## 请参阅  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [事件](../../../visual-basic/programming-guide/language-features/events/events.md)