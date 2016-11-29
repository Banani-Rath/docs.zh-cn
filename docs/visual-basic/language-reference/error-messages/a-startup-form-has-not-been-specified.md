---
title: "未指定启动窗体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrAppModel_NoStartupForm"
dev_langs: 
  - "VB"
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 未指定启动窗体
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

应用程序使用 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 类，但未指定启动窗体。  
  
 当在项目设计器中选中**“启用应用程序框架”**复选框，但未指定**“启动窗体”**时，将发生这种情况。  有关更多信息，请参见[“项目设计器”, “应用程序”页 \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)。  
  
### 更正此错误  
  
1.  为应用程序指定启动对象。  
  
     有关更多信息，请参见[“项目设计器”, “应用程序”页 \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)。  
  
2.  重写 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> 方法，将 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> 属性设置为启动窗体。  
  
## 请参阅  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>   
 [Visual Basic 应用程序模型概述](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)