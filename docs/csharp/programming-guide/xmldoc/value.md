---
title: "&lt;value&gt;（C# 编程指南） | Microsoft Docs"
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
  - "<value>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<value> C# XML 标记"
  - "value C# XML 标记"
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;value&gt;（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## 语法  
  
```  
<value>property-description</value>  
```  
  
#### 参数  
 `property-description`  
 属性的说明。  
  
## 备注  
 \<value\> 标记使您得以描述属性所代表的值。  请注意，当在 Visual Studio .NET 开发环境中通过代码向导添加属性时，它将会为新属性添加 [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md) 标记。  然后，应该手动添加 \<value\> 标记以描述该属性所表示的值。  
  
 使用 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。  
  
## 示例  
 [!CODE [csProgGuideDocComments#14](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDocComments#14)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [建议的文档注释标记](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)