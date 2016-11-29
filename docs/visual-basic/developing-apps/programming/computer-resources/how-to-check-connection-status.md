---
title: "如何：在 Visual Basic 中检查连接状态 | Microsoft Docs"
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
  - "连接状态"
  - "连接, 检查状态"
  - "IsAvailable 属性, 关于 IsAvailable"
  - "Web 连接"
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
caps.latest.revision: 26
caps.handback.revision: 26
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：在 Visual Basic 中检查连接状态
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> 属性可用于确定计算机是否拥有工作网络或 Internet 连接。  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### 检查计算机是否拥有工作连接  
  
-   确定 `IsAvailable` 属性是 `True` 还是 `False`。  下面的代码检查属性的状态并进行报告：  
  
     [!CODE [VbResourceTasks#3](../CodeSnippet/VS_Snippets_VBCSharp/VbResourceTasks#3)]  
  
     此代码示例也可用作 IntelliSense 代码段。  在代码段选择器中，此代码示例位于**“连接和网络”**中。  有关更多信息，请参见 [代码段](/visual-studio/ide/code-snippets)。  
  
## 请参阅  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>