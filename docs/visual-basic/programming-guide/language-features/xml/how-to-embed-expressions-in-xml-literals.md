---
title: "如何：在 XML 文本中嵌入表达式 (Visual Basic) | Microsoft Docs"
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
  - "嵌入的表达式 [Visual Basic]"
  - "XML 文本 [Visual Basic], 嵌入的表达式"
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：在 XML 文本中嵌入表达式 (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

可以将 XML 文本与嵌入式表达式组合在一起，以创建包含运行时创建的内容的 XML 文档、片断或元素。  下面的示例演示如何使用嵌入式表达式在运行时填充元素内容、特性和元素名称。  
  
 嵌入式表达式的语法是 `<%=` `exp` `%>`，与 [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] 使用的语法相同。有关更多信息，请参见 [XML 中的嵌入式表达式](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。  
  
 使用 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API 也可以创建 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 对象。  有关更多信息，请参见 <xref:System.Xml.Linq.XElement>。  
  
## 过程  
  
#### 插入文本作为元素内容  
  
-   下面的示例演示如何在开始和结束名称元素之间插入 `contactName` 变量中包含的文本。  
  
     [!CODE [VbXMLSamples#39](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#39)]  
  
     该示例产生下面的输出：  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### 插入文本作为特性值  
  
-   下面的示例演示如何插入 `phoneType` 变量中包含的文本作为 `type` 特性的值。  
  
     [!CODE [VbXMLSamples#40](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#40)]  
  
     该示例产生下面的输出：  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### 插入文本作为元素名称  
  
-   下面的示例演示如何插入 `elementName` 变量中包含的文本作为元素的名称。  
  
     使用这一方法创建元素时，必须将它们放置在 \<\/\> 标记之中。  
  
     [!CODE [VbXMLSamples#41](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#41)]  
  
     该示例产生下面的输出：  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## 请参阅  
 [如何：创建 XML 文本](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)   
 [XML 中的嵌入式表达式](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)