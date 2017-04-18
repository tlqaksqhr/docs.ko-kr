---
title: "방법: 사용자 지정 활동 디자이너 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# 방법: 사용자 지정 활동 디자이너 만들기
사용자 지정 활동 디자이너는 일반적으로 디자이너를 함께 디자인 화면에 끌어 놓을 수 있는 다른 활동을 사용하여 연결된 활동을 구성할 수 있도록 구현됩니다.이 기능을 사용하려면 사용자 지정 활동 디자이너가 임의의 활동을 배치할 수 있는 “끌어 놓기 영역”을 제공하고, 디자인 화면에서 요소의 결과 컬렉션을 관리하는 방법도 제공해야 합니다.이 항목에서는 이러한 끌어 놓기 영역이 포함된 사용자 지정 활동 디자이너를 만드는 방법과 디자이너 요소 컬렉션을 관리하는 데 필요한 편집 기능을 제공하는 사용자 지정 활동 디자이너를 만드는 방법에 대해 설명합니다.  
  
 사용자 지정 활동 디자이너는 일반적으로 특정 디자이너가 없는 활동의 기본 활동 디자이너 형식인 <xref:System.Activities.Presentation.ActivityDesigner>에서 상속합니다.이 형식은 속성 표와 상호 작용하고, 색, 아이콘 등과 같은 기본 기능을 구성하는 디자인 타임 환경을 제공합니다.  
  
 <xref:System.Activities.Presentation.ActivityDesigner>는 <xref:System.Activities.Presentation.WorkflowItemPresenter> 및 <xref:System.Activities.Presentation.WorkflowItemsPresenter>라는 두 도우미 컨트롤을 사용하여 사용자 지정 활동 디자이너를 쉽게 개발할 수 있습니다.또한 자식 요소 끌어서 놓기, 삭제, 선택, 추가 등과 같은 일반적인 기능을 처리합니다.<xref:System.Activities.Presentation.WorkflowItemPresenter>는 단일 자식 UI 요소를 허용하고 “끌어 놓기 영역”을 제공하지만 <xref:System.Activities.Presentation.WorkflowItemsPresenter>는 자식 요소 정렬, 이동, 삭제, 추가 등과 같은 추가 기능을 비롯한 여러 UI 요소를 지원할 수 있습니다.  
  
 사용자 지정 활동 디자이너의 구현에서 주목해야 할 또 다른 주요 부분은 [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] 데이터 바인딩을 사용하여 디자이너에서 편집 중인 항목의 메모리에 저장된 인스턴스에 시각적 편집 내용을 바인딩하는 방법과 관련된 내용입니다.이 방법은 변경 내용 알림을 활성화하고 해당 상태의 변경 내용과 비슷한 이벤트를 추적하는 모델 항목 트리에 의해 수행됩니다.  
  
 이 항목에서는 두 가지 절차에 대해 간략하게 설명합니다.  
  
1.  첫 번째 절차는 <xref:System.Activities.Presentation.WorkflowItemPresenter>를 사용하여 다른 활동을 받는 끌어 놓기 영역을 제공하는 사용자 지정 활동 디자이너를 만드는 방법에 대해 설명하며,[사용자 지정 복합 디자이너 \- 워크플로 항목 프리젠터](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-item-presenter.md) 샘플을 기반으로 합니다.  
  
2.  두 번째 절차는 <xref:System.Activities.Presentation.WorkflowItemsPresenter>를 사용하여 포함된 요소 컬렉션을 편집하는 데 필요한 기능을 제공하는 사용자 지정 활동 디자이너를 만드는 방법에 대해 설명하며,[사용자 지정 복합 디자이너 \- 워크플로 항목 프리젠터](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-items-presenter.md) 샘플을 기반으로 합니다.  
  
### WorkflowItemPresenter를 사용하여 끌어 놓기 영역이 있는 사용자 지정 활동 디자이너를 만들려면  
  
1.  [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]을 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트…**를 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  **설치된 템플릿** 창의 기본 언어 범주에서 **Windows**를 선택합니다.  
  
4.  **템플릿** 창에서 **WPF 응용 프로그램**을 선택합니다.  
  
5.  **이름** 상자에 `UsingWorkflowItemPresenter`를 입력합니다.  
  
6.  **위치** 상자에 프로젝트를 저장할 디렉터리를 입력하거나 **찾아보기**를 클릭하여 해당 디렉터리를 찾습니다.  
  
7.  **솔루션** 상자에서 기본값을 사용합니다.  
  
8.  **확인**을 클릭합니다.  
  
