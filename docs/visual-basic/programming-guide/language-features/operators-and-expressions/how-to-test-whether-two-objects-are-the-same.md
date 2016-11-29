---
title: "如何：测试两个对象是否相同 (Visual Basic) | Microsoft Docs"
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
  - "Is 运算符 [Visual Basic], 比较对象"
  - "对象 [Visual Basic], 引用同一对象的变量"
  - "引用变量"
  - "变量 [Visual Basic], 参考"
  - "变量 [Visual Basic], 引用同一对象"
  - "Visual Basic 代码, 运算符"
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：测试两个对象是否相同 (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

如果有两个引用对象的变量，您可以使用 `Is` 或 `IsNot` 运算符或者同时使用这两个运算符来确定它们是否引用同一个实例。  
  
### 测试两个对象是否相同  
  
-   使用带有两个作为操作数的变量的 [Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md) 或 [IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)。  
  
     [!CODE [VbVbalrOperators#69](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#69)]  
  
 您可能需要根据两个对象是否引用同一个实例来决定要执行的具体操作。  前面的示例将控件 `c` 与窗体 `f` 上的活动控件进行比较。  如果没有活动控件，或者如果有活动控件但该控件不是与 `c` 相同的控件实例，则 `If` 语句会失败，并且过程将返回，而不会进一步进行处理。  
  
 您可以根据自己的需要决定使用 `Is` 还是 `IsNot`。  在指定的表达式中，其中一个可能比另一个更容易读懂。  
  
## 请参阅  
 [比较运算符 \(Visual Basic\)](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)