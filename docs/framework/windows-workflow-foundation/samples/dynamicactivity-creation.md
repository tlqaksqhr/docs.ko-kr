---
title: "DynamicActivity 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8ebe82f-98c8-4452-aed7-2c60a512b097
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 43f39d5c78e59925ad73fe7277300848877f83f2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="dynamicactivity-creation"></a><span data-ttu-id="e6afa-102">DynamicActivity 만들기</span><span class="sxs-lookup"><span data-stu-id="e6afa-102">DynamicActivity Creation</span></span>
<span data-ttu-id="e6afa-103">이 샘플에서는 <xref:System.Activities.DynamicActivity> 활동을 사용하여 런타임에 활동을 만드는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-103">This sample demonstrates two different ways to create an activity at runtime using the <xref:System.Activities.DynamicActivity> activity.</span></span>  
  
 <span data-ttu-id="e6afa-104">이 샘플에서는 <xref:System.Activities.Statements.Sequence> 및 <xref:System.Activities.Statements.ForEach%601> 활동이 포함된 <xref:System.Activities.Statements.Assign%601> 활동이 들어 있는 본문을 사용하여 런타임에 활동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-104">In this sample, an activity is created at runtime with a body that contains a <xref:System.Activities.Statements.Sequence> activity that contains <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.Assign%601> activities.</span></span> <span data-ttu-id="e6afa-105">여기에서는 정수의 입력 목록이 활동에 전달되고 속성으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-105">An input list of integers is passed into the activity and set as a property.</span></span> <span data-ttu-id="e6afa-106">그런 다음 <xref:System.Activities.Statements.ForEach%601> 활동에서 값의 목록을 반복하며 누적 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-106">The <xref:System.Activities.Statements.ForEach%601> activity then iterates over the list of values and accumulates it.</span></span> <span data-ttu-id="e6afa-107"><xref:System.Activities.Statements.Assign%601> 활동에서는 목록의 요소 수로 누적기를 나눠 평균 값을 계산하고 그 결과를 평균에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-107">In the <xref:System.Activities.Statements.Assign%601> activity, the average value is calculated by dividing the accumulator by the number of elements in the list and assign it to the average.</span></span>  
  
 <span data-ttu-id="e6afa-108">이 샘플에서는 변수를 입력 인수로 이동하고 값을 출력 인수로 반환하는 <xref:System.Activities.DynamicActivity> 활동의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-108">The sample demonstrates the usage of a <xref:System.Activities.DynamicActivity> activity that flows in variables as input arguments and returning values as output arguments.</span></span> <span data-ttu-id="e6afa-109">이 활동에는 정수 목록인 `Numbers`라는 입력 인수 한 개가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-109">The activity has one input argument named `Numbers` that is a list of integers.</span></span> <span data-ttu-id="e6afa-110"><xref:System.Activities.Statements.ForEach%601> 활동에서 값의 목록을 반복하며 누적 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-110">The <xref:System.Activities.Statements.ForEach%601> activity iterates over the list of values and accumulates it.</span></span> <span data-ttu-id="e6afa-111"><xref:System.Activities.Statements.Assign%601> 활동에서는 목록의 요소 수로 누적기를 나눠 평균 값을 계산하고 그 결과를 평균에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-111">In the <xref:System.Activities.Statements.Assign%601> activity, the average value is calculated by dividing the accumulator by the number of elements in the list and assigning it to the average.</span></span> <span data-ttu-id="e6afa-112">평균은 `Average`라는 출력 인수로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-112">The average is returned as an output argument named `Average`.</span></span>  
  
 <span data-ttu-id="e6afa-113">프로그래밍 방식으로 동적 활동을 만드는 경우 입력과 출력이 다음 코드 예제에서와 같이 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-113">When the dynamic activity is created programmatically, the input and output are declared as shown in the following code example.</span></span>  
  
```csharp  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
};  
```  
  
 <span data-ttu-id="e6afa-114">다음 코드 예제에서는 목록의 값에 대한 평균을 계산하는 `DynamicActivity`의 완벽한 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-114">The following code example shows the complete definition of the `DynamicActivity` that computes the average of the values in a list.</span></span>  
  
```  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
    Implementation = () =>  
        new Sequence  
        {  
            Variables = { result, accumulator },  
            Activities =  
            {  
                new ForEach<int>  
                {  
                    Values =  new ArgumentValue<IEnumerable<int>> { ArgumentName = "Numbers" },                                  
                    Body = new ActivityAction<int>  
                    {  
                        Argument = iterationVariable,  
                        Handler = new Assign<int>  
                        {  
                            To = accumulator,  
                            Value = new InArgument<int>(env => iterationVariable.Get(env) +  accumulator.Get(env))  
                        }  
                    }  
                },  
  
                // Calculate the average and assign to the output argument.  
                new Assign<double>  
                {  
                    To = new ArgumentReference<double> { ArgumentName = "Average" },  
                    Value = new InArgument<double>(env => accumulator.Get(env) / numbers.Get(env).Count<int>())  
                },  
            }  
        }  
};  
```  
  
 <span data-ttu-id="e6afa-115">XAML에서 이를 만드는 경우 입력과 출력이 다음 예제에서와 같이 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-115">When created in XAML, the input and output are declared as shown in the following example.</span></span>  
  
```xml  
<Activity x:Class="Microsoft.Samples.DynamicActivityCreation.FindAverage"  
          xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
          xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Numbers" Type="InArgument(scg:List(x:Int32))" />  
    <x:Property Name="Average" Type="OutArgument(x:Double)" />  
  </x:Members>  
    ...  
    ...  
</Activity>  
```  
  
 <span data-ttu-id="e6afa-116">[!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]에서 XAML을 시각적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-116">The XAML can be created visually using the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)].</span></span> <span data-ttu-id="e6afa-117">Visual Studio 프로젝트에 포함 되어 있는 경우에 "빌드 작업"을 "None" 컴파일할 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-117">If it is included in a Visual Studio project, be sure to set its "Build Action" to "None" to prevent it from being compiled.</span></span> <span data-ttu-id="e6afa-118">그런 다음 아래와 같은 호출을 사용하여 동적으로 XAML을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-118">The XAML can then be loaded dynamically using the following call.</span></span>  
  
```  
Activity act2 = ActivityXamlServices.Load(@"FindAverage.xaml");  
```  
  
 <span data-ttu-id="e6afa-119">프로그래밍 방식으로 만들거나 XAML 워크플로를 로드하여 만든 <xref:System.Activities.DynamicActivity> 인스턴스를 다음 코드 예제에서와 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-119">The <xref:System.Activities.DynamicActivity> instance created programmatically or through loading a XAML workflow can be used as shown in the following code example.</span></span> <span data-ttu-id="e6afa-120">에 전달 된 "작동"는 점에 유의 하십시오는 `WorkflowInvoker.Invoke` 된 "act" <xref:System.Activities.Activity> 첫 번째 코드 예제에 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-120">Please note that "act" passed to the `WorkflowInvoker.Invoke` is the "act" <xref:System.Activities.Activity> defined in the first code example.</span></span>  
  
```  
IDictionary<string, object> results = WorkflowInvoker.Invoke(act, new Dictionary<string, object> { { "Numbers", numbers } });  
  
Console.WriteLine("The average calculated using the code activity is = " + results["Average"]);  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="e6afa-121">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="e6afa-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="e6afa-122">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 DynamicActivityCreation.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DynamicActivityCreation.sln solution file.</span></span>  
  
2.  <span data-ttu-id="e6afa-123">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="e6afa-124">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-124">To run the solution, press CTRL+F5.</span></span>  
  
## <a name="command-line-arguments"></a><span data-ttu-id="e6afa-125">명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="e6afa-125">Command line arguments</span></span>  
 <span data-ttu-id="e6afa-126">이 샘플에는 명령줄 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-126">This sample accepts command line arguments.</span></span> <span data-ttu-id="e6afa-127">활동에서 평균을 계산하는 데 필요한 숫자 목록을 사용자가 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-127">Users can provide a list of numbers for the activity to calculate their average.</span></span> <span data-ttu-id="e6afa-128">사용할 숫자의 목록을 입력할 때는 목록의 각 숫자를 공백으로 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-128">The list of numbers to be used is passed as a list of numbers separated by a space.</span></span> <span data-ttu-id="e6afa-129">예를 들어 5, 10, 32의 평균을 계산하려면 다음과 같은 명령줄을 사용하여 샘플을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-129">For example, to calculate the average of 5, 10, and 32 invoke the sample using the following command line.</span></span>  
  
 <span data-ttu-id="e6afa-130">**DynamicActivityCreation 5 10 32**</span><span class="sxs-lookup"><span data-stu-id="e6afa-130">**DynamicActivityCreation 5 10 32**</span></span>  
> [!IMPORTANT]
>  <span data-ttu-id="e6afa-131">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e6afa-132">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e6afa-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e6afa-133">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="e6afa-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e6afa-134">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6afa-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\DynamicActivityCreation`