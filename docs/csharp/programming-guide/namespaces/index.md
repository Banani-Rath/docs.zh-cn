---
title: "命名空间（C# 编程指南） | Microsoft Docs"
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
  - "C# 语言, 命名空间"
  - "命名空间 [C#]"
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 命名空间（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

使用 C\# 编程时，通过两种方式来大量使用命名空间。  首先，.NET Framework 使用命名空间来组织它的众多类，如下所示：  
  
 [!CODE [csProgGuide#22](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuide#22)]  
  
 `System` 是一个命名空间，`Console` 是该命名空间中的类。  可以使用 `using` 关键字，因此不必使用完整的名称，如以下示例所示：  
  
 [!CODE [csProgGuide#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuide#1)]  
  
 [!CODE [csProgGuide#25](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuide#25)]  
  
 有关更多信息，请参见 [using 指令](../../../csharp/language-reference/keywords/using-directive.md)。  
  
 其次，在较大的编程项目中，声明自己的命名空间可以帮助控制类名称和方法名称的范围。  使用 [namespace](../../../csharp/language-reference/keywords/namespace.md) 关键字可声明命名空间，如下例所示：  
  
 [!CODE [csProgGuideNamespaces#6](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#6)]  
  
## 命名空间概述  
 命名空间具有以下属性：  
  
-   组织大型代码项目。  
  
-   使用 `.` 运算符将它们分隔。  
  
-   `using directive` 不必为每个类指定命名空间的名称。  
  
-   `global` 命名空间是“根”命名空间：`global::System` 始终引用 .NET Framework 命名空间 `System`。  
  
## 相关章节  
 有关命名空间的更多信息，请参见下列主题：  
  
-   [使用命名空间](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [如何：使用全局命名空间别名](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [如何：使用 My 命名空间](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## C\# 语言规范  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [命名空间关键字](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [using 指令](../../../csharp/language-reference/keywords/using-directive.md)   
 [:: 运算符](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [. 运算符](../../../csharp/language-reference/operators/member-access-operator.md)