---
title: "NULL 条件运算符（C# 和 Visual Basic） | Microsoft Docs"
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
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
caps.handback.revision: 3
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# NULL 条件运算符（C# 和 Visual Basic）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

用于在执行成员访问 \(`?.`\) 或索引 \(`?[`\) 操作之前，测试是否存在 NULL。  这些运算符可帮助编写更少的代码来处理 null 检查，尤其是对于下降到数据结构。  
  
```c#  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
  
```  
  
```vb  
Dim length = customers?.Length  ‘’ null if customers is null  
Dim first as Customer = customers?(0);  ‘’ null if customers is null  
Dim count as Integer? = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
  
```  
  
 最后一个示例演示 NULL 条件运算符会短路。  如果条件成员访问和索引操作链中的某个操作返回 NULL，则该链其余部分的执行将停止。  表达式中优先级较低的其他操作将继续。  例如，以下的示例中的 `E` 将始终执行，`??` 和 `==` 操作将执行。  
  
```vb-c#  
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
  
```  
  
 NULL 条件成员访问的另一个用途是使用非常少的代码以线程安全的方式调用委托。  旧方法需要如下所示的代码：  
  
```c#  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…)  
  
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
  
```  
  
 新的方法是要简单得多：  
  
```vb-c#  
PropertyChanged?.Invoke(e)  
  
```  
  
 新方法是线程安全的，因为编译器生成代码以评估 `PropertyChanged`（仅一次），从而使结果保持在临时变量中。  
  
 你需要显式调用 `Invoke` 方法，因为不存在 NULL 条件委托调用语法 `PropertyChanged?(e)`。  有太多不明确的分析情况来允许它。  
  
## 语言规范  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
 有关详细信息，请参阅 [Visual Basic 语言参考](../../../visual-basic/language-reference/index.md)。  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [Visual Basic 语言参考](../../../visual-basic/language-reference/index.md)   
 [Visual Basic 编程指南](../../../visual-basic/programming-guide/index.md)