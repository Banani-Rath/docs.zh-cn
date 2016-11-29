---
title: "如何：声明、实例化和使用委托（C# 编程指南） | Microsoft Docs"
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
  - "委托 [C#], 声明和实例化"
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：声明、实例化和使用委托（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

在 C\# 1.0 及更高版本中，可以按以下示例所示声明委托。  
  
 [!CODE [csProgGuideDelegates#13](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#13)]  
  
 [!CODE [csProgGuideDelegates#14](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#14)]  
  
 C\# 2.0 提供了更简单的方法来编写上面的声明，如以下示例所示。  
  
 [!CODE [csProgGuideDelegates#32](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#32)]  
  
 在 C\# 2.0 及更高版本中，还可以使用匿名方法来声明和初始化[委托](../../../csharp/language-reference/keywords/delegate.md)，如以下示例所示。  
  
 [!CODE [csProgGuideDelegates#15](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#15)]  
  
 在 C\# 3.0 及更高版本中，还可以使用 Lambda 表达式来声明和实例化委托，如以下示例所示。  
  
 [!CODE [csProgGuideDelegates#31](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#31)]  
  
 有关更多信息，请参见 [Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)。  
  
 下面的示例阐释声明、实例化和使用委托。  `BookDB` 类封装一个书店数据库，它维护一个书籍数据库。  它公开 `ProcessPaperbackBooks` 方法，该方法在数据库中查找所有平装书，并对每本平装书调用一个委托。  使用的 `delegate` 类型名为 `ProcessBookDelegate`。  `Test` 类使用该类打印平装书的书名和平均价格。  
  
 委托的使用促进了书店数据库和客户代码之间功能的良好分隔。  客户代码不知道书籍的存储方式和书店代码查找平装书的方式。  书店代码也不知道找到平装书后将对平装书执行什么处理。  
  
## 示例  
 [!CODE [csProgGuideDelegates#12](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#12)]  
  
## 可靠编程  
  
-   声明委托。  
  
     下面的语句声明一个新的委托类型。  
  
     [!CODE [csProgGuideDelegates#16](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#16)]  
  
     每个委托类型都描述参数的数目和类型，以及它可以封装的方法的返回值类型。  每当需要一组新的参数类型或新的返回值类型时，都必须声明一个新的委托类型。  
  
-   实例化委托。  
  
     声明了委托类型后，必须创建委托对象并使之与特定方法关联。  在上一个示例中，您通过按下面示例中的方式将 `PrintTitle` 方法传递到 `ProcessPaperbackBooks` 方法来实现这一点：  
  
     [!CODE [csProgGuideDelegates#17](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#17)]  
  
     这将创建与[静态](../../../csharp/language-reference/keywords/static.md)方法 `Test.PrintTitle` 关联的新委托对象。  类似地，对象 `totaller` 的非静态方法 `AddBookToTotal` 是按下面示例中的方式传递的：  
  
     [!CODE [csProgGuideDelegates#18](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#18)]  
  
     在两个示例中，都向 `ProcessPaperbackBooks` 方法传递了一个新的委托对象。  
  
     委托创建后，它的关联方法就不能更改；委托对象是不可变的。  
  
-   调用委托。  
  
     创建委托对象后，通常将委托对象传递给将调用该委托的其他代码。  通过委托对象的名称（后面跟着要传递给委托的参数，括在括号内）调用委托对象。  下面是委托调用的示例：  
  
     [!CODE [csProgGuideDelegates#19](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideDelegates#19)]  
  
     与本例一样，可以通过使用 `BeginInvoke` 和 `EndInvoke` 方法同步或异步调用委托。  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [事件](../../../csharp/programming-guide/events/index.md)   
 [委托](../../../csharp/programming-guide/delegates/index.md)