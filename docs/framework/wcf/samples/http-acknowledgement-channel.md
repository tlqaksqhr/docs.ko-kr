---
title: "HTTP 승인 채널"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 469f3056-5ef2-4753-8acf-b574d23d83cf
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d07a17c5ed4302657671e0247e44ac0ef6e75518
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="http-acknowledgement-channel"></a><span data-ttu-id="b55be-102">HTTP 승인 채널</span><span class="sxs-lookup"><span data-stu-id="b55be-102">HTTP Acknowledgement Channel</span></span>
<span data-ttu-id="b55be-103">HTTP 승인 채널은 서비스에서 들어오는 메시지를 수신할 때 승인을 자동으로 보내지 않고 들어오는 메시지를 승인하거나 거부할 수 있게 단방향 메시지 패턴을 변경하는 계층화된 채널의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-103">The HTTP Acknowledgement Channel is an example of a layered channel that changes the one-way messaging pattern, allowing a service to acknowledge or refuse incoming messages rather than automatically sending an acknowledgement on receipt.</span></span> <span data-ttu-id="b55be-104">또한 HTTP 승인 채널을 사용하면 서비스에서는 메시지가 처리될 것임을 비즈니스 수준에서 보장할 수 있을 때까지 승인을 지연시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-104">The HTTP Acknowledgement Channel also allows the service to delay acknowledgement until it can make a business-level guarantee that the message will be processed.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b55be-105">세부 항목</span><span class="sxs-lookup"><span data-stu-id="b55be-105">Demonstrates</span></span>  
 <span data-ttu-id="b55be-106">계층화된 채널의 예(HTTP 승인 채널)인 <xref:System.ServiceModel.Channels.ReceiveContext></span><span class="sxs-lookup"><span data-stu-id="b55be-106"><xref:System.ServiceModel.Channels.ReceiveContext>, Layered channel example (HTTP Acknowledgement channel).</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="b55be-107">토론</span><span class="sxs-lookup"><span data-stu-id="b55be-107">Discussion</span></span>  
 <span data-ttu-id="b55be-108">HTTP 승인 채널에서는 <xref:System.ServiceModel.Channels.ReceiveContext>를 구현하여 HTTP 요청-응답 메시징 패턴을 지연 승인을 사용하는 단방향 패턴으로 변형합니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-108">The HTTP Acknowledgement Channel implements <xref:System.ServiceModel.Channels.ReceiveContext> to reshape the HTTP request-reply messaging pattern to a one-way pattern with delayed acknowledgement.</span></span> <span data-ttu-id="b55be-109">이 새 패턴을 사용하면 서비스에서는 메시지 처리가 완료될 때까지 클라이언트를 차단하지 않고 HTTP OK 상태 코드 200 형식으로 승인을 보내 메시지가 처리되도록 하거나, HTTP 내부 서버 오류 상태 코드 500 형식으로 클라이언트에 실패 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-109">Using this new pattern, a service can ensure message processing by sending an acknowledgement in the form of an HTTP OK status code of 200 without blocking the client until message processing completes or can send a failure message to the client in the form of an HTTP Internal Server error status code of 500.</span></span> <span data-ttu-id="b55be-110">예를 들어 서비스에서는 큐에 메시지를 쓴 후 승인을 보내고, 그런 다음 메시지를 비동기적으로 계속 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-110">For example, a service could send an acknowledgement after writing a message to a queue, and then continue processing the message asynchronously.</span></span> <span data-ttu-id="b55be-111">이 시나리오에서 클라이언트는 서비스로부터 승인을 받을 때까지 각 메시지를 다시 보낸 경우 서비스에서 메시지를 한 번 이상 처리했음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-111">In this scenario, a client could be assured its messages were processed at least once by the service, if it re-sent each message until it received an acknowledgement from the service.</span></span> <span data-ttu-id="b55be-112">서비스에서 메시지 처리를 보장하지 않고 HTTP를 통해 신속하게 비동기적으로 메시지를 처리해야 하는 경우에는 <xref:System.ServiceModel.Channels.OneWayBindingElement>가 더 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-112">Note that, if a service requires fast asynchronous message processing over HTTP without any message processing guarantees, then the <xref:System.ServiceModel.Channels.OneWayBindingElement> is a more appropriate choice.</span></span>  
  
 <span data-ttu-id="b55be-113"><xref:System.ServiceModel.Channels.ReceiveContext>는 메시지를 서비스에서 처리할 수 있는지 여부를 확인하는 동안 메시지를 보관하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-113"><xref:System.ServiceModel.Channels.ReceiveContext> is used to hold the message in place while it is determined whether the message can be processed at the service.</span></span> <span data-ttu-id="b55be-114">서비스에서 메시지를 성공적으로 처리할 수 있음을 나타내려면 <xref:System.ServiceModel.Channels.ReceiveContext> 개체에 대해 Complete를 호출하여 HTTP OK 상태 코드를 보내고, 서비스에서 메시지를 처리할 수 있는지 여부를 나타내려면 <xref:System.ServiceModel.Channels.ReceiveContext> 개체에 대해 `Abandon`의 <xref:System.ServiceModel.Channels.ReceiveContext> 메서드를 호출하여 HTTP 내부 서버 오류 상태 코드를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-114">The ability of a service to successfully process the message is indicated by calling Complete on the <xref:System.ServiceModel.Channels.ReceiveContext> object that sends an HTTP OK status code and whether the service can process the message is indicated by calling <xref:System.ServiceModel.Channels.ReceiveContext>’s `Abandon` method on the <xref:System.ServiceModel.Channels.ReceiveContext> object, which sends an HTTP Internal Server error status code.</span></span>  
  
 <span data-ttu-id="b55be-115">이 예제에서 클라이언트는 직원 ID를 보내 정보 처리를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-115">In this example, the client requests processing information by sending an employee ID.</span></span> <span data-ttu-id="b55be-116">서비스 쪽에서는 받은 직원 ID가 50보다 크면 HTTP 상태 코드 500(내부 서버 오류)을 클라이언트로 다시 보내고, 그렇지 않으면 처리를 성공적으로 수행할 수 있는 것으로 가정하고 HTTP 상태 코드 200(성공)을 클라이언트로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-116">On the service end, if the employee ID received is greater than 50, the service sends an HTTP Status code of 500 (Internal Server Error) back to the client, otherwise it is assumed that the processing can be successfully done and sends an HTTP Status code of 200 (Successful) to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b55be-117">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b55be-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b55be-118">관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-118">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] with Administrator privileges.</span></span>  
  
