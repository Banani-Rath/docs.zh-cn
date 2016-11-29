---
title: "如何：创建集合初始值设定项所使用的集合 (Visual Basic) | Microsoft Docs"
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
  - "集合初始值设定项 [Visual Basic]"
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：创建集合初始值设定项所使用的集合 (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

使用集合初始值设定项创建集合时，Visual Basic 编译器会搜索该集合类型的 `Add` 方法，所搜索的 `Add` 方法的参数要与用于该集合的集合初始值设定项中的值类型相匹配。  此 `Add` 方法用于以集合初始值设定项中的值填充集合。  
  
## 示例  
 下面的示例演示 `OrderCollection` 集合，该集合包含一个公共 `Add` 方法，集合初始值设定项可使用该方法添加 `Order` 类型的对象。  `Add` 方法允许使用集合初始值设定项的缩写语法。  
  
 [!CODE [VbVbalrCollectionInitializersHowTo2#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2#4)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo2#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2#1)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo2#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2#2)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo2#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2#3)]  
  
## 请参阅  
 [集合初始值设定项](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [如何：创建集合初始值设定项所使用的 Add 扩展方法](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)