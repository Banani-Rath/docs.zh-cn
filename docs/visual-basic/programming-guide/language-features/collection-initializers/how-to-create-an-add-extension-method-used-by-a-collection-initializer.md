---
title: "如何：创建集合初始值设定项所使用的 Add 扩展方法 (Visual Basic) | Microsoft Docs"
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
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：创建集合初始值设定项所使用的 Add 扩展方法 (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

使用集合初始值设定项创建集合时，Visual Basic 编译器会搜索该集合类型的 `Add` 方法，所搜索的 `Add` 方法的参数要与用于该集合的集合初始值设定项中的值类型相匹配。  此 `Add` 方法用于以集合初始值设定项中的值填充集合。  
  
 如果没有匹配的 `Add` 方法并且无法修改集合的代码，则可以添加一个名为 `Add` 的扩展方法，该方法接受集合初始值设定项所需的参数。  在对泛型集合使用集合初始值设定项时，通常需要这样操作。  
  
## 示例  
 下面的示例演示如何将扩展方法添加到泛型类型 <xref:System.Collections.Generic.List%601>，以便可以使用集合初始值设定项添加 `Employee` 类型的对象。  通过扩展方法可以使用集合初始值设定项短语法。  
  
 [!CODE [VbVbalrCollectionInitializersHowTo1#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1#1)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo1#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1#2)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo1#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1#3)]  
  
## 请参阅  
 [集合初始值设定项](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [如何：创建集合初始值设定项所使用的集合](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)