---
title: "동적 재구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b20786ae-cce6-4f91-b6cb-9cae116faf8b
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 32339bbf40513f06c7a719c632f1c606c195b6bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="dynamic-reconfiguration"></a><span data-ttu-id="fe80a-102">동적 재구성</span><span class="sxs-lookup"><span data-stu-id="fe80a-102">Dynamic Reconfiguration</span></span>
<span data-ttu-id="fe80a-103">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 라우팅 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-103">This sample demonstrates the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] routing service.</span></span> <span data-ttu-id="fe80a-104">라우팅 서비스는 응용 프로그램에 내용 기반 라우터를 손쉽게 포함할 수 있게 해 주는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-104">The routing service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="fe80a-105">이 샘플에서는 라우팅 서비스를 사용하여 통신하도록 표준 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator 샘플을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-105">This sample adapts the standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator Sample to communicate using the routing service.</span></span> <span data-ttu-id="fe80a-106">이 샘플에서는 런타임 동안 라우팅 서비스를 동적으로 다시 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-106">This sample shows how the routing service can be dynamically reconfigured during runtime.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fe80a-107">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="fe80a-108">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="fe80a-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fe80a-109">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="fe80a-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fe80a-110">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\DynamicReconfiguration`  
  
## <a name="sample-details"></a><span data-ttu-id="fe80a-111">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="fe80a-111">Sample Details</span></span>  
 <span data-ttu-id="fe80a-112">런타임 도중 라우팅 서비스를 동적으로 다시 구성하기 위해 이 샘플에서는 새 <xref:System.ServiceModel.Routing.RoutingConfiguration> 개체를 만들고 이를 적용하는 타이머를 5초마다 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-112">To dynamically reconfigure the routing service during runtime, this sample fires a timer every five seconds that creates a new <xref:System.ServiceModel.Routing.RoutingConfiguration> object and applies it.</span></span> <span data-ttu-id="fe80a-113">이 구성에서는 일반 계산기 끝점이나 반올림 계산기 끝점 중 하나를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-113">This configuration references either the regular Calculator endpoint or the Rounding Calculator endpoint.</span></span> <span data-ttu-id="fe80a-114">계산기 클라이언트 응용 프로그램의 메시지가 반환되는 서비스는 라우팅 서비스가 해당 시점에 라우트하도록 구성된 대상에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-114">The Calculator Client application has its messages returned from one service or the other, depending on which one the routing service is configured to route to at that time.</span></span>  
  
 <span data-ttu-id="fe80a-115">사용자 지정 동작을 통해 동적으로 다시 구성하는 라우팅 서비스의 기능이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-115">The routing service’s capabilitiy for dynamic reconfiguration through a custom behavior is used.</span></span> <span data-ttu-id="fe80a-116">이 사용자 지정 동작은 5초마다 발생하는 간단한 스레드 타이머가 들어 있고 `UpdateRules` 메서드에 대한 콜백을 생성하는 서비스 확장을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-116">This custom behavior attaches a service extension, which contains a simple thread timer that fires every five seconds, which results in a callback to the `UpdateRules` method.</span></span> <span data-ttu-id="fe80a-117">이 콜백은 새 라우팅 구성을 만들고 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-117">This callback creates and applies the new routing configuration.</span></span> <span data-ttu-id="fe80a-118">실제 배포에서 이 콜백은 SQL-Event 알림 또는 WS-Discovery 알림과 같은 일부 다른 형식의 이벤트 결과로 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-118">In an actual deployment, this callback would likely be accomplished as a result of some other type of event, such as a SQL-Event notification, or a WS-Discovery announcement.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="fe80a-119">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="fe80a-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="fe80a-120">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 DynamicReconfiguration.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open DynamicReconfiguration.sln.</span></span>  
  
