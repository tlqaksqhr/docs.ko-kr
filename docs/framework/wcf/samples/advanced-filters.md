---
title: "고급 필터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d81590f-e036-4f96-824a-4a187f462764
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 357b57bb39ca31b48d21cb83209a72d0b3d12a62
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="advanced-filters"></a><span data-ttu-id="bf729-102">고급 필터</span><span class="sxs-lookup"><span data-stu-id="bf729-102">Advanced Filters</span></span>
<span data-ttu-id="bf729-103">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 라우팅 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-103">This sample demonstrates a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] routing service.</span></span> <span data-ttu-id="bf729-104">라우팅 서비스는 응용 프로그램에 내용 기반 라우터를 손쉽게 포함할 수 있게 해 주는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-104">The routing service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="bf729-105">이 샘플에서는 라우팅 서비스를 사용하여 통신하도록 표준 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator 샘플을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-105">This sample adapts the standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator sample to communicate using the routing service.</span></span> <span data-ttu-id="bf729-106">이 샘플에서는 메시지 필터 및 메시지 필터 테이블을 사용하여 내용 기반 라우팅 논리를 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-106">This sample shows how to define content-based routing logic through the use of message filters and message filter tables.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bf729-107">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bf729-108">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bf729-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bf729-109">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="bf729-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bf729-110">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedFilters`  
  
## <a name="sample-details"></a><span data-ttu-id="bf729-111">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="bf729-111">Sample Details</span></span>  
 <span data-ttu-id="bf729-112">다음 표에서는 라우팅 서비스의 메시지 필터 테이블에 추가되는 메시지 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-112">The following table shows the message filters that are added to the message filter table of the routing service.</span></span>  
  
|<span data-ttu-id="bf729-113">필터</span><span class="sxs-lookup"><span data-stu-id="bf729-113">Filter</span></span>|<span data-ttu-id="bf729-114">규칙</span><span class="sxs-lookup"><span data-stu-id="bf729-114">Rule</span></span>|<span data-ttu-id="bf729-115">우선 순위</span><span class="sxs-lookup"><span data-stu-id="bf729-115">Priority</span></span>|  
|------------|----------|--------------|  
|<span data-ttu-id="bf729-116">If(헤더 있음)</span><span class="sxs-lookup"><span data-stu-id="bf729-116">If (has header)</span></span>|<span data-ttu-id="bf729-117">반올림</span><span class="sxs-lookup"><span data-stu-id="bf729-117">Rounding</span></span>|<span data-ttu-id="bf729-118">2</span><span class="sxs-lookup"><span data-stu-id="bf729-118">2</span></span>|  
|<span data-ttu-id="bf729-119">If(Ep2에 나타남)</span><span class="sxs-lookup"><span data-stu-id="bf729-119">If (showed up on Ep2)</span></span>|<span data-ttu-id="bf729-120">기본</span><span class="sxs-lookup"><span data-stu-id="bf729-120">Regular</span></span>|<span data-ttu-id="bf729-121">1</span><span class="sxs-lookup"><span data-stu-id="bf729-121">1</span></span>|  
|<span data-ttu-id="bf729-122">If(Address2와 함께 나타남)</span><span class="sxs-lookup"><span data-stu-id="bf729-122">If (showed up with Address2)</span></span>|<span data-ttu-id="bf729-123">반올림</span><span class="sxs-lookup"><span data-stu-id="bf729-123">Rounding</span></span>|<span data-ttu-id="bf729-124">1</span><span class="sxs-lookup"><span data-stu-id="bf729-124">1</span></span>|  
|<span data-ttu-id="bf729-125">If(RoundRobin1)</span><span class="sxs-lookup"><span data-stu-id="bf729-125">If (RoundRobin1)</span></span>|<span data-ttu-id="bf729-126">기본</span><span class="sxs-lookup"><span data-stu-id="bf729-126">Regular</span></span>|<span data-ttu-id="bf729-127">0</span><span class="sxs-lookup"><span data-stu-id="bf729-127">0</span></span>|  
|<span data-ttu-id="bf729-128">If(RoundRobin2)</span><span class="sxs-lookup"><span data-stu-id="bf729-128">If (RoundRobin2)</span></span>|<span data-ttu-id="bf729-129">반올림</span><span class="sxs-lookup"><span data-stu-id="bf729-129">Rounding</span></span>|<span data-ttu-id="bf729-130">0</span><span class="sxs-lookup"><span data-stu-id="bf729-130">0</span></span>|  
  
 <span data-ttu-id="bf729-131">메시지 필터와 메시지 필터 테이블은 코드 또는 응용 프로그램 구성 파일에서 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-131">The message filters and message filter tables can be created and configured either through code or in the application configuration file.</span></span> <span data-ttu-id="bf729-132">이 샘플의 경우 RoutingService\routing.cs 파일에서는 코드를 통해 정의된 메시지 필터 및 메시지 필터 테이블을 볼 수 있으며, RoutingService\App.config 파일에서는 응용 프로그램 구성 파일에 정의된 메시지 필터 및 메시지 필터 테이블을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-132">For this sample, you can find the message filters and message filter tables defined through code in the RoutingService\routing.cs file, or defined in the application configuration file in the RoutingService\App.config file.</span></span> <span data-ttu-id="bf729-133">다음 단락에서는 코드를 통해 이 샘플의 메시지 필터 및 메시지 필터 테이블을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-133">The following paragraphs describe how the message filters and message filter tables are created for this sample through code.</span></span>  
  
 <span data-ttu-id="bf729-134">첫 번째 필터인 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>는 사용자 지정 헤더를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-134">First, an <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> looks for the custom header.</span></span> <span data-ttu-id="bf729-135"><xref:System.ServiceModel.WSHttpBinding>의 결과는 SOAP 1.2를 사용하는 봉투 버전이므로 SOAP 1.2 네임스페이스를 사용하기 위해 XPath 문이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-135">Note that <xref:System.ServiceModel.WSHttpBinding> results in an envelope version using SOAP 1.2, so the XPath statement is defined to use the SOAP 1.2 namespace.</span></span> <span data-ttu-id="bf729-136"><xref:System.ServiceModel.Dispatcher.XPathMessageFilter>의 기본 네임스페이스 관리자가 SOAP 1.2 네임스페이스의 접두사 /s12를 이미 정의했으므로 이 접두사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-136">The default namespace manager for <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>s already defines a prefix for the SOAP 1.2 namespace, /s12, which can be used.</span></span> <span data-ttu-id="bf729-137">그러나 기본 네임스페이스 관리자에 클라이언트가 실제 헤더 값을 정의하는 데 사용하는 사용자 지정 네임스페이스는 없으므로 해당 접두사를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-137">However, the default namespace manager does not have the custom namespace that the client uses to define the actual header value, so that prefix must be defined.</span></span> <span data-ttu-id="bf729-138">이 헤더와 함께 표시되는 모든 메시지는 이 필터와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-138">Any message that shows up with this header matches this filter.</span></span>  
  
