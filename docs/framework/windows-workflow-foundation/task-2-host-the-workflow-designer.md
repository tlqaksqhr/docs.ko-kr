---
title: "태스크 2: Workflow Designer 호스팅 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# 태스크 2: Workflow Designer 호스팅
이 항목에서는 [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] 응용 프로그램에서 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 인스턴스를 호스팅하는 절차를 설명합니다.  
  
 이 절차에서는 디자이너가 포함된 **Grid** 컨트롤을 구성하고, 기본 <xref:System.Activities.Statements.Sequence> 활동이 포함된 <xref:System.Activities.Presentation.WorkflowDesigner> 인스턴스를 프로그래밍 방식으로 만들고, 디자이너 메타데이터를 등록하여 모든 기본 제공 활동에 대한 디자이너 지원을 제공하고, [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] 응용 프로그램에서 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]를 호스팅합니다.  
  
### Workflow Designer를 호스팅하려면  
  
1.  [태스크 1: 새 Windows Presentation Foundation 응용 프로그램 만들기](../../../docs/framework/windows-workflow-foundation//task-1-create-a-new-wpf-app.md)에서 만든 HostingApplication 프로젝트를 엽니다.  
  
2.  [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]를 쉽게 사용할 수 있도록 창의 크기를 조정합니다.이렇게 하려면 디자이너에서 **MainWindow**를 선택하고, F4 키를 눌러 **속성** 창이 표시되면 이 창의 **레이아웃** 섹션에서 **너비** 값을 600으로, **높이** 값을 350으로 설정합니다.  
  
3.  디자이너에서 **Grid** 패널을 선택\(**MainWindow** 안의 상자를 클릭\)하고 **속성** 창의 맨 위에 있는 **Name** 속성을 "grid1"로 설정하여 표 이름을 설정합니다.  
  
4.  **속성** 창에서 `ColumnDefinitions` 속성 옆의 줄임표\(**...**\)를 클릭하여 **컬렉션 편집기** 대화 상자를 엽니다.  
  
5.  **컬렉션 편집기** 대화 상자에서 **추가** 단추를 세 번 클릭하여 레이아웃에 세 개의 열을 삽입합니다.첫 번째 열에는 **도구 상자**가 포함되어 있고 두 번째 열에는 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]가 호스팅되며 세 번째 열은 속성 검사자에 사용됩니다.  
  
6.  가운데 열의 `Width` 속성 값을 "4\*"로 설정합니다.  
  
7.  **확인**을 클릭하여 변경 내용을 저장합니다.다음 XAML이 MainWindow.xaml 파일에 추가됩니다.  
  
    ```  
  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
  
    ```  
  
8.  **솔루션 탐색기**에서 MainWindow.xaml을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 선택합니다.다음 단계에 따라 코드를 수정합니다.  
  
    1.  다음 네임스페이스를 추가합니다.  
  
        ```csharp  
  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
  
        ```  
  
    2.  <xref:System.Activities.Presentation.WorkflowDesigner>의 인스턴스를 보관할 전용 멤버 필드를 선언하려면 `MainWindow`에 다음 코드를 추가합니다.  
  
        ```csharp  
  
        public partial class MainWindow : Window  
        {  
            private WorkflowDesigner wd;  
  
            public MainWindow()  
            {  
                InitializeComponent();  
            }  
        }  
  
        ```  
  
    3.  다음 `AddDesigner` 메서드를 `MainWindow` 클래스에 추가합니다.이 구현에서는 <xref:System.Activities.Presentation.WorkflowDesigner>의 인스턴스를 만들고 여기에 <xref:System.Activities.Statements.Sequence> 활동을 추가한 다음 grid1 **Grid**의 가운데 열에 배치합니다.  
  
        ```csharp  
  
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
  
        ```  
  
    4.  디자이너 메타데이터를 등록하여 모든 기본 제공 활동에 대한 디자이너 지원을 추가합니다.그러면 도구 상자의 활동을 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]의 원래 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 놓을 수 있습니다.이렇게 하려면 `RegisterMetadata` 메서드를 `MainWindow` 클래스에 추가합니다.  
  
        ```csharp  
  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        ```  
  
         활동 디자이너 등록[!INCLUDE[crabout](../../../includes/crabout-md.md)][방법: 사용자 지정 활동 디자이너 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-a-custom-activity-designer.md)를 참조하십시오.  
  
    5.  `MainWindow` 클래스 생성자에서 앞에서 선언한 메서드에 호출을 추가하여 디자이너 지원을 위한 메타데이터를 등록하고 <xref:System.Activities.Presentation.WorkflowDesigner>를 만듭니다.  
  
        ```csharp  
        public MainWindow()  
        {  
            InitializeComponent();  
  
            // Register the metadata  
            RegisterMetadata();  
  
            // Add the WFF Designer  
            AddDesigner();  
        }  
  
        ```  
  
        > [!NOTE]
        >  `RegisterMetadata` 메서드는 <xref:System.Activities.Statements.Sequence> 활동을 포함한 기본 제공 활동의 디자이너 메타데이터를 등록합니다.`AddDesigner` 메서드는 <xref:System.Activities.Statements.Sequence> 활동을 사용하기 때문에 `RegisterMetadata` 메서드를 먼저 호출해야 합니다.  
  
9. F5 키를 눌러 솔루션을 빌드하고 실행합니다.  
  
10. 다시 호스팅된 Workflow Designer에 **도구 상자** 및 **PropertyGrid** 지원을 추가하는 방법은 [태스크 3: 도구 상자 및 PropertyGrid 창 만들기](../../../docs/framework/windows-workflow-foundation//task-3-create-the-toolbox-and-propertygrid-panes.md)를 참조하십시오.  
  
## 참고 항목  
 [Workflow Designer 재호스팅](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md)   
 [태스크 1: 새 Windows Presentation Foundation 응용 프로그램 만들기](../../../docs/framework/windows-workflow-foundation//task-1-create-a-new-wpf-app.md)   
 [태스크 3: 도구 상자 및 PropertyGrid 창 만들기](../../../docs/framework/windows-workflow-foundation//task-3-create-the-toolbox-and-propertygrid-panes.md)