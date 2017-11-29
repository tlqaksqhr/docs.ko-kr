---
title: Advanced Policy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3dd941509c37618480a20530d3f5239750917e98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="advanced-policy"></a><span data-ttu-id="20ac7-102">Advanced Policy</span><span class="sxs-lookup"><span data-stu-id="20ac7-102">Advanced Policy</span></span>
<span data-ttu-id="20ac7-103">이 샘플은 Simple Policy 샘플의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-103">This sample extends the Simple Policy sample.</span></span> <span data-ttu-id="20ac7-104">Simple Policy 예제의 가계 할인 규칙과 기업 할인 규칙 이외에 새로운 규칙이 몇 가지 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-104">In addition to the residential discount and business discount rules from the Simple Policy example, several new rules have been added.</span></span>  
  
 <span data-ttu-id="20ac7-105">첫째, 고가치 규칙이 추가되어 값이 큰 주문에 대해 더 큰 할인을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-105">A high-value rule is added, which provides a bigger discount for high-value orders.</span></span> <span data-ttu-id="20ac7-106">이 규칙은 할인 필드를 덮어쓰고 가계 할인 규칙과 기업 할인 규칙보다 우선적으로 적용되도록 이전 두 규칙보다 작은 우선 순위 값이 부여되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-106">It is given a priority value less than the previous two rules so that it will overwrite the discount field and take precedence over both the residential and business discount rules.</span></span>  
  
 <span data-ttu-id="20ac7-107">둘째, 합계 계산 규칙이 추가되어 할인 수준을 기반으로 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-107">A calculate total rule is also added, which computes the total based on the discount level.</span></span> <span data-ttu-id="20ac7-108">워크플로 활동에 정의된 메서드를 참조하는 방법과 Else 작업 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-108">It shows how to reference a method defined on the workflow activity, as well as how to use else actions.</span></span> <span data-ttu-id="20ac7-109">이 규칙은 할인 필드가 변경될 때마다 확인되는 연결 동작을 보여 주기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-109">This rule also demonstrates chaining behavior since it will be evaluated anytime the discount field changes.</span></span> <span data-ttu-id="20ac7-110">뿐만 아니라 CalculateTotal 메서드의 RuleWriteAttribute를 사용하여 메서드 특성 지정도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-110">Furthermore, method attributing is shown with the RuleWriteAttribute on the CalculateTotal method.</span></span> <span data-ttu-id="20ac7-111">이로 인해 이 규칙의 영향을 받는 규칙(ErrorTotalRule)은 메서드가 실행될 때마다 재확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-111">This causes impacted rules (ErrorTotalRule) to be re-evaluated whenever the method gets executed.</span></span>  
  
 <span data-ttu-id="20ac7-112">셋째, 오류를 감지하는 규칙이 추가되었습니다(이 경우에는 합계가 0보다 작을 때).</span><span class="sxs-lookup"><span data-stu-id="20ac7-112">The last rule added is one that detects errors (in this case, Total less than 0).</span></span> <span data-ttu-id="20ac7-113">오류가 감지되면 정책 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-113">If this occurs, the policy execution is halted.</span></span>  
  
 <span data-ttu-id="20ac7-114">이러한 규칙 추가 외에도, 각 규칙에 `Console.Writeline` 호출이 작업으로 추가되어 규칙 실행 상황을 보기 쉬울 뿐만 아니라 참조된 형식의 정적 메서드에 액세스할 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-114">Finally, `Console.Writeline` calls are added as actions to each rule to provide more visibility into rule execution, while also showing that it is possible to access static methods on referenced types.</span></span> <span data-ttu-id="20ac7-115">사용자는 추적을 사용하여 실행된 규칙을 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-115">You could also use tracking to get visibility into the rules that are executed.</span></span>  
  
 <span data-ttu-id="20ac7-116">이 샘플에 사용된 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-116">The rules used in this sample are:</span></span>  
  
 <span data-ttu-id="20ac7-117">**ResidentialDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="20ac7-117">**ResidentialDiscountRule:**</span></span>  
  
 <span data-ttu-id="20ac7-118">IF OrderValue > 500 AND CustomerType = Residential</span><span class="sxs-lookup"><span data-stu-id="20ac7-118">IF OrderValue > 500 AND CustomerType = Residential</span></span>  
  
 <span data-ttu-id="20ac7-119">THEN Discount = 5%</span><span class="sxs-lookup"><span data-stu-id="20ac7-119">THEN Discount = 5%</span></span>  
  
 <span data-ttu-id="20ac7-120">**BusinessDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="20ac7-120">**BusinessDiscountRule:**</span></span>  
  
 <span data-ttu-id="20ac7-121">IF OrderValue > 10000 AND CustomerType = Business</span><span class="sxs-lookup"><span data-stu-id="20ac7-121">IF OrderValue > 10000 AND CustomerType = Business</span></span>  
  
 <span data-ttu-id="20ac7-122">THEN Discount = 10%</span><span class="sxs-lookup"><span data-stu-id="20ac7-122">THEN Discount = 10%</span></span>  
  
 <span data-ttu-id="20ac7-123">**HighValueDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="20ac7-123">**HighValueDiscountRule:**</span></span>  
  
 <span data-ttu-id="20ac7-124">IF OrderValue > 20000</span><span class="sxs-lookup"><span data-stu-id="20ac7-124">IF OrderValue > 20000</span></span>  
  
 <span data-ttu-id="20ac7-125">THEN Discount = 15%</span><span class="sxs-lookup"><span data-stu-id="20ac7-125">THEN Discount = 15%</span></span>  
  
 <span data-ttu-id="20ac7-126">**TotalRule:**</span><span class="sxs-lookup"><span data-stu-id="20ac7-126">**TotalRule:**</span></span>  
  
 <span data-ttu-id="20ac7-127">IF Discount > 0</span><span class="sxs-lookup"><span data-stu-id="20ac7-127">IF Discount > 0</span></span>  
  
 <span data-ttu-id="20ac7-128">THEN CalculateTotal(OrderValue, Discount)</span><span class="sxs-lookup"><span data-stu-id="20ac7-128">THEN CalculateTotal(OrderValue, Discount)</span></span>  
  
 <span data-ttu-id="20ac7-129">ELSE Total = OrderValue</span><span class="sxs-lookup"><span data-stu-id="20ac7-129">ELSE Total = OrderValue</span></span>  
  
 <span data-ttu-id="20ac7-130">**ErrorTotalRule:**</span><span class="sxs-lookup"><span data-stu-id="20ac7-130">**ErrorTotalRule:**</span></span>  
  
 <span data-ttu-id="20ac7-131">IF 총 \< 0</span><span class="sxs-lookup"><span data-stu-id="20ac7-131">IF Total \< 0</span></span>  
  
 <span data-ttu-id="20ac7-132">THEN Error = "Fired ErrorTotalRule"; Halt</span><span class="sxs-lookup"><span data-stu-id="20ac7-132">THEN Error = "Fired ErrorTotalRule"; Halt</span></span>  
  
 <span data-ttu-id="20ac7-133">규칙 확인 및 실행은 추적을 통해서도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-133">Rule evaluation and execution can also be seen through tracing and tracking.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="20ac7-134">이 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="20ac7-134">To build the sample</span></span>  
  
1.  <span data-ttu-id="20ac7-135">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-135">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="20ac7-136">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-136">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="20ac7-137">Ctrl+F5를 눌러 디버깅 없이 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-137">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="20ac7-138">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="20ac7-138">To run the sample</span></span>  
  
-   <span data-ttu-id="20ac7-139">SDK 명령 프롬프트 창에서 샘플의 주 폴더 아래에 있는 AdvancedPolicy\bin\debug 폴더 또는 AdvancedPolicy\bin 폴더(Visual Basic 버전 샘플의 경우)의 .exe 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-139">In the SDK Command Prompt window, run the .exe file in the AdvancedPolicy\bin\debug folder (or the AdvancedPolicy \bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="20ac7-140">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-140">The samples may already be installed on your computer.</span></span> <span data-ttu-id="20ac7-141">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="20ac7-141">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="20ac7-142">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="20ac7-142">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="20ac7-143">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20ac7-143">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a><span data-ttu-id="20ac7-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20ac7-144">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="20ac7-145">Simple Policy</span><span class="sxs-lookup"><span data-stu-id="20ac7-145">Simple Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
