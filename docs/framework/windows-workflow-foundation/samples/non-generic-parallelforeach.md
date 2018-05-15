---
title: 비제네릭 ParallelForEach
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bb74af3763e21b0f3529319a1c0fdbd7145632e6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="non-generic-parallelforeach"></a><span data-ttu-id="1e0b4-102">비제네릭 ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="1e0b4-102">Non-Generic ParallelForEach</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="1e0b4-103"> 도구 상자에 포함 하 여 제어 흐름 작업 집합이 제공 <xref:System.Activities.Statements.ParallelForEach%601>, 반복할 수 있도록는 <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-103"> ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ParallelForEach%601>, which allows iterating through <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` collections.</span></span>  
  
 <span data-ttu-id="1e0b4-104"><xref:System.Activities.Statements.ParallelForEach%601> 필요한 해당 <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> 속성 형식이 되도록 <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-104"><xref:System.Activities.Statements.ParallelForEach%601> requires its <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> property to be of type <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span></span> <span data-ttu-id="1e0b4-105">사용자가를 구현 하는 데이터 구조 반복 불가능이 <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` 인터페이스 (예를 들어 <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="1e0b4-105">This precludes users from iterating over data structures that implement <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="1e0b4-106"><xref:System.Activities.Statements.ParallelForEach%601>의 비제네릭 버전은 컬렉션 값의 형식에 대한 호환성을 유지하기 위해 런타임 복잡성이 더 높아지지만 이러한 요구 사항의 제약을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-106">The non-generic version of <xref:System.Activities.Statements.ParallelForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="1e0b4-107">이 샘플에서는 비제네릭 <xref:System.Activities.Statements.ParallelForEach%601> 활동과 디자이너를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ParallelForEach%601> activity and its designer.</span></span> <span data-ttu-id="1e0b4-108">이 활동을 사용하여 <xref:System.Collections.ArrayList>를 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="parallelforeach-activity"></a><span data-ttu-id="1e0b4-109">ParallelForEach 활동</span><span class="sxs-lookup"><span data-stu-id="1e0b4-109">ParallelForEach Activity</span></span>  
 <span data-ttu-id="1e0b4-110">C#/VB `foreach` 문은 컬렉션의 각 요소에 대해 포함 문을 실행하여 컬렉션의 요소를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-110">The C#/VB `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="1e0b4-111">그에 상응하는 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 활동은 <xref:System.Activities.Statements.ForEach%601> 및 <xref:System.Activities.Statements.ParallelForEach%601>입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="1e0b4-112"><xref:System.Activities.Statements.ForEach%601> 활동은 값 목록과 본문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="1e0b4-113">런타임에 목록이 반복되고 목록의 각 값에 대해 본문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="1e0b4-114"><xref:System.Activities.Statements.ParallelForEach%601>에는 <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>이 있습니다. <xref:System.Activities.Statements.ParallelForEach%601>의 반환 결과가 <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>이면 `true` 활동이 일찍 완료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-114"><xref:System.Activities.Statements.ParallelForEach%601> has a <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, so that the <xref:System.Activities.Statements.ParallelForEach%601> activity could complete early if the evaluation of the <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> returns `true`.</span></span> <span data-ttu-id="1e0b4-115"><xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>은 각 반복을 완료한 후에 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-115">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> is evaluated after each iteration is completed.</span></span>  
  
 <span data-ttu-id="1e0b4-116">대부분의 경우 제네릭 버전의 활동이 기본 솔루션이어야 합니다. 제네릭 버전은 이를 사용하는 대부분의 시나리오에 적용되고 컴파일 시 형식 검사 기능을 제공하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-116">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it is used and provides type checking at compile time.</span></span> <span data-ttu-id="1e0b4-117">비제네릭 <xref:System.Collections.IEnumerable> 인터페이스를 구현하는 형식을 반복하는 데는 비제네릭 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-117">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="1e0b4-118">클래스 정의</span><span class="sxs-lookup"><span data-stu-id="1e0b4-118">Class Definition</span></span>  
 <span data-ttu-id="1e0b4-119">다음 코드 예제에서는 비제네릭 `ParallelForEach` 활동의 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-119">The following code example shows the definition of a non-generic `ParallelForEach` activity is.</span></span>  
  
