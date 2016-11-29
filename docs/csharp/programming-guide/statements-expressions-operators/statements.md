---
title: "语句（C# 编程指南） | Microsoft Docs"
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
  - "C# 语言, 语句"
  - "语句 [C#], 关于语句"
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
caps.latest.revision: 28
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 语句（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

程序所执行的操作以“语句”表达。  常见操作包括声明变量、赋值、调用方法、循环访问集合，以及根据给定条件分支到一个或另一个代码块。  语句在程序中的执行顺序称为“控制流”或“执行流”。  根据程序对运行时所收到的输入的响应，在程序每次运行时控制流可能有所不同。  
  
 语句可以是以分号结尾的单行代码，或者是语句块中的一系列单行语句。  语句块括在括号 {} 中，并且可以包含嵌套块。  下面的代码演示两个单行语句示例和一个多行语句块：  
  
 [!CODE [csProgGuideStatements#1](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#1)]  
  
## 语句的类型  
 下表列出 C\# 中的各种语句类型及其关联的关键字，并提供指向包含更多信息的主题的链接：  
  
|类别|C\# 关键字\/说明|  
|--------|-----------------|  
|声明语句|声明语句引入新的变量或常量。  变量声明可以选择为变量赋值。  在常量声明中必须赋值。<br /><br /> [!CODE [csProgGuideStatements#23](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#23)]|  
|表达式语句|用于计算值的表达式语句必须在变量中存储该值。<br /><br /> [!CODE [csProgGuideStatements#24](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#24)]|  
|[选择语句](../../../csharp/language-reference/keywords/selection-statements.md)|选择语句用于根据一个或多个指定条件分支到不同的代码段。  有关更多信息，请参见下列主题：<br /><br /> [if](../../../csharp/language-reference/keywords/if-else.md), [else](../../../csharp/language-reference/keywords/if-else.md), [switch](../../../csharp/language-reference/keywords/switch.md), [case](../../../csharp/language-reference/keywords/switch.md)|  
|[迭代语句](../../../csharp/language-reference/keywords/iteration-statements.md)|迭代语句用于遍历集合（如数组），或重复执行同一组语句直到满足指定的条件。  有关更多信息，请参见下列主题：<br /><br /> [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), [foreach](../../../csharp/language-reference/keywords/foreach-in.md), [in](../../../csharp/language-reference/keywords/foreach-in.md), [while](../../../csharp/language-reference/keywords/while.md)|  
|[跳转语句](../../../csharp/language-reference/keywords/jump-statements.md)|跳转语句将控制转移给另一代码段。  有关更多信息，请参见下列主题：<br /><br /> [break](../../../csharp/language-reference/keywords/break.md), [continue](../../../csharp/language-reference/keywords/continue.md), [default](../../../csharp/language-reference/keywords/switch.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md)，[yield](../../../csharp/language-reference/keywords/yield.md)|  
|[异常处理语句](../../../csharp/language-reference/keywords/exception-handling-statements.md)|异常处理语句用于从运行时发生的异常情况正常恢复。  有关更多信息，请参见下列主题：<br /><br /> [throw](../../../csharp/language-reference/keywords/throw.md), [try\-catch](../../../csharp/language-reference/keywords/try-catch.md), [try\-finally](../../../csharp/language-reference/keywords/try-finally.md), [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)|  
|[检查和未检查](../../../csharp/language-reference/keywords/checked-and-unchecked.md)|检查和未检查语句用于指定当将结果存储在变量中、但该变量过小而不能容纳结果值时，是否允许数值运算导致溢出。  有关更多信息，请参见[检查](../../../csharp/language-reference/keywords/checked.md)和[未检查](../../../csharp/language-reference/keywords/unchecked.md)。|  
|`await` 语句|如果标记与 [异步](../../../csharp/language-reference/keywords/async.md) 修饰符的方法，在方法可以使用 [等待](../../../csharp/language-reference/keywords/await.md) 运算符。  当控件移到在异步方法中的一个 `await` 表达式，控件回调用方，因此，在方法的进度挂起，直到等待任务完成。  当任务完成后，执行在方法可以恢复。<br /><br /> 有关简单示例，请参见 [方法](../../../csharp/programming-guide/classes-and-structs/methods.md)“Async "方法”一节。  有关更多信息，请参见[使用 Async 和 Await 的异步编程](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)。|  
|`yield return` 语句|迭代器对集合的自定义迭代，如列表或数组。  迭代器使用 [将返回](../../../csharp/language-reference/keywords/yield.md) 语句返回每个元素一个节点。  当 `yield return` 语句时，代码的当前位置确保。  迭代器，当下次时，调用执行从该位置进行重新启动。<br /><br /> 有关更多信息，请参见[迭代器](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)。|  
|`fixed` 语句|Fixed 语句禁止垃圾回收器重定位可移动的变量。  有关更多信息，请参见 [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)。|  
|`lock` 语句|lock 语句用于限制一次仅允许一个线程访问代码块。  有关更多信息，请参见 [lock](../../../csharp/language-reference/keywords/lock-statement.md)。|  
|标记语句|可以为语句指定一个标记，然后使用 [goto](../../../csharp/language-reference/keywords/goto.md) 关键字跳转到该标记语句。  （参见下一行中的示例。）|  
|空语句|空语句只含一个分号。  空语句不执行任何操作，可以在需要语句但不需要执行任何操作的地方使用。  下面的示例演示空语句的两种用法：<br /><br /> [!CODE [csProgGuideStatements#25](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#25)]|  
  
## 嵌入语句  
 一些语句（例如 [do](../../../csharp/language-reference/keywords/do.md)、[while](../../../csharp/language-reference/keywords/while.md)、[for](../../../csharp/language-reference/keywords/for.md) 和 [foreach](../../../csharp/language-reference/keywords/foreach-in.md)）后面始终跟有一条嵌入语句。  此嵌入语句可以是单个语句，也可以是语句块中括在括号 {} 内的多个语句。  甚至可以在括号 {} 内包含单行嵌入语句，如下面的示例所示：  
  
 [!CODE [csProgGuideStatements#26](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#26)]  
  
 未括在括号 {} 内的嵌入语句不能作为声明语句或标记语句。  下面的示例演示了这种情况：  
  
 [!CODE [csProgGuideStatements#27](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#27)]  
  
 将该嵌入语句放在语句块中以修复错误：  
  
 [!CODE [csProgGuideStatements#28](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#28)]  
  
## 嵌套语句块  
 语句块可以嵌套，如以下代码所示：  
  
 [!CODE [csProgGuideStatements#29](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#29)]  
  
## 无法访问的语句  
 如果编译器认为在任何情况下控制流都无法到达特定语句，将生成警告 CS0162，如下面的示例所示：  
  
 [!CODE [csProgGuideStatements#22](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#22)]  
  
## 相关章节  
  
-   [语句关键字](../../../csharp/language-reference/keywords/statement-keywords.md)  
  
-   [表达式](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
-   [运算符](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
## C\# 语言规范  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 请参阅  
 [C\# 编程指南](../../../csharp/programming-guide/index.md)