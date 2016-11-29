---
title: "如何：提供文件操作进度对话框（C# 编程指南） | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "进度对话框 [C#]"
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：提供文件操作进度对话框（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

如果您使用 <xref:Microsoft.VisualBasic?displayProperty=fullName> 命名空间里的  <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> 方法，则可以提供能够显示 Windows 中文件操作进程的标准对话框。  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### 在 Visual Studio 中添加引用  
  
1.  在菜单栏上，依次选择“项目”、“添加引用”。  
  
     出现“引用管理器”对话框。  
  
2.  在“程序集”区域中，选择“框架”（如果尚未选择）。  
  
3.  在名称列表中，选中“Microsoft.VisualBasic”复选框，然后选择“确定”按钮关闭对话框。  
  
## 示例  
 下面的代码将 `sourcePath` 指定的目录复制到 `destinationPath` 指定的目录中。  此代码还提供一个标准对话框，该对话框显示预计完成操作还需要的时间量。  
  
 [!CODE [csFilesandFolders#11](../CodeSnippet/VS_Snippets_VBCSharp/csFilesAndFolders#11)]  
  
## 请参阅  
 [文件系统和注册表](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)