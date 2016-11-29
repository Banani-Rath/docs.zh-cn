---
title: "重构和“重命名”对话框 (Visual Basic) | Microsoft Docs"
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
  - "vb.RenameSymbol"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "符号，重命名"
  - "名称，更改符号"
  - "“重命名”对话框"
ms.assetid: 001d2d81-9bb6-4e8e-ae3a-20c0daaa3959
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 重构和“重命名”对话框 (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

使用 Visual Basic 的内置**“重命名”**对话框可以重命名符号代码中的标识符，如字段、局部变量、方法、命名空间、属性和类型。  通过右击元素声明可以打开**“重命名”**对话框。  
  
 **新名称**  
 指定代码元素的新名称。  
  
 **位置**  
 标识在执行重命名操作时要搜索的命名空间。  
  
## 重命名操作  
 针对不同类型的重命名的元素，**“重命名”**对话框执行的重命名操作可能有所不同。  
  
|元素类型|重命名操作|  
|----------|-----------|  
|类|将类的所有声明和用法更改为新名称。  对于分部类，重命名操作将传播到所有部分。|  
|字段|将字段的声明和用法更改为新名称。|  
|局部变量|将变量的声明和用法更改为新名称。|  
|方法|将方法的名称和对该方法的所有引用更改为新名称。|  
|命名空间|将声明、所有 `Imports` 语句和所有完全限定名中的命名空间的名称更改为新名称。|  
|属性|将属性的声明和用法更改为新名称。|  
  
## 重构  
 为了提供完整的重构体验，Visual Basic 与 Developer Express Inc. 合作  以获取重构支持。  有关 MSDN Visual Basic 开发人员中心的详细信息以及如何下载该工具的说明，请参阅 [Refactor\!](http://go.microsoft.com/fwlink/?LinkId=155788)（重构！）。  重构！  支持 15 以上的各种重构功能，  其中包括重新排列参数、提取方法、封装字段及创建重载等操作。  
  
## 请参阅  
 [使用 Visual Basic 开发环境](../../../visual-basic/developing-apps/using-ide/using-the-visual-basic-development-environment.md)