2.  <span data-ttu-id="b55be-119">열기는 **HttpAckChannel** 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-119">Open the **HttpAckChannel** solution.</span></span>  
  
3.  <span data-ttu-id="b55be-120">새 인스턴스를 시작는 **서비스** 프로젝트에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 **솔루션 탐색기**를 선택 하 고 **디버그**, **새 인스턴스 시작** 상황에 맞는 메뉴입니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-120">Start a new instance of the **Service** project by right clicking the project in **Solution Explorer**, and selecting **Debug**, **Start new instance** from the context menu.</span></span>  
  
4.  <span data-ttu-id="b55be-121">새 인스턴스를 시작는 **클라이언트** 프로젝트에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 **솔루션 탐색기**를 선택 하 고 **디버그**, 및 **새 인스턴스 시작** 상황에 맞는 메뉴입니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-121">Start a new instance of the **Client** project by right clicking the project in **Solution Explorer**, and selecting **Debug**, and **Start new instance** from the context menu.</span></span>  
  
5.  <span data-ttu-id="b55be-122">서비스가 시작된 후 클라이언트 창에서 Enter 키를 눌러 클라이언트가 서비스로 메시지를 보내도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-122">Once the service has started, press ENTER in the client window to let the client send a message to the service.</span></span>  
  
6.  <span data-ttu-id="b55be-123">서비스에서 첫 번째 메시지를 처리하고 HTTP OK 상태 코드를 클라이언트로 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-123">The first message is processed on the service, and it sends an HTTP OK status code back to the client.</span></span>  
  
7.  <span data-ttu-id="b55be-124">서비스에서 두 번째 메시지를 처리하지 못하고 HTTP 내부 서버 오류 상태 코드를 클라이언트로 다시 보냅니다. 그러면 클라이언트에서 <xref:System.ServiceModel.CommunicationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-124">The second message is unsuccessful, and it sends an HTTP Internal Server error status code back to the client, which raises a <xref:System.ServiceModel.CommunicationException> on the client.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b55be-125">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b55be-126">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b55be-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b55be-127">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="b55be-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b55be-128">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55be-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpAckChannel`
