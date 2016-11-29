---
title: "My.Response 对象 | Microsoft Docs"
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
  - "My.MyWebExtension.Response"
  - "My.Response"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Response 对象"
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# My.Response 对象
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

获取与 <xref:System.Web.UI.Page> 关联的 <xref:System.Web.HttpResponse> 对象。  该对象使您得以将 HTTP 响应数据发送到客户端，并包含有关该响应的信息。  
  
## 备注  
 `My.Response` 对象包含与页面关联的当前 <xref:System.Web.HttpResponse> 对象。  
  
 `My.Response` 对象仅可用于 [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] 应用程序。  
  
## 示例  
 下面的示例从 `My.Request` 对象中获取标头集合，并使用 `My.Response` 对象将其写入到 ASP.NET 页面。  
  
 [!CODE [VbVbalrMyWeb#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrMyWeb#1)]  
  
## 请参阅  
 <xref:System.Web.HttpResponse>   
 [My.Request 对象](../../../visual-basic/language-reference/objects/my-request-object.md)