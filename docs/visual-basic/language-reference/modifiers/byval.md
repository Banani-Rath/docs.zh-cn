---
title: "ByVal (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ByVal"
  - "ByVal"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ByVal 关键字"
  - "ByVal 关键字, 上下文"
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# ByVal (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

指定按如下方式传递参数：被调用的过程或属性不能更改调用它的代码中参数下面的变量的值。  
  
## 备注  
 `ByVal` 修饰符可用于下面的上下文中：  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator 语句](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 示例  
 下面的示例演示如何将 `ByVal` 形参传入机制与引用类型实参一起使用。  在该示例中，实参是 `c1`，它是类 `Class1` 的一个实例。  `ByVal` 防止过程中的代码更改引用实参 `c1` 的基础值，但是不保护 `c1` 的可访问字段和属性。  
  
 [!CODE [VbVbalrKeywords#10](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrKeywords#10)]  
  
## 请参阅  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)   
 [通过值和通过引用传递参数](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)