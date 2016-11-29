---
title: "&lt;c&gt; (Visual Basic) | Microsoft Docs"
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
  - "<c> XML 标记"
  - "c XML 标记"
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;c&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

指示说明中的文本是代码。  
  
## 语法  
  
```  
<c>text</c>  
```  
  
#### 参数  
  
|||  
|-|-|  
|Parameter|说明|  
|`text`|希望将其指示为代码的文本。|  
  
## 备注  
 `<c>` 标记为您提供了一种方法，以指示说明中的文本应标记为代码。  使用 [\<code\>](../../../visual-basic/language-reference/xmldoc/code.md) 可将多行指示为代码。  
  
 使用 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## 示例  
 本示例使用摘要一节中的 `<c>` 标记指示 `Counter` 是代码。  
  
 [!CODE [VbVbcnXmlDocComments#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#1)]  
  
## 请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)