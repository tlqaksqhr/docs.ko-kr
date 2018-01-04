---
title: "디자이너 재호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b676ad31-5f64-4d84-9a36-b4d7113a2f4d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44577450bb81e255caf22f306dcd0276821d262c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="designer-rehosting"></a><span data-ttu-id="301f0-102">디자이너 재호스팅</span><span class="sxs-lookup"><span data-stu-id="301f0-102">Designer ReHosting</span></span>
<span data-ttu-id="301f0-103">디자이너 재호스팅은 사용자 지정 응용 프로그램 내에 워크플로 디자인 캔버스를 호스트하는 방식을 가리키는 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-103">Designer rehosting is a common scenario that refers to hosting the workflow design canvas inside of a custom application.</span></span> <span data-ttu-id="301f0-104">대부분의 사람들이 가장 잘 알고 있는 호스팅 응용 프로그램은 Visual Studio이지만, 응용 프로그램에 Workflow Designer를 표시하는 것이 유용할 수 있는 시나리오는 그 밖에도 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-104">The hosting application most people are familiar with is Visual Studio, however there are a number of scenarios where showing the workflow designer in an application may be useful:</span></span>  
  
-   <span data-ttu-id="301f0-105">최종 사용자가 현재 활성 상태 등 프로세스에 대한 런타임 데이터와 프로세스를 시각화하고 실행 시간 데이터 또는 워크플로 인스턴스에 대한 기타 정보를 집계하는 데 사용할 수 있는 모니터링 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="301f0-105">Monitoring applications (allowing an end user to visualize the process, as well as runtime data about the process such as the currently active state, aggregate execution time data, or other information about an instance of the workflow).</span></span>  
  
-   <span data-ttu-id="301f0-106">한정된 활동 집합으로 프로세스를 사용자 지정하는 데 사용할 수 있는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="301f0-106">Applications that allow a user to customize the process with a limited set of activities.</span></span>  
  
 <span data-ttu-id="301f0-107">이러한 유형의 응용 프로그램을 지원하기 위해 .NET Framework 내에 Workflow Designer가 함께 제공되며, 이 Workflow Designer를 WPF 응용 프로그램 내에 호스트하거나 적절한 WPF 호스팅 코드를 사용하여 WinForms 응용 프로그램에 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-107">To support these types of applications, the workflow designer ships inside the .NET Framework, and can be hosted inside a WPF application, or in a WinForms application with the appropriate WPF hosting code.</span></span> <span data-ttu-id="301f0-108">이 샘플에서는 다음 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-108">This sample demonstrates:</span></span>  
  
-   <span data-ttu-id="301f0-109">WF 디자이너 재호스팅</span><span class="sxs-lookup"><span data-stu-id="301f0-109">Rehosting the WF designer.</span></span>  
  
-   <span data-ttu-id="301f0-110">재호스트된 도구 상자 및 속성 표 사용</span><span class="sxs-lookup"><span data-stu-id="301f0-110">Using the rehosted toolbox and property grid as well.</span></span>  
  
## <a name="rehosting-the-designer"></a><span data-ttu-id="301f0-111">디자이너 재호스팅</span><span class="sxs-lookup"><span data-stu-id="301f0-111">Rehosting the designer</span></span>  
 <span data-ttu-id="301f0-112">이 샘플에서는 다음과 같은 표 레이아웃에 표시되는 디자이너를 포함할 WPF 레이아웃을 만드는 방법을 보여 줍니다. (공간의 제약 때문에 도구 상자 코드는 생략했습니다.)</span><span class="sxs-lookup"><span data-stu-id="301f0-112">This sample shows how to create the WPF layout to contain the designer, seen in the following grid layout (Toolbox code omitted for space concerns).</span></span> <span data-ttu-id="301f0-113">여기에서는 디자이너와 속성 표가 포함되는 테두리의 이름에 주목할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-113">Note the naming of the borders which contain the designer and property grid.</span></span>  
  
