---
title: "사용자 지정 복합 디자이너 - 워크플로 항목 프리젠터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 70055c4b-1173-47a3-be80-b5bce6f59e9a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b708d39ba6e5f53579f575d5e228de43db3d90a9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="custom-composite-designers---workflow-items-presenter"></a><span data-ttu-id="92c61-102">사용자 지정 복합 디자이너 - 워크플로 항목 프리젠터</span><span class="sxs-lookup"><span data-stu-id="92c61-102">Custom Composite Designers - Workflow Items Presenter</span></span>
<span data-ttu-id="92c61-103"><xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> 는 포함된 요소의 컬렉션을 편집할 수 있도록 하는 WF 디자이너 프로그래밍 모델의 키 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-103">The <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> is a key type in the WF designer programming model that allows for the editing of a collection of contained elements.</span></span> <span data-ttu-id="92c61-104">이 샘플에서는 이러한 편집 가능한 컬렉션을 표시하는 활동 디자이너를 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-104">This sample shows how to build an activity designer that surfaces such an editable collection.</span></span>  
  
 <span data-ttu-id="92c61-105">이 샘플에서는 다음 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-105">This sample demonstrates:</span></span>  
  
-   <span data-ttu-id="92c61-106"><xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>를 사용하여 사용자 지정 활동 디자이너 만들기</span><span class="sxs-lookup"><span data-stu-id="92c61-106">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="92c61-107">"축소" 또는 "확장" 보기를 사용 하 여 활동 디자이너 만들기</span><span class="sxs-lookup"><span data-stu-id="92c61-107">Creating an activity designer with a "collapsed" and "expanded" view.</span></span>  
  
-   <span data-ttu-id="92c61-108">다시 호스트된 응용 프로그램에서 기본 디자이너 재정의</span><span class="sxs-lookup"><span data-stu-id="92c61-108">Overriding a default designer in a rehosted application.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="92c61-109">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="92c61-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="92c61-110">열기는 **UsingWorkflowItemsPresenter.sln** C# 또는 VB에 대 한 샘플 솔루션 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-110">Open the **UsingWorkflowItemsPresenter.sln** sample solution for C# or for VB in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="92c61-111">솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-111">Build and run the solution.</span></span> <span data-ttu-id="92c61-112">다시 호스트된 Workflow Designer 응용 프로그램이 열리며 여기에서 활동을 캔버스로 끌어 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-112">A rehosted workflow designer application should open, and you can drag activities onto the canvas.</span></span>  
  
## <a name="sample-highlights"></a><span data-ttu-id="92c61-113">샘플의 중요 사항</span><span class="sxs-lookup"><span data-stu-id="92c61-113">Sample Highlights</span></span>  
 <span data-ttu-id="92c61-114">이 샘플의 코드는 다음 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-114">The code for this sample shows the following:</span></span>  
  
-   <span data-ttu-id="92c61-115">디자이너가 빌드되는 활동:  `Parallel`</span><span class="sxs-lookup"><span data-stu-id="92c61-115">The activity a designer is built for:  `Parallel`</span></span>  
  
-   <span data-ttu-id="92c61-116"><xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>를 사용하여 사용자 지정 활동 디자이너를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="92c61-116">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span> <span data-ttu-id="92c61-117">고려해야 할 몇 가지 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-117">A few things to point out:</span></span>  
  
    -   <span data-ttu-id="92c61-118">WPF 데이터 바인딩을 사용하여 `ModelItem.Branches`에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-118">Note the use of WPF data binding to bind to `ModelItem.Branches`.</span></span> <span data-ttu-id="92c61-119">`ModelItem`은 디자이너가 사용될 기본 개체(이 경우 `WorkflowElementDesigner`)를 참조하는 `Parallel`의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-119">`ModelItem` is the property on `WorkflowElementDesigner` that refers to the underlying object the designer is being used for, in this case, our `Parallel`.</span></span>  
  
    -   <span data-ttu-id="92c61-120"><xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType>을 사용하여 컬렉션의 개별 항목을 시각적으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-120">The <xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> can be used to put a visual to display between the individual items in the collection.</span></span>  
  
    -   <span data-ttu-id="92c61-121"><xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType>은 컬렉션에 있는 항목의 레이아웃을 결정하는 데 제공할 수 있는 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-121"><xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> is a template that can be provided to determine the layout of the items in the collection.</span></span> <span data-ttu-id="92c61-122">이 경우에는 가로 스택 패널이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-122">In this case, a horizontal stack panel is used.</span></span>  
  
 <span data-ttu-id="92c61-123">다음 코드 예제에서는 이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-123">This following example code shows this.</span></span>  
  
