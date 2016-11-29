---
title: "My.Request 对象 | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "My.MyWebExtension.Request"
  - "My.Request"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Request 对象"
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# My.Request 对象
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

获取请求的页的 <xref:System.Web.HttpRequest> 对象。  
  
## 备注  
 `My.Request` 对象包含有关当前 HTTP 请求的信息。  
  
 `My.Request` 对象仅可用于 ASP.NET 应用程序。  
  
## 示例  
 下面的示例从 `My.Request` 对象中获取标头集合，并使用 `My.Response` 对象将其写入到 ASP.NET 页面。  
  
 [!CODE [VbVbalrMyWeb#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyWeb#1)]  
  
## 请参阅  
 <xref:System.Web.HttpRequest>   
 [My.Response 对象](../../../visual-basic/language-reference/objects/my-response-object.md)