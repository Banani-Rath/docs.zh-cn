---
title: "&lt;para&gt; (Visual Basic) | Microsoft Docs"
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
  - "<para> XML 标记"
  - "para XML 标记"
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# &lt;para&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

指定将内容格式化为段落。  
  
## 语法  
  
```  
<para>content</para>  
```  
  
#### 参数  
 `content`  
 段落文本。  
  
## 备注  
 `<para>` 标记用于某个标记（例如 [\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md)、[\<remarks\>](../../../visual-basic/language-reference/xmldoc/remarks.md) 或 [\<returns\>](../../../visual-basic/language-reference/xmldoc/returns.md)）内部，使您可以将结构添加到文本中。  
  
 使用 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。  
  
## 示例  
 此示例使用 `<para>` 标记将 `UpdateRecord` 方法的备注部分拆分为两个段落。  
  
 [!CODE [VbVbcnXmlDocComments#6](../CodeSnippet/VS_Snippets_VBCSharp/VbVbcnXmlDocComments#6)]  
  
## 请参阅  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)