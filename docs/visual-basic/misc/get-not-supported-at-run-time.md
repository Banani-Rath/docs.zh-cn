---
title: "运行时不支持 Get 语句 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID393"
ms.assetid: b527c5a8-3f24-42e9-871f-e6305c9f514b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 运行时不支持 Get 语句
你试图在运行时读取仅在设计时才可访问的属性。  
  
### 更正此错误  
  
1.  检查该属性并确定可以在什么情况下对其进行设置。  
  
2.  删除对该属性的引用。  
  
## 请参阅  
 [NIB 如何：修改项目属性和配置设置](http://msdn.microsoft.com/zh-cn/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)