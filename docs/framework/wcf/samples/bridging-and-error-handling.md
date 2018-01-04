---
title: "브리징과 오류 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ae87d1a-b615-4014-a494-a53f63ff0137
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84a7d3385d89d4308e6a75d303a567fb4d7b22d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bridging-and-error-handling"></a><span data-ttu-id="148ac-102">브리징과 오류 처리</span><span class="sxs-lookup"><span data-stu-id="148ac-102">Bridging and Error Handling</span></span>
<span data-ttu-id="148ac-103">이 샘플에서는 서로 다른 바인딩을 사용하는 클라이언트와 서비스 간의 브리징 통신에 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 라우팅 서비스를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-103">This sample demonstrates how the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] routing service is used for bridging communication between a client and a service that use different bindings.</span></span> <span data-ttu-id="148ac-104">또한 장애 조치 시나리오에 백업 서비스를 사용하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-104">This sample also shows how to use a back-up service for failover scenarios.</span></span> <span data-ttu-id="148ac-105">라우팅 서비스는 응용 프로그램에 내용 기반 라우터를 손쉽게 포함할 수 있게 해 주는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-105">The routing service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="148ac-106">이 샘플에서는 라우팅 서비스를 사용하여 통신하도록 표준 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator 샘플을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-106">This sample adapts the standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator Sample to communicate using the routing service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="148ac-107">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="148ac-108">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="148ac-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="148ac-109">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="148ac-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="148ac-110">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\ErrorHandlingAndBridging`  
  
## <a name="sample-details"></a><span data-ttu-id="148ac-111">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="148ac-111">Sample Details</span></span>  
 <span data-ttu-id="148ac-112">이 샘플에서 계산기 클라이언트는 라우터에 의해 노출된 끝점으로 메시지를 보내도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-112">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="148ac-113">라우팅 서비스는 전송된 모든 메시지를 승인하고 이를 계산기 서비스에 해당하는 끝점에 전달하도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-113">The routing service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="148ac-114">다음은 기본 계산기 서비스, 백업 계산기 서비스 및 계산기 클라이언트의 구성과 라우팅 서비스를 사용하여 클라이언트와 서비스 간에 통신이 이루어지는 방법에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-114">The following points describe the configuration of the primary Calculator service, the back-up Calculator service, and the Calculator client and how the communication between the client and the service happens using the routing service:</span></span>  
  
-   <span data-ttu-id="148ac-115">계산기 클라이언트는 BasicHttpBinding을 사용하도록 구성된 반면 계산기 서비스는 NetTcpBinding을 사용하도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-115">The Calculator client is configured to use BasicHttpBinding while the Calculator service is configured to use NetTcpBinding.</span></span> <span data-ttu-id="148ac-116">라우팅 서비스에서는 메시지를 계산기 서비스로 보내기 전에 필요에 따라 자동으로 변환하며, 계산기 클라이언트에서 액세스할 수 있도록 응답도 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-116">The routing service automatically converts the messages as necessary before sending them to the Calculator service and it also converts the responses so that the Calculator client can access them.</span></span>  
  
-   <span data-ttu-id="148ac-117">라우팅 서비스에서는 두 개의 계산기 서비스, 즉 기본 계산기 서비스와 백업 계산기 서비스를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-117">The routing service knows about two Calculator services: the primary Calculator service and the back-up Calculator service.</span></span> <span data-ttu-id="148ac-118">라우팅 서비스는 먼저 기본 Calculator 서비스 끝점과 통신하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-118">The routing service first attempts to communicate with the primary Calculator service endpoint.</span></span> <span data-ttu-id="148ac-119">끝점이 다운되어 통신에 실패하면 라우팅 서비스는 백업 계산기 서비스 끝점과 통신하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-119">If this attempt fails due to the endpoint being down, the routing service then tries to communicate with the back-up Calculator service endpoint.</span></span>  
  
 <span data-ttu-id="148ac-120">따라서 클라이언트에서 보내는 메시지는 라우터가 받아 실제 계산기 서비스로 다시 라우트합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-120">Thus messages sent from the client are received by the router and are rerouted to the actual Calculator service.</span></span> <span data-ttu-id="148ac-121">계산기 서비스 끝점이 다운된 경우 라우팅 서비스에서는 백업 계산기 서비스 끝점으로 메시지를 라우트합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-121">If the Calculator service endpoint is down, the routing service routes the message to the back-up Calculator service endpoint.</span></span> <span data-ttu-id="148ac-122">백업 계산기 서비스에서 보내는 메시지는 다시 서비스 라우터로 전송되고 라우터는 이를 다시 계산기 클라이언트에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-122">Messages from the back-up Calculator service are sent back to the service router, which in turn passes them back to the Calculator client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="148ac-123">백업 목록에는 둘 이상의 끝점이 정의되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-123">A back-up list can have more than one endpoint defined.</span></span> <span data-ttu-id="148ac-124">이 경우 백업 서비스 끝점이 다운되면 라우팅 서비스에서는 연결에 성공할 때까지 목록의 다음 백업 끝점에 연결하려는 시도를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-124">In this case if the back-up service endpoint is down, the routing service attempts to connect to the next back-up endpoint in the list until a successful connection occurs.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="148ac-125">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="148ac-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="148ac-126">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 RouterBridgingAndErrorHandling.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-126">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open RouterBridgingAndErrorHandling.sln.</span></span>  
  
2.  <span data-ttu-id="148ac-127">Visual Studio에서 F5 키나 Ctrl+Shift+B를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-127">Press F5 or CTRL+SHIFT+B in Visual Studio</span></span>  
  
    1.  <span data-ttu-id="148ac-128">F5 키를 누를 때 필요한 프로젝트가 자동 시작 하려는 경우 솔루션을 마우스 오른쪽 단추로 클릭를 **속성**, 및는 **시작 프로젝트** 노드 아래의 **공용속성**선택, **여러 개의 시작 프로젝트**, 모든 프로젝트 설정 하 고 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-128">If you would like to auto-launch the necessary projects when you press F5, right-click the solution, select **Properties**, and in the **Startup Project** node under **Common Properties**, select **Multiple Startup Projects**, and set all projects to **Start**.</span></span>  
  
    2.  <span data-ttu-id="148ac-129">Ctrl+Shift+B를 사용하여 프로젝트를 빌드하는 경우에는 다음 응용 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-129">If you build the project with CTRL+SHIFT+B, start the following applications:</span></span>  
  
        1.  <span data-ttu-id="148ac-130">계산기 클라이언트(./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="148ac-130">Calculator client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="148ac-131">계산기 서비스(./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="148ac-131">Calculator service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="148ac-132">라우팅 서비스(./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="148ac-132">Routing Service (./RoutingService/bin/RoutingService.exe)</span></span>  
  
3.  <span data-ttu-id="148ac-133">계산기 클라이언트에서 Enter 키를 눌러 클라이언트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-133">In the Calculator Client, press ENTER to start the client.</span></span>  
  
     <span data-ttu-id="148ac-134">다음과 같은 내용이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-134">You should see the following output:</span></span>  
  
    ```Output  
    Add(100,15.99) = 115.99  
    Subtract(145,76.54) = 68.46  
    Multiply(9,81.25) = 731.25  
    Divide(22,7) = 3.14285714285714  
    ```  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="148ac-135">코드 또는 App.config를 통해 구성 가능</span><span class="sxs-lookup"><span data-stu-id="148ac-135">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="148ac-136">이 샘플은 App.config 파일을 사용하여 라우터 동작을 정의하도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-136">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="148ac-137">App.config 파일이 인식되지 않도록 이 파일의 이름을 다른 이름으로 바꾸고 `ConfigureRouterViaCode()` 메서드 호출의 주석 처리를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-137">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to `ConfigureRouterViaCode()`.</span></span> <span data-ttu-id="148ac-138">어떤 방법을 사용하든 라우터 동작은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-138">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="148ac-139">시나리오</span><span class="sxs-lookup"><span data-stu-id="148ac-139">Scenario</span></span>  
 <span data-ttu-id="148ac-140">이 샘플에서는 프로토콜 브리지 및 오류 처리기 역할을 하는 서비스 라우터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-140">This sample demonstrates the service router acting as a protocol bridge and error handler.</span></span> <span data-ttu-id="148ac-141">이 시나리오에서는 내용 기반 라우팅이 발생하지 않으므로 라우팅 서비스는 대상 끝점의 미리 구성된 집합에 직접 메시지를 전달하도록 구성된 투명 프록시 노드 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-141">In this scenario, no content-based routing occurs; the routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span> <span data-ttu-id="148ac-142">또한 라우팅 서비스에서는 통신하도록 구성된 끝점에 메시지를 보내려고 할 때 발생하는 오류를 투명하게 처리하는 추가 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-142">The routing service also performs the additional steps of transparently handling errors that occur when it tries to send to the endpoints that it is configured to communicate with.</span></span> <span data-ttu-id="148ac-143">프로토콜 브리지 역할을 하는 라우팅 서비스를 사용하면 사용자가 외부 통신용 프로토콜과 내부 통신용 프로토콜을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-143">By acting as a protocol bridge, the routing service enables the user to define one protocol for external communication and another for internal communication.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="148ac-144">실제 시나리오</span><span class="sxs-lookup"><span data-stu-id="148ac-144">Real World Scenario</span></span>  
 <span data-ttu-id="148ac-145">Contoso에서는 상호 운용할 수는 서비스 끝점을 제공하면서 내부적으로 성능을 최적화하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-145">Contoso wants to provide an interoperable service endpoint to the world, while optimizing performance internally.</span></span> <span data-ttu-id="148ac-146">따라서 Contoso에서는 BasicHttpBinding을 사용하는 끝점을 통해 서비스를 노출하지만, 내부적으로는 라우팅 서비스를 통해 해당 서비스에서 사용하는 NetTcpBinding을 사용하는 끝점에 해당 연결을 브리징합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-146">Thus it exposes its services to the world through an endpoint using the BasicHttpBinding, while internally using the routing service to bridge that connection to the endpoint using NetTcpBinding, which its services use.</span></span> <span data-ttu-id="148ac-147">더욱이 Contoso에서는 프로덕션 서비스 중 어느 하나가 일시적으로 중지되더라도 정상적으로 서비스를 제공할 수 있기를 원하므로, 필요할 때 오류 처리 기능을 사용하여 자동으로 백업 끝점으로 장애 조치하는 라우터 서비스 뒤에 여러 개의 끝점을 가상화하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="148ac-147">Furthermore, Contoso wants its service offering to be tolerant of temporary outages in any one of their production services and thus virtualizes multiple endpoints behind the router service using the ’s error handling capabilities to automatically failover to back-up endpoints when necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="148ac-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="148ac-148">See Also</span></span>  
 [<span data-ttu-id="148ac-149">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="148ac-149">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
