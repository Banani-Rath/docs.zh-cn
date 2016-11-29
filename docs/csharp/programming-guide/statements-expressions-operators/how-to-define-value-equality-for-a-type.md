---
title: "如何：为类型定义值相等性（C# 编程指南） | Microsoft Docs"
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
  - "Equals 方法 [C#], 重写"
  - "等效性 [C#]"
  - "对象等效性 [C#]"
  - "重写 Equals 方法 [C#]"
  - "值相等性 [C#]"
ms.assetid: 4084581e-b931-498b-9534-cf7ef5b68690
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：为类型定义值相等性（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

在定义类或结构时，您将决定为类型创建值相等性（或等效性）的自定义定义是否有意义。  通常，当类型的对象预期要添加到某类集合时，或者当这些对象主要用于存储一组字段或属性时，您将实现值相等性。  您可以基于类型中所有字段和属性的比较来定义值相等性，也可以基于子集进行定义。  但在任何一种情况下，类和结构中的实现均应遵循五个等效性保证条件：  
  
1.  x.`Equals`\(x\) 返回 `true.` 。这称为自反属性。  
  
2.  x.`Equals`\(y\) 返回与 `Equals`\(x\) 相同的值。  这称为对称属性。  
  
3.  如果 \(x.`Equals`\(y\) && y.`Equals`\(z\)\) 返回 `true`，则 x.`Equals`\(z\) 返回 `true`。  这称为可传递属性。  
  
4.  只要不修改 x 和 y 所引用的对象，x.`Equals`\(y\) 的后续调用就返回相同的值。  
  
5.  x.`Equals`\(null\) 返回 `false`。  但是，null.Equals\(null\) 会引发异常；它不遵循上面的第二条规则。  
  
 您定义的任何结构已经具有它从 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> 方法的 <xref:System.ValueType?displayProperty=fullName> 重写中继承的默认值相等性实现。  此实现使用反射来检查类型中的所有公共和非公共字段以及属性。  尽管此实现可生成正确的结果，但与您专门为类型编写的自定义实现相比，它的速度相对较慢。  
  
 类和结构的值相等性的实现详细信息不同。  但是，类和结构都需要相同的基础步骤来实现相等性：  
  
1.  重写 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> [虚](../../../csharp/language-reference/keywords/virtual.md)方法。  大多数情况下，您的 `bool Equals( object obj )` 实现应只调入作为 <xref:System.IEquatable%601?displayProperty=fullName> 接口的实现的类型特定 `Equals` 方法。  （请参见步骤 2。）  
  
2.  通过提供类型特定的 `Equals` 方法实现 <xref:System.IEquatable%601?displayProperty=fullName> 接口。  实际的等效性比较将在此接口中执行。  例如，您可能决定通过仅比较类型中的一两个字段来定义相等性。  不要从 `Equals` 中引发异常。  仅适用于类：此方法应仅检查类中声明的字段。  它应调用 `base.Equals` 来检查基类中的字段。  （如果类型直接从 <xref:System.Object> 中继承，则不要这样做，因为 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> 的 <xref:System.Object> 实现会执行引用相等性检查。）  
  
3.  可选，但建议这样做：重载 [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) 和 [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md) 运算符。  
  
4.  重写 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>，使具有值相等性的两个对象生成相同的哈希代码。  
  
5.  可选：若要支持“大于”或“小于”定义，请为类型实现 <xref:System.IComparable%601> 接口，并同时重载 [\<\=](../../../csharp/language-reference/operators/less-than-equal-operator.md) 和 [\>\=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) 运算符。  
  
 下面的第一个示例演示了类实现。  第二个示例演示了结构实现。  
  
## 示例  
 下面的示例演示如何在类（引用类型）中实现值相等性。  
  
 [!CODE [csProgGuideStatements#19](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#19)]  
  
 在类（引用类型）上，两种 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> 方法的默认实现均执行引用相等性比较，而不是值相等性检查。  当实施者重写虚方法时，目的是为了为其指定值相等性语义。  
  
 即使类不重载 `==` 和 `!=` 运算符，也可以将这些运算符与类一起使用。  但是，默认行为是执行引用相等性检查。  在类中，如果您重载 `Equals` 方法，则应重载 `==` 和 `!=` 运算符，但这并不是必需的。  
  
## 示例  
 下面的示例演示如何在结构（值类型）中实现值相等性：  
  
 [!CODE [csProgGuideStatements#20](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideStatements#20)]  
  
 对于结构，<xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>（<xref:System.ValueType?displayProperty=fullName> 中的重写版本）的默认实现通过使用反射来比较类型中每个字段的值，从而执行值相等性检查。  当实施者重写结构中的 `Equals` 虚方法时，目的是为了提供更高效的方法来执行值相等性检查，并选择根据结构的字段或属性的某个子集来进行比较。  
  
 除非结构显式重载了 [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) 和 [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md) 运算符，否则这些运算符将无法对结构进行运算。  
  
## 请参阅  
 [相等比较](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)