9. **솔루션 탐색기**에서 MainWindows.xaml 파일을 마우스 오른쪽 단추로 클릭한 다음 **삭제**를 선택하고 **Microsoft Visual Studio** 대화 상자에서 **확인**을 클릭하여 확인합니다.  
  
10. **솔루션 탐색기**에서 UsingWorkflowItemPresenter 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 선택한 다음 **새 항목…**을 선택하여 **새 항목 추가** 대화 상자를 표시하고 왼쪽의 **설치된 템플릿** 섹션에서 **WPF** 범주를 선택합니다.  
  
11. **창\(WPF\)** 템플릿을 선택하고 이름을 `RehostingWFDesigner`로 지정한 다음 **추가**를 클릭합니다.  
  
12. RehostingWFDesigner.xaml 파일을 열고 다음 코드를 붙여 넣어 응용 프로그램의 UI를 정의합니다.  
  
    ```  
  
    <Window x:Class=" UsingWorkflowItemPresenter.RehostingWFDesigner"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            xmlns:sapt="clr-namespace:System.Activities.Presentation.Toolbox;assembly=System.Activities.Presentation"  
            xmlns:sys="clr-namespace:System;assembly=mscorlib"  
            Title="Window1" Height="600" Width="900">  
        <Window.Resources>  
            <sys:String x:Key="AssemblyName">System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35</sys:String>  
        </Window.Resources>  
        <Grid>  
            <Grid.ColumnDefinitions>  
                <ColumnDefinition Width="2*"/>  
                <ColumnDefinition Width="7*"/>  
                <ColumnDefinition Width="3*"/>  
            </Grid.ColumnDefinitions>  
            <Border Grid.Column="0">  
                <sapt:ToolboxControl Name="Toolbox">  
                    <sapt:ToolboxCategory CategoryName="Basic">  
                        <sapt:ToolboxItemWrapper AssemblyName="{StaticResource AssemblyName}" >  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.Sequence  
                            </sapt:ToolboxItemWrapper.ToolName>  
                           </sapt:ToolboxItemWrapper>  
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.WriteLine  
                            </sapt:ToolboxItemWrapper.ToolName>  
  
                        </sapt:ToolboxItemWrapper>  
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.If  
                            </sapt:ToolboxItemWrapper.ToolName>  
  
                        </sapt:ToolboxItemWrapper>  
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.While  
                            </sapt:ToolboxItemWrapper.ToolName>  
  
                        </sapt:ToolboxItemWrapper>  
                    </sapt:ToolboxCategory>  
                </sapt:ToolboxControl>  
            </Border>  
            <Border Grid.Column="1" Name="DesignerBorder"/>  
            <Border Grid.Column="2" Name="PropertyBorder"/>  
        </Grid>  
    </Window>  
  
    ```  
  
13. 활동 유형에 활동 디자이너를 연결하려면 메타데이터 저장소에 해당 활동 디자이너를 등록해야 합니다.이렇게 하려면 `RegisterMetadata` 메서드를 `RehostingWFDesigner` 클래스에 추가합니다.`RegisterMetadata` 메서드의 범위 내에 <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> 개체를 만들고 <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> 메서드를 호출하여 특성을 추가합니다.<xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> 메서드를 호출하여 <xref:System.Activities.Presentation.Metadata.AttributeTable>을 메타데이터 저장소에 추가합니다.다음 코드에는 디자이너의 재호스팅 논리가 포함되어 있습니다.이 코드는 메타데이터를 등록하고 `SimpleNativeActivity`를 도구 상자에 넣고 워크플로를 만듭니다.RehostingWFDesigner.xaml.cs 파일에 이 코드를 넣습니다.  
  
    ```  
  
    using System;  
    using System.Activities.Core.Presentation;  
    using System.Activities.Presentation;  
    using System.Activities.Presentation.Metadata;  
    using System.Activities.Presentation.Toolbox;  
    using System.Activities.Statements;  
    using System.ComponentModel;  
    using System.Windows;  
  
    namespace UsingWorkflowItemPresenter  
    {  
        // Interaction logic for RehostingWFDesigner.xaml  
        public partial class RehostingWFDesigner  
        {  
            public RehostingWFDesigner()  
            {  
                InitializeComponent();  
            }  
  
            protected override void OnInitialized(EventArgs e)  
            {  
                base.OnInitialized(e);  
                // register metadata  
                (new DesignerMetadata()).Register();  
                RegisterCustomMetadata();  
                // add custom activity to toolbox  
                Toolbox.Categories.Add(new ToolboxCategory("Custom activities"));  
                Toolbox.Categories[1].Add(new ToolboxItemWrapper(typeof(SimpleNativeActivity)));  
  
                // create the workflow designer  
                WorkflowDesigner wd = new WorkflowDesigner();  
                wd.Load(new Sequence());  
                DesignerBorder.Child = wd.View;  
                PropertyBorder.Child = wd.PropertyInspectorView;  
  
            }  
  
            void RegisterCustomMetadata()  
            {  
                AttributeTableBuilder builder = new AttributeTableBuilder();  
                builder.AddCustomAttributes(typeof(SimpleNativeActivity), new DesignerAttribute(typeof(SimpleNativeDesigner)));  
                MetadataStore.AddAttributeTable(builder.CreateTable());  
            }  
        }  
    }  
  
    ```  
  
