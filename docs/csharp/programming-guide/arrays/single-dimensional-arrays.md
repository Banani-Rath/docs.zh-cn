---
title: "一维数组（C# 编程指南） | Microsoft Docs"
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
  - "数组 [C#], 单维"
  - "单维数组 [C#]"
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 一维数组（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

可按下面的示例所示声明五个整数的一维数组。  
  
 [!CODE [csProgGuideArrays#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#4)]  
  
 此数组包含从 `array[0]` 到 `array[4]` 的元素。  [new](../../../csharp/language-reference/keywords/new.md) 运算符用于创建数组并将数组元素初始化为它们的默认值。  在此例中，所有数组元素都初始化为零。  
  
 可以用相同的方式声明存储字符串元素的数组。  例如：  
  
 [!CODE [csProgGuideArrays#5](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#5)]  
  
## 数组初始化  
 可以在声明数组时将其初始化，在这种情况下不需要级别说明符，因为级别说明符已经由初始化列表中的元素数提供。  例如：  
  
 [!CODE [csProgGuideArrays#6](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#6)]  
  
 可以用相同的方式初始化字符串数组。  下面声明一个字符串数组，其中每个数组元素用每天的名称初始化：  
  
 [!CODE [csProgGuideArrays#7](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#7)]  
  
 如果在声明数组时将其初始化，则可以使用下列快捷方式：  
  
 [!CODE [csProgGuideArrays#8](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#8)]  
  
 可以声明一个数组变量但不将其初始化，但在将数组分配给此变量时必须使用 `new` 运算符。  例如：  
  
 [!CODE [csProgGuideArrays#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#9)]  
  
 C\# 3.0 引入了隐式类型的数组。  有关更多信息，请参见 [隐式类型的数组](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)。  
  
## 值类型数组和引用类型数组  
 请看下列数组声明：  
  
 [!CODE [csProgGuideArrays#10](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#10)]  
  
 该语句的结果取决于 `SomeType` 是值类型还是引用类型。  如果为值类型，则语句将创建一个有 10 个元素的数组，每个元素都有 `SomeType` 类型。  如果 `SomeType` 是引用类型，则该语句将创建一个由 10 个元素组成的数组，其中每个元素都初始化为空引用。  
  
 有关值类型和引用类型的更多信息，请参见[类型](../../../csharp/language-reference/keywords/types.md)。  
  
## 请参阅  
 <xref:System.Array>   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [数组](../../../csharp/programming-guide/arrays/index.md)   
 [多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [交错数组](../../../csharp/programming-guide/arrays/jagged-arrays.md)