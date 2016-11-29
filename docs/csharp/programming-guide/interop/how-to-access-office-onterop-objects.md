---
title: "如何：通过使用 Visual C# 功能访问 Office 互操作对象（C# 编程指南） | Microsoft Docs"
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
  - "dynamic [C#], Office 编程"
  - "命名参数和可选参数 [C#], Office 编程"
  - "命名参数 [C#], Office 编程"
  - "Office 编程 [C#]"
  - "可选参数 [C#], Office 编程"
  - "可选参数 [C#], Office 编程"
ms.assetid: 041b25c2-3512-4e0f-a4ea-ceb2999e4d5e
caps.latest.revision: 33
caps.handback.revision: 33
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：通过使用 Visual C# 功能访问 Office 互操作对象（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Visual C\# 2010 引入了可以简化对 Office API 对象的访问的新功能。  这些新功能包括命名实参和可选实参、名为 `dynamic` 的新类型，以及在 COM 方法中将实参传递为引用形参（就像它们是值形参）的功能。  
  
 在本主题中，你将利用这些新功能来编写创建并显示 Microsoft Office Excel 工作表的代码。  然后，你将编写添加包含链接到 Excel 工作表的图标的 Office Word 文档的代码。  
  
 若要完成本演练，你的计算机上必须安装 Microsoft Office Excel 2007 和 Microsoft Office Word 2007 或更高版本。  
  
 如果你使用的操作系统早于 [!INCLUDE[windowsver](../../../csharp/programming-guide/interop/includes/windowsver_md.md)]，请确保安装 [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)]。  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### 创建新的控制台应用程序  
  
1.  启动 Visual Studio。  
  
2.  在**“文件”**菜单上，指向**“新建”**，然后单击**“项目”**。  此时将出现“新建项目”对话框。  
  
3.  在“已安装的模板”窗格中，展开“Visual C\#”，然后单击“Windows”。  
  
4.  查看“新建项目”对话框的顶部，确保“.NET Framework 4”（或更高版本）选为目标框架。  
  
5.  在**“模板”**窗格中，单击**“控制台应用程序”**。  
  
6.  在“名称”字段中键入项目的名称。  
  
7.  单击“确定”。  
  
     新项目将出现在“解决方案资源管理器”中。  
  
### 添加引用  
  
1.  在“解决方案资源管理器”中，右键单击你的项目名称，然后单击“添加引用”。  将显示**“添加引用”**对话框。  
  
2.  在“程序集”页上，在“组件名称”列表中选择“Microsoft.Office.Interop.Word”，然后按住 Ctrl 键并选择“Microsoft.Office.Interop.Excel”。  如果未看到程序集，你可能需要确保安装并显示它们（参阅[如何：安装 Office 主互操作程序集](../Topic/How%20to:%20Install%20Office%20Primary%20Interop%20Assemblies.md)）  
  
3.  单击“确定”。  
  
### 添加必要的 using 指令  
  
1.  在“解决方案资源管理器”中，右键单击“Program.cs”文件，然后单击“查看代码”。  
  
