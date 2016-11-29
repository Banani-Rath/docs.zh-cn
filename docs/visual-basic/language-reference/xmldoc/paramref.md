---
title: "&lt;paramref&gt; (Visual Basic) | Microsoft Docs"
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
  - "<paramref> XML 标记"
  - "paramref XML 标记"
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;paramref&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

将一个词格式化为参数。  
  
## 语法  
  
```  
<paramref name="name"/>  
```  
  
#### 参数  
 `name`  
 要引用的参数名。  将此名称用双引号括起来 \(" "\)。  
  
## 备注  
 `<paramref>` 标记为您提供了一种指示词为参数的方法。  可以处理 XML 文件，从而用某种独特的方法格式化该参数。  
  
 使用 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## 示例  
 本示例使用 `<paramref>` 标记引用 `id` 参数。  
  
 [!CODE [VbVbcnXmlDocComments#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#6)]  
  
## 请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)