```  
XPathMessageContext namespaceManager = new XPathMessageContext();  
namespaceManager.AddNamespace("custom", "http://my.custom.namespace/");  
  
XPathMessageFilter xpathFilter = new XPathMessageFilter("/s12:Envelope/s12:Header/custom:RoundingCalculator = 1", namespaceManager);  
```  
  
 <span data-ttu-id="bf729-139">두 번째 필터는 <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>에서 받은 모든 메시지를 일치시키는 `calculatorEndpoint`입니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-139">The second filter is an <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>, which matches any message that was received on the `calculatorEndpoint`.</span></span> <span data-ttu-id="bf729-140">끝점 이름은 서비스 끝점 개체가 만들어질 때 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-140">The endpoint name is defined when a service endpoint object is created.</span></span>  
  
```  
EndpointNameMessageFilter endpointNameFilter = new EndpointNameMessageFilter("calculatorEndpoint");  
```  
  
 <span data-ttu-id="bf729-141">세 번째 필터는 <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>입니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-141">The third filter is a <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>.</span></span> <span data-ttu-id="bf729-142">이 필터는 제공된 주소 접두사 또는 앞 부분과 일치하는 주소를 가진 끝점에 표시되는 모든 메시지를 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-142">This matches any message that showed up on an endpoint with an address that matches the address prefix (or the front portion) provided.</span></span> <span data-ttu-id="bf729-143">이 예제에서 주소 접두사는 "http://localhost/routingservice/router/rounding/"으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-143">In this example the address prefix is defined as "http://localhost/routingservice/router/rounding/".</span></span> <span data-ttu-id="bf729-144">즉, 주소가 "http://localhost/routingservice/router/rounding/*"로 지정된 모든 들어오는 메시지는 이 필터와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-144">This means that any incoming messages that are addressed to "http://localhost/routingservice/router/rounding/*" are matched by this filter.</span></span> <span data-ttu-id="bf729-145">이 경우 주소가 "http://localhost/routingservice/router/rounding/calculator"인 반올림 계산기 끝점에 표시되는 메시지가 이에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-145">In this case, it is messages that show up on the Rounding Calculator endpoint, which has the address of "http://localhost/routingservice/router/rounding/calculator".</span></span>  
  
