---
title: "将数组作为参数传递（C# 编程指南） | Microsoft Docs"
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
  - "数组 [C#], 作为参数传递"
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 将数组作为参数传递（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

数组可作为实参传递给方法形参。  由于数组是引用类型，因此方法可以更改元素的值。  
  
## 将一维数组作为参数传递  
 可以将初始化的一维数组传递给方法。  例如，下面的语句将数组发送到 print 方法。  
  
 [!CODE [csProgGuideArrays#34](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#34)]  
  
 下面的代码显示 print 方法的部分实现。  
  
 [!CODE [csProgGuideArrays#33](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#33)]  
  
 您可以在一个步骤中初始化和传递新数组，如下面的示例所示。  
  
 [!CODE [CsProgGuideArrays#35](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#35)]  
  
## 示例  
  
### 说明  
 在下面的示例中，将初始化一个字符串数组并将其作为参数传递到字符串的 `PrintArray` 方法。  该方法显示数组的元素。  接下来，调用 `ChangeArray` 和 `ChangeArrayElement` 方法以演示通过值发送数组参数时不会阻止更改这些数组元素。  
  
### 代码  
 [!CODE [csProgGuideArrays#30](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#30)]  
  
## 将多维数组作为参数传递  
 可采用与传递一维数组相同的方式将初始化的多维数组传递给方法。  
  
 [!CODE [csProgGuideArrays#41](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#41)]  
  
 下面的代码显示 print 方法的部分声明，该方法接受一个二维数组作为其参数。  
  
 [!CODE [csProgGuideArrays#36](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#36)]  
  
 您可以在一个步骤中初始化和传递新数组，如下面的示例所示。  
  
 [!CODE [csProgGuideArrays#32](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#32)]  
  
## 示例  
  
### 说明  
 在下面的示例中，将初始化一个二维整数数组并将其传递到 `Print2DArray` 方法。  该方法显示数组的元素。  
  
### 代码  
 [!CODE [csProgGuideArrays#31](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#31)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [数组](../../../csharp/programming-guide/arrays/index.md)   
 [一维数组](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [交错数组](../../../csharp/programming-guide/arrays/jagged-arrays.md)