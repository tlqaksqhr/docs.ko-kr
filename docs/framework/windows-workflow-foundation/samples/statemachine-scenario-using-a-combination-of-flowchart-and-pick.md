---
title: "FlowChart와 Pick을 함께 사용하는 StateMachine 시나리오"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4a4ff644367f0bcd6562bd8931406a11f39d62df
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="statemachine-scenario-using-a-combination-of-flowchart-and-pick"></a><span data-ttu-id="c59b0-102">FlowChart와 Pick을 함께 사용하는 StateMachine 시나리오</span><span class="sxs-lookup"><span data-stu-id="c59b0-102">StateMachine Scenario Using a Combination of FlowChart and Pick</span></span>
<span data-ttu-id="c59b0-103">이 샘플에서는 <xref:System.Activities.Statements.Flowchart> 및 <xref:System.Activities.Statements.Pick> 활동을 함께 사용하여 간단한 스톱워치 시나리오를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-103">This sample demonstrates how to implement a simple stopwatch scenario using a combination of the <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Pick> activities.</span></span> <span data-ttu-id="c59b0-104">이 샘플에서는 Pick 활동 내의 Receive 및 Send를 사용하여 스톱워치 이벤트를 수신 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-104">It uses Receive and Send within the Pick activity to listen for stopwatch events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c59b0-105">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c59b0-106">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c59b0-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c59b0-107">이 디렉터리가 없으면 다운로드 페이지로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="c59b0-107">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c59b0-108">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="sample-details"></a><span data-ttu-id="c59b0-109">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="c59b0-109">Sample Details</span></span>  
 <span data-ttu-id="c59b0-110">다음 표에서는 이 샘플의 프로젝트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-110">The following table lists the projects in this sample.</span></span>  
  
|<span data-ttu-id="c59b0-111">프로젝트 이름</span><span class="sxs-lookup"><span data-stu-id="c59b0-111">Project Name</span></span>|<span data-ttu-id="c59b0-112">설명</span><span class="sxs-lookup"><span data-stu-id="c59b0-112">Description</span></span>|  
|-|-|  
|<span data-ttu-id="c59b0-113">StopWatchService</span><span class="sxs-lookup"><span data-stu-id="c59b0-113">StopWatchService</span></span>|<span data-ttu-id="c59b0-114">이 프로젝트에는 <xref:System.Activities.Statements.Flowchart> 및 <xref:System.Activities.Statements.Pick> 활동을 함께 사용한 스톱워치 샘플의 상태 시스템 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-114">This project contains the implementation of a state machine for the stopwatch sample using a combination of the <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Pick> activities.</span></span><br /><br /> <span data-ttu-id="c59b0-115"><xref:System.Activities.Statements.Pick> 활동에는 <xref:System.Activities.Statements.PickBranch> 속성 내에서 <xref:System.Activities.Statements.Pick.Branches%2A>, `GetStart` 및 `GetStop` 이벤트를 수신 대기하는 세 개의 `GetOff` 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-115">The <xref:System.Activities.Statements.Pick> activity has 3 <xref:System.Activities.Statements.PickBranch> statements within the <xref:System.Activities.Statements.Pick.Branches%2A> property that listen for `GetStart`, `GetStop` and `GetOff` events.</span></span> <span data-ttu-id="c59b0-116">들어오는 이벤트를 기준으로 분기 중 하나의 트리거가 활성화되고 해당하는 <xref:System.Activities.Statements.PickBranch.Action%2A>이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-116">Based on the incoming event, the triggers for one of the branches activate and the corresponding <xref:System.Activities.Statements.PickBranch.Action%2A> is triggered.</span></span> <span data-ttu-id="c59b0-117"><xref:System.Activities.Statements.PickBranch.Action%2A> 속성에는 <xref:System.Activities.Statements.Switch%601> 문이 있습니다. 이 문은 전환이 올바른지 확인하는데, 올바른 경우 `currentState` 속성이 전환 상태로 업데이트되고 클라이언트에 보내집니다. </span><span class="sxs-lookup"><span data-stu-id="c59b0-117">In the <xref:System.Activities.Statements.PickBranch.Action%2A> property, there is a <xref:System.Activities.Statements.Switch%601> statement that evaluates whether the transition is a legitimate transition and if it is, the `currentState` property is updated to the transitioning state and sent to the client.</span></span><br /><br /> <span data-ttu-id="c59b0-118"><xref:System.Activities.Statements.FlowDecision>의 마지막에 있는 <xref:System.Activities.Statements.Flowchart> 활동은 `currentState` 속성을 확인하여 상태가 터미널 상태인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-118">The <xref:System.Activities.Statements.FlowDecision> activity at the end of the <xref:System.Activities.Statements.Flowchart> evaluates the `currentState` property to determine whether the state is terminal.</span></span> <span data-ttu-id="c59b0-119">터미널 상태이면 워크플로가 종료되고, 그렇지 않으면 제어가 <xref:System.Activities.Statements.Pick> 활동의 시작으로 다시 돌아가 루프를 실행하여 워크플로가 추가 스톱워치 이벤트를 기다립니다. </span><span class="sxs-lookup"><span data-stu-id="c59b0-119">If it is, the workflow ends; otherwise control loops back to the start of the <xref:System.Activities.Statements.Pick> activity where the workflow waits for more stopwatch events.</span></span>|  
|<span data-ttu-id="c59b0-120">StopWatchClient</span><span class="sxs-lookup"><span data-stu-id="c59b0-120">StopWatchClient</span></span>|<span data-ttu-id="c59b0-121">간단한 Send 또는 Receive 활동 조합을 사용하여 다양한 스톱워치 이벤트를 보내는 간단한 순차 워크플로 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-121">This is a simple sequential workflow console application that sends various stopwatch events with simple Send or Receive activity combinations.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="c59b0-122">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="c59b0-122">To use this sample</span></span>  
  
1.  <span data-ttu-id="c59b0-123">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 StateMachineWithPick.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-123">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open StateMachineWithPick.sln solution file.</span></span>  
  
2.  <span data-ttu-id="c59b0-124">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-124">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="c59b0-125">StopWatchService.exe를 시작 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] .exe 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 관리자 권한으로 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-125">Start the StopWatchService.exe from [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] as an administrator by right clicking the .exe file and selecting **Run as administrator**.</span></span>  
  
    1.  <span data-ttu-id="c59b0-126">StateMachineWithPick\CS\StopWatchService\bin\Debug 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-126">Navigate to the StateMachineWithPick\CS\StopWatchService\bin\Debug folder.</span></span>  
  
    2.  <span data-ttu-id="c59b0-127">StopWatchService.exe 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-127">Right-click the StopWatchService.exe file and select **Run as administrator**.</span></span>  
  
4.  <span data-ttu-id="c59b0-128">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 StopWatchClient 클라이언트 응용 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-128">Start the StopWatchClient client application from within [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    1.  <span data-ttu-id="c59b0-129">**솔루션 탐색기**, 선택는 **StopWatchClient** 프로젝트를 마우스 오른쪽 단추로 클릭 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-129">In **Solution Explorer**, select the **StopWatchClient** project and right-click **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="c59b0-130">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-130">To run the solution, press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="c59b0-131">StopWatchService.exe에 대한 콘솔 창으로 다시 전환하여 상태 전환을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-131">Switch back to the console window for the StopWatchService.exe to view the state transitions.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c59b0-132">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c59b0-133">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c59b0-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c59b0-134">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="c59b0-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c59b0-135">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c59b0-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`