---
title: "如何：将字节数组转换为 int（C# 编程指南） | Microsoft Docs"
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
  - "字节数组 [C#], 转换为 int"
  - "转换 [C#], 字节数组转换为 int"
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：将字节数组转换为 int（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

此示例演示如何使用 <xref:System.BitConverter> 类将字节数组转换为 [int](../../../csharp/language-reference/keywords/int.md) 并返回字节数组。  例如，在从网络读取字节之后，可能需要将字节转换为内置数据类型。  除了示例中的 [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False) 方法之外，下表列出了 <xref:System.BitConverter> 类中将字节（来自字节数组）转换为其他内置类型的方法。  
  
|返回类型|方法|  
|----------|--------|  
|`bool`|[ToBoolean\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToBoolean(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`char`|[ToChar\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToChar(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`double`|[ToDouble\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToDouble(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`short`|[ToInt16\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt16(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`int`|[ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`long`|[ToInt64\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt64(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`float`|[ToSingle\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToSingle(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`ushort`|[ToUInt16\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt16(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`uint`|[ToUInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`ulong`|[ToUInt64\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt64(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
  
## 示例  
 此示例实例化字节数组，并在计算机结构为 little\-endian 的情况下反转数组（即首先存储最低有效字节），然后调用 [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False) 方法以将数组中的四个字节转换为 `int`。  [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False) 的第二个参数指定字节数组的起始索引。  
  
> [!NOTE]
>  输出可能会根据计算机结构的 endian 设置而不同。  
  
 [!CODE [csProgGuideTypes#22](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#22)]  
  
## 示例  
 在此示例中，调用 <xref:System.BitConverter> 类的 <xref:System.BitConverter.GetBytes%28System.Int32%29> 方法以将 `int` 转换为字节数组。  
  
> [!NOTE]
>  输出可能会根据计算机结构的 endian 设置而不同。  
  
 [!CODE [csProgGuideTypes#23](../CodeSnippet/VS_Snippets_VBCSharp/CsProgGuideTypes#23)]  
  
## 请参阅  
 <xref:System.BitConverter>   
 <xref:System.BitConverter.IsLittleEndian>   
 [类型](../../../csharp/programming-guide/types/index.md)