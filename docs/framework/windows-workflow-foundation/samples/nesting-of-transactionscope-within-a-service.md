---
title: "서비스 내에 TransactionScope 중첩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7e1ba64-1384-4eba-add8-415636e2d6d0
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 475da3f9204764a2585bd7a50381db7ad72c2b1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="nesting-of-transactionscope-within-a-service"></a><span data-ttu-id="cf203-102">서비스 내에 TransactionScope 중첩</span><span class="sxs-lookup"><span data-stu-id="cf203-102">Nesting of TransactionScope within a service</span></span>
<span data-ttu-id="cf203-103">이 샘플은 한 서비스 내의 <xref:System.Activities.Statements.TransactionScope> 활동 인스턴스 여러 개를 처리하는 방법을 보여 주는 두 개의 시나리오로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-103">This sample consists of two scenarios that run showing how to handle <xref:System.Activities.Statements.TransactionScope> activity instances within a service.</span></span> <span data-ttu-id="cf203-104">우선 <xref:System.Activities.Statements.TransactionScope> 활동을 사용하여 클라이언트에 새 트랜잭션을 만들어 트랜잭션을 시작하고 <xref:System.ServiceModel.Activities.TransactedReceiveScope>를 사용하여 서버에서 트랜잭션을 받고 트랜잭션 수명의 범위를 정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-104">First the transaction is initiated using the <xref:System.Activities.Statements.TransactionScope> activity to create a new transaction on the client and <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive and scope the lifetime of the transaction on the server.</span></span> <span data-ttu-id="cf203-105">서비스 내의 첫째 시나리오는 보조 <xref:System.Activities.Statements.TransactionScope> 활동을 실행하여 서비스 내에 중첩되는 <xref:System.Activities.Statements.TransactionScope> 활동을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-105">The first scenario within the service runs a secondary <xref:System.Activities.Statements.TransactionScope> activity to demonstrate the nesting of the <xref:System.Activities.Statements.TransactionScope> activities within the service.</span></span> <span data-ttu-id="cf203-106">둘째 시나리오에서는 중첩된 <xref:System.Activities.Statements.TransactionScope> 활동 내에 제한 시간이 적용되는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-106">The second scenario shows how time-outs are respected within the nested <xref:System.Activities.Statements.TransactionScope> activities.</span></span>  
  
## <a name="client-application"></a><span data-ttu-id="cf203-107">클라이언트 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="cf203-107">Client Application</span></span>  
 <span data-ttu-id="cf203-108">클라이언트 응용 프로그램에서는 <xref:System.Activities.Statements.TransactionScope> 활동을 시작하고, 분산 트랜잭션 ID를 출력하고, 서버로 메시지를 보내고, 트랜잭션을 이동하고, 회신을 받고, 분산 트랜잭션 ID를 다시 출력한 후 완료되는 워크플로를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-108">The client application runs a workflow that starts a <xref:System.Activities.Statements.TransactionScope> activity, prints the distributed transaction ID, sends a message to the server, flows the transaction, receives the reply, prints the distributed transaction ID again and completes.</span></span> <span data-ttu-id="cf203-109">이 응용 프로그램에서는 각 서비스 시나리오에 대해 이를 한 번씩 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-109">It does this once for each service scenario.</span></span>  
  
## <a name="server-application"></a><span data-ttu-id="cf203-110">서버 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="cf203-110">Server Application</span></span>  
 <span data-ttu-id="cf203-111">서버 프로젝트는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에 호스트되며, 클라이언트에서 보낸 메시지를 수신할 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-111">The server project is hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>, which creates the endpoint to listen for the message from the client.</span></span> <span data-ttu-id="cf203-112">이 워크플로는 클라이언트에서 이동한 트랜잭션을 받고, 분산 트랜잭션 ID를 출력한 다음 둘째 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동을 실행하는 <xref:System.Activities.Statements.TransactionScope>를 중심으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-112">The workflow is centered on the <xref:System.ServiceModel.Activities.TransactedReceiveScope>, which receives the flowed transaction from the client, prints the distributed transaction ID and then executes a second <xref:System.Activities.Statements.TransactionScope> activity.</span></span> <span data-ttu-id="cf203-113">첫째 시나리오에서는 트랜잭션이 성공적으로 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-113">In the first scenario, the transaction is completed successfully.</span></span> <span data-ttu-id="cf203-114">둘째 시나리오에서는 <xref:System.Activities.Statements.TransactionScope> 활동의 본문이 5초 지연되며 트랜잭션 제한 시간은 2초로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-114">In the second scenario, the body of the <xref:System.Activities.Statements.TransactionScope> activity is a five-second delay and the time-out for the transaction is set to two seconds.</span></span> <span data-ttu-id="cf203-115">트랜잭션 제한 시간을 초과하면 트랜잭션이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-115">When the transaction times out the transaction is aborted.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="cf203-116">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="cf203-116">To run the sample</span></span>  
  
1.  <span data-ttu-id="cf203-117">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 TransactionServiceExample.sln 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-117">Open the TransactionServiceExample.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="cf203-118">솔루션을 빌드하려면 CTRL + SHIFT + B 키를 누르거나 선택 **솔루션 빌드** 에서 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="cf203-118">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="cf203-119">빌드가 성공한 후 솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **시작 프로젝트 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-119">Once the build has succeeded, right-click the solution and select **Set Startup Projects**.</span></span> <span data-ttu-id="cf203-120">대화 상자에서 선택 **여러 개의 시작 프로젝트** 하 고 두 프로젝트에 대 한 작업 확인 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-120">From the dialog box, select **Multiple Startup Projects** and ensure the action for both projects is **Start**.</span></span>  
  
4.  <span data-ttu-id="cf203-121">F5 키를 누르거나 선택 **디버깅 시작** 에서 **디버그** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="cf203-121">Press F5 or select **Start Debugging** from the **Debug** menu.</span></span> <span data-ttu-id="cf203-122">또는 CTRL + f 5를 눌러 수도 있고 선택할 **디버깅 하지 않고 시작** 에서 **디버그** 메뉴 디버깅 없이 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-122">Alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf203-123">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cf203-124">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="cf203-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cf203-125">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="cf203-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cf203-126">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf203-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TRSComposability`
