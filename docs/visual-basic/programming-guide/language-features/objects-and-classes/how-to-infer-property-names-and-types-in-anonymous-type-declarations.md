---
title: "如何：推断匿名类型声明中的属性名和类型 (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "推理属性名称 [Visual Basic]"
  - "匿名类型 [Visual Basic], 推断属性名和类型"
  - "推理属性类型 [Visual Basic]"
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：推断匿名类型声明中的属性名和类型 (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

匿名类型不提供直接指定属性的数据类型的机制。 所有属性的类型都是推断出来的。 下面的示例从用于初始化属性的值，直接推断 `Name`和 `Price` 属性的类型。  
  
 [!CODE [VbVbalrAnonymousTypes#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#1)]  
  
 匿名类型还可以从其他来源推断属性名和类型。 以下各部分提供了可以进行推断的情况列表，以及不能进行推断的情况的示例。  
  
## 成功推理  
  
#### 匿名类型可以从以下来源推断属性名和类型：  
  
-   从变量名称。 匿名类型 `anonProduct` 将具有两个属性：`productName` 和 `productPrice`。 它们的数据类型将是原始变量的数据类型，分别为 `String` 和 `Double`。  
  
     [!CODE [VbVbalrAnonymousTypes#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#11)]  
  
-   从其他对象的属性或字段名称。 例如，考虑包含 `Name` 和 `ID` 属性的 `CarClass` 类型的 `car` 对象。 若要创建一个匿名类型实例 `car1`，并且其 `Name` 和 `ID` 属性使用 `car` 对象的值进行初始化，则可以编写下面的代码：  
  
     [!CODE [VbVbalrAnonymousTypes#34](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#34)]  
  
     以上声明等效于定义匿名类型 `car2` 的一行较长的代码。  
  
     [!CODE [VbVbalrAnonymousTypes#35](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#35)]  
  
-   从 XML 成员名称。  
  
     [!CODE [VbVbalrAnonymousTypes#12](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#12)]  
  
     为 `anon` 产生的类型将具有一个属性 `Book`，其类型为 <xref:System.Collections.IEnumerable>\(Of XElement\)。  
  
-   从没有参数的函数，例如下面示例中的 `SomeFunction`。  
  
     `Dim sc As New SomeClass`  
  
     `Dim anon1 = New With {Key sc.SomeFunction()}`  
  
     下面代码中的变量 `anon2` 是具有一个属性（一个名为 `First` 的字符）的匿名类型。 这段代码将显示函数 <xref:System.Linq.Enumerable.First%2A> 返回的字母“E”。  
  
     [!CODE [VbVbalrAnonymousTypes#13](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#13)]  
  
## 推理失败  
  
#### 名称推理在许多情况下将失败，包括：  
  
-   推理派生自对方法、构造函数或需要参数的参数化属性的调用。 如果 `someFunction` 具有一个或多个参数，则上面的 `anon1` 声明将失败。  
  
     `' Not valid.`  
  
     `' Dim anon3 = New With {Key sc.someFunction(someArg)}`  
  
     向新属性名赋值可以解决这一问题。  
  
     `' Valid.`  
  
     `Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}`  
  
-   推理派生自复杂表达式。  
  
    ```  
    Dim aString As String = "Act "  
    ' Not valid.  
    ' Dim label = New With {Key aString & "IV"}  
    ```  
  
     将表达式的结果赋给属性名可以消除此错误。  
  
     [!CODE [VbVbalrAnonymousTypes#14](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#14)]  
  
-   对多个属性的推理会产生两个或更多的同名属性。 回到前面示例中的声明，在那些声明中，不能将 `product.Name` 和 `car1.Name` 同时列为同一匿名类型的属性。 这是因为这些属性的推断标识符都是 `Name`。  
  
     `' Not valid.`  
  
     `' Dim anon5 = New With {Key product.Name, Key car1.Name}`  
  
     通过为不同属性名赋值可以解决此问题。  
  
     [!CODE [VbVbalrAnonymousTypes#36](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#36)]  
  
     请注意，更改大小写（在大写和小写字母之间切换）不能区分两个名称。  
  
     `Dim price = 0`  
  
     `' Not valid, because Price and price are the same name.`  
  
     `' Dim anon7 = New With {Key product.Price, Key price}`  
  
-   属性的初始类型和值取决于尚未建立的另一个属性。 例如，`.IDName = .LastName` 在匿名类型声明中无效，除非 `.LastName` 已经初始化。  
  
     `' Not valid.`  
  
     `' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}`  
  
     在此示例中，可以通过逆转声明属性的顺序来解决问题。  
  
     [!CODE [VbVbalrAnonymousTypes#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#15)]  
  
-   匿名类型的属性名和 <xref:System.Object> 的成员的名称相同。 例如，因为 `Equals` 是 <xref:System.Object> 的一个方法，所以下面的声明会失败。  
  
     `' Not valid.`  
  
     `' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _`  
  
     `'                       "greater than", Key .Less = "less than"}`  
  
     可以通过更改属性名来修复该问题：  
  
     [!CODE [VbVbalrAnonymousTypes#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes#16)]  
  
## 请参阅  
 [对象初始值设定项：命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)