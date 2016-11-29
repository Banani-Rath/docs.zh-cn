---
title: "如何：使用全局命名空间别名（C# 编程指南） | Microsoft Docs"
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
  - "别名 [C#]"
  - "全局命名空间 [C#]"
  - "命名空间 [C#], 全局命名空间限定符"
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：使用全局命名空间别名（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

当成员可能被同名的其他实体隐藏时，能够访问全局[命名空间](../../../csharp/language-reference/keywords/namespace.md)中的成员非常有用。  
  
 例如，在下面的代码中，`Console` 在 <xref:System> 命名空间中解析为 `TestApp.Console` 而不是 `Console` 类型。  
  
 [!CODE [csProgGuide#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuide#1)]  
  
 [!CODE [csProgGuideNamespaces#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#1)]  
  
 由于类 `TestApp.System` 隐藏了 `System` 命名空间，因此使用 `System.Console` 仍然会导致错误：  
  
 [!CODE [csProgGuideNamespaces#2](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#2)]  
  
 但是，可以通过使用 `global::System.Console` 避免这一错误，如下所示：  
  
 [!CODE [csProgGuideNamespaces#3](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#3)]  
  
 当左侧的标识符为 `global` 时，对右侧标识符的搜索将从全局命名空间开始。  例如，下面的声明将 `TestApp` 作为全局空间的一个成员进行引用。  
  
 [!CODE [csProgGuideNamespaces#4](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#4)]  
  
 显然，并不推荐创建自己的名为 `System` 的命名空间，您不可能遇到出现此情况的任何代码。  但是，在较大的项目中，很有可能在一个窗体或其他窗体中出现命名空间重复。  在这种情况下，全局命名空间限定符可保证您可以指定根命名空间。  
  
## 示例  
 在此示例中，命名空间 `System` 用于包括类 `TestClass`，因此必须使用 `global::System.Console` 来引用 `System.Console` 类，该类被 `System` 命名空间隐藏。  而且，别名 `colAlias` 用于引用命名空间 `System.Collections`；因此，将使用此别名而不是命名空间来创建 <xref:System.Collections.Hashtable?displayProperty=fullName> 的实例。  
  
 [!CODE [csProgGuideNamespaces#5](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideNamespaces#5)]  
  
  **A 1**  
**B 2**  
**C 3**   
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [命名空间](../../../csharp/programming-guide/namespaces/index.md)   
 [. 运算符](../../../csharp/language-reference/operators/member-access-operator.md)   
 [:: 运算符](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)