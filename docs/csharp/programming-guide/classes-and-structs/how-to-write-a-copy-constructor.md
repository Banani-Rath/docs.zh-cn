---
title: "如何：编写复制构造函数（C# 编程指南） | Microsoft Docs"
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
  - "C# 语言, 复制构造函数"
  - "复制构造函数 [C#]"
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：编写复制构造函数（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

C\# 不会为对象提供复制构造函数，但是，您可以自己编写。  
  
## 示例  
 在下面的示例中，`Person` [类](../../../csharp/language-reference/keywords/class.md)定义采用 `Person` 实例作为其参数的复制构造函数。  将参数属性的值赋给 `Person` 新实例的属性。  代码包含一个备用复制构造函数，可以将想要复制的实例的 `Name` 和 `Age` 属性发送到选件类的实例构造函数中。  
  
 [!CODE [csProgGuideObjects#16](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideObjects#16)]  
  
## 请参阅  
 <xref:System.ICloneable>   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [类和结构](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [构造函数](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [析构函数](../../../csharp/programming-guide/classes-and-structs/destructors.md)