```xaml  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition Width="2*"/>  
        <ColumnDefinition Width="7*"/>  
        <ColumnDefinition Width="3*"/>  
    </Grid.ColumnDefinitions>  
    <Border Grid.Column="0">  
        <sapt:ToolboxControl>...</sapt:ToolboxControl>  
    </Border>  
    <Border Grid.Column="1" Name="DesignerBorder"/>  
    <Border Grid.Column="2" Name="PropertyBorder"/>  
</Grid>  
```  
  
 <span data-ttu-id="301f0-114">다음으로 이 샘플에서는 디자이너를 만들고 해당 기본 <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> 및 <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A>를 사용자 인터페이스의 적절한 컨테이너와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-114">Next the sample creates the designer, and associates its primary <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> with the appropriate container in the user interface.</span></span> <span data-ttu-id="301f0-115">아래에 추가로 나와 있는 몇몇 코드 줄에 대해서는 약간의 설명이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-115">There are a few additional lines of code in the following example that merit some explanation.</span></span> <span data-ttu-id="301f0-116"><xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> 호출은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에 제공되는 활동에 대한 기본 활동 디자이너를 연결하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-116">The <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> call is required to associate the default activity designers for the activities shipped with [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="301f0-117"><xref:System.Activities.Presentation.WorkflowDesigner.Load%2A>는 편집할 WF 항목을 전달하기 위해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-117"><xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> is called to pass in the WF item to be edited.</span></span> <span data-ttu-id="301f0-118">마지막으로, <xref:System.Activities.Presentation.WorkflowDesigner.View%2A>(기본 캔버스) 및 <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A>(속성 표)가 사용자 인터페이스 화면에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-118">Finally, the <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (primary canvas) and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (property grid) are placed onto the user interface surface.</span></span>  
  
```csharp  
protected override void OnInitialized(EventArgs e)  
{  
   base.OnInitialized(e);  
   // register metadata  
   (new DesignerMetadata()).Register();  
  
   // create the workflow designer  
   WorkflowDesigner wd = new WorkflowDesigner();  
   wd.Load(new Sequence());  
   DesignerBorder.Child = wd.View;  
   PropertyBorder.Child = wd.PropertyInspectorView;  
}  
```  
  
## <a name="using-the-rehosted-toolbox"></a><span data-ttu-id="301f0-119">재호스트된 도구 상자 사용</span><span class="sxs-lookup"><span data-stu-id="301f0-119">Using the rehosted toolbox</span></span>  
 <span data-ttu-id="301f0-120">이 샘플에서는 재호스트된 도구 상자 컨트롤을 XAML에 선언적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-120">This sample uses the rehosted toolbox control declaratively in XAML.</span></span> <span data-ttu-id="301f0-121">코드에서 <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper> 생성자에 형식을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-121">Note that in code, one can pass a type to the <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper> constructor.</span></span>  
  
```xaml  
<!-- Copyright (c) Microsoft Corporation. All rights reserved-->  
<Window x:Class="Microsoft.Samples.DesignerRehosting.RehostingWfDesigner"  
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
            <sapt:ToolboxControl>  
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
  
#### <a name="using-the-sample"></a><span data-ttu-id="301f0-122">샘플 사용</span><span class="sxs-lookup"><span data-stu-id="301f0-122">Using the sample</span></span>  
  
1.  <span data-ttu-id="301f0-123">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 DesignerRehosting.sln 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-123">Open the DesignerRehosting.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="301f0-124">F5 키를 눌러 응용 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-124">Press F5 to compile and run the application.</span></span>  
  
3.  <span data-ttu-id="301f0-125">재호스트된 디자이너와 함께 WPF 응용 프로그램이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-125">A WPF application starts with a rehosted designer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="301f0-126">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="301f0-127">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="301f0-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="301f0-128">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="301f0-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="301f0-129">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="301f0-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\DesignerRehosting\Basic`