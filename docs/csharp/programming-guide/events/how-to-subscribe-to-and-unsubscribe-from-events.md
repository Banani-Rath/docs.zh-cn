---
title: "如何：订阅和取消订阅事件（C# 编程指南） | Microsoft Docs"
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
  - "代码编辑器, 事件处理程序"
  - "事件处理程序 [C#], 创建"
  - "事件 [C#], 使用 IDE 创建"
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
translationtype: Human Translation
---
# 如何：订阅和取消订阅事件（C# 编程指南）
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

如果您想编写引发事件时调用的自定义代码，则可以订阅由其他类发布的事件。  例如，可以订阅某个按钮的 `click` 事件，以使应用程序在用户单击该按钮时执行一些有用的操作。  
  
### 使用 Visual Studio IDE 订阅事件  
  
1.  如果看不到**“属性”**窗口，请在**“设计”**视图中，右击要为其创建事件处理程序的窗体或控件，然后选择**“属性”**。  
  
2.  在**“属性”**窗口的顶部，单击**“事件”**图标。  
  
3.  双击要创建的事件，例如 `Load` 事件。  
  
     [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)] 会创建一个空事件处理程序方法，并将其添加到您的代码中。  或者，您也可以在**“代码”**视图中手动添加代码。  例如，下面的代码行声明了一个在 `Form` 类引发 `Load` 事件时调用的事件处理程序方法。  
  
     [!CODE [csProgGuideEvents#11](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuideEvents#11)]  
  
     还会在项目的 Form1.Designer.cs 文件的 `InitializeComponent` 方法中自动生成订阅该事件所需的代码行。  该代码行类似于：  
  
    ```  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### 以编程方式订阅事件  
  
1.  定义一个事件处理程序方法，其签名与该事件的委托签名匹配。  例如，如果事件基于 <xref:System.EventHandler> 委托类型，则下面的代码表示方法存根：  
  
    ```  
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2.  使用加法赋值运算符 \(`+=`\) 来为事件附加事件处理程序。  在下面的示例中，假设名为 `publisher` 的对象拥有一个名为 `RaiseCustomEvent` 的事件。  请注意，订户类需要引用发行者类才能订阅其事件。  
  
    ```  
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     请注意，前面的语法是 C\# 2.0 中的新语法。  此语法完全等效于必须使用 `new` 关键字显式创建封装委托的 C\# 1.0 语法：  
  
    ```  
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     还可以通过使用 lambda 表达式添加事件处理程序：  
  
    ```  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
        this.Click += (s,e) => { MessageBox.Show(  
           ((MouseEventArgs)e).Location.ToString());};  
    }  
    ```  
  
     有关更多信息，请参见 [如何：在 LINQ 外部使用 Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md)。  
  
### 使用匿名方法订阅事件  
  
-   如果以后不必取消订阅某个事件，则可以使用加法赋值运算符 \(`+=`\) 将匿名方法附加到此事件。  在下面的示例中，假设名为 `publisher` 的对象拥有一个名为 `RaiseCustomEvent`  的事件，并且还定义了一个 `CustomEventArgs` 类以承载某些类型的专用事件信息。  请注意，订户类需要引用 `publisher` 才能订阅其事件。  
  
    ```  
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     请务必注意，如果使用匿名函数订阅事件，事件的取消订阅过程将比较麻烦。  这种情况下若要取消订阅，必须返回到该事件的订阅代码，将该匿名方法存储在委托变量中，然后将此委托添加到该事件中。  一般来说，如果必须在后面的代码中取消订阅某个事件，则建议您不要使用匿名函数订阅此事件。  有关匿名函数的更多信息，请参见[匿名函数](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)。  
  
## 取消订阅  
 要防止在引发事件时调用事件处理程序，请取消订阅该事件。  要防止资源泄露，应在释放订户对象之前取消订阅事件。  在取消订阅事件之前，在发布对象中作为该事件的基础的多路广播委托会引用封装了订户的事件处理程序的委托。  只要发布对象保持该引用，垃圾回收功能就不会删除订户对象。  
  
#### 取消订阅事件  
  
-   使用减法赋值运算符 \(`-=`\) 取消订阅事件：  
  
    ```  
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     所有订户都取消订阅事件后，发行者类中的事件实例将设置为 `null`。  
  
## 请参阅  
 [事件](../../../csharp/programming-guide/events/index.md)   
 [event](../../../csharp/language-reference/keywords/event.md)   
 [如何：发布符合 .NET Framework 准则的事件](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)   
 [\-\= 运算符](../../../csharp/language-reference/operators/subtraction-assignment-operator-1.md)   
 [\+\= 运算符](../../../csharp/language-reference/operators/addition-assignment-operator.md)