---
title: "트랜잭션 호송 범위"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37141708-a29f-4b6a-81fe-f8a11f825061
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 085c52d94db5af12a022fa353a80d69534bfe219
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="transaction-convoy-scope"></a><span data-ttu-id="7f562-102">트랜잭션 호송 범위</span><span class="sxs-lookup"><span data-stu-id="7f562-102">Transaction Convoy Scope</span></span>
<span data-ttu-id="7f562-103">이 샘플에서는 <xref:System.ServiceModel.Activities.TransactedReceiveScope>와 함께 Parallel Convoy 메시징 활동 패턴을 만들어 많은 작업이 모두 같은 트랜잭션에서 순서에 관계없이 발생할 수 있는 프로토콜을 모델링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-103">This sample demonstrates how to create a Parallel Convoy messaging activity pattern in conjunction with a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to model a protocol where a number of operations can happen in any order all under the same transaction.</span></span> <span data-ttu-id="7f562-104">또한 트랜잭션이 서버로 이동되지 않는 경우<xref:System.ServiceModel.Activities.TransactedReceiveScope>가 자동으로 새 트랜잭션을 만들어 클라이언트가 어떤 트랜잭션도 사용하지 않도록 하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-104">This sample also demonstrates how a <xref:System.ServiceModel.Activities.TransactedReceiveScope> automatically creates a new transaction when one is not flowed to the server, so the client does not make use of any transactions.</span></span>  
  
 <span data-ttu-id="7f562-105">이 샘플은 클라이언트와 서버를 나타내는 두 개의 워크플로 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-105">The sample consists of two workflow projects that represent the client and server.</span></span> <span data-ttu-id="7f562-106">클라이언트 프로젝트는 서버 워크플로를 부트스트랩하는 메시지를 보내 시작되는 워크플로를 실행하며, 이 워크플로는 상관 관계를 초기화하고 나머지 메시징 활동에 대해 트랜잭션 범위를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-106">The client project runs a workflow that begins by sending a message to bootstrap the server workflow, which initializes a correlation and starts a transactional scope for the remainder of the messaging activities.</span></span> <span data-ttu-id="7f562-107">클라이언트 <xref:System.Activities.Statements.Sequence> 활동에는 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 쌍과 세 분기가 있는 <xref:System.Activities.Statements.Parallel> 활동이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-107">The client <xref:System.Activities.Statements.Sequence> activity contains an initial <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> pair and then a <xref:System.Activities.Statements.Parallel> activity with three branches.</span></span> <span data-ttu-id="7f562-108">각 분기는 서버에 단방향 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-108">Each branch sends a one-way message to the server.</span></span> <span data-ttu-id="7f562-109"><xref:System.Activities.Statements.Parallel.CompletionCondition%2A> 활동의 <xref:System.Activities.Statements.Parallel> 속성은 세 분기가 모두 완료되도록 `false`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-109">The <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> property of the <xref:System.Activities.Statements.Parallel> activity is set to `false` so that all three branches complete.</span></span>  
  
 <span data-ttu-id="7f562-110">서버 워크플로는 클라이언트 워크플로와 비슷하지만 서버 워크플로의 경우에는 메시징 활동이 통신의 서버측을 향하고, 수행되는 모든 작업이 같은 트랜잭션에서 실행되도록 메시징 활동이 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동 내에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-110">The server workflow is similar to the client workflow except the messaging activities are oriented towards the server side of the communication and they are contained within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity so that all work done executes under the same transaction.</span></span> <span data-ttu-id="7f562-111">서버에서 첫 번째 메시지를 받으면 트랜잭션이 만들어지고 이 트랜잭션이 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 본문 범위의 앰비언트 트랜잭션이 되어 이 범위 내의 모든 활동이 해당 트랜잭션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-111">When the first message is received on the server, a transaction is created and is made ambient for the scope of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> body so that any activity within this scope can access the transaction.</span></span> <span data-ttu-id="7f562-112">그러면 받는 메시지가 모두 병렬로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-112">After this, all receives execute in parallel.</span></span> <span data-ttu-id="7f562-113">받는 메시지는 모두 병렬 활동의 완료 조건에 설명되어 있는 것처럼 한 번만 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-113">All receives must execute exactly once as described by the completion condition on the parallel activity.</span></span> <span data-ttu-id="7f562-114"><xref:System.ServiceModel.Activities.TransactedReceiveScope> 본문의 끝에 암시적 유지 지점이 있으며 지속성 작업도 같은 트랜잭션에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-114">An implicit persistence point exists at the end of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> body and the persistence operation is also executed under the same transaction.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="7f562-115">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="7f562-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="7f562-116">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 ParallelConvoySample.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-116">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ParallelConvoySample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="7f562-117">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-117">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="7f562-118">두 프로젝트 모두 시작되도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-118">Ensure both projects are set to start.</span></span>  
  
    1.  <span data-ttu-id="7f562-119">**솔루션 탐색기**솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **시작 프로젝트 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-119">In **Solution Explorer**, right-click the solution and select **Set Startup Projects**.</span></span>  
  
    2.  <span data-ttu-id="7f562-120">선택 **여러 개의 시작 프로젝트** 두 프로젝트에 대 한 작업으로 설정 되었는지 확인 하 고 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-120">Select **Multiple Startup Projects** and ensure the action for both projects is set to **Start**.</span></span>  
  
4.  <span data-ttu-id="7f562-121">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-121">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="7f562-122">서버에서 `Server is running`이라고 출력되고 이는 서버가 준비되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-122">The server prints `Server is running`, which indicates the server is ready.</span></span>  
  
     <span data-ttu-id="7f562-123">클라이언트 콘솔 창에서 아무 키나 눌러 샘플을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-123">Press any key in the client console window to start the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7f562-124">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7f562-125">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7f562-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7f562-126">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="7f562-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7f562-127">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f562-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedConvoyScope`