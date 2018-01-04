---
title: "값 범위에서 전환할 사용자 지정 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 441e0a17-421f-430c-ba97-59e4cc6c88e3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13c409865846acdf7b557c20330f9a2fd62d47d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="custom-activity-to-switch-on-a-range-of-values"></a><span data-ttu-id="2541b-102">값 범위에서 전환할 사용자 지정 활동</span><span class="sxs-lookup"><span data-stu-id="2541b-102">Custom Activity to Switch on a Range of Values</span></span>
<span data-ttu-id="2541b-103">이 샘플에서는 <xref:System.Activities.Statements.Switch%601>의 사용을 확장하는 사용자 지정 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-103">This sample demonstrates how to create a custom activity that extends the use of a <xref:System.Activities.Statements.Switch%601>.</span></span> <span data-ttu-id="2541b-104">일반적인 <xref:System.Activities.Statements.Switch%601> 문을 사용하면 단일 값에 따라 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-104">A conventional <xref:System.Activities.Statements.Switch%601> statement allows switching based upon a single value.</span></span> <span data-ttu-id="2541b-105">그러나 값 범위에 따라 활동을 전환해야 하는 비즈니스 시나리오도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-105">But, there are business scenarios where an activity must switch based upon a range of values.</span></span> <span data-ttu-id="2541b-106">예를 들어 활동이 전환되는 기준 값이 1과 5 사이인 경우 하나의 동작을 실행하고 값이 6에서 10 사이인 경우 다른 동작을 실행하고 다른 모든 값의 경우 기본 동작을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-106">For example, an activity might execute one action when the value being switched upon is between 1 and 5, another action when the value is between 6 and 10, and a default action for all other values.</span></span> <span data-ttu-id="2541b-107">이 사용자 지정 활동을 사용하면 해당 시나리오를 정확하게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-107">This custom activity enables exactly that scenario.</span></span>  
  
## <a name="the-switchrange-activity"></a><span data-ttu-id="2541b-108">SwitchRange 활동</span><span class="sxs-lookup"><span data-stu-id="2541b-108">The SwitchRange Activity</span></span>  
 <span data-ttu-id="2541b-109">`SwitchRange` 활동은 식의 결과 값이 `Cases` 중 하나의 범위 내에 포함되는 경우 자식 활동을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-109">The `SwitchRange` activity schedules a child activity when the result value of its expression is included within the range of one of its `Cases`.</span></span>  
  
 <span data-ttu-id="2541b-110">다음 코드 예제는 값 범위에 따라 전환되는 사용자 지정 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-110">The following code example is a custom activity that switches based upon a range of values.</span></span>  
  
```csharp  
public sealed class SwitchRange<T> : NativeActivity where T : IComparable  
{  
   [RequiredArgument]  
   [DefaultValue(null)]  
   public InArgument<T> Expression { get; set; }  
  
   public IList<CaseRange<T>> Cases  
  
   [DefaultValue(null)]  
   public Activity Default { get; set; }}  
}  
```  
  
|<span data-ttu-id="2541b-111">속성</span><span class="sxs-lookup"><span data-stu-id="2541b-111">Property</span></span>|<span data-ttu-id="2541b-112">설명</span><span class="sxs-lookup"><span data-stu-id="2541b-112">Description</span></span>|  
|-|-|  
|<span data-ttu-id="2541b-113">식</span><span class="sxs-lookup"><span data-stu-id="2541b-113">Expression</span></span>|<span data-ttu-id="2541b-114">Cases 목록의 범위를 기준으로 계산 및 비교될 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-114">This is the expression to be evaluated and compared against the ranges in the Cases list.</span></span> <span data-ttu-id="2541b-115">식의 결과 형식은 T 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-115">The result of the expression is of type T.</span></span>|  
|<span data-ttu-id="2541b-116">Cases</span><span class="sxs-lookup"><span data-stu-id="2541b-116">Cases</span></span>|<span data-ttu-id="2541b-117">각 케이스는 범위(시작과 끝)와 활동(본문)으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-117">Each case consists of a range (From and To) and an activity (Body).</span></span> <span data-ttu-id="2541b-118">식은 범위를 기준으로 계산 및 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-118">The expression is evaluated and compared against the ranges.</span></span> <span data-ttu-id="2541b-119">식의 결과가 케이스 중 하나의 범위 내에 있는 경우 해당 활동이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-119">If the result of the expression is within the range of one of the cases, the corresponding activity is executed.</span></span>|  
|<span data-ttu-id="2541b-120">기본</span><span class="sxs-lookup"><span data-stu-id="2541b-120">Default</span></span>|<span data-ttu-id="2541b-121">일치하는 케이스가 없는 경우 실행되는 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-121">The activity that is executed when no case is matched.</span></span> <span data-ttu-id="2541b-122">`null`로 설정되어 있으면 아무 동작도 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-122">When set to `null`, no action is taken.</span></span>|  
  