```  
PrefixEndpointAddressMessageFilter prefixAddressFilter = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://localhost/routingservice/router/rounding/"));  
```  
  
 <span data-ttu-id="bf729-146">마지막 두 메시지 필터는 사용자 지정 <xref:System.ServiceModel.Dispatcher.MessageFilter>입니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-146">The last two message filters are custom <xref:System.ServiceModel.Dispatcher.MessageFilter>s.</span></span> <span data-ttu-id="bf729-147">이 예제에서는 "RoundRobin" 메시지 필터가 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-147">In this example, a "RoundRobin" message filter is used.</span></span> <span data-ttu-id="bf729-148">이 메시지 필터는 제공된 RoutingService\RoundRobinMessageFilter.cs 파일에 만들어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-148">This message filter is created in the provided RoutingService\RoundRobinMessageFilter.cs file.</span></span> <span data-ttu-id="bf729-149">이 두 필터는 동일한 그룹으로 설정된 경우 번갈아서 메시지 일치를 보고하다가 메시지 불일치를 보고하므로 한 번에 한 필터만 `true`로 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-149">These filters, when set to the same group, alternate between reporting that they match the message and that they do not, such that only one of them responds `true` at a time.</span></span>  
  
```  
RoundRobinMessageFilter roundRobinFilter1 = new RoundRobinMessageFilter("group1");  
  
RoundRobinMessageFilter roundRobinFilter2 = new RoundRobinMessageFilter("group1");  
```  
  
 <span data-ttu-id="bf729-150">그런 다음에는 이러한 모든 메시지가 <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-150">Next, all of those messages are added to a <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>.</span></span> <span data-ttu-id="bf729-151">이때 메시지 필터 테이블에서 필터가 실행되는 순서에 영향을 주도록 우선 순위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-151">In doing so, priorities are specified to influence the order in which the message filter table executes the filters.</span></span> <span data-ttu-id="bf729-152">우선 순위가 높을수록 일찍 실행되고 우선 순위가 낮을수록 나중에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-152">The higher the priority, the sooner the filter is executed; the lower the priority, the later a filter is executed.</span></span> <span data-ttu-id="bf729-153">따라서 우선 순위가 2인 필터는 우선 순위가 1인 필터보다 먼저 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-153">Thus a filter at priority 2 runs before a filter at priority 1.</span></span> <span data-ttu-id="bf729-154">우선 순위가 지정되지 않은 경우 기본 우선 순위는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-154">The default priority level if none is specified is 0.</span></span> <span data-ttu-id="bf729-155">메시지 필터 테이블에서는 지정된 우선 순위의 필터를 모두 실행한 후에 다음으로 낮은 우선 순위로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-155">A message filter table executes all of the filters at a given priority level before moving to the next lowest priority level.</span></span> <span data-ttu-id="bf729-156">특정 우선 순위에서 일치 항목을 찾은 경우 메시지 필터 테이블에서는 다음으로 낮은 우선 순위에서 일치 항목을 계속 찾으려고 시도하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-156">If a match is found at a particular priority, then the message filter table does not continue trying to find matches at the next lower priority.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf729-157">이 예제에서는 메시지 필터 우선 순위를 사용하는 방법을 보여 주지만, 일반적으로는 우선 순위 없이도 제대로 작동하도록 필터를 디자인하고 구성하는 것이 성능과 디자인 면에서 보다 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-157">While this example shows how to use message filter priorities, in general it is more performant and better design to design and configure your filters such that they do not require prioritization to function correctly.</span></span>  
  
 <span data-ttu-id="bf729-158">첫 번째로 추가되는 필터는 XPath 필터이며 해당 우선 순위는 2로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-158">The first filter to be added is the XPath filter and its priority is set to 2.</span></span> <span data-ttu-id="bf729-159">이 필터가 첫 번째로 실행되는 메시지 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-159">This is the first message filter that executes.</span></span> <span data-ttu-id="bf729-160">이 필터로 사용자 지정 헤더를 찾은 경우 다른 필터의 결과에 상관없이 해당 메시지가 반올림 계산기 끝점으로 라우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-160">If it finds the custom header, regardless of what the results of the other filters would be, the message is routed to the Rounding Calculator endpoint.</span></span>  
  
 <span data-ttu-id="bf729-161">우선 순위 1에서는 두 개의 필터가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-161">At priority 1, two filters are added.</span></span> <span data-ttu-id="bf729-162">이 두 필터는 우선 순위가 2인 XPath 필터로 일치하는 메시지를 찾지 못한 경우에만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-162">Again, these only run if the XPath filter at priority 2 does not match the message.</span></span> <span data-ttu-id="bf729-163">이 두 필터는 메시지가 표시될 때 메시지 주소로 지정된 위치를 확인하는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-163">These two filters show two different ways to determine where the message was addressed when it showed up.</span></span> <span data-ttu-id="bf729-164">두 필터는 메시지가 두 끝점 중 하나에 도착했는지 여부를 효율적으로 확인하며 동시에 둘 모두가 `true`를 반환하지는 않으므로 동일한 우선 순위에서 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-164">Because the two filters effectively check to see whether the message arrived at one of the two endpoints, they can be run at the same priority level because they do not both return `true` at the same time.</span></span>  
  
 <span data-ttu-id="bf729-165">마지막으로, 최하위 우선 순위인 우선 순위 0에서는 RoundRobin 메시지 필터가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-165">Finally, at Priority 0 (the lowest priority) run the RoundRobin message filters.</span></span> <span data-ttu-id="bf729-166">이러한 필터는 동일한 그룹 이름으로 구성되므로 한 번에 하나만 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-166">Because the filters are configured with the same group name, only one of them matches at a time.</span></span> <span data-ttu-id="bf729-167">사용자 지정 헤더가 있는 모든 메시지는 라우트되고 모두 가상화된 특정 끝점으로 주소가 지정되었으므로 RoundRobin 메시지 필터로 처리되는 메시지는 사용자 지정 헤더 없이 기본 라우터 끝점으로 주소가 지정된 메시지뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-167">Because all messages with the custom header have been routed and all those addressed to the specific virtualized endpoints, messages handled by the RoundRobin message filters are only messages that were addressed to the default router endpoint without the custom header.</span></span> <span data-ttu-id="bf729-168">이러한 메시지는 각 호출마다 하나씩 전환되므로 작업 중 절반은 일반 계산기 끝점으로 이동하고 나머지 절반은 반올림 계산기 끝점으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-168">Because these messages switch on a message for each call, half of the operations go to the Regular Calculator endpoint and the other half go to the Rounding Calculator endpoint.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="bf729-169">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="bf729-169">To use this sample</span></span>  
  
