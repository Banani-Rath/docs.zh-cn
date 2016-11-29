---
title: "private（C# 参考） | Microsoft Docs"
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
  - "private_CSharpKeyword"
  - "private"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "private 关键字 [C#]"
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# private（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`private` 关键字是一个成员访问修饰符。  私有访问是允许的最低访问级别。  私有成员只有在声明它们的类和结构体中才是可访问的，如下例所示：  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  
  
 同一体中的嵌套类型也可以访问那些私有成员。  
  
 在定义私有成员的类或结构外引用它会导致编译时错误。  
  
 有关 `private` 与其他访问修饰符的比较，请参见[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)和[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。  
  
## 示例  
 在此示例中，`Employee` 类包含两个私有数据成员 `name` 和 `salary`。  作为私有成员，它们只能通过成员方法来访问。  添加名为 `GetName` 和 `Salary` 的公共方法，以便可以对私有成员进行受控的访问。  通过公共方法访问 `name` 成员，而通过公共只读属性访问`salary` 成员。  （有关更多信息，请参见 [属性](../../../csharp/programming-guide/classes-and-structs/properties.md)。）  
  
 [!CODE [csrefKeywordsModifiers#10](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsModifiers#10)]  
  
## C\# 语言规范  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 请参阅  
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [C\# 关键字](../../../csharp/language-reference/keywords/index.md)   
 [访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [修饰符](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [内部](../../../csharp/language-reference/keywords/internal.md)