---
title: "&lt;remarks&gt; (Visual Basic) | Microsoft Docs"
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
  - "<remarks> XML 标记"
  - "remarks XML 标记"
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;remarks&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

指定成员的备注部分。  
  
## 语法  
  
```  
<remarks>description</remarks>  
```  
  
#### 参数  
 `description`  
 成员的说明。  
  
## 备注  
 使用 `<remarks>` 标记添加有关类型的信息，以此补充用 [\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md) 指定的信息。  
  
 此信息显示在对象浏览器。  有关对象浏览器的信息，请参见 [查看代码的结构](/visual-studio/ide/viewing-the-structure-of-code)。  
  
 使用 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## 示例  
 此示例使用 `<remarks>` 标记解释 `UpdateRecord` 方法的作用。  
  
 [!CODE [VbVbcnXmlDocComments#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#6)]  
  
## 请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)