1.  <span data-ttu-id="bf729-170">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 AdvancedFilters.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-170">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open AdvancedFilters.sln.</span></span>  
  
2.  <span data-ttu-id="bf729-171">열려는 **솔루션 탐색기**선택, **솔루션 탐색기** 에서 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="bf729-171">To open **Solution Explorer**, select **Solution Explorer** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="bf729-172">[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 F5 키 또는 Ctrl+Shift+B를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-172">Press F5 or CTRL+SHIFT+B in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="bf729-173">F5 키를 누를 때 필요한 프로젝트가 자동 시작 하려는 경우 솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-173">If you would like to auto-launch the necessary projects when you press F5, right-click the solution and select **Properties**.</span></span> <span data-ttu-id="bf729-174">선택 된 **시작 프로젝트** 노드 아래의 **공용 속성** 왼쪽된 창에서.</span><span class="sxs-lookup"><span data-stu-id="bf729-174">Select the **Startup Project** node under **Common Properties** in the left pane.</span></span> <span data-ttu-id="bf729-175">선택은 **여러 개의 시작 프로젝트** 라디오 단추 및 모든 프로젝트에 설정 된 **시작** 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-175">Select the **Multiple Startup Projects**  radio button and set all of the projects to have the **Start** action.</span></span>  
  
    2.  <span data-ttu-id="bf729-176">Ctrl+Shift+B를 사용하여 프로젝트를 빌드할 경우에는 다음 응용 프로그램을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-176">If you build the project with CTRL+SHIFT+B, you must start the following applications:</span></span>  
  
        1.  <span data-ttu-id="bf729-177">계산기 클라이언트(./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="bf729-177">Calculator Client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="bf729-178">계산기 서비스(./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="bf729-178">Calculator Service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="bf729-179">반올림 계산기 서비스(./RoundingCalcService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="bf729-179">Routing Calculator Service (./RoundingCalcService/bin/service.exe)</span></span>  
  
        4.  <span data-ttu-id="bf729-180">라우팅 서비스(./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="bf729-180">RoutingService (./RoutingService/bin/RoutingService.exe)</span></span>  
  
4.  <span data-ttu-id="bf729-181">계산기 클라이언트의 콘솔 창에서 Enter 키를 눌러 클라이언트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-181">In the console window of the Calculator client, press ENTER to start the client.</span></span> <span data-ttu-id="bf729-182">그러면 클라이언트에서는 선택 가능한 대상 끝점 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-182">The client returns a list of destination endpoints to choose from.</span></span>  
  
5.  <span data-ttu-id="bf729-183">해당하는 문자를 입력하여 대상 끝점을 선택하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-183">Choose a destination endpoint by typing its corresponding letter and press ENTER.</span></span>  
  
6.  <span data-ttu-id="bf729-184">그런 다음 클라이언트에서는 사용자 지정 헤더를 추가할지 여부를 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-184">Next, the client asks you if you want to add a custom header.</span></span> <span data-ttu-id="bf729-185">예의 경우 Y 키, 아니요의 경우 N 키를 누른 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-185">Press Y for Yes or N for No, then press ENTER.</span></span>  
  
7.  <span data-ttu-id="bf729-186">선택에 따라 서로 다른 출력이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-186">Depending on the selections you made, you should see different outputs.</span></span>  
  
    1.  <span data-ttu-id="bf729-187">다음은 메시지에 사용자 지정 헤더를 추가한 경우 반환되는 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-187">The following is the output returned if you added a custom header to the messages.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    2.  <span data-ttu-id="bf729-188">다음은 사용자 지정 헤더가 없는 반올림 계산기 끝점을 선택한 경우 반환되는 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-188">The following is the output returned if you chose the Rounding Calculator endpoint without a custom header.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    3.  <span data-ttu-id="bf729-189">다음은 사용자 지정 헤더가 없는 일반 계산기 끝점을 선택한 경우 반환되는 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-189">The following is the output returned if you chose the Regular Calculator endpoint without a custom header.</span></span>  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68. 46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
    4.  <span data-ttu-id="bf729-190">다음은 사용자 지정 헤더가 없는 기본 라우터 끝점을 선택한 경우 반환되는 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-190">The following is the output returned if you chose the Default Router endpoint without a custom header.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.14285714285714  
        ```  
  
8.  <span data-ttu-id="bf729-191">계산기 서비스 및 반올림 계산기 서비스에서도 호출된 작업의 로그를 각 해당 콘솔 창에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-191">The Calculator Service and the Rounding Calculator Service also prints out a log of the operations invoked to their respective console windows.</span></span>  
  
9. <span data-ttu-id="bf729-192">클라이언트 콘솔 창에 입력 `quit` 종료 하려면 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-192">In the client console window, type `quit` and press ENTER to exit.</span></span>  
  
10. <span data-ttu-id="bf729-193">서비스 콘솔 창에서 Enter 키를 눌러 서비스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-193">Press ENTER in the services console windows to terminate the services.</span></span>  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="bf729-194">코드 또는 App.config를 통해 구성 가능</span><span class="sxs-lookup"><span data-stu-id="bf729-194">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="bf729-195">이 샘플은 App.config 파일을 사용하여 라우터 동작을 정의하도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-195">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="bf729-196">RoutingService\App.config 파일이 인식되지 않도록 이 파일의 이름을 다른 이름으로 바꾸고, RoutingService\routing.cs에서 `ConfigureRouterViaCode()` 메서드 호출의 주석 처리를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-196">You can also change the name of the RoutingService\App.config file to something else so that it is not recognized and uncomment the method call to `ConfigureRouterViaCode()` in RoutingService\routing.cs.</span></span> <span data-ttu-id="bf729-197">어떤 방법을 사용하든 라우터 동작은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-197">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="bf729-198">시나리오</span><span class="sxs-lookup"><span data-stu-id="bf729-198">Scenario</span></span>  
 <span data-ttu-id="bf729-199">이 샘플에서는 한 끝점을 통해 노출되는 서비스의 여러 형식 또는 구현을 허용하는 내용 기반 라우터의 역할을 하는 라우터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-199">This sample demonstrates the router acting as a content-based router allowing multiple types or implementation of services to be exposed through one endpoint.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="bf729-200">실제 시나리오</span><span class="sxs-lookup"><span data-stu-id="bf729-200">Real World Scenario</span></span>  
 <span data-ttu-id="bf729-201">Contoso에서는 모든 서비스를 가상화하여 서로 다른 여러 형식의 서비스에 액세스할 수 있게 해 주는 하나의 끝점만 공개하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-201">Contoso wants to virtualize all of their services to expose only one endpoint publicly through which they offer access to multiple different types of services.</span></span> <span data-ttu-id="bf729-202">이 경우 라우팅 서비스의 내용 기반 라우팅 기능을 사용하여 들어오는 요청을 보낼 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bf729-202">In this case they utilize the routing service’s content-based routing capabilities to determine where the incoming requests should be sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf729-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf729-203">See Also</span></span>  
 [<span data-ttu-id="bf729-204">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="bf729-204">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
