---
title: "如何：在 Visual Basic 中创建文件 | Microsoft Docs"
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
  - "文件, 创建"
  - "文本文件, 创建"
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：在 Visual Basic 中创建文件
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

此示例使用 <xref:System.IO.File> 类中的 <xref:System.IO.File.Create%2A> 方法在指定的路径中创建一个空文本文件。  
  
## 示例  
 [!CODE [VbFileIOMisc#1](../CodeSnippet/VS_Snippets_VBCSharp/VbFileIOMisc#1)]  
  
## 编译代码  
 使用 `file` 变量写入该文件。  
  
## 可靠编程  
 如果该文件已存在，则替换它。  
  
 以下情况可能会导致异常：  
  
-   路径名格式不正确。  例如，它包含非法字符或仅包含空白 \(<xref:System.ArgumentException>\)。  
  
-   此路径是只读的 \(<xref:System.IO.IOException>\)。  
  
-   路径名是 `Nothing` \(<xref:System.ArgumentNullException>\)。  
  
-   路径名太长 \(<xref:System.IO.PathTooLongException>\)。  
  
-   路径无效 \(<xref:System.IO.DirectoryNotFoundException>\)。  
  
-   路径仅是一个冒号“:”\(<xref:System.NotSupportedException>\)。  
  
## .NET Framework 安全性  
 在部分信任的环境中可能引发 <xref:System.Security.SecurityException>。  
  
 对 <xref:System.IO.File.Create%2A> 方法的调用要求 <xref:System.Security.Permissions.FileIOPermission>。  
  
 如果用户没有创建文件的权限，将引发 <xref:System.UnauthorizedAccessException>。  
  
## 请参阅  
 <xref:System.IO>   
 <xref:System.IO.File.Create%2A>   
 [通过部分受信任的代码使用库](../Topic/Using%20Libraries%20from%20Partially%20Trusted%20Code.md)   
 [代码访问安全性基础知识](../Topic/Code%20Access%20Security%20Basics.md)