2.  将以下 `using` 指令添加到代码文件的顶部。  
  
     [!CODE [csProgGuideOfficeHowTo#1](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#1)]  
  
### 创建银行帐户列表  
  
1.  将以下类定义粘贴到“Program.cs”中的 `Program` 类下。  
  
     [!CODE [csProgGuideOfficeHowTo#2](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#2)]  
  
2.  将以下代码添加到 `Main` 方法，以创建包含两个帐户的 `bankAccounts` 列表。  
  
     [!CODE [csProgGuideOfficeHowTo#3](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#3)]  
  
### 声明将帐户信息导出到 Excel 的方法  
  
1.  将以下方法添加到 `Program` 类以设置 Excel 工作表。  
  
     方法 [Add](http://go.microsoft.com/fwlink/?LinkId=210910) 有一个可选参数，用于指定特定的模板。  如果希望使用形参的默认值，你可以借助可选形参（[!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] 中新增）忽略该形参的实参。  由于以下代码中未发送任何参数，`Add` 将使用默认模板并创建新的工作簿。  C\# 早期版本中的等效语句要求占位符参数：`ExcelApp.Workbooks.Add(Type.Missing)`.  
  
     [!CODE [csProgGuideOfficeHowTo#4](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#4)]  
  
2.  在 `DisplayInExcel` 的末尾添加以下代码。  代码将值插入工作表第一行的前两列。  
  
     [!CODE [csProgGuideOfficeHowTo#5](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#5)]  
  
3.  在 `DisplayInExcel` 的末尾添加以下代码。  `foreach` 循环将帐户列表中的信息放入工作表连续行的前两列。  
  
     [!CODE [csProgGuideOfficeHowTo#7](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#7)]  
  
4.  在 `DisplayInExcel` 的末尾添加以下代码以将列宽调整为适合内容。  
  
     [!CODE [csProgGuideOfficeHowTo#13](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#13)]  
  
     早期版本的 C\# 要求显式强制转换这些操作，因为 `ExcelApp.Columns[1]` 返回 `Object`，`AutoFit` 为 Excel [Range](http://go.microsoft.com/fwlink/?LinkId=210911) 方法。  以下各行显示强制转换。  
  
     [!CODE [csProgGuideOfficeHowTo#14](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#14)]  
  
     如果程序集由 [\/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) 编译器选项引用或者如果 Excel 的“嵌入互操作类型”属性设置为 true，则 [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] 及更高版本会自动将返回的 `Object` 转换为 `dynamic`。  True 是此属性的默认值。  
  
### 运行项目  
  
1.  在 `Main` 的末尾添加以下行。  
  
     [!CODE [csProgGuideOfficeHowTo#8](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#8)]  
  
2.  按 Ctrl\+F5。  
  
     出现包含两个帐户数据的 Excel 工作表。  
  
### 添加 Word 文档  
  
1.  若要说明 [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] 以及更高版本在其他哪些方面增强了 Office 编程，可以使用以下代码打开 Word 应用程序并创建链接到 Excel 工作表的图标。  
  
     将方法 `CreateIconInWordDoc`（在此步骤后面提供）粘贴到 `Program` 类中。  `CreateIconInWordDoc` 利用命名参数和可选参数来降低对 [Add](http://go.microsoft.com/fwlink/?LinkId=210937) 和 [PasteSpecial](http://go.microsoft.com/fwlink/?LinkId=147099) 的方法调用的复杂度。  这些调用合并了其他两项新功能，这两项新功能在简化对具有引用参数的 COM 方法的调用的 [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] 中引入。  首先，你可以将实参发送到引用形参，就像它们是值形参一样。  即，你可以直接发送值，而无需为每个引用参数创建变量。  编译器会生成临时变量以保存参数值，并将在你从调用返回时丢弃变量。  其次，你可以忽略参数列表中的 `ref` 关键字。  
  
     `Add` 方法有四个引用参数，所有引用参数都是可选的。  在 [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] 或更高版本中，如果希望使用其默认值，可以忽略任何或所有形参的实参。  在 [!INCLUDE[csharp_orcas_long](../../../csharp/programming-guide/interop/includes/csharp_orcas_long_md.md)] 以及更早版本中，由于形参是引用形参，因此必须为每个形参提供实参且实参必须是变量。  
  
     `PasteSpecial` 方法可插入剪贴板的内容。  该方法有七个引用参数，所有引用参数都是可选的。  以下代码为其中两个形参指定实参：`Link` 用于创建指向剪贴板内容源的连接，`DisplayAsIcon` 用于将链接显示为图标。  在 [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] 中，你可以对其中两个形参使用命名实参而忽略其他形参。  尽管这些是引用形参，你也不必使用 `ref` 关键字，或者创建变量以实参形式发送。  你可以直接发送值。  在 [!INCLUDE[csharp_orcas_long](../../../csharp/programming-guide/interop/includes/csharp_orcas_long_md.md)] 以及早期版本中，你必须为每个引用形参发送变量实参。  
  
     [!CODE [csProgGuideOfficeHowTo#9](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#9)]  
  
     在 [!INCLUDE[csharp_orcas_long](../../../csharp/programming-guide/interop/includes/csharp_orcas_long_md.md)] 或早期版本的语言中，需要以下更复杂的代码。  
  
     [!CODE [csProgGuideOfficeHowTo#10](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#10)]  
  
2.  在 `Main` 的末尾添加以下语句。  
  
     [!CODE [csProgGuideOfficeHowTo#11](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#11)]  
  
3.  在 `DisplayInExcel` 的末尾添加以下语句。  `Copy` 方法可将工作表添加到剪贴板。  
  
     [!CODE [csProgGuideOfficeHowTo#12](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#12)]  
  
4.  按 Ctrl\+F5。  
  
     将出现包含图标的 Word 文档。  双击该图标以将工作表置于前台。  
  
### 设置嵌入互操作类型属性  
  
1.  当调用运行时不需要主互操作程序集 \(PIA\) 的 COM 类型时，可能实现其他增强。  删除 PIA 的依赖项可实现版本独立性并且更易于部署。  有关不使用 PIA 编程的优势的详细信息，请参阅[演练：嵌入托管程序集中的类型](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)。  
  
     此外，由于可以通过使用类型 `dynamic`（而非 `Object`）表示 COM 方法必需并返回的类型，因此更易于编程。  具有类型 `dynamic` 的变量在运行时以前均不会计算，从而消除了显式强制转换的需要。  有关详细信息，请参阅[使用类型 dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)。  
  
     在 [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)] 中，默认行为是嵌入类型信息，而不是使用 PIA。  由于该默认行为，因此不需要显式强制转换，之前的几个示例也得到简化。  例如，`DisplayInExcel` 中 `worksheet` 的声明会写为 `Excel._Worksheet workSheet = excelApp.ActiveSheet` 而非 `Excel._Worksheet workSheet = (Excel.Worksheet)excelApp.ActiveSheet`。  在相同方法中对 `AutoFit` 的调用还将要求在不进行默认行为的情况下显式强制转换，因为 `ExcelApp.Columns[1]` 返回 `Object`，并且 `AutoFit` 为 Excel 方法。  以下代码显示强制转换。  
  
     [!CODE [csProgGuideOfficeHowTo#14](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#14)]  
  
2.  若要更改默认行为并使用 PIA 代替嵌入类型信息，请展开“解决方案资源管理器”中的“引用”节点，然后选择“Microsoft.Office.Interop.Excel”或“Microsoft.Office.Interop.Word”。  
  
3.  如果看不到“属性”窗口，请按“F4”。  
  
4.  在属性列表中找到“嵌入互操作类型”，将其值更改为“False”。  同样地，你还可以通过在命令提示符下使用 [\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) 编译器选项代替 [\/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) 进行编译。  
  
### 将其他格式添加到表格  
  
1.  将在 `DisplayInExcel` 中对 `AutoFit` 的两个调用替换为以下语句。  
  
     [!CODE [csProgGuideOfficeHowTo#15](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#15)]  
  
     [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=210948) 方法有七个值参数，每个值参数都是可选的。  使用命名参数和可选参数，你可以为这些参数中的所有或部分提供参数，也可以不为它们中的任何一个提供。  在上一条语句中，仅为其中一个形参 `Format` 提供实参。  由于 `Format` 是参数列表中的第一个参数，因此无需提供参数名称。  但是，如果包含参数名称，语句则可能更易于理解，如以下代码所示。  
  
     [!CODE [csProgGuideOfficeHowTo#16](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#16)]  
  
2.  按 Ctrl\+F5 查看结果。  其他格式在 [XlRangeAutoFormat](http://go.microsoft.com/fwlink/?LinkId=210967) 枚举中列出。  
  
3.  将步骤 1 中的语句与以下代码比较（以下代码显示 [!INCLUDE[csharp_orcas_long](../../../csharp/programming-guide/interop/includes/csharp_orcas_long_md.md)] 或早期版本中要求的参数）。  
  
     [!CODE [csProgGuideOfficeHowTo#17](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#17)]  
  
## 示例  
 以下代码显示完整示例。  
  
 [!CODE [csProgGuideOfficeHowTo#18](../CodeSnippet/VS_Snippets_VBCSharp/csprogguideofficehowto#18)]  
  
## 请参阅  
 <xref:System.Type.Missing?displayProperty=fullName>   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [使用类型 dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [命名参数和可选参数](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)   
 [如何：在 Office 编程中使用命名参数和可选参数](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)