---
title: "多维数组（C# 编程指南） | Microsoft Docs"
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
  - "数组 [C#], 多维"
  - "多维数组 [C#]"
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 多维数组（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

数组可以具有多个维度。  例如，下列声明创建一个四行两列的二维数组。  
  
 [!CODE [csProgGuideArrays#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#11)]  
  
 下列声明创建一个三维（4、2 和 3）数组。  
  
 [!CODE [csProgGuideArrays#12](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#12)]  
  
## 数组初始化  
 可以在声明数组时将其初始化，如下例所示。  
  
 [!CODE [csProgGuideArrays#13](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#13)]  
  
 也可以初始化数组但不指定级别。  
  
 [!CODE [csProgGuideArrays#14](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#14)]  
  
 如果选择声明一个数组变量但不将其初始化，必须使用 `new` 运算符将一个数组分配给此变量。  以下示例显示 `new` 的用法。  
  
 [!CODE [csProgGuideArrays#15](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#15)]  
  
 以下示例将值分配给特定的数组元素。  
  
 [!CODE [csProgGuideArrays#16](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#16)]  
  
 同样，下面的示例获取特定数组元素的值，并将它赋给变量`elementValue`。  
  
 [!CODE [csProgGuideArrays#42](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#42)]  
  
 以下代码示例将数组元素初始化为默认值（交错数组除外）：  
  
 [!CODE [csProgGuideArrays#17](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#17)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [数组](../../../csharp/programming-guide/arrays/index.md)   
 [一维数组](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [交错数组](../../../csharp/programming-guide/arrays/jagged-arrays.md)