2.  <span data-ttu-id="fe80a-121">열려는 **솔루션 탐색기**선택, **솔루션 탐색기** 에서 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="fe80a-121">To open **Solution Explorer**, select **Solution Explorer** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="fe80a-122">키를 눌러 **F5** 또는 **CTRL + SHIFT + B** 에서 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-122">Press **F5** or **CTRL+SHIFT+B** in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="fe80a-123">키를 누를 때 필요한 프로젝트가 자동 시작을 원하는 경우 **F5**솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-123">If you would like to auto-launch the necessary projects when you press **F5**, right-click the solution and select **Properties**.</span></span> <span data-ttu-id="fe80a-124">선택 된 **시작 프로젝트** 노드 아래의 **공용 속성** 왼쪽된 창에서.</span><span class="sxs-lookup"><span data-stu-id="fe80a-124">Select the **Startup Project** node under **Common Properties** in the left pane.</span></span> <span data-ttu-id="fe80a-125">선택은 **여러 개의 시작 프로젝트** 라디오 단추 및 모든 프로젝트에 설정 된 **시작** 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-125">Select the **Multiple Startup Projects**  radio button and set all of the projects to have the **Start** action.</span></span>  
  
    2.  <span data-ttu-id="fe80a-126">사용 하 여 프로젝트를 빌드하면 **CTRL + SHIFT + B**, 다음 응용 프로그램을 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-126">If you build the project with **CTRL+SHIFT+B**, you must start the following applications:</span></span>  
  
        1.  <span data-ttu-id="fe80a-127">계산기 클라이언트(./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="fe80a-127">Calculator Client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="fe80a-128">계산기 서비스(./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="fe80a-128">Calculator Service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="fe80a-129">반올림 계산기 서비스(./RoundingCalcService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="fe80a-129">Routing Calculator Service (./RoundingCalcService/bin/service.exe)</span></span>  
  
        4.  <span data-ttu-id="fe80a-130">라우팅 서비스(./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="fe80a-130">RoutingService (./RoutingService/bin/RoutingService.exe)</span></span>  
  
4.  <span data-ttu-id="fe80a-131">계산기 클라이언트의 콘솔 창에서 Enter 키를 눌러 클라이언트를 시작하고 계산기 서비스 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-131">In the console window of the Calculator Client, press ENTER to start the client and to call the Calculator service operations.</span></span>  
  
     <span data-ttu-id="fe80a-132">라우팅 서비스에서는 5초마다 라우팅 구성이 동적으로 변경될 때 반올림 계산기와 일반 계산기에 메시지를 교대로 라우트합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-132">The routing service routes messages to the Rounding Calculator and to the regular Calculator alternately as the routing configuration changes dynamically every five seconds.</span></span> <span data-ttu-id="fe80a-133">라우팅 서비스에서 메시지를 보내도록 구성된 대상 끝점에 따라 클라이언트 콘솔 창에 출력되는 내용이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-133">Depending on which endpoint the routing service is configured to send messages to there are different outputs in the client console window.</span></span>  
  
5.  <span data-ttu-id="fe80a-134">Enter 키를 반복해서 5초 이상씩 계속 누르고 서비스 결과의 변화를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-134">Continue pressing ENTER repeatedly over more than five seconds and observe the change in the results from the service.</span></span>  
  
    1.  <span data-ttu-id="fe80a-135">다음은 라우터 서비스가 메시지를 반올림 계산기 서비스로 라우트하도록 구성된 경우에 반환되는 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-135">The following is the output returned if the Router Service is configured to route messages to the Rounding Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.2  
        Divide(22,7) = 3.1  
        ```  
  
    2.  <span data-ttu-id="fe80a-136">다음은 라우팅 서비스가 메시지를 일반 계산기 서비스로 라우트하도록 구성된 경우에 반환되는 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-136">The following is the output returned if the routing service is configured to route messages to the regular Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
6.  <span data-ttu-id="fe80a-137">계산기 서비스 및 반올림 계산기 서비스에서도 호출된 작업의 로그를 각 해당 콘솔 창에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-137">The Calculator Service and the Rounding Calculator Service also print out a log of the operations invoked to their respective console windows.</span></span>  
  
7.  <span data-ttu-id="fe80a-138">클라이언트 콘솔 창에서 "quit"를 입력 하 고 enter 키를 눌러 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-138">In the client console window, type "quit" and press ENTER to exit.</span></span>  
  
8.  <span data-ttu-id="fe80a-139">서비스 콘솔 창에서 Enter 키를 눌러 서비스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-139">Press ENTER in the services console windows to terminate the services.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="fe80a-140">시나리오</span><span class="sxs-lookup"><span data-stu-id="fe80a-140">Scenario</span></span>  
 <span data-ttu-id="fe80a-141">이 샘플에서는 한 끝점을 통해 노출되는 서비스의 여러 형식 또는 구현을 허용하는 내용 기반 라우터의 역할을 하는 라우터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-141">This sample demonstrates the router acting as a content-based router allowing multiple types or implementation of services to be exposed through one endpoint.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="fe80a-142">실제 시나리오</span><span class="sxs-lookup"><span data-stu-id="fe80a-142">Real World Scenario</span></span>  
 <span data-ttu-id="fe80a-143">Contoso에서는 모든 서비스를 가상화하여 서로 다른 여러 형식의 서비스에 액세스할 수 있게 해 주는 하나의 끝점만 공개하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-143">Contoso wants to virtualize all of their services to expose only one endpoint publicly through which they offer access to multiple different types of services.</span></span> <span data-ttu-id="fe80a-144">이 경우 라우팅 서비스의 내용 기반 라우팅 기능을 사용하여 들어오는 요청을 보낼 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fe80a-144">In this case they utilize the routing service’s content-based routing capabilities to determine where the incoming requests should be sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe80a-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe80a-145">See Also</span></span>  
 [<span data-ttu-id="fe80a-146">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="fe80a-146">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
