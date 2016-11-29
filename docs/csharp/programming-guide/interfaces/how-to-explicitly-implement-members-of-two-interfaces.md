---
title: "如何：显式实现两个接口的成员（C# 编程指南） | Microsoft Docs"
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
  - "继承 [C#], 显式实现接口成员"
  - "接口 [C#], 通过继承显式实现"
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：显式实现两个接口的成员（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

显式[接口](../../../csharp/language-reference/keywords/interface.md)实现还允许程序员实现具有相同成员名称的两个接口，并为每个接口成员各提供一个实现。  本示例同时以公制单位和英制单位显示框的尺寸。  Box [类](../../../csharp/language-reference/keywords/class.md)实现 IEnglishDimensions 和 IMetricDimensions 两个接口，它们表示不同的度量系统。  两个接口有相同的成员名称 Length 和 Width。  
  
## 示例  
 [!CODE [csProgGuideInheritance#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#9)]  
  
## 可靠编程  
 如果希望默认度量采用英制单位，请正常实现 Length 和 Width 这两个方法，并从 IMetricDimensions 接口显式实现 Length 和 Width 方法：  
  
 [!CODE [csProgGuideInheritance#10](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#10)]  
  
 这种情况下，可以从类实例访问英制单位，而从接口实例访问公制单位：  
  
 [!CODE [csProgGuideInheritance#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideInheritance#11)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [类和结构](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [接口](../../../csharp/programming-guide/interfaces/index.md)   
 [如何：显式实现接口成员](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)