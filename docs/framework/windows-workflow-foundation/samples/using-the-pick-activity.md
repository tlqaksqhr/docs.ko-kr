---
title: "Pick 활동 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18c8af9717cb03bd262ceb0a62c91dbc778071c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-pick-activity"></a><span data-ttu-id="236b2-102">Pick 활동 사용</span><span class="sxs-lookup"><span data-stu-id="236b2-102">Using the Pick Activity</span></span>
<span data-ttu-id="236b2-103">이 샘플에서는 <xref:System.Activities.Statements.Pick> 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-103">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>  
  
 <span data-ttu-id="236b2-104"><xref:System.Activities.Statements.Pick> 활동은 이벤트 기반의 제어 모델링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-104">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="236b2-105">이는 `switch` 문의 분기 중 하나에서만 실행되는 C# `switch` 문과 비슷한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-105">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="236b2-106">그러나 값을 기준으로 분기가 실행되는 `switch` 문과 달리 <xref:System.Activities.Statements.Pick> 활동은 활동의 완료 방식을 기준으로 분기가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-106">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>  
  
 <span data-ttu-id="236b2-107">이 샘플에서는 지정된 시간 내에 사용자의 이름을 입력하라는 메시지를 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-107">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="236b2-108">이 샘플의 <xref:System.Activities.Statements.Pick> 활동에는 사용자가 이름을 5초 안에 입력했는지 여부를 기준으로 실행되는 두 개의 분기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-108">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="236b2-109">사용자가 이름을 5초 안에 입력하면 사용자 지정 `ReadLine` 활동이 포함된 첫째 분기가 실행되고, 사용자가 이름을 5초 안에 입력하지 않으면 <xref:System.Activities.Statements.Delay> 활동이 포함된 둘째 분기가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-109">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="236b2-110">사용자가 콘솔에 이름을 입력하고 나면 해당 이름이 콘솔에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-110">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="236b2-111">이름을 5초 안에 입력하지 않으면 작업 제한 시간이 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-111">If an input is not entered within 5 seconds, the operation is timed out.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="236b2-112">세부 항목</span><span class="sxs-lookup"><span data-stu-id="236b2-112">Demonstrates</span></span>  
 <span data-ttu-id="236b2-113"><xref:System.Activities.Statements.Pick> 활동</span><span class="sxs-lookup"><span data-stu-id="236b2-113"><xref:System.Activities.Statements.Pick> activity.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="236b2-114">토론</span><span class="sxs-lookup"><span data-stu-id="236b2-114">Discussion</span></span>  
 <span data-ttu-id="236b2-115">이 샘플에는 디자이너 워크플로와 코딩된 워크플로가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-115">The sample includes a Designer workflow and coded workflow.</span></span>  
  
 <span data-ttu-id="236b2-116">디자이너 워크플로</span><span class="sxs-lookup"><span data-stu-id="236b2-116">Designer Workflow</span></span>  
 <span data-ttu-id="236b2-117">디자이너 버전의 샘플에서는 디자이너를 사용하여 워크플로를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-117">The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="236b2-118">여기에 포함되는 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-118">The following files are included:</span></span>  
  
-   <span data-ttu-id="236b2-119">Program.cs: 샘플 워크플로를 실행하는 `Main` 함수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-119">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>  
  
-   <span data-ttu-id="236b2-120">ReadString.cs: 콘솔에서 입력을 읽는 사용자 지정 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-120">ReadString.cs: A custom activity that reads some input from the console.</span></span>  
  
-   <span data-ttu-id="236b2-121">Sequence1.xaml: Pick을 사용하는 디자이너를 통해 만들어진 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-121">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>  
  
 <span data-ttu-id="236b2-122">코딩된 워크플로</span><span class="sxs-lookup"><span data-stu-id="236b2-122">Coded Workflow</span></span>  
 <span data-ttu-id="236b2-123">코딩된 버전의 샘플에서는 코드를 사용하여 워크플로를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-123">The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="236b2-124">여기에 포함되는 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-124">The following files are included:</span></span>  
  
-   <span data-ttu-id="236b2-125">Program.cs: 샘플 워크플로를 실행하는 `Main` 함수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-125">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>  
  
-   <span data-ttu-id="236b2-126">ReadString.cs: 콘솔에서 입력을 읽는 사용자 지정 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-126">ReadString.cs: A custom activity that reads some input from the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="236b2-127">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="236b2-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="236b2-128">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Pick.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Pick.sln solution file.</span></span>  
  
2.  <span data-ttu-id="236b2-129">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="236b2-130">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-130">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="236b2-131">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="236b2-132">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="236b2-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="236b2-133">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="236b2-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="236b2-134">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236b2-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`