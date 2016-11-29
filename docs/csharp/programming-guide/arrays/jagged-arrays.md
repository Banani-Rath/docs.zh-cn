---
title: "交错数组（C# 编程指南） | Microsoft Docs"
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
  - "数组 [C#], 交错"
  - "交错数组 [C#]"
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 交错数组（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

交错数组是元素为数组的数组。  交错数组元素的维度和大小可以不同。  交错数组有时称为“数组的数组”。以下示例说明如何声明、初始化和访问交错数组。  
  
 下面声明一个由三个元素组成的一维数组，其中每个元素都是一个一维整数数组：  
  
 [!CODE [csProgGuideArrays#19](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#19)]  
  
 必须初始化 `jaggedArray` 的元素后才可以使用它。  可以如下例所示初始化该元素：  
  
 [!CODE [csProgGuideArrays#20](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#20)]  
  
 每个元素都是一个一维整数数组。  第一个元素是由 5 个整数组成的数组，第二个是由 4 个整数组成的数组，而第三个是由 2 个整数组成的数组。  
  
 也可以使用初始值设定项用值填充数组元素，在这种情况下不需要数组大小。  例如：  
  
 [!CODE [csProgGuideArrays#21](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#21)]  
  
 还可以在声明数组时将其初始化，如：  
  
 [!CODE [csProgGuideArrays#22](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#22)]  
  
 可以使用下面的速记格式。  请注意：不能从元素初始化中省略 `new` 运算符，因为不存在元素的默认初始化：  
  
 [!CODE [csProgGuideArrays#23](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#23)]  
  
 交错数组是数组的数组，因此其元素是引用类型并初始化为 `null`。  
  
 可以如下例所示访问个别数组元素：  
  
 [!CODE [csProgGuideArrays#24](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#24)]  
  
 可以混合使用交错数组和多维数组。  下面声明和初始化一个一维交错数组，该数组包含大小不同的三个二维数组元素。  有关二维数组的详细信息，请参阅[多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)。  
  
 [!CODE [csProgGuideArrays#25](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#25)]  
  
 可以如本例所示访问个别元素，该示例显示第一个数组的元素 `[1,0]` 的值（值为 `5`）：  
  
 [!CODE [csProgGuideArrays#26](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#26)]  
  
 方法 `Length` 返回包含在交错数组中的数组的数目。  例如，假定您已声明了前一个数组，则此行：  
  
 [!CODE [csProgGuideArrays#27](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#27)]  
  
 返回值 3。  
  
## 示例  
 本例生成一个数组，该数组的元素为数组自身。  每一个数组元素都有不同的大小。  
  
 [!CODE [csProgGuideArrays#18](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideArrays#18)]  
  
## 请参阅  
 <xref:System.Array>   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [数组](../../../csharp/programming-guide/arrays/index.md)   
 [一维数组](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)