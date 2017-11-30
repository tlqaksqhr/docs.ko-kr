---
title: "사용자 지정 복합 디자이너 - 워크플로 항목 프리젠터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3fa40a7a864ae65d15d787f5dec58a8da7b8e9a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="bb5fb-102">사용자 지정 복합 디자이너 - 워크플로 항목 프리젠터</span><span class="sxs-lookup"><span data-stu-id="bb5fb-102">Custom Composite Designers - Workflow Item Presenter</span></span>
<span data-ttu-id="bb5fb-103"><xref:System.Activities.Presentation.WorkflowItemPresenter> 임의의 활동을 배치할 수 있는 "끌어 놓기 영역"을 만들 수 있도록 하는 WF 디자이너 프로그래밍 모델의 키 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="bb5fb-104">이 예제에서는 "드롭 영역" 같은."해당 표면 활동 디자이너를 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>  
  
 <span data-ttu-id="bb5fb-105">이 샘플에서는 다음 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-105">This sample demonstrates:</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="bb5fb-106">세부 항목</span><span class="sxs-lookup"><span data-stu-id="bb5fb-106">Demonstrates</span></span>  
  
-   <span data-ttu-id="bb5fb-107"><xref:System.Activities.Presentation.WorkflowItemPresenter>를 사용하여 사용자 지정 활동 디자이너 만들기</span><span class="sxs-lookup"><span data-stu-id="bb5fb-107">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>  
  
-   <span data-ttu-id="bb5fb-108">메타데이터 저장소를 사용하여 사용자 지정 디자이너 등록</span><span class="sxs-lookup"><span data-stu-id="bb5fb-108">Registering the custom designer using the metadata store.</span></span>  
  
-   <span data-ttu-id="bb5fb-109">다시 호스트된 도구 상자를 선언적으로 또는 명령적으로 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="bb5fb-109">Programming the rehosted toolbox declaratively and imperatively.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="bb5fb-110">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="bb5fb-110">Sample Details</span></span>  
 <span data-ttu-id="bb5fb-111">이 샘플의 코드는 다음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-111">The code for this sample shows:</span></span>  
  
-   <span data-ttu-id="bb5fb-112">`SimpleNativeActivity` 클래스에 대해 사용자 지정 활동 디자이너가 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-112">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>  
  
-   <span data-ttu-id="bb5fb-113"><xref:System.Activities.Presentation.WorkflowItemPresenter>를 사용하여 사용자 지정 활동 디자이너를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="bb5fb-113">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>  
  
```xaml  
<sap:ActivityDesigner x:Class="Microsoft.Samples.UsingWorkflowItemPresenter.SimpleNativeDesigner"  
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
  
 <span data-ttu-id="bb5fb-114">WPF 데이터 바인딩을 사용하여 `ModelItem.Body`에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-114">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="bb5fb-115">`ModelItem`에 속성 <xref:System.Activities.Presentation.ActivityDesigner> 디자이너 사용 되 고,이 경우 기본 개체를 참조 하는 **SimpleNativeActivity**합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-115">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>  
  
#### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="bb5fb-116">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="bb5fb-116">To setup, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="bb5fb-117">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-117">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="bb5fb-118">F5 키를 눌러 응용 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-118">Press F5 to compile and run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bb5fb-119">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bb5fb-120">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bb5fb-121">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bb5fb-122">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb5fb-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="bb5fb-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb5fb-123">See Also</span></span>  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 [<span data-ttu-id="bb5fb-124">워크플로 디자이너로 응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="bb5fb-124">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