14. 솔루션 탐색기에서 References 디렉터리를 마우스 오른쪽 단추로 클릭하고 **참조 추가…**를 선택하여 **참조 추가** 대화 상자를 표시합니다.  
  
15. **.NET** 탭을 클릭하고 **System.Activities.Core.Presentation**이라는 어셈블리를 찾아 선택한 다음 **확인**을 클릭합니다.  
  
16. 같은 절차를 사용하여 다음 어셈블리에 참조를 추가합니다.  
  
    1.  System.Data.DataSetExtensions.dll  
  
    2.  System.Activities.Presentation.dll  
  
    3.  System.ServiceModel.Activities.dll  
  
17. App.xaml 파일을 열고 StartUpUri의 값을 “RehostingWFDesigner.xaml”로 변경합니다.  
  
18. **솔루션 탐색기**에서 UsingWorkflowItemPresenter 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 선택한 다음 **새 항목…**을 선택하여 **새 항목 추가** 대화 상자를 표시하고 왼쪽의 **설치된 템플릿** 섹션에서 **워크플로** 범주를 선택합니다.  
  
19. **활동 디자이너** 템플릿을 선택하고 이름을 `SimpleNativeDesigner`로 지정한 다음 **추가**를 클릭합니다.  
  
20. SimpleNativeDesigner.xaml 파일을 열고 다음 코드를 붙여 넣습니다.이 코드에서는 <xref:System.Activities.Presentation.ActivityDesigner>를 루트 요소로 사용하고 복합 활동 디자이너에서 자식 형식을 표시할 수 있도록 바인딩을 사용하여 <xref:System.Activities.Presentation.WorkflowItemPresenter>를 디자이너에 통합하는 방법을 보여 줍니다.  
  
    > [!NOTE]
    >  <xref:System.Activities.Presentation.ActivityDesigner>의 스키마를 사용하면 사용자 지정 활동 디자이너 정의에 자식 요소를 하나만 추가할 수 있지만, `StackPanel`, `Grid` 또는 다른 복합 UI 요소 중에서 선택하여 추가할 수 있습니다.  
  
    ```  
  
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemPresenter.SimpleNativeDesigner"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
        <sap:ActivityDesigner.Resources>  
            <DataTemplate x:Key="Collapsed">  
                <StackPanel>  
                    <TextBlock>This is the collapsed view</TextBlock>  
                </StackPanel>  
            </DataTemplate>  
            <DataTemplate x:Key="Expanded">  
                <StackPanel>  
                    <TextBlock>Custom Text</TextBlock>  
                    <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
                                            HintText="Please drop an activity here" />  
                </StackPanel>  
            </DataTemplate>  
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
                <Style.Triggers>  
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">  
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
                    </DataTrigger>  
                </Style.Triggers>  
            </Style>  
        </sap:ActivityDesigner.Resources>  
        <Grid>  
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />  
        </Grid>  
    </sap:ActivityDesigner>  
  
    ```  
  
21. **솔루션 탐색기**에서 UsingWorkflowItemPresenter 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 선택한 다음 **새 항목…**을 선택하여 **새 항목 추가** 대화 상자를 표시하고 왼쪽의 **설치된 템플릿** 섹션에서 **워크플로** 범주를 선택합니다.  
  
22. **코드 활동** 템플릿을 선택하고 이름을 `SimpleNativeActivity`로 지정한 다음 **추가**를 클릭합니다.  
  
23. SimpleNativeActivity.cs 파일에 다음 코드를 입력하여 `SimpleNativeActivity` 클래스를 구현합니다.  
  
    ```  
  
    using System.Activities;  
  
    namespace UsingWorkflowItemPresenter  
    {  
        public sealed class SimpleNativeActivity : NativeActivity  
        {  
            // this property contains an activity that will be scheduled in the execute method  
    // the WorkflowItemPresenter in the designer is bound to this to enable editing  
    // of the value  
            public Activity Body { get; set; }  
  
            protected override void CacheMetadata(NativeActivityMetadata metadata)  
            {  
               metadata.AddChild(Body);  
               base.CacheMetadata(metadata);  
  
            }  
  
            protected override void Execute(NativeActivityContext context)  
            {  
                context.ScheduleActivity(Body);  
            }  
        }  
    }  
  
    ```  
  
