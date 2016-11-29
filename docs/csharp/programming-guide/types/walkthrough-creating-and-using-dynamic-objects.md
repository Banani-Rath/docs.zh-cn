---
title: "演练：创建和使用动态对象（C# 和 Visual Basic） | Microsoft Docs"
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
  - "动态对象"
  - "动态对象 [C#]"
  - "动态对象 [Visual Basic]"
ms.assetid: 568f1645-1305-4906-8625-5d77af81e04f
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 演练：创建和使用动态对象（C# 和 Visual Basic）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

动态对象会在运行时（而非编译时）公开成员，如属性和方法。  这使您可以创建对象来处理与静态类型或格式不匹配的结构。  例如，您可以使用动态对象引用 HTML 文档对象模型 \(DOM\)，该模型可包含有效 HTML 标记元素和特性的任意组合。  由于每个 HTML 文档都是唯一的，因此在运行时将确定特定 HTML 文档的成员。  引用某 HTML 元素的特性的常用方法是，将相应特性的名称传递给该元素的 `GetProperty` 方法。  若要引用 HTML 元素 `<div id="Div1">` 的 `id` 特性，您首先需要获取对 `<div>` 元素的引用，然后再使用 `divElement.GetProperty("id")`。  如果使用动态对象，则可以将 `id` 特性引用为 `divElement.id`。  
  
 动态对象还提供对动态语言（如 IronPython 和 IronRuby）的便捷访问。  可以使用动态对象引用在运行时解释的动态脚本。  
  
 通过使用后期绑定引用动态对象。  在 C\# 中，将后期绑定对象的类型指定为 `dynamic`。  在 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 中，将后期绑定对象的类型指定为 `Object`。  有关更多信息，请参见[dynamic](../../../csharp/language-reference/keywords/dynamic.md)和[早期绑定和后期绑定](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)。  
  
 可以通过使用 <xref:System.Dynamic?displayProperty=fullName> 命名空间中的类创建自定义动态对象。  例如，可以创建 <xref:System.Dynamic.ExpandoObject> 并在运行时指定该对象的成员。  也可以创建您自己的继承 <xref:System.Dynamic.DynamicObject> 类的类型。  然后，可以重写 <xref:System.Dynamic.DynamicObject> 类的成员以提供运行时动态功能。  
  
 在本演练中，您将执行以下任务：  
  
-   创建一个自定义对象，该对象会将文本文件的内容作为对象的属性动态公开。  
  
-   创建使用 `IronPython` 库的项目。  
  
## 系统必备  
 需要 IronPython 2.6.1 for .NET 4.0 才能完成此演练。  可以从 [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223) 下载 IronPython 2.6.1 for .NET 4.0。  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## 创建自定义动态对象  
 您在本演练中创建的第一个项目将定义一个搜索文本文件内容的自定义动态对象。  要搜索的文本由动态属性的名称指定。  例如，如果调用代码指定 `dynamicFile.Sample`，则动态类将返回一个字符串泛型列表，其中包含该文件中以“Sample”开头的所有行。  搜索不区分大小写。  动态类还支持两个可选参数。  第一个参数是一个搜索选项枚举值，它指定动态类应在行的开头、行的结尾或行中任意位置搜索匹配项。  第二个参数指定动态类应在搜索之前去除每行中的前导空格和尾随空格。  例如，如果调用代码指定 `dynamicFile.Sample(StringSearchOption.Contains)`，则动态类将在行中的任意位置搜索“Sample”。  如果调用代码指定 `dynamicFile.Sample(StringSearchOption.StartsWith, false)`，则动态类将在每行的开头搜索“Sample”，但不会移除前导空格和尾随空格。  动态类的默认行为是在每行的开头搜索匹配项，并移除前导空格和尾随空格。  
  
#### 创建自定义动态类  
  
1.  启动 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]。  
  
2.  在**“文件”**菜单上指向**“新建”**，然后单击**“项目”**。  
  
3.  在**“新建项目”**对话框的**“项目类型”**窗格中，确保选中**“Windows”**。  在**“模板”**窗格中，选择**“控制台应用程序”**。  在**“名称”**框中，键入 `DynamicSample`，然后单击**“确定”**。  至此新项目创建完毕。  
  