```xaml  
<sad:WorkflowItemsPresenter HintText="Drop Activities Here"  
                              Items="{Binding Path=ModelItem.Branches}">  
    <sad:WorkflowItemsPresenter.SpacerTemplate>  
      <DataTemplate>  
        <Ellipse Width="10" Height="10" Fill="Black"/>  
      </DataTemplate>  
    </sad:WorkflowItemsPresenter.SpacerTemplate>  
    <sad:WorkflowItemsPresenter.ItemsPanel>  
      <ItemsPanelTemplate>  
        <StackPanel Orientation="Horizontal"/>  
      </ItemsPanelTemplate>  
    </sad:WorkflowItemsPresenter.ItemsPanel>  
  </sad:WorkflowItemsPresenter>  
```  
  
-   <span data-ttu-id="92c61-124">`DesignerAttribute` 형식에 `Parallel`를 연결한 다음 보고되는 특성을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-124">Perform an association of the `DesignerAttribute` to the `Parallel` type and then output the attributes reported.</span></span>  
  
    -   <span data-ttu-id="92c61-125">먼저 모든 기본 디자이너를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-125">First, register all of the default designers.</span></span>  
  
 <span data-ttu-id="92c61-126">다음은 코드 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-126">The following is the code example.</span></span>  
  
```csharp  
// register metadata  
(new DesignerMetadata()).Register();  
RegisterCustomMetadata();  
```  
  
```vb  
' register metadata  
Dim metadata = New DesignerMetadata()  
metadata.Register()  
' register custom metadata  
RegisterCustomMetadata()  
```  
  
    -   <span data-ttu-id="92c61-127">그런 다음 `RegisterCustomMetadata` 메서드에서 병렬을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-127">Then, override the parallel in `RegisterCustomMetadata` method.</span></span>  
  
 <span data-ttu-id="92c61-128">다음 코드에서는 C# 및 Visual Basic으로 이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-128">The following code shows this in C# and Visual Basic.</span></span>  
 
```csharp  
void RegisterCustomMetadata()  
{  
      AttributeTableBuilder builder = new AttributeTableBuilder();  
      builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));  
      MetadataStore.AddAttributeTable(builder.CreateTable());  
}  
```  
  
```vb  
Sub RegisterCustomMetadata()  
   Dim builder As New AttributeTableBuilder()  
   builder.AddCustomAttributes(GetType(Parallel), New DesignerAttribute(GetType(CustomParallelDesigner)))  
   MetadataStore.AddAttributeTable(builder.CreateTable())  
End Sub  
```  
  
-   <span data-ttu-id="92c61-129">마지막으로, 다양한 데이터 템플릿과 트리거를 사용하여 `IsRootDesigner` 속성을 기반으로 적절한 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-129">Finally, note the use of differing data templates and triggers to select the appropriate template based on the `IsRootDesigner` property.</span></span>  
  
 <span data-ttu-id="92c61-130">다음은 코드 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-130">The following is the code example.</span></span>  
  
```xaml  
<sad:ActivityDesigner x:Class="Microsoft.Samples.CustomParallelDesigner"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:sad="clr-namespace:System.Activities.Design;assembly=System.Activities.Design"  
    xmlns:sadv="clr-namespace:System.Activities.Design.View;assembly=System.Activities.Design">  
  <sad:ActivityDesigner.Resources>  
    <DataTemplate x:Key="Expanded">  
      <StackPanel>  
        <TextBlock>This is the Expanded View</TextBlock>  
        <sad:WorkflowItemsPresenter HintText="Drop Activities Here"  
                                    Items="{Binding Path=ModelItem.Branches}">  
          <sad:WorkflowItemsPresenter.SpacerTemplate>  
            <DataTemplate>  
              <Ellipse Width="10" Height="10" Fill="Black"/>  
            </DataTemplate>  
          </sad:WorkflowItemsPresenter.SpacerTemplate>  
          <sad:WorkflowItemsPresenter.ItemsPanel>  
            <ItemsPanelTemplate>  
              <StackPanel Orientation="Horizontal"/>  
            </ItemsPanelTemplate>  
          </sad:WorkflowItemsPresenter.ItemsPanel>  
        </sad:WorkflowItemsPresenter>  
      </StackPanel>  
    </DataTemplate>  
    <DataTemplate x:Key="Collapsed">  
      <TextBlock>This is the Collapsed View</TextBlock>  
    </DataTemplate>  
    <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
      <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
      <Style.Triggers>  
        <DataTrigger Binding="{Binding Path=IsRootDesigner}" Value="true">  
          <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
        </DataTrigger>  
      </Style.Triggers>  
    </Style>  
  </sad: ActivityDesigner.Resources>  
  <Grid>  
    <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>  
  </Grid>  
</sad: ActivityDesigner>  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="92c61-131">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="92c61-132">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="92c61-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="92c61-133">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="92c61-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="92c61-134">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c61-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemsPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="92c61-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92c61-135">See Also</span></span>  
 <xref:System.Activities.Presentation.WorkflowItemsPresenter>  
 [<span data-ttu-id="92c61-136">워크플로 디자이너로 응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="92c61-136">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
