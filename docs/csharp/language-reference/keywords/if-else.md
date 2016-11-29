---
title: "if-else（C# 参考） | Microsoft Docs"
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
  - "if_CSharpKeyword"
  - "else"
  - "else_CSharpKeyword"
  - "if"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "else 关键字 [C#]"
  - "if 关键字 [C#]"
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
caps.latest.revision: 32
caps.handback.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# if-else（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`if` 语句基于 `Boolean` 表达式的值来识别运行哪个语句。 在下面的示例中，`Boolean` 变量 `result` 已被设置为 `true`，然后被签入到了 `if` 语句。 输出为 `The condition is true`。  
  
 [!CODE [csrefKeywordsSelection#1](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#1)]  
  
 你可以通过将本主题中的示例放入控制台应用的 `Main` 方法中来运行它们。  
  
 C\# 中的 `if` 语句可以采用两种形式，如以下示例所示。  
  
```c#  
  
// if-else statement if (condition) { then-statement; } else { else-statement; } // Next statement in the program. // if statement without an else if (condition) { then-statement; } // Next statement in the program.  
```  
  
 在 `if-else` 语句中，如果 `condition` 计算结果为 true，则 `then-statement` 将运行。 如果 `condition` 为 false，则 `else-statement` 将运行。 由于 `condition` 不能同时为 true 和 false，因此，`if-else` 语句的 `then-statement` 和 `else-statement` 永远不能同时运行。`then-statement` 或 `else-statement` 运行后，控件将转移到 `if` 语句之后的下一个语句。  
  
 在不包括 `else` 语句的 `if` 语句中，如果 `condition` 为 true，则 `then-statement` 将运行。 如果 `condition` 为 false，则控件将转移到 `if` 语句之后的下一个语句。  
  
 `then-statement` 和 `else-statement` 都可由单个语句或包含在括号中 \(`{}`\) 的多个语句组成。 对于单个语句，括号是可选的，但建议选择。  
  
 `then-statement` 和 `else-statement` 中的语句可为任何类型，包括嵌套在原始 `if` 语句中的另一个 `if` 语句。 在嵌套的 `if` 语句中，每个 `else` 子句都属于上一个无相应 `else` 的 `if`。 在下面的示例中，如果 `m > 10` 和 `n > 20` 计算结果都为 true，则将显示 `Result1`。 如果 `m > 10` 为 true 但 `n > 20` 为 false，则将显示 `Result2`。  
  
 [!CODE [csrefKeywordsSelection#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#2)]  
  
 相反，如果你希望在 `(m > 10)` 为 false 的时候显示 `Result2`，则可以通过使用括号来指定此关联，以建立嵌套的 `if` 语句的开头和结尾，如以下示例所示。  
  
 [!CODE [csrefKeywordsSelection#3](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#3)]  
  
 如果条件 `(m > 10)` 计算结果为 false，则将显示 `Result2`。  
  
## 示例  
 在下例中，当通过键盘输入字符时，该程序将使用嵌套的 `if` 语句来确定输入的字符是否为字母字符。 如果输入的字符是字母字符，则程序将检查输入的字符是大写还是小写。 每种情况都会显示一条消息。  
  
 [!CODE [csrefKeywordsSelection#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#4)]  
  
## 示例  
 你也可以将 `if` 语句嵌套到 else 块中，如以下部分代码所示。 示例将 `if` 语句嵌套在两个 else 块和一个 then 块中。 注释指定每个块中哪些条件为 true 哪些条件为 false。  
  
 [!CODE [csrefKeywordsSelection#5](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#5)]  
  
## 示例  
 下面的示例确定了输入的字符是一个小写字母，还是大写字母，还是一个数字。 如果所有三个条件都为 false，该字符不是字母数字字符。 此示例显示了每种情况的消息内容。  
  
 [!CODE [csrefKeywordsSelection#6](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsSelection#6)]  
  
 正如 else 块或 then 块中的语句可以是任何有效的语句一样，你可以将任何有效的布尔表达式用于此条件。 你可以使用类似 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md)、[&](../../../csharp/language-reference/operators/and-operator.md)、[&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)、[&#124;](../../../csharp/language-reference/operators/or-operator.md) 和 [\!](../../../csharp/language-reference/operators/logical-negation-operator.md) 的逻辑运算符来创建符合条件。 下面的代码演示了示例。  
  
```c#  
// NOT bool result = true; if (!result) { Console.WriteLine("The condition is true (result is false)."); } else { Console.WriteLine("The condition is false (result is true)."); } // Short-circuit AND int m = 9; int n = 7; int p = 5; if (m >= n && m >= p) { Console.WriteLine("Nothing is larger than m."); } // AND and NOT if (m >= n && !(p > m)) { Console.WriteLine("Nothing is larger than m."); } // Short-circuit OR if (m > n || m > p) { Console.WriteLine("m isn't the smallest."); } // NOT and OR m = 4; if (!(m >= n || m >= p)) { Console.WriteLine("Now m is the smallest."); } // Output: // The condition is false (result is true). // Nothing is larger than m. // Nothing is larger than m. // m isn't the smallest. // Now m is the smallest.  
```  
  
## C\# 语言规范  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [C\# 关键字](../../../csharp/language-reference/keywords/index.md)   
 [?: 运算符](../../../csharp/language-reference/operators/conditional-operator.md)   
 [if\-else 语句 \(C\+\+\)](/visual-cpp/cpp/if-else-statement-cpp)   
 [switch](../../../csharp/language-reference/keywords/switch.md)