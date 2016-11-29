---
title: "可选参数 &lt;参数名&gt; 的可选值的类型不符合 CLS | Microsoft Docs"
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
  - "BC40042"
  - "vbc40042"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40042"
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 可选参数 &lt;参数名&gt; 的可选值的类型不符合 CLS
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

过程标记为 `<CLSCompliant(True)>`，但所声明的 [Optional](../../../visual-basic/language-reference/modifiers/optional.md) 参数的默认值属于不符合 CLS 的类型。  
  
 为使过程符合 [语言独立性和与语言无关的组件](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\)，它必须只使用符合 CLS 的类型。  这一点适用于参数类型、返回类型及其所有局部变量的类型。  它也适用于可选参数的默认值。  
  
 以下 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 数据类型不符合 CLS：  
  
-   [SByte 数据类型](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger 数据类型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Ulong 数据类型](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Ushort 数据类型](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 将 <xref:System.CLSCompliantAttribute> 特性应用于编程元素时，将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合。  此参数没有默认值，您必须提供一个值。  
  
 如果没有将 <xref:System.CLSCompliantAttribute> 应用于某个元素，则认为该元素是不符合的。  
  
 默认情况下，此消息是一个警告。  有关隐藏警告或将警告视为错误的信息，请参见 [在 Visual Basic 中配置警告](/visual-studio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID：**BC40042  
  
### 更正此错误  
  
-   如果可选参数必须具有这一特定类型的默认值，则移除 <xref:System.CLSCompliantAttribute>。  该过程无法符合 CLS。  
  
-   如果该过程必须符合 CLS，则将这一默认值的类型更改为最相似且符合 CLS 的类型。  例如，如果不需要 2,147,483,647 以上的数值范围，您可以使用 `Integer` 替换 `UInteger`。  如果您确实需要扩展的范围，可以将 `UInteger` 替换为 `Long`。  
  
-   如果您针对的是自动化对象或 COM 对象，请记住，某些类型具有与 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 中不同的数据宽度。  例如，`int` 在其他环境中经常是 16 位。  如果您接受来自此类组件中的 16 位整数，则在您所管理的 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 代码中将其声明为 `Short` 而不是 `Integer`。  
  
## 请参阅  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/zh-cn/4c705105-69a2-4e5e-b24e-0633bc32c7f3)