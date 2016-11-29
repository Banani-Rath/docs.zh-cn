---
title: "如何：在 Visual Basic 中下载文件 | Microsoft Docs"
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
  - "下载文件"
  - "下载 Internet 资源, 文件"
  - "文件, 下载"
  - "文件, 传输"
  - "远程计算机, 从中下载"
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：在 Visual Basic 中下载文件
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

可以使用 <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> 方法下载远程文件，并将下载后的文件存储到特定位置。  如果 `ShowUI` 参数设置为 `True`，则显示一个对话框，该对话框显示下载的进度并允许用户取消该操作。  默认情况下，不会覆盖同名的现有文件；如果希望覆盖现有文件，则将 `overwrite` 参数设为 `True`。  
  
 以下情况可能会导致异常：  
  
-   驱动器名称无效 \(<xref:System.ArgumentException>\)。  
  
-   尚未提供必要的身份验证（<xref:System.UnauthorizedAccessException> 或 <xref:System.Security.SecurityException>）。  
  
-   服务器没有在指定的 `connectionTimeout` 内响应 \(<xref:System.TimeoutException>\)。  
  
-   请求被网站拒绝 \(<xref:System.Net.WebException>\)。  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
> [!IMPORTANT]
>  不要根据文件的名称来判断文件的内容。  例如，Form1.vb 文件可能不是 Visual Basic 源文件。  在应用程序中使用输入的数据之前，需验证所有的输入内容。  文件的内容可能不是预期内容，并且用来读取该文件的方法可能失败。  
  
### 下载文件  
  
-   使用 `DownloadFile` 方法下载文件，同时将目标文件的位置指定为字符串或 URI 并指定要存储该文件的位置。  此示例从 `http://www.cohowinery.com/downloads` 下载 `WineList.txt` 文件，并将下载后的该文件保存到 `C:\Documents and Settings\All Users\Documents` 中：  
  
     [!CODE [VbResourceTasks#9](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#9)]  
  
### 下载文件，并指定超时间隔  
  
-   使用 `DownloadFile` 方法下载文件，同时将目标文件的位置指定为字符串或 URI，指定要存储该文件的位置，并以毫秒为单位指定超时间隔（默认值为 1000）。  此示例从 `http://www.cohowinery.com/downloads` 下载 `WineList.txt` 文件，然后将该文件保存到 `C:\Documents and Settings\All Users\Documents`，同时将超时间隔指定为 500 毫秒：  
  
     [!CODE [VbResourceTasks#10](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#10)]  
  
### 在提供用户名和密码的情况下下载文件  
  
-   使用 `DownLoadFile` 方法下载文件，同时将目标文件的位置指定为字符串或 URI，并指定要存储该文件的位置、用户名和密码。  此示例使用用户名 `anonymous` 和空密码从 `http://www.cohowinery.com/downloads` 下载 `WineList.txt` 文件，然后将该文件保存到 `C:\Documents and Settings\All Users\Documents`。  
  
     [!CODE [VbResourceTasks#11](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#11)]  
  
    > [!IMPORTANT]
    >  `DownLoadFile` 方法使用的 FTP 协议以纯文本方式发送信息（包括密码），因此不应用它传送敏感信息。  
  
## 请参阅  
 <xref:Microsoft.VisualBasic.Devices.Network>   
 <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>   
 [如何：上载文件](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)   
 [如何：分析文件路径](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)