---
title: Using Variables with a .NET Framework 3.5 Ruleset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a5d0be8f8d88581e889ea2a659037f424a9a1c89
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a><span data-ttu-id="053c9-102">Using Variables with a .NET Framework 3.5 Ruleset</span><span class="sxs-lookup"><span data-stu-id="053c9-102">Using Variables with a .NET Framework 3.5 Ruleset</span></span>
<span data-ttu-id="053c9-103">이 샘플에서는 <xref:System.Activities.Statements.Interop> 활동을 사용하여 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]에서 작성되고 정책과 규칙을 사용하는 사용자 지정 활동을 통합하는 워크플로를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-103">This sample demonstrates how to create a workflow that uses the <xref:System.Activities.Statements.Interop> activity to integrate a custom activity written in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] that uses policy and rules.</span></span> <span data-ttu-id="053c9-104">이 샘플에서는 사용자 지정 활동에서 노출하는 종속성 속성에 변수를 바인딩하여 사용자 지정 활동에 데이터를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-104">The workflow passes data to the custom activity by binding variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="sample-walkthrough"></a><span data-ttu-id="053c9-105">샘플 연습</span><span class="sxs-lookup"><span data-stu-id="053c9-105">Sample walkthrough</span></span>  
  
#### <a name="to-examine-travelrulelibrary"></a><span data-ttu-id="053c9-106">TravelRuleLibrary를 검사하려면</span><span class="sxs-lookup"><span data-stu-id="053c9-106">To examine TravelRuleLibrary</span></span>  
  
1.  <span data-ttu-id="053c9-107">[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 InteropWith35RuleSet.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-107">Using [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="053c9-108">Workflow Designer에서 TravelRuleSet.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-108">Open the TravelRuleSet.cs in the workflow designer.</span></span>  
  
     <span data-ttu-id="053c9-109"><xref:System.Workflow.Activities.PolicyActivity>가 포함된 사용자 지정 순차 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-109">A custom sequential activity that contains a <xref:System.Workflow.Activities.PolicyActivity> is displayed.</span></span>  
  
3.  <span data-ttu-id="053c9-110">DiscountPolicy 정책 활동을 두 번 클릭하여 규칙을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-110">Double-click the DiscountPolicy policy activity to examine the rules.</span></span>  
  
     <span data-ttu-id="053c9-111">규칙 편집기에 규칙이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-111">The Rules editor pops up to show the rules.</span></span>  
  
4.  <span data-ttu-id="053c9-112">마우스 오른쪽 단추로 클릭는 `DiscountPolicy` 선택 하 고는 **코드 보기** 병행 C# 코드 활동에 대 한 코드를 검사 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-112">Right click the `DiscountPolicy` and select the **View Code** option to examine the code beside C# code for the activity.</span></span>  
  
     <span data-ttu-id="053c9-113">`DiscountLevel`의 종속성 속성 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-113">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="053c9-114">이 설정은 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]의 인수에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-114">This is equivalent to arguments in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="053c9-115">참조 인수를 [변수 및 인수](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-115"> arguments, see [Variables and Arguments](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span></span>  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="053c9-116">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="053c9-116">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="053c9-117"><xref:System.Activities.Statements.Interop> 활동을 사용하여 `TravelRuleLibrary` 프로젝트에 만든 사용자 지정 규칙 집합과 통합되는 순차 워크플로 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-117">This is a sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom Rule set created in the `TravelRuleLibrary` project.</span></span> <span data-ttu-id="053c9-118">변수는 최상위 <xref:System.Activities.Statements.Sequence> 활동에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-118">Variables are created on the top level <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="053c9-119"><xref:System.Activities.Statements.Interop> 활동은 `TravelRuleSet` 활동과 통합하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-119">The <xref:System.Activities.Statements.Interop> activity is used to integrate with the `TravelRuleSet` activity.</span></span> <span data-ttu-id="053c9-120"><xref:System.Activities.Statements.Sequence>에 선언된 변수는 종속성 속성에 바인딩하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-120">The variables that are declared on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="053c9-121">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="053c9-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="053c9-122">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 InteropWith35RuleSet.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="053c9-123">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="053c9-124">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="053c9-125">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="053c9-126">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="053c9-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="053c9-127">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="053c9-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="053c9-128">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="053c9-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`