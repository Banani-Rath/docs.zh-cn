---
title: "long（C# 参考） | Microsoft Docs"
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
  - "long_CSharpKeyword"
  - "long"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "long 关键字 [C#]"
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# long（C# 参考）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`long` 关键字表示一种整型，该类型根据下表显示的大小和范围存储值。  
  
|类型|范围|大小|.NET Framework 类型|  
|--------|--------|--------|-----------------------|  
|`long`|\-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807|有符号 64 位整数|<xref:System.Int64?displayProperty=fullName>|  
  
## 文本  
 可如下例所示声明并初始化 `long` 类型的变量：  
  
```  
  
long long1 = 4294967296;  
```  
  
 如果整数没有后缀，则其类型为以下类型中可表示其值的第一个类型：[int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、`long`、[ulong](../../../csharp/language-reference/keywords/ulong.md)。  在上例中，它是 `long` 类型，因为它超出了 [uint](../../../csharp/language-reference/keywords/uint.md) 的范围（有关整型的存储大小，请参见 [整型表](../../../csharp/language-reference/keywords/integral-types-table.md)）。  
  
 还可以像下面这样，在 `long` 类型中使用后缀 L：  
  
```  
  
long long2 = 4294967296L;  
```  
  
 当使用后缀 L 时，将根据整数的大小确定它的类型为 `long` 还是 [ulong](../../../csharp/language-reference/keywords/ulong.md)。  在此例中，它是 `long`，因为它小于 [ulong](../../../csharp/language-reference/keywords/ulong.md) 的范围的下限。  
  
 此后缀常用于调用重载方法。  以下面使用 `long` 和 [int](../../../csharp/language-reference/keywords/int.md) 参数的重载方法为例：  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 使用后缀 L 可保证调用正确的类型，例如：  
  
```  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5L);   // Calling the method with the long parameter  
```  
  
 可在同一个表达式中同时使用 `long` 类型和其他数值整型，这时表达式的计算结果为 `long`（在关系表达式或布尔表达式中为 [bool](../../../csharp/language-reference/keywords/bool.md)）类型。  例如，下列表达式计算为 `long`：  
  
```  
898L + 88  
```  
  
> [!NOTE]
>  也可用小写字母“l”作后缀。  但是，因为字母“l”容易与数字“1”混淆，会生成编译器警告。为清楚起见，请使用“L”。  
  
 有关兼用浮点型和整型的算术表达式的信息，请参见 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。  
  
## 转换  
 存在从 `long` 到 [float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。  其他情况下必须使用显式转换。  例如，不使用显式类型转换时，下列语句将产生编译错误：  
  
```  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 存在从 [sbyte](../../../csharp/language-reference/keywords/sbyte.md)、[byte](../../../csharp/language-reference/keywords/byte.md)、[short](../../../csharp/language-reference/keywords/short.md)、[ushort](../../../csharp/language-reference/keywords/ushort.md)、[int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md) 或 [char](../../../csharp/language-reference/keywords/char.md) 到 `long` 的预定义隐式转换。  
  
 还请注意，不存在从浮点型到 `long` 类型的隐式转换。  例如，除非使用显式强制转换，否则以下语句将生成一个编译器错误：  
  
```  
  
        long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## C\# 语言规范  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 请参阅  
 <xref:System.Int64>   
 [C\# 参考](../../../csharp/language-reference/index.md)   
 [C\# 编程指南](../../../csharp/programming-guide/index.md)   
 [C\# 关键字](../../../csharp/language-reference/keywords/index.md)   
 [整型表](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [显式数值转换表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)