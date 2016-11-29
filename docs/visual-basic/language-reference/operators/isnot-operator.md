---
title: "IsNot 运算符 (Visual Basic) | Microsoft Docs"
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
  - "vb.isnot"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IsNot 运算符"
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# IsNot 运算符 (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

比较两个对象引用变量。  
  
## 语法  
  
```  
  
result = object1 IsNot object2  
```  
  
## 部件  
 `result`  
 必选。  一个 `Boolean` 值。  
  
 `object1`  
 必选。  任何 `Object` 变量或表达式。  
  
 `object2`  
 必选。  任何 `Object` 变量或表达式。  
  
## 备注  
 `IsNot` 运算符确定两个对象引用是否引用不同的对象。  但是，它不执行值比较。  如果 `object1` 和 `object2` 引用同一个对象实例，则 `result` 为 `False`；如果它们不引用同一个对象，则 `result` 为 `True`。  
  
 `IsNot` 是与 `Is` 运算符相反的运算符。  `IsNot` 的优点是您可以避免使用 `Not` 和 `Is` 的笨拙语法，后者难以读取。  
  
 可以使用 `Is` 和 `IsNot` 运算符测试早期绑定和后期绑定的对象。  
  
> [!NOTE]
>  `IsNot` 运算符不能用于比较从 `TypeOf` 运算符返回的表达式。  而是 `Not` 和 `Is` 属性必须一起使用。  
  
## 示例  
 下面的代码示例使用 `Is` 运算符和 `IsNot` 运算符进行同样的比较。  
  
 [!CODE [VbVbalrOperators#29](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#29)]  
  
## 请参阅  
 [Is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)   
 [TypeOf 运算符](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [如何：测试两个对象是否相同](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)