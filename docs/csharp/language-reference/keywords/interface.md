---
title: "接口（C# 参考） | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "interface_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "接口关键字 [C#]"
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: 29
caps.handback.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 接口（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

接口只包含[方法](../../../csharp/programming-guide/classes-and-structs/methods.md)、[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)、[事件](../../../csharp/programming-guide/events/index.md)或[索引器](../../../csharp/programming-guide/indexers/index.md)的签名。  实现接口的类或结构必须实现接口定义中指定的接口成员。  在下面的示例，类 `ImplementationClass` 必须实现一个不具有参数并返回 `void` 的名为 `SampleMethod` 的方法。  
  
 有关更多信息和示例，请参见[接口](../../../csharp/programming-guide/interfaces/index.md)。  
  
## 示例  
 [!CODE [csrefKeywordsTypes#14](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsTypes#14)]  
  
 接口可以是命名空间或类的成员，并且可以包含下列成员的签名：  
  
-   [方法](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [属性](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [索引器](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [事件](../../../csharp/language-reference/keywords/event.md)  
  
 一个接口可从一个或多个基接口继承。  
  
 当基类型列表包含基类和接口时，基类必须是列表中的第一项。  
  
 实现接口的类可以显式实现该接口的成员。  显式实现的成员不能通过类实例访问，而只能通过接口实例访问。  
  
 有关显式接口实现的更多详细信息和代码示例，请参见[显式接口实现](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)。  
  
## 示例  
 下面的示例演示了接口实现。  在此示例中，接口包含属性声明，类包含实现。  实现 `IPoint` 的类的任何实例都具有整数属性 `x` 和 `y`。  
  
 [!CODE [csrefKeywordsTypes#15](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsTypes#15)]  
  
## C\# 语言规范  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [C\# 关键字](../../../csharp/language-reference/keywords/index.md)   
 [引用类型](../../../csharp/language-reference/keywords/reference-types.md)   
 [接口](../../../csharp/programming-guide/interfaces/index.md)   
 [使用属性](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [使用索引器](../../../csharp/programming-guide/indexers/using-indexers.md)   
 [类](../../../csharp/language-reference/keywords/class.md)   
 [struct](../../../csharp/language-reference/keywords/struct.md)   
 [接口](../../../csharp/programming-guide/interfaces/index.md)