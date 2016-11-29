---
title: "接口 (Visual Basic) | Microsoft Docs"
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
  - "接口"
  - "接口 [Visual Basic]"
  - "接口, Visual Basic"
  - "Visual Basic 代码, 接口"
ms.assetid: 61b06674-12c9-430b-be68-cc67ecee1f5b
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# 接口 (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*接口*定义类所能实现的属性、方法和事件。  接口允许将功能定义为一些紧密相关的属性、方法和事件的小组；这样就减少了兼容性问题，因为可以在不损害现有代码的情况下开发接口的增强型实现。  在任何时候都可以通过开发附加接口和实现来添加新的功能。  
  
 以下是为何要使用接口继承而不用类继承的一些其他原因：  
  
-   在应用程序要求很多可能不相关的对象类型以提供某种功能的情况下，接口的适用性更强。  
  
-   接口比基类更灵活，因为可以定义单个实现来实现多个接口。  
  
-   在无需从基类继承实现的情况下，接口更好。  
  
-   在无法使用类继承的情况下接口非常有用。  例如，结构无法从类继承，但它们可以实现接口。  
  
## 声明接口  
 接口定义包含在 `Interface` 和 `End Interface` 语句内。  在 `Interface` 语句后面，可以选择添加列出一个或多个继承的接口的 `Inherits` 语句。  在声明中，`Inherits` 语句必须出现在除注释外的所有其他语句之前。  接口定义中其余的语句应该包括 `Event`、`Sub`、`Function`、`Property`、`Interface`、`Class`、`Structure` 和 `Enum` 语句。  接口不能包含任何实现代码或与实现代码关联的语句，如 `End Sub` 或 `End Property`。  
  
 在命名空间中，接口语句默认为 `Friend`，但也可以显式声明为 `Public` 或 `Friend`。  在类、模块、接口和结构中定义的接口默认为 `Public`，但也可以显式声明为 `Public`、`Friend`、`Protected` 或 `Private`。  
  
> [!NOTE]
>  `Shadows` 关键字可应用于所有界面成员。  `Overloads` 关键字可应用于界面定义中声明的 `Sub`、`Function` 和 `Property` 语句。  此外，`Property` 语句可以具有 `Default`、`ReadOnly` 或 `WriteOnly` 修饰符。  不允许使用任何其他修饰符：`Public`、`Private`、`Friend`、`Protected`、`Shared`、`Overrides`、`MustOverride` 或 `Overridable`。  有关详细信息，请参阅[声明上下文和默认访问级别](../../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。  
  
 例如，下面的代码定义了一个函数、一个属性和一个事件的接口。  
  
 [!CODE [VbVbalrOOP#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#17)]  
  
## 实现接口  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 保留字 `Implements` 有两种使用方式。  `Implements` 语句表示类或结构实现接口。  `Implements` 关键字表示类成员或结构成员实现特定的接口成员。  
  
### Implements 语句  
 如果一个类或结构实现一个或多个接口，则它必须紧随在 `Class` 或 `Structure` 语句之后包括 `Implements` 语句。  `Implements` 语句需要一个由类实现的接口的逗号分隔列表。  类或结构必须使用 `Implements` 关键字来实现所有的接口成员。  
  
### Implements 关键字  
 `Implements` 关键字需要一个要实现的接口成员的逗号分隔列表。  通常只指定单个接口成员，但也可以指定多个成员。  接口成员的规范由接口名称（必须在类中的 implements 语句中指定）、句点和要实现的成员函数、属性或事件的名称组成。  实现接口成员的成员名称可使用任何合法标识符，不受早期 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 版本中使用的 `InterfaceName_MethodName` 约定的限制。  
  
 例如，以下代码显示了如何声明一个名为 `Sub1` 的用于实现接口方法的子例程：  
  
 [!CODE [VbVbalrOOP#69](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#69)]  
  
 实现成员的参数类型和返回类型必须与接口属性或接口中的成员声明匹配。  实现接口元素的最常用方法是采用一个与接口同名的成员，如上述示例所示。  
  
 要声明接口方法的实现，可以使用任何在实例方法声明上合法的特性（包括 `Overloads`、`Overrides`、`Overridable`、`Public`、`Private`、`Protected`、`Friend`、`Protected Friend`、`MustOverride`、`Default` 和 `Static`）。  `Shared` 特性是不合法的，因为它定义类而不是实例方法。  
  
 使用 `Implements`，你还可以编写单个方法来实现接口中定义的多个方法，如下面的示例所示：  
  
 [!CODE [VbVbalrOOP#70](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#70)]  
  
 可以使用私有成员来实现接口成员。  在私有成员实现一个接口成员时，即使在类的对象变量上不能直接使用该成员，仍然可以通过接口将其变为可用成员。  
  
### 接口实现示例  
 实现接口的类必须实现其所有属性、方法和事件。  
  
 下面的示例定义了两个接口。  第二个接口 `Interface2` 继承 `Interface1` 并定义附加属性和方法。  
  
 [!CODE [VbVbalrOOP#39](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#39)]  
  
 下一个示例则实现在上一示例中定义的接口 `Interface1`：  
  
 [!CODE [VbVbalrOOP#40](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#40)]  
  
 最后一个示例实现 `Interface2`，包括继承自 `Interface1` 的方法：  
  
 [!CODE [VbVbalrOOP#41](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOOP#41)]  
  
 可以使用 readwrite 属性实现 readonly 属性（也就是说，无需在实现类中将其声明为 readonly）。  实现接口承诺至少实现接口声明的成员，但你还可以提供更多功能，如允许对属性进行编写。  
  
## 相关主题  
  
|标题|说明|  
|--------|--------|  
|[演练：创建和实现接口](../../../../visual-basic/programming-guide/language-features/interfaces/walkthrough-creating-and-implementing-interfaces.md)|提供引导你定义和实现自己的接口的详细过程。|  
|[泛型接口中的变体](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)|讨论泛型接口中的协变和逆变，提供 .NET Framework 中的变体泛型接口列表。|