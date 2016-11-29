---
title: "Visual Basic 编码约定 | Microsoft Docs"
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
  - "编码约定, Visual Basic"
  - "示例 [Visual Basic], 编码约定"
  - "Visual Basic 代码, 约定"
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: 48
caps.handback.revision: 48
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
translationtype: Human Translation
---
# Visual Basic 编码约定
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Microsoft 开发的示例和文档符合本主题中的准则。  如果您遵循相同的编码约定，您可能会得到以下好处：  
  
-   代码将具有一致的外观，以便读者可以更多地关注内容而非布局。  
  
-   读者能够根据以前的经验作出假设，从而更加快速地理解代码。  
  
-   您可以更轻松地复制、更改和维护代码。  
  
-   您可以帮助确保您的代码演示的是 Visual Basic 的“最佳实践”。  
  
## 命名约定  
  
-   有关命名指南的信息，请参见 [命名准则](../Topic/Naming%20Guidelines.md) 主题。  
  
-   请不要在变量名中使用“My”或“my”。  此做法会与 `My` 对象混淆。  
  
-   您无需更改自动生成代码中的对象的名称，就可以让它们符合指南。  
  
## 布局约定  
  
-   插入制表符作为空格，并使用四空格缩进的智能缩进。  
  
-   使用“整齐排列代码（重新格式化）”在代码编辑器中重新设置代码的格式。  有关详细信息，请参阅 [选项，文本编辑器，基本 \(Visual Basic\)](/visual-studio/ide/reference/options-text-editor-basic-visual-basic)。  
  
-   每行仅使用一个语句。  不要使用 Visual Basic 行分隔符 \(:\)。  
  
-   在语言允许的情况下，避免使用显式行继续符“\_”，而应使用隐式行继续符。  
  
-   每行仅使用一个声明。  
  
-   如果“整齐排列代码（重新格式化）”未自动格式化继续行，则手动将继续行缩进一个制表位。  但是，始终左对齐列表中的项。  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   在方法和属性定义之间添加至少一个空白行。  
  
## 注释约定  
  
-   将注释放到另一行，而不要放在代码行的末尾。  
  
-   以大写字母开始注释文本，并以句点结束注释文本。  
  
-   在注释分隔符 \('\) 和注释文本之间插入一个空格。  
  
     [!CODE [VbVbalrGuidelines#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#2)]  
  
-   请勿将已设置格式的星号块环绕在注释周围。  
  
## 程序结构  
  
-   在使用 `Main` 方法时，对新的控制台应用程序使用默认结构，对命令行参数使用 `My`。  
  
     [!CODE [VbVbalrGuidelines#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#3)]  
  
## 语言指南  
  
### String 数据类型  
  
-   要连接字符串，请使用与号 \(&\)。  
  
     [!CODE [VbVbalrGuidelines#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#4)]  
  
-   若要将字符串追加到循环，请使用 <xref:System.Text.StringBuilder> 对象。  
  
     [!CODE [VbVbalrGuidelines#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#5)]  
  
### 事件处理程序中的宽松委托  
 不要将参数（对象和 EventArgs）显式限定到事件处理程序。  如果不使用传递给事件的事件参数（例如，发送方为对象，e 为 EventArgs\)，请使用宽松委托，而忽略代码中的事件参数：  
  
 [!CODE [VbVbalrGuidelines#7](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#7)]  
  
### 无符号数据类型  
  
-   使用 `Integer` 而不是无符号类型，除非必须使用无符号类型。  
  
### 数组  
  
-   初始化声明行上的数组时，请使用短语法。  例如，使用以下语句。  
  
     [!CODE [VbVbalrGuidelines#8](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#8)]  
  
     不要使用下列语法。  
  
     [!CODE [VbVbalrGuidelines#9](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#9)]  
  
-   将数组指定符置于类型上而不是变量上。  例如，使用以下语句：  
  
     [!CODE [VbVbalrGuidelines#11](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#11)]  
  
     不要使用下列语法：  
  
     [!CODE [VbVbalrGuidelines#10](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#10)]  
  
-   声明和初始化基本数据类型的数组时，使用 { } 语法。  例如，使用以下语句：  
  
     [!CODE [VbVbalrGuidelines#12](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#12)]  
  
     不要使用下列语法：  
  
     [!CODE [VbVbalrGuidelines#13](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#13)]  
  
### 使用 With 关键字  
 在对一个对象执行一系列调用时，请考虑使用 `With` 关键字：  
  
 [!CODE [VbVbalrGuidelines#15](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#15)]  
  
### 使用 Try...Catch 和 Using 语句来处理异常  
 不要使用 `On Error Goto`。  
  
### 使用 IsNot 关键字  
 使用 `IsNot` 关键字而非 `Not...Is Nothing`。  
  
### New 关键字  
  
-   使用短实例化。  例如，使用以下语句：  
  
     [!CODE [VbVbalrGuidelines#21](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#21)]  
  
     下行与上行等效：  
  
     [!CODE [VbVbalrGuidelines#22](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#22)]  
  
-   对于新对象使用对象初始值设定项，而不使用无参数的构造函数：  
  
     [!CODE [VbVbalrGuidelines#23](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#23)]  
  
### 事件处理  
  
-   使用 `Handles` 而不是 `AddHandler`：  
  
     [!CODE [VbVbalrGuidelines#24](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#24)]  
  
-   使用 `AddressOf`，且不要显式实例化此委托：  
  
     [!CODE [VbVbalrGuidelines#25](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#25)]  
  
-   定义事件时，使用短语法并让编译器定义此委托：  
  
     [!CODE [VbVbalrGuidelines#26](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#26)]  
  
-   不要验证事件是否是 `Nothing` \(null\)，在调用 `RaiseEvent` 方法前。  `RaiseEvent` 会在引发事件之前检查是否存在 `Nothing`。  
  
### 使用共享成员  
 使用类名称调用 `Shared` 成员，而不是从实例变量调用。  
  
### 使用 XML 文本  
 XML 文本简化了处理 XML 时的最常规任务，例如，加载、查询和转换。  在使用 XML 进行开发时，请遵循下列准则：  
  
-   使用 XML 文本创建 XML 文档和片段，而不直接调用 XML API。  
  
-   在文件或项目级别导入 XML 命名空间，以利用 XML 文本的性能优化。  
  
-   使用 XML 轴属性访问 XML 文档中的元素和特性。  
  
-   使用嵌入表达式包括值并根据现有的值创建 XML，而不是使用 API 调用（如 `Add` 方法）：  
  
     [!CODE [VbVbalrGuidelines#27](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#27)]  
  
### LINQ 查询  
  
-   对于查询变量使用有意义的名称：  
  
     [!CODE [VbVbalrGuidelines#28](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#28)]  
  
-   提供查询中的元素的名称，确保匿名类型的属性名称使用正确的 Pascal 大小写：  
  
     [!CODE [VbVbalrGuidelines#29](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#29)]  
  
-   在结果中的属性名称不明确时重命名属性。  例如，如果查询返回一个客户姓名和一个订单 ID，请重命名它们而不是在结果中保留它们的 `Name` 和 `ID` 形式：  
  
     [!CODE [VbVbalrGuidelines#30](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#30)]  
  
-   使用类型推断来声明查询变量和范围变量：  
  
     [!CODE [VbVbalrGuidelines#31](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#31)]  
  
-   对齐 `From` 语句下面的查询子句：  
  
     [!CODE [VbVbalrGuidelines#32](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#32)]  
  
-   在其他查询子句之前使用 `Where` 子句，以确保后面的查询子句作用于一组经过筛选的数据：  
  
     [!CODE [VbVbalrGuidelines#33](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#33)]  
  
-   使用 `Join` 子句显式定义联接运算，而不是使用 `Where` 子句隐式定义联接运算：  
  
     [!CODE [VbVbalrGuidelines#34](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrGuidelines#34)]  
  
## 请参阅  
 [代码安全维护指南](../Topic/Secure%20Coding%20Guidelines.md)