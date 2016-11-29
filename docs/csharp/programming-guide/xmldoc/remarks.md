---
title: "&lt;remarks&gt;（C# 编程指南） | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "remarks"
  - "<remarks>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<remarks> C# XML 标记"
  - "remarks C# XML 标记"
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
caps.latest.revision: 15
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;remarks&gt;（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## 语法  
  
```  
<remarks>description</remarks>  
```  
  
#### 参数  
 `Description`  
 成员的说明。  
  
## 备注  
 \<remarks\> 标记用于添加有关某个类型的信息，从而补充由 [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md) 所指定的信息。  此信息显示在 [Object Browser Window](http://msdn.microsoft.com/zh-cn/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) 中。  
  
 使用 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。  
  
## 示例  
 [!CODE [csProgGuideDocComments#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDocComments#9)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [建议的文档注释标记](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)