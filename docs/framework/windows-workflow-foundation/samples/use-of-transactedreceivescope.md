---
title: "TransactedReceiveScope 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d455f1dc-bfc5-43d6-8ae9-bc3b3a3ea08a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dc43f04da0404c309c727aef93b74faec5047ac6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="use-of-transactedreceivescope"></a><span data-ttu-id="ffd43-102">TransactedReceiveScope 사용</span><span class="sxs-lookup"><span data-stu-id="ffd43-102">Use of TransactedReceiveScope</span></span>
<span data-ttu-id="ffd43-103">이 샘플에서는 <xref:System.Activities.Statements.TransactionScope>를 사용하여 클라이언트에 새 트랜잭션을 만들고 <xref:System.ServiceModel.Activities.TransactedReceiveScope>를 사용하여 이동된 트랜잭션과 함께 메시지를 받고 서버에 있는 트랜잭션의 수명 주기 범위를 지정하여 클라이언트에서 서버로 트랜잭션을 이동하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-103">This sample shows how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span> <span data-ttu-id="ffd43-104">이 샘플은 클라이언트와 서버의 역할을 나타내는 두 개의 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-104">The sample consists of two projects that fill the roles of client and server.</span></span>  
  
## <a name="client-application"></a><span data-ttu-id="ffd43-105">클라이언트 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ffd43-105">Client Application</span></span>  
 <span data-ttu-id="ffd43-106">클라이언트 응용 프로그램에서는 분산 트랜잭션 ID를 출력하고, 서버로 메시지를 보내고, 트랜잭션을 이동하고, 회신을 받고, 분산 트랜잭션 ID를 다시 출력한 후 완료되는 워크플로를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-106">The client application runs a workflow that prints the distributed transaction ID, sends a message to the server, flows the transaction, receives the reply, prints the distributed transaction ID again and completes.</span></span> <span data-ttu-id="ffd43-107">분산 트랜잭션 ID를 처음 출력할 때는 트랜잭션이 아직 로컬인 상태이므로 빈 GUID가 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-107">When the distributed transaction ID is initially prints, it is an empty GUID as the transaction is still only local.</span></span>  
  
## <a name="server-application"></a><span data-ttu-id="ffd43-108">서버 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ffd43-108">Server Application</span></span>  
 <span data-ttu-id="ffd43-109">서버 프로젝트도 클라이언트의 경우와 비슷하지만, 워크플로가 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에 호스트된다는 점에서 차이가 있습니다. 서버의 경우 클라이언트의 메시지를 끝점에서 수신해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-109">The server project is similar, however, the workflow is hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> because it must listen on an endpoint for the message from the client.</span></span> <span data-ttu-id="ffd43-110">이 워크플로는 클라이언트에서 이동한 트랜잭션을 받고, 전달된 메시지를 출력하고, 분산 트랜잭션 ID를 출력하고, 클라이언트에 회신을 보내는 <xref:System.ServiceModel.Activities.TransactedReceiveScope>를 중심으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-110">The workflow is centered on the <xref:System.ServiceModel.Activities.TransactedReceiveScope>, which receives the flowed transaction from the client, prints the message that was sent, prints the distributed transaction ID and sends the reply to the client.</span></span> <span data-ttu-id="ffd43-111">이번에는 분산 트랜잭션 ID가 빈 GUID가 아니며, 트랜잭션 인식 활동을 <xref:System.ServiceModel.Activities.TransactedReceiveScope>의 본문에 추가한 경우 이동한 트랜잭션 하에서 해당 활동이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-111">The distributed transaction ID is now a non-empty GUID and if a transaction-aware activity was added to the body of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>, it would execute under the flowed transaction.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="ffd43-112">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ffd43-112">To run the sample</span></span>  
  
1.  <span data-ttu-id="ffd43-113">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 TransactedReceiveScope.sln 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-113">Open the TransactedReceiveScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ffd43-114">솔루션을 빌드하려면 CTRL + SHIFT + B 키를 누르거나 선택 **솔루션 빌드** 에서 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="ffd43-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="ffd43-115">빌드가 성공한 후 솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **시작 프로젝트 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-115">Once the build has succeeded, right-click the solution and select **Set Startup Projects**.</span></span> <span data-ttu-id="ffd43-116">이 대화 상자에서 선택 **여러 개의 시작 프로젝트** 하 고 두 프로젝트에 대 한 작업 확인 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-116">From the dialog, select **Multiple Startup Projects** and ensure the action for both projects is **Start**.</span></span>  
  
4.  <span data-ttu-id="ffd43-117">F5 키를 누르거나 선택 **디버깅 시작** 에서 **디버그** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="ffd43-117">Press F5 or select **Start Debugging** from the **Debug** menu.</span></span> <span data-ttu-id="ffd43-118">또는 CTRL + f 5를 눌러 수도 있고 선택할 **디버깅 하지 않고 시작** 에서 **디버그** 메뉴 디버깅 없이 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-118">Alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ffd43-119">클라이언트를 시작하기 전에 서버를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-119">The server must be running prior to starting the client.</span></span> <span data-ttu-id="ffd43-120">서비스를 호스트하는 콘솔 창의 출력을 통해 서비스가 시작되었음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-120">The output from the console window hosting the service indicates when it has started.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ffd43-121">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ffd43-122">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ffd43-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ffd43-123">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="ffd43-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ffd43-124">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd43-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TransactedReceiveScope`