## <a name="caserange-class"></a><span data-ttu-id="2541b-123">CaseRange 클래스</span><span class="sxs-lookup"><span data-stu-id="2541b-123">CaseRange Class</span></span>  
 <span data-ttu-id="2541b-124">`CaseRange` 클래스는 `SwitchRange` 활동 내의 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-124">The `CaseRange` class represents a range within a `SwitchRange` activity.</span></span> <span data-ttu-id="2541b-125">`CaseRange`의 모든 인스턴스에는 범위(`From` 과 `To`로 구성)와 `Body`의 식이 범위 내에서 계산되는 경우 예약되는 `SwitchRange` 활동이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-125">Every instance of `CaseRange` contains a range (composed of a `From` and a `To`) and a `Body` activity that is scheduled if the expression in the `SwitchRange` is evaluated within the range.</span></span>  
  
 <span data-ttu-id="2541b-126">다음 코드 예제는 `CaseRange` 클래스에 대한 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-126">The following code example is the definition for the `CaseRange` class.</span></span>  
  
```  
public class CaseRange<T> where T : IComparable  
{  
    public T From { get; set; }  
  
    public T To { get; set; }  
  
    public Activity Action { get; set; }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="2541b-127">샘플에 정의된 `SwitchRange` 및 `CaseRange` 클래스는 `IComparable`을 구현하는 모든 형식을 사용할 수 있는 제네릭 클래스입니다(예: <xref:System.Activities.Statements.Switch%601> 클래스).</span><span class="sxs-lookup"><span data-stu-id="2541b-127">Both the `SwitchRange` and `CaseRange` classes, which are defined in the sample are generic classes that can work with any type that implements `IComparable`, like the <xref:System.Activities.Statements.Switch%601> class.</span></span>  
  
## <a name="sample-usage"></a><span data-ttu-id="2541b-128">샘플 사용</span><span class="sxs-lookup"><span data-stu-id="2541b-128">Sample Usage</span></span>  
 <span data-ttu-id="2541b-129">다음 코드 예제에서는 `SwitchRange` 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-129">The following code example demonstrates how to use the `SwitchRange` activity.</span></span>  
  
```csharp  
Activity SwitchRange = new SwitchRange<int>  
{  
    Expression = new InArgument<int>(value),  
    Cases =   
    {  
        new CaseRange<int>                      
        {  
            From = 1,  
            To = 5,  
            Action = new WriteLine  
            {  
                Text = "Case 1-5 selected",  
            }  
        },  
        new CaseRange<int>  
        {  
            From = 6,  
            To = 10,  
            Action = new WriteLine  
            {  
                Text = "Case 6-10 selected",  
            }  
        }  
    },  
    Default = new WriteLine { Text = "Default Case selected" }  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="2541b-130">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="2541b-130">To use this sample</span></span>  
  
1.  <span data-ttu-id="2541b-131">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 SwitchRange.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-131">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the SwitchRange.sln solution file.</span></span>  
  
2.  <span data-ttu-id="2541b-132">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-132">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="2541b-133">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-133">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2541b-134">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-134">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2541b-135">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2541b-135">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2541b-136">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="2541b-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2541b-137">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2541b-137">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SwitchRange`