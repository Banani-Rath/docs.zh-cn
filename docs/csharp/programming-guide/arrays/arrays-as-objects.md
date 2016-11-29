---
title: "作为对象的数组（C# 编程指南） | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "数组 [C#], 作为对象"
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 作为对象的数组（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

在 C\# 中，数组实际上是对象，而不只是像 C 和 C\+\+ 中那样的可寻址连续内存区域。  <xref:System.Array> 是所有数组类型的抽象基类型。  可以使用 <xref:System.Array> 具有的属性以及其他类成员。  这种用法的一个示例是使用 <xref:System.Array.Length%2A> 属性来获取数组的长度。  下面的代码将 `numbers` 数组的长度（为 `5`）赋给名为 `lengthOfNumbers` 的变量：  
  
 [!CODE [csProgGuideArrays#3](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#3)]  
  
 <xref:System.Array> 类提供了许多其他有用的方法和属性，用于排序、搜索和复制数组。  
  
## 示例  
 此示例使用 <xref:System.Array.Rank%2A> 属性来显示数组的维数。  
  
 [!CODE [csProgGuideArrays#2](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#2)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [数组](../../../csharp/programming-guide/arrays/index.md)   
 [一维数组](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [交错数组](../../../csharp/programming-guide/arrays/jagged-arrays.md)