4.  右击 DynamicSample 项目，指向**“添加”**，然后单击**“类”**。  在**“名称”**框中，键入 `ReadOnlyFile`，然后单击**“确定”**。  这将添加一个包含 ReadOnlyFile 类的新文件。  
  
5.  在 ReadOnlyFile.cs 或 ReadOnlyFile.vb 文件的顶部，添加要导入 <xref:System.IO?displayProperty=fullName> 和 <xref:System.Dynamic?displayProperty=fullName> 命名空间的以下代码。  
  
     [!CODE [VbDynamicWalkthrough#1](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#1)]  
  
6.  自定义动态对象使用一个枚举来确定搜索条件。  在类语句的前面，添加以下枚举定义。  
  
     [!CODE [VbDynamicWalkthrough#2](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#2)]  
  
7.  更新类语句以继承 `DynamicObject` 类，如以下代码示例所示。  
  
     [!CODE [VbDynamicWalkthrough#3](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#3)]  
  
8.  将以下代码添加到 `ReadOnlyFile` 类，定义一个用于文件路径的私有字段，并定义 `ReadOnlyFile` 类的构造函数。  
  
     [!CODE [VbDynamicWalkthrough#4](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#4)]  
  
9. 将下面的 `GetPropertyValue` 方法添加到 `ReadOnlyFile` 类。  `GetPropertyValue` 方法接收搜索条件作为输入，并返回文本文件中符合该搜索条件的行。  由 `ReadOnlyFile` 类提供的动态方法将调用 `GetPropertyValue` 方法以检索其各自的结果。  
  
     [!CODE [VbDynamicWalkthrough#5](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#5)]  
  
10. 在 `GetPropertyValue` 方法的后面添加以下代码，重写 <xref:System.Dynamic.DynamicObject> 类的 <xref:System.Dynamic.DynamicObject.TryGetMember%2A> 方法。  当请求动态类的成员且未指定任何参数时，将调用 <xref:System.Dynamic.DynamicObject.TryGetMember%2A> 方法。  `binder` 参数包含有关被引用成员的信息，而 `result` 参数则引用为指定的成员返回的结果。  <xref:System.Dynamic.DynamicObject.TryGetMember%2A> 方法会返回一个布尔值，如果请求的成员存在，则返回的布尔值为 `true`，否则返回的布尔值为 `false`。  
  
     [!CODE [VbDynamicWalkthrough#6](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#6)]  
  
11. 在 `TryGetMember` 方法的后面添加以下代码，重写 <xref:System.Dynamic.DynamicObject> 类的 <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> 方法。  当使用参数请求动态类的成员时，将调用 <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> 方法。  `binder` 参数包含有关被引用成员的信息，而 `result` 参数则引用为指定的成员返回的结果。  `args` 参数包含一个传递给成员的参数的数组。  <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> 方法会返回一个布尔值，如果请求的成员存在，则返回的布尔值为 `true`，否则返回的布尔值为 `false`。  
  
     `TryInvokeMember` 方法的自定义版本期望第一个参数为您在上一步骤中定义的 `StringSearchOption` 枚举中的值。  `TryInvokeMember` 方法期望第二个参数为一个布尔值。  如果这两个参数有一个或全部为有效值，则将它们传递给 `GetPropertyValue` 方法以检索结果。  
  
     [!CODE [VbDynamicWalkthrough#7](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#7)]  
  
12. 保存并关闭文件。  
  
#### 创建示例文本文件  
  
1.  右击 DynamicSample 项目，指向**“添加”**，然后单击**“新建项”**。  在**“已安装的模板”**窗格中，选择**“常规”**，然后选择**“文本文件”**模板。  在**“名称”**框中保留默认名称 TextFile1.txt，然后单击**“添加”**。  这会将一个新的文本文件添加到项目中。  
  
2.  将以下文本复制到 TextFile1.txt 文件。  
  
    ```  
    List of customers and suppliers  
  
    Supplier: Lucerne Publishing (http://www.lucernepublishing.com/)  
    Customer: Preston, Chris  
    Customer: Hines, Patrick  
    Customer: Cameron, Maria  
    Supplier: Graphic Design Institute (http://www.graphicdesigninstitute.com/)   
    Supplier: Fabrikam, Inc. (http://www.fabrikam.com/)   
    Customer: Seubert, Roxanne  
    Supplier: Proseware, Inc. (http://www.proseware.com/)   
    Customer: Adolphi, Stephan  
    Customer: Koch, Paul  
    ```  
  
3.  保存并关闭文件。  
  
#### 创建一个使用自定义动态对象的示例应用程序  
  
1.  在**“解决方案资源管理器”**中，双击 Module1.vb 文件（如果使用的是 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]）或 Program.cs 文件（如果使用的是 Visual C\#）。  
  
2.  将以下代码添加到 Main 过程，为 TextFile1.txt 文件创建一个 `ReadOnlyFile` 类的实例。  此代码将使用后期绑定来调用动态成员，并检索包含字符串“Customer”的文本行。  
  
     [!CODE [VbDynamicWalkthrough#8](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthrough#8)]  
  
3.  保存文件，然后按 Ctrl\+F5 生成并运行应用程序。  
  
## 调用动态语言库  
 在此演练中创建的下一项目将访问以动态语言 IronPython 编写的库。  创建此项目之前，必须安装 IronPython 2.6.1 for .NET 4.0。  可以从 [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223) 下载 IronPython 2.6.1 for .NET 4.0。  
  
#### 创建自定义动态类  
  
1.  在 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 中的**“文件”**菜单上，指向**“新建”**，然后单击**“项目”**。  
  
2.  在**“新建项目”**对话框的**“项目类型”**窗格中，确保选中**“Windows”**。  在**“模板”**窗格中，选择**“控制台应用程序”**。  在**“名称”**框中键入 `DynamicIronPythonSample`，然后单击**“确定”**。  至此新项目创建完毕。  
  
3.  如果使用的是 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]，请右击 DynamicIronPythonSample 项目，然后单击**“属性”**。  单击**“引用”**选项卡。  单击**“添加”**按钮。  如果使用的是 Visual C\#，请在**“解决方案资源管理器”**中，右击**“引用”**文件夹，然后单击**“添加引用”**。  
  
4.  在**“浏览”**选项卡上，浏览到安装 IronPython 库的文件夹。  例如，C:\\Program Files\\IronPython 2.6 for .NET 4.0。  选择**“IronPython.dll”**、**“IronPython.Modules.dll”**、**“Microsoft.Scripting.dll”**和**“Microsoft.Dynamic.dll”**库。  单击**“确定”**。  
  
5.  如果使用的是 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]，请编辑 Module1.vb 文件。  如果使用的是 Visual C\#，请编辑 Program.cs 文件。  
  
6.  在文件的顶部，添加下面的代码以从 IronPython 库导入 `Microsoft.Scripting.Hosting` 和 `IronPython.Hosting` 命名空间。  
  
     [!CODE [VbDynamicWalkthroughIronPython#1](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython#1)]  
  
7.  在 Main 方法中，添加下面的代码以创建用于托管 IronPython 库的新 `Microsoft.Scripting.Hosting.ScriptRuntime` 对象。  `ScriptRuntime` 对象加载 IronPython 库模块 random.py。  
  
     [!CODE [VbDynamicWalkthroughIronPython#2](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython#2)]  
  
8.  在用于加载 random.py 模块的代码之后，添加下面的代码以创建一个整数数组。  数组传递给 random.py 模块的 `shuffle` 方法，该方法对数组中的值进行随机排序。  
  
     [!CODE [VbDynamicWalkthroughIronPython#3](../CodeSnippet/VS_Snippets_VBCSharp/vbdynamicwalkthroughironpython#3)]  
  
9. 保存文件，然后按 Ctrl\+F5 生成并运行应用程序。  
  
## 请参阅  
 <xref:System.Dynamic?displayProperty=fullName>   
 <xref:System.Dynamic.DynamicObject?displayProperty=fullName>   
 [使用类型 dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [早期绑定和后期绑定](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [实现动态接口 \(外部博客\)](http://go.microsoft.com/fwlink/?LinkId=230895)