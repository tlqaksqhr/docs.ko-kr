---
title: "CancellationScope 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39c5c338-b316-43d6-b7fe-a543281dd1ec
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f8fcd972b31490142f94581c664ca2988237684
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="using-cancellationscope"></a><span data-ttu-id="e0732-102">CancellationScope 사용</span><span class="sxs-lookup"><span data-stu-id="e0732-102">Using CancellationScope</span></span>
<span data-ttu-id="e0732-103">이 샘플에서는 <xref:System.Activities.Statements.CancellationScope> 활동을 사용하여 응용 프로그램에서 작업을 취소하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-103">This sample demonstrates how to use the <xref:System.Activities.Statements.CancellationScope> activity to cancel work in an application.</span></span>  
  
 <span data-ttu-id="e0732-104">많은 중간 계층 구성 요소 및 서비스는 잘 알려진 트랜잭션 프로그래밍 구문을 사용하여 취소를 처리하지만</span><span class="sxs-lookup"><span data-stu-id="e0732-104">Many middle tier components and services rely on the well-known programming construct of transactions to handle cancellation for them.</span></span>  <span data-ttu-id="e0732-105">트랜잭션에서 수행할 수 없는 작업을 취소해야 하는 경우도 많습니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-105">However, there are many situations in which work that cannot be done in a transaction must be canceled.</span></span>  <span data-ttu-id="e0732-106">취소해야 하는 작업을 먼저 추적해야 하기 때문에 취소를 사용하는 것이 트랜잭션을 사용하는 것보다 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-106">Using cancellation is more difficult than using transactions, because work that must be canceled must first be tracked.</span></span> [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]<span data-ttu-id="e0732-107">는 <xref:System.Activities.Statements.CancellationScope> 활동을 제공하여 이 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-107"> helps you with this by providing a <xref:System.Activities.Statements.CancellationScope> activity.</span></span>  
  
 <span data-ttu-id="e0732-108">취소는 활동 내에서 또는 활동의 부모에서 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-108">Cancellation can be triggered either from within an activity or from the activity's parent.</span></span>  <span data-ttu-id="e0732-109">자식 활동은 <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.Flowchart> 또는 사용자 지정 복합 활동과 같은 부모 활동에 의해 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-109">Child activities are scheduled by their parent activity (such as a <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.Flowchart>, or a custom composite activity).</span></span>  <span data-ttu-id="e0732-110">이유에 관계없이 부모 활동은 자식 활동을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-110">The parent activity can cancel child activities for any reason.</span></span>  <span data-ttu-id="e0732-111">예를 들어 세 개의 자식 분기가 있는 <xref:System.Activities.Statements.Parallel> 활동은 분기를 완료하고 <xref:System.Activities.Statements.Parallel.CompletionCondition%2A>식이 `true`로 평가될 때마다 나머지 자식 분기를 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-111">For example, a <xref:System.Activities.Statements.Parallel> activity with three child branches will cancel the remaining child branches whenever it completes a branch and the <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> expression evaluates to `true`.</span></span> <span data-ttu-id="e0732-112"><xref:System.Activities.WorkflowApplication.Cancel%2A>을 호출하여 호스트 응용 프로그램에서 워크플로를 외부적으로 취소할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-112">The workflow can also be canceled externally by the host application by calling <xref:System.Activities.WorkflowApplication.Cancel%2A>.</span></span>  
  
 <span data-ttu-id="e0732-113"><xref:System.Activities.Statements.CancellationScope> 활동을 사용하려면 취소해야 하는 작업을 <xref:System.Activities.Statements.CancellationScope.Body%2A> 속성에 넣고 취소 후에 수행되는 작업을 <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> 속성에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-113">To use the <xref:System.Activities.Statements.CancellationScope> activity, put the work that needs to be canceled into the <xref:System.Activities.Statements.CancellationScope.Body%2A> property, and put the work that is performed after cancellation into the <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> property.</span></span>  
  
 <span data-ttu-id="e0732-114">이 샘플에서는 활동 자체 내에서 활동을 취소하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-114">This sample demonstrates cancelling an activity from within the activity itself.</span></span>  
  
 <span data-ttu-id="e0732-115">이 샘플에서 <xref:System.Activities.Statements.CancellationScope> 활동을 보여 주기 위해 사용하는 시니리오에서는 고객이 최대한 빨리 마이애미행 비행기표를 구입하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-115">The scenario that the sample uses to demonstrate the <xref:System.Activities.Statements.CancellationScope> activity is a client wanting to buy a ticket to Miami as soon as possible.</span></span> <span data-ttu-id="e0732-116">거래를 원하는 두 개의 여행사가 있으며,</span><span class="sxs-lookup"><span data-stu-id="e0732-116">There are two travel agencies that want the business.</span></span> <span data-ttu-id="e0732-117">샘플에서는 <xref:System.Activities.Statements.CancellationScope> 활동 내에서 두 개의 <xref:System.Activities.Statements.Parallel>를 사용하여 이 비즈니스 논리를 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-117">The sample uses two <xref:System.Activities.Statements.CancellationScope> within a <xref:System.Activities.Statements.Parallel> activity to model this business logic.</span></span> <span data-ttu-id="e0732-118"><xref:System.Activities.Statements.Parallel.CompletionCondition%2A> 활동의 <xref:System.Activities.Statements.Parallel>은 `true`로 설정됩니다. <xref:System.Activities.Statements.Parallel.CompletionCondition%2A>은 분기 중 하나가 완료된 후 확인되므로 첫 번째 분기가 완료된 후 나머지 분기가 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-118">The <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> of the <xref:System.Activities.Statements.Parallel> activity is set to `true`; since the <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> is checked after any branch completes, this will cause the remaining branch to be canceled after the first branch completes.</span></span> <span data-ttu-id="e0732-119">클라이언트 응용 프로그램은 두 여행사에 비행기표 구입을 문의한 후 둘 중 한 여행사에서 비행기표를 구입했음을 확인하면 다른 여행사에서의 주문을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-119">The client application asks both agencies to buy the ticket, and when the first one confirms that the ticket has been bought, the application cancels the order at the other agency.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="e0732-120">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="e0732-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="e0732-121">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 CancelationScopeXAML.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-121">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CancelationScopeXAML.sln solution file.</span></span>  
  
2.  <span data-ttu-id="e0732-122">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-122">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="e0732-123">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-123">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e0732-124">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e0732-125">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e0732-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e0732-126">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="e0732-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e0732-127">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0732-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\CancellationScope`