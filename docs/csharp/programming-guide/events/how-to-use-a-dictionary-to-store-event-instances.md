---
title: "如何：使用字典存储事件实例（C# 编程指南） | Microsoft Docs"
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
  - "事件 [C#], 在 Dictionary 中存储实例"
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：使用字典存储事件实例（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`accessor-declarations` 的一种用法是公开很多事件但不为每个事件分配字段，而是使用字典来存储这些事件实例。  这只在具有很多事件但您预计大多数事件都不会实现时才有用。  
  
## 示例  
 [!CODE [csProgGuideEvents#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideEvents#9)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [事件](../../../csharp/programming-guide/events/index.md)   
 [委托](../../../csharp/programming-guide/delegates/index.md)