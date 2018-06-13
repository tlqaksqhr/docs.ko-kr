---
title: Using Variables with a .NET Framework 3.5 Ruleset
ms.date: 03/30/2017
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
ms.openlocfilehash: 9fa6eaf58aaddc4673f08ec9a9001647a494877d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516858"
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a><span data-ttu-id="5c384-102">Using Variables with a .NET Framework 3.5 Ruleset</span><span class="sxs-lookup"><span data-stu-id="5c384-102">Using Variables with a .NET Framework 3.5 Ruleset</span></span>
<span data-ttu-id="5c384-103">이 샘플에서는 <xref:System.Activities.Statements.Interop> 활동을 사용하여 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]에서 작성되고 정책과 규칙을 사용하는 사용자 지정 활동을 통합하는 워크플로를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-103">This sample demonstrates how to create a workflow that uses the <xref:System.Activities.Statements.Interop> activity to integrate a custom activity written in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] that uses policy and rules.</span></span> <span data-ttu-id="5c384-104">이 샘플에서는 사용자 지정 활동에서 노출하는 종속성 속성에 변수를 바인딩하여 사용자 지정 활동에 데이터를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-104">The workflow passes data to the custom activity by binding variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="sample-walkthrough"></a><span data-ttu-id="5c384-105">샘플 연습</span><span class="sxs-lookup"><span data-stu-id="5c384-105">Sample walkthrough</span></span>  
  
#### <a name="to-examine-travelrulelibrary"></a><span data-ttu-id="5c384-106">TravelRuleLibrary를 검사하려면</span><span class="sxs-lookup"><span data-stu-id="5c384-106">To examine TravelRuleLibrary</span></span>  
  
1.  <span data-ttu-id="5c384-107">InteropWith35RuleSet.sln 솔루션 파일을 열고 Visual Studio를 사용 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-107">Using Visual Studio, open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="5c384-108">워크플로 디자이너에서 TravelRuleSet.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-108">Open the TravelRuleSet.cs in the workflow designer.</span></span>  
  
     <span data-ttu-id="5c384-109"><xref:System.Workflow.Activities.PolicyActivity>가 포함된 사용자 지정 순차 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-109">A custom sequential activity that contains a <xref:System.Workflow.Activities.PolicyActivity> is displayed.</span></span>  
  
3.  <span data-ttu-id="5c384-110">DiscountPolicy 정책 활동을 두 번 클릭하여 규칙을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-110">Double-click the DiscountPolicy policy activity to examine the rules.</span></span>  
  
     <span data-ttu-id="5c384-111">규칙 편집기에 규칙이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-111">The Rules editor pops up to show the rules.</span></span>  
  
4.  <span data-ttu-id="5c384-112">마우스 오른쪽 단추로 클릭는 `DiscountPolicy` 선택 하 고는 **코드 보기** 병행 C# 코드 활동에 대 한 코드를 검사 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-112">Right click the `DiscountPolicy` and select the **View Code** option to examine the code beside C# code for the activity.</span></span>  
  
     <span data-ttu-id="5c384-113">`DiscountLevel`의 종속성 속성 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-113">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="5c384-114">이 설정은 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]의 인수에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-114">This is equivalent to arguments in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span> <span data-ttu-id="5c384-115">인수에 대 한 자세한 내용은 참조 [변수 및 인수](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-115">For more information about arguments, see [Variables and Arguments](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span></span>  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="5c384-116">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="5c384-116">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="5c384-117"><xref:System.Activities.Statements.Interop> 활동을 사용하여 `TravelRuleLibrary` 프로젝트에 만든 사용자 지정 규칙 집합과 통합되는 순차 워크플로 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-117">This is a sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom Rule set created in the `TravelRuleLibrary` project.</span></span> <span data-ttu-id="5c384-118">변수는 최상위 <xref:System.Activities.Statements.Sequence> 활동에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-118">Variables are created on the top level <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="5c384-119"><xref:System.Activities.Statements.Interop> 활동은 `TravelRuleSet` 활동과 통합하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-119">The <xref:System.Activities.Statements.Interop> activity is used to integrate with the `TravelRuleSet` activity.</span></span> <span data-ttu-id="5c384-120"><xref:System.Activities.Statements.Sequence>에 선언된 변수는 종속성 속성에 바인딩하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-120">The variables that are declared on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="5c384-121">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="5c384-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="5c384-122">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 InteropWith35RuleSet.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="5c384-123">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="5c384-124">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5c384-125">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5c384-126">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5c384-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5c384-127">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="5c384-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5c384-128">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c384-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`