```  
[ContentProperty("Body")]  
public class ParallelForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    public Activity<bool> CompletionCondition  
    [DefaultValue(null)]  
    [DependsOn("CompletionCondition")]  
    ActivityAction<object> Body { get; set; }   
}  
```  
  
 <span data-ttu-id="1e0b4-120">Body(옵션)</span><span class="sxs-lookup"><span data-stu-id="1e0b4-120">Body (optional)</span></span>  
 <span data-ttu-id="1e0b4-121">컬렉션의 각 요소에 대해 실행되는 <xref:System.Activities.ActivityAction> 형식의 <xref:System.Object>입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-121">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="1e0b4-122">각 개별 요소는 Argument 속성을 통해 본문에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-122">Each individual element is passed into the Body through its Argument property.</span></span>  
  
 <span data-ttu-id="1e0b4-123">Values(옵션)</span><span class="sxs-lookup"><span data-stu-id="1e0b4-123">Values (optional)</span></span>  
 <span data-ttu-id="1e0b4-124">반복되는 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-124">The collection of elements that are iterated over.</span></span> <span data-ttu-id="1e0b4-125">컬렉션의 모든 요소가 호환 가능한 형식인지 확인하는 작업은 런타임에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-125">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
 <span data-ttu-id="1e0b4-126">CompletionCondition(옵션)</span><span class="sxs-lookup"><span data-stu-id="1e0b4-126">CompletionCondition (optional)</span></span>  
 <span data-ttu-id="1e0b4-127"><xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> 속성은 반복을 완료한 후에 매번 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-127">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> property is evaluated after any iteration completes.</span></span> <span data-ttu-id="1e0b4-128">그 결과가 `true`이면 예약하여 대기 중인 반복이 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-128">If it evaluates to `true`, then the scheduled pending iterations are canceled.</span></span> <span data-ttu-id="1e0b4-129">이 속성을 설정하지 않으면 Branches 컬렉션의 모든 활동이 완료될 때까지 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-129">If this property is not set, all activities in the Branches collection execute until completion.</span></span>  
  
## <a name="example-of-using-parallelforeach"></a><span data-ttu-id="1e0b4-130">ParallelForEach 사용 예제</span><span class="sxs-lookup"><span data-stu-id="1e0b4-130">Example of Using ParallelForEach</span></span>  
 <span data-ttu-id="1e0b4-131">다음 코드에서는 응용 프로그램에서 ParallelForEach 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-131">The following code demonstrates how to use the ParallelForEach activity in an application.</span></span>  
  
```  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ParallelForEach  
    {  
       Values = new InArgument<IEnumerable>(c=> names),  
       Body = new ActivityAction<object>   
       {                          
           Argument = iterationVariable,  
           Handler = new WriteLine  
           {  
               Text = new InArgument<string>(env => string.Format("Hello {0}",                                                               iterationVariable.Get(env)))  
           }  
       }  
   };  
```  
  
## <a name="parallelforeach-designer"></a><span data-ttu-id="1e0b4-132">ParallelForEach 디자이너</span><span class="sxs-lookup"><span data-stu-id="1e0b4-132">ParallelForEach Designer</span></span>  
 <span data-ttu-id="1e0b4-133">샘플의 활동 디자이너는 기본 제공 <xref:System.Activities.Statements.ParallelForEach%601> 활동에 제공되는 디자이너와 모양이 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-133">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span> <span data-ttu-id="1e0b4-134">디자이너의 도구 상자에 표시 된 **샘플**, **비 제네릭 활동** 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-134">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="1e0b4-135">디자이너 라는 **ParallelForEachWithBodyFactory** 도구 상자에서 활동을 노출 하기 때문에 <xref:System.Activities.Presentation.IActivityTemplateFactory> 올바르게 구성 된 활동을 만드는 도구 상자에서 <xref:System.Activities.ActivityAction>합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-135">The designer is named **ParallelForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox that creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```  
public sealed class ParallelForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ParallelForEach()  
        {  
            Body = new ActivityAction<object>()  
            {  
                Argument = new DelegateInArgument<object>()  
                {  
                    Name = "item"  
                }  
            }  
        };  
    }  
}  
```  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="1e0b4-136">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="1e0b4-136">To run the sample</span></span>  
  
1.  <span data-ttu-id="1e0b4-137">선택한 프로젝트를 솔루션의 시작 프로젝트로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-137">Set the project of your choice as the startup project of the solution.</span></span>  
  
    1.  <span data-ttu-id="1e0b4-138">**CodeTestClient** 코드를 사용 하 여 활동을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-138">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2.  <span data-ttu-id="1e0b4-139">**DesignerTestClient** 디자이너 내에서 활동을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-139">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2.  <span data-ttu-id="1e0b4-140">프로젝트를 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-140">Build and run the project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1e0b4-141">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-141">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1e0b4-142">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-142">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1e0b4-143">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-143">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1e0b4-144">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e0b4-144">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
