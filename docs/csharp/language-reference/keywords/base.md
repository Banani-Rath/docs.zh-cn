---
title: "base（C# 参考） | Microsoft Docs"
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
  - "base"
  - "BaseClass.BaseClass"
  - "base_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "base 关键字 [C#]"
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# base（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`base` 关键字用于从派生类中访问基类的成员：  
  
-   调用基类上已被其他方法重写的方法。  
  
-   指定创建派生类实例时应调用的基类构造函数。  
  
 基类访问只能在构造函数、实例方法或实例属性访问器中进行。  
  
 从静态方法中使用 `base` 关键字是错误的。  
  
 所访问的基类是类声明中指定的基类。  例如，如果指定 `class ClassB : ClassA`，则无论 ClassA 的基类如何，从 ClassB 上访问 ClassA 的成员。  
  
## 示例  
 在本例中，基类 `Person` 和派生类 `Employee` 都有一个名为 `Getinfo` 的方法。  通过使用 `base` 关键字，可以从派生类中调用基类的 `Getinfo` 方法。  
  
 [!CODE [csrefKeywordsAccess#1](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsAccess#1)]  
  
 有关其他示例，请参见 [new](../../../csharp/language-reference/keywords/new.md)、[virtual](../../../csharp/language-reference/keywords/virtual.md) 和 [override](../../../csharp/language-reference/keywords/override.md)。  
  
## 示例  
 本示例显示如何指定在创建派生类实例时调用的基类构造函数。  
  
 [!CODE [csrefKeywordsAccess#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsAccess#2)]  
  
## C\# 语言规范  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [C\# 关键字](../../../csharp/language-reference/keywords/index.md)   
 [this](../../../csharp/language-reference/keywords/this.md)