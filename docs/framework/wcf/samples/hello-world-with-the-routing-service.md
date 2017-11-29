---
title: "Hello World 라우팅 서비스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6a03f3eeab6ce30c011a6f67c64cc3997130c895
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="hello-world-with-the-routing-service"></a><span data-ttu-id="5a2e1-102">Hello World 라우팅 서비스</span><span class="sxs-lookup"><span data-stu-id="5a2e1-102">Hello World with the Routing Service</span></span>
<span data-ttu-id="5a2e1-103">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 라우팅 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-103">This sample demonstrates the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Routing Service.</span></span> <span data-ttu-id="5a2e1-104">라우팅 서비스는 응용 프로그램에 내용 기반 라우터를 손쉽게 포함할 수 있게 해 주는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-104">The Routing Service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="5a2e1-105">이 샘플에서는 라우팅 서비스를 사용하여 통신하도록 표준 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator 샘플을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-105">This sample adapts the standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator Sample to communicate using the Routing Service.</span></span> <span data-ttu-id="5a2e1-106">이 샘플에서 계산기 클라이언트는 라우터에 의해 노출된 끝점으로 메시지를 보내도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-106">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="5a2e1-107">라우팅 서비스는 전송된 모든 메시지를 승인하고 이를 계산기 서비스에 해당하는 끝점에 전달하도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-107">The Routing Service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="5a2e1-108">따라서 클라이언트에서 보내는 메시지는 라우터가 받아 실제 계산기 서비스로 다시 라우트합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-108">Thus messages sent from the client are received by the router and re-routed to the actual Calculator service.</span></span> <span data-ttu-id="5a2e1-109">계산기 서비스에서 보내는 메시지는 다시 라우터로 전송되고 라우터는 이를 다시 계산기 클라이언트에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-109">Messages from the Calculator service are sent back to the router, which in turn passes them back to the Calculator client.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="5a2e1-110">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="5a2e1-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="5a2e1-111">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 HelloRoutingService.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-111">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open HelloRoutingService.sln.</span></span>  
  
2.  <span data-ttu-id="5a2e1-112">F5 또는 Ctrl+Shift+B를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-112">Press F5 or CTRL+SHIFT+B.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5a2e1-113">F5 키를 누르면 계산기 클라이언트가 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-113">If you press F5, the Calculator Client automatically starts.</span></span> <span data-ttu-id="5a2e1-114">Ctrl+Shift+B(빌드)를 누를 경우에는 다음 응용 프로그램을 직접 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-114">If you press CTRL+SHIFT+B (build), you must start following applications yourself.</span></span>  
    >   
    >  1.  <span data-ttu-id="5a2e1-115">계산기 클라이언트(./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="5a2e1-115">Calculator client (./CalculatorClient/bin/client.exe</span></span>  
    > 2.  <span data-ttu-id="5a2e1-116">계산기 서비스(./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="5a2e1-116">Calculator service (./CalculatorService/bin/service.exe)</span></span>  
    > 3.  <span data-ttu-id="5a2e1-117">라우팅 서비스(./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="5a2e1-117">Routing service (./RoutingService/bin/RoutingService.exe)</span></span>  
  
3.  <span data-ttu-id="5a2e1-118">Enter 키를 눌러 클라이언트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-118">Press ENTER to start the client.</span></span>  
  
     <span data-ttu-id="5a2e1-119">다음과 같은 내용이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-119">You should see the following output:</span></span>  
  
     <span data-ttu-id="5a2e1-120">Add(100,15.99) = 115.99</span><span class="sxs-lookup"><span data-stu-id="5a2e1-120">Add(100,15.99) = 115.99</span></span>  
  
     <span data-ttu-id="5a2e1-121">Subtract(145,76.54) = 68.46</span><span class="sxs-lookup"><span data-stu-id="5a2e1-121">Subtract(145,76.54) = 68.46</span></span>  
  
     <span data-ttu-id="5a2e1-122">Multiply(9,81.25) = 731.25</span><span class="sxs-lookup"><span data-stu-id="5a2e1-122">Multiply(9,81.25) = 731.25</span></span>  
  
     <span data-ttu-id="5a2e1-123">Divide(22,7) = 3.14285714285714</span><span class="sxs-lookup"><span data-stu-id="5a2e1-123">Divide(22,7) = 3.14285714285714</span></span>  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="5a2e1-124">코드 또는 App.Config를 통해 구성 가능</span><span class="sxs-lookup"><span data-stu-id="5a2e1-124">Configurable via Code or App.Config</span></span>  
 <span data-ttu-id="5a2e1-125">이 샘플은 App.config 파일을 사용하여 라우터 동작을 정의하도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-125">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="5a2e1-126">App.config 파일이 인식되지 않도록 이 파일의 이름을 다른 이름으로 바꾸고 ConfigureRouterViaCode() 메서드 호출의 주석 처리를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-126">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to ConfigureRouterViaCode().</span></span> <span data-ttu-id="5a2e1-127">어떤 방법을 사용하든 라우터 동작은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-127">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="5a2e1-128">시나리오</span><span class="sxs-lookup"><span data-stu-id="5a2e1-128">Scenario</span></span>  
 <span data-ttu-id="5a2e1-129">이 샘플에서는 기본 메시지 펌프 역할을 하는 라우터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-129">This sample demonstrates the router acting as a basic message pump.</span></span> <span data-ttu-id="5a2e1-130">라우팅 서비스는 미리 구성된 대상 끝점 집합에 직접 메시지를 전달하도록 구성된 투명 프록시 노드 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-130">The routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="5a2e1-131">실제 시나리오</span><span class="sxs-lookup"><span data-stu-id="5a2e1-131">Real World Scenario</span></span>  
 <span data-ttu-id="5a2e1-132">Contoso에서는 서비스의 명명, 주소 지정, 구성 및 보안과 관련하여 유연성을 향상시키려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-132">Contoso wants to increase the flexibility it has in the naming, addressing, configuration, and security of its services.</span></span> <span data-ttu-id="5a2e1-133">이를 위해 Contoso에서는 공개 끝점 역할을 할 서비스 앞에 기본 메시지 펌프를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-133">To do this, they place a basic message pump in front of their services to act as a public facing endpoint.</span></span> <span data-ttu-id="5a2e1-134">이렇게 하면 실제 서비스 앞에 추가 보안 기능을 배치할 수 있으며 나중에 확장된 솔루션이나 서비스 버전 관리를 보다 쉽게 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-134">This allows them to place additional security in front of their actual services and make it easier to implement scaled out solutions or service versioning at a later date.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5a2e1-135">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-135">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5a2e1-136">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5a2e1-137">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5a2e1-138">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a2e1-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a><span data-ttu-id="5a2e1-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a2e1-139">See Also</span></span>  
 [<span data-ttu-id="5a2e1-140">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="5a2e1-140">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
