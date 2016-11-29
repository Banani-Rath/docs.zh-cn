---
title: "内存不足（Visual Basic 编译器错误） | Microsoft Docs"
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
  - "vbc2004"
  - "bc2004"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC2004"
ms.assetid: 6bc0939c-e279-4875-a91c-f4076860b5b9
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 内存不足（Visual Basic 编译器错误）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

可用内存不足。  
  
 **错误 ID：**BC2004  
  
### 更正此错误  
  
-   关闭不必要的应用程序、文档和源文件。  
  
-   消除不必要的控件和窗体，以便同一时间加载较少的控件和窗体。  
  
-   减少 `Public` 变量的数目。  
  
-   检查可用的磁盘空间。  
  
-   请通过安装更多的内存或重新分配内存来增加可用 RAM。  
  
-   确保不再需要内存时释放内存。  
  
## 请参阅  
 [错误类型](../../../visual-basic/programming-guide/language-features/error-types.md)