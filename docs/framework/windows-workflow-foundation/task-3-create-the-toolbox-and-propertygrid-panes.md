---
title: "태스크 3: 도구 상자 및 PropertyGrid 창 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# 태스크 3: 도구 상자 및 PropertyGrid 창 만들기
이 태스크에서는 **도구 상자** 및 **PropertyGrid** 창을 만든 후 다시 호스팅된 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)]에 추가합니다.  
  
 일련의 [Workflow Designer 재호스팅](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md) 항목에 있는 세 가지 태스크를 완료한 후 MainWindow.xaml.cs 파일에 포함되는 코드가 이 항목의 마지막에 참조용으로 제공됩니다.  
  
### 도구 상자를 만들어 표에 추가하려면  
  
1.  [태스크 2: Workflow Designer 호스팅](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md)에 설명되어 있는 절차를 수행하여 결과로 얻은 HostingApplication 프로젝트를 엽니다.  
  
2.  **솔루션 탐색기** 창에서 MainWindow.xaml 파일을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 선택합니다.  
  
3.  `MainWindow` 클래스에 `GetToolboxControl` 메서드를 추가합니다. 이 메서드는 <xref:System.Activities.Presentation.Toolbox.ToolboxControl>을 만들고 새 **도구 상자** 범주를 **도구 상자**에 추가하며 <xref:System.Activities.Statements.Assign> 및 <xref:System.Activities.Statements.Sequence> 활동 형식을 해당 범주에 할당합니다.  
  
    ```csharp  
  
    private ToolboxControl GetToolboxControl()  
    {  
        // Create the ToolBoxControl.  
        ToolboxControl ctrl = new ToolboxControl();  
  
        // Create a category.  
        ToolboxCategory category = new ToolboxCategory("category1");  
  
        // Create Toolbox items.  
        ToolboxItemWrapper tool1 =   
            new ToolboxItemWrapper("System.Activities.Statements.Assign",   
            typeof(Assign).Assembly.FullName, null, "Assign");  
  
        ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",   
            typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
        // Add the Toolbox items to the category.  
        category.Add(tool1);  
        category.Add(tool2);  
  
        // Add the category to the ToolBox control.  
        ctrl.Categories.Add(category);  
        return ctrl;  
    }  
  
    ```  
  
4.  `MainWindow` 클래스에 개인 `AddToolbox` 메서드를 추가합니다. 이 메서드는 표의 왼쪽 열에 **도구 상자**를 배치합니다.  
  
    ```csharp  
  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
  
    ```  
  
5.  다음 코드와 같이 `MainWindow()` 클래스 생성자에 `AddToolBox` 메서드에 대한 호출을 추가합니다.  
  
    ```csharp  
  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
  
    ```  
  
6.  F5 키를 눌러 솔루션을 빌드하고 실행합니다.<xref:System.Activities.Statements.Assign> 및 <xref:System.Activities.Statements.Sequence> 활동이 포함된 **도구 상자**가 표시됩니다.  
  
### PropertyGrid를 만들려면  
  
1.  **솔루션 탐색기** 창에서 MainWindow.xaml 파일을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 선택합니다.  
  
2.  `MainWindow` 클래스에 `AddPropertyInspector` 메서드를 추가하여 표의 맨 오른쪽 열에 **PropertyGrid** 창을 배치합니다.  
  
    ```csharp  
  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
  
    ```  
  
3.  다음 코드와 같이 `MainWindow()` 클래스 생성자에 `AddPropertyInspector` 메서드에 대한 호출을 추가합니다.  
  
    ```csharp  
  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
        this.AddToolBox();  
  
        this.AddPropertyInspector();   
    }  
  
    ```  
  
4.  F5 키를 눌러 솔루션을 빌드하고 실행합니다.**도구 상자**, 워크플로 디자인 캔버스 및 **PropertyGrid** 창이 모두 표시됩니다. <xref:System.Activities.Statements.Assign> 활동 또는 <xref:System.Activities.Statements.Sequence> 활동을 디자인 캔버스로 끌면 강조 표시된 활동에 따라 속성 표가 업데이트됩니다.  
  
## 예제  
 이제 MainWindow.xaml.cs 파일에 다음 코드가 들어 있어야 합니다.  
  
```  
  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
//dlls added  
using System.Activities;  
using System.Activities.Core.Presentation;  
using System.Activities.Presentation;  
using System.Activities.Presentation.Metadata;  
using System.Activities.Presentation.Toolbox;  
using System.Activities.Statements;  
using System.ComponentModel;  
  
namespace HostingApplication  
{  
    /// <summary>  
    /// Interaction logic for MainWindow.xaml  
    /// </summary>  
    public partial class MainWindow : Window  
    {  
        private WorkflowDesigner wd;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
            RegisterMetadata();  
            AddDesigner();  
            this.AddToolBox();  
            this.AddPropertyInspector();  
        }  
  
        private void AddDesigner()  
        {  
            //Create an instance of WorkflowDesigner class.  
            this.wd = new WorkflowDesigner();  
  
            //Place the designer canvas in the middle column of the grid.  
            Grid.SetColumn(this.wd.View, 1);  
  
            //Load a new Sequence as default.  
            this.wd.Load(new Sequence());  
  
            //Add the designer canvas to the grid.  
            grid1.Children.Add(this.wd.View);  
        }  
  
        private void RegisterMetadata()  
        {  
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        private ToolboxControl GetToolboxControl()  
        {  
            // Create the ToolBoxControl.  
            ToolboxControl ctrl = new ToolboxControl();  
  
            // Create a category.  
            ToolboxCategory category = new ToolboxCategory("category1");  
  
            // Create Toolbox items.  
            ToolboxItemWrapper tool1 =  
                new ToolboxItemWrapper("System.Activities.Statements.Assign",  
                typeof(Assign).Assembly.FullName, null, "Assign");  
  
            ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",  
                typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
            // Add the Toolbox items to the category.  
            category.Add(tool1);  
            category.Add(tool2);  
  
            // Add the category to the ToolBox control.  
            ctrl.Categories.Add(category);  
            return ctrl;  
        }  
  
        private void AddToolBox()  
        {  
            ToolboxControl tc = GetToolboxControl();  
            Grid.SetColumn(tc, 0);  
            grid1.Children.Add(tc);  
        }  
  
        private void AddPropertyInspector()  
        {  
            Grid.SetColumn(wd.PropertyInspectorView, 2);  
            grid1.Children.Add(wd.PropertyInspectorView);  
        }  
  
    }  
}  
  
```  
  
## 참고 항목  
 [Workflow Designer 재호스팅](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md)   
 [태스크 1: 새 Windows Presentation Foundation 응용 프로그램 만들기](../../../docs/framework/windows-workflow-foundation//task-1-create-a-new-wpf-app.md)   
 [태스크 2: Workflow Designer 호스팅](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md)