24. **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  
  
25. **디버그** 메뉴에서 **디버깅하지 않고 시작**을 선택하여 다시 호스팅된 사용자 지정 디자인 창을 엽니다.  
  
### WorkflowItemsPresenter를 사용하여 사용자 지정 활동 디자이너를 만들려면  
  
1.  두 번째 사용자 지정 활동 디자이너에 대한 절차는 몇 가지 수정된 부분만 제외하고는 첫 번째 디자이너에 대한 절차와 비슷합니다. 수정된 부분 중 하나는 두 번째 응용 프로그램의 이름을 `UsingWorkflowItemsPresenter`로 지정한다는 사실입니다.또한 이 응용 프로그램은 새 사용자 지정 활동을 정의하지 않습니다.  
  
2.  주요 차이점은 CustomParallelDesigner.xaml 및 RehostingWFDesigner.xaml.cs 파일에 있습니다.다음은 UI를 정의하는 CustomParallelDesigne.xaml 파일의 코드입니다.  
  
    ```  
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemsPresenter.CustomParallelDesigner"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
        <sap:ActivityDesigner.Resources>  
            <DataTemplate x:Key="Collapsed">  
                <TextBlock>This is the Collapsed View</TextBlock>  
            </DataTemplate>  
            <DataTemplate x:Key="Expanded">  
                <StackPanel>  
                    <TextBlock HorizontalAlignment="Center">This is the</TextBlock>  
                    <TextBlock HorizontalAlignment="Center">extended view</TextBlock>  
                    <sap:WorkflowItemsPresenter HintText="Drop Activities Here"  
                                        Items="{Binding Path=ModelItem.Branches}">  
                        <sap:WorkflowItemsPresenter.SpacerTemplate>  
                            <DataTemplate>  
                                <Ellipse Width="10" Height="10" Fill="Black"/>  
                            </DataTemplate>  
                        </sap:WorkflowItemsPresenter.SpacerTemplate>  
                        <sap:WorkflowItemsPresenter.ItemsPanel>  
                            <ItemsPanelTemplate>  
                                <StackPanel Orientation="Horizontal"/>  
                            </ItemsPanelTemplate>  
                        </sap:WorkflowItemsPresenter.ItemsPanel>  
                    </sap:WorkflowItemsPresenter>  
                </StackPanel>  
            </DataTemplate>  
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
                <Style.Triggers>  
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">  
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
                    </DataTrigger>  
                </Style.Triggers>  
            </Style>  
        </sap:ActivityDesigner.Resources>  
        <Grid>  
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>  
        </Grid>  
    </sap:ActivityDesigner>  
  
    ```  
  
3.  다음은 재호스팅 논리를 제공하는 RehostingWFDesigner.xaml.cs 파일의 코드입니다.  
  
    ```  
  
    using System;  
    using System.Activities.Core.Presentation;  
    using System.Activities.Presentation;  
    using System.Activities.Presentation.Metadata;  
    using System.Activities.Statements;  
    using System.ComponentModel;  
    using System.Windows;  
  
    namespaceUsingWorkflowItemsPresenter  
    {  
        public partial class RehostingWfDesigner : Window  
        {  
            public RehostingWfDesigner()  
            {  
                InitializeComponent();  
            }  
  
            protected override void OnInitialized(EventArgs e)  
            {  
                base.OnInitialized(e);  
                // register metadata  
                (new DesignerMetadata()).Register();  
                RegisterCustomMetadata();  
  
                // create the workflow designer  
                WorkflowDesigner wd = new WorkflowDesigner();  
                wd.Load(new Sequence());  
                DesignerBorder.Child = wd.View;  
                PropertyBorder.Child = wd.PropertyInspectorView;  
  
            }  
  
            void RegisterCustomMetadata()  
            {  
                AttributeTableBuilder builder = new AttributeTableBuilder();  
                builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));  
                MetadataStore.AddAttributeTable(builder.CreateTable());  
            }  
        }  
    }  
    ```  
  
## 참고 항목  
 <xref:System.Activities.Presentation.ActivityDesigner>   
 <xref:System.Activities.Presentation.WorkflowItemPresenter>   
 <xref:System.Activities.Presentation.WorkflowItemsPresenter>   
 <xref:System.Activities.Presentation.WorkflowViewElement>   
 <xref:System.Activities.Presentation.Model.ModelItem>   
 [워크플로 디자인 환경 사용자 지정](../../../docs/framework/windows-workflow-foundation//customizing-the-workflow-design-experience.md)