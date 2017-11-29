---
title: "WCF Discovery 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84fad0e4-23b1-45b5-a2d4-c9cdf90bbb22
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1afd3d94ceb3389a7d87528371925120f3c92764
ms.sourcegitcommit: e99dfadbca1992c187179b6a3b42bef44534ebb6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2017
---
# <a name="wcf-discovery-overview"></a><span data-ttu-id="0f5fd-102">WCF Discovery 개요</span><span class="sxs-lookup"><span data-stu-id="0f5fd-102">WCF Discovery Overview</span></span>
<span data-ttu-id="0f5fd-103">Discovery API는 WS-Discovery 프로토콜을 사용한 웹 서비스의 동적 게시 및 검색을 위한 통합 프로그래밍 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-103">The Discovery APIs provide a unified programming model for the dynamic publication and discovery of Web services using the WS-Discovery protocol.</span></span> <span data-ttu-id="0f5fd-104">이러한 API를 통해 서비스는 스스로를 게시할 수 있고 클라이언트는 게시된 서비스를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-104">These APIs allow services to publish themselves and clients to find published services.</span></span> <span data-ttu-id="0f5fd-105">서비스가 검색 가능하게 되면 해당 서비스는 검색 요청을 수신하고 이에 대해 응답하는 것 외에 알림 메시지를 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-105">Once a service is made discoverable, the service has the ability to send announcement messages as well as listen for and respond to discovery requests.</span></span> <span data-ttu-id="0f5fd-106">검색 가능한 서비스는 Hello 메시지를 보내 네트워크에서 서비스의 도착을 알리며, Bye 메시지를 보내 네트워크에서 서비스의 출발을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-106">Discoverable services can send Hello messages to announce their arrival on a network and Bye messages to announce their departure from a network.</span></span> <span data-ttu-id="0f5fd-107">클라이언트는 서비스를 찾기 위해 서비스 계약 형식, 키워드 및 네트워크 범위와 같은 특정 조건이 포함된 `Probe` 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-107">To find a service, clients send a `Probe` request that contains specific criteria such as service contract type, keywords, and scope on the network.</span></span> <span data-ttu-id="0f5fd-108">서비스는 `Probe` 요청을 받고 자신이 이 조건에 일치하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-108">Services receive the `Probe` request and determine whether they match the criteria.</span></span> <span data-ttu-id="0f5fd-109">일치할 경우 서비스는 서비스에 연결하는 데 필요한 정보와 함께 `ProbeMatch` 메시지를 클라이언트로 돌려보내 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-109">If a service matches, it responds by sending a `ProbeMatch` message back to the client with the information necessary to contact the service.</span></span> <span data-ttu-id="0f5fd-110">또한 클라이언트는 끝점 주소가 변경된 경우에도 서비스를 찾을 수 있는 `Resolve` 요청을 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-110">Clients can also send `Resolve` requests that allow them to find services that may have changed their endpoint address.</span></span> <span data-ttu-id="0f5fd-111">일치하는 서비스는 `Resolve` 메시지를 클라이언트로 돌려보내 `ResolveMatch` 요청에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-111">Matching services respond to `Resolve` requests by sending a `ResolveMatch` message back to the client.</span></span>  
  
## <a name="ad-hoc-and-managed-modes"></a><span data-ttu-id="0f5fd-112">애드혹 및 관리 모드</span><span class="sxs-lookup"><span data-stu-id="0f5fd-112">Ad-Hoc and Managed Modes</span></span>  
 <span data-ttu-id="0f5fd-113">Discovery API가 지원하는 모드는 관리 모드와 애드혹 모드, 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-113">The Discovery API supports two different modes: Managed and Ad-Hoc.</span></span> <span data-ttu-id="0f5fd-114">관리 모드에는 사용 가능한 서비스에 대한 정보를 유지 관리하는 검색 프록시라는 중앙 서버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-114">In Managed mode there is a centralized server called a discovery proxy that maintains information about available services.</span></span> <span data-ttu-id="0f5fd-115">검색 프록시는 다양한 방법을 통해 서비스에 대한 정보로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-115">The discovery proxy can be populated with information about services in a variety of ways.</span></span> <span data-ttu-id="0f5fd-116">예를 들어 서비스가 시작 시에 검색 프록시로 알림 메시지를 보낼 수도 있고, 프록시가 데이터베이스 또는 구성 파일에서 데이터를 읽어 사용 가능한 서비스를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-116">For example, services can send announcement messages during start up to the discovery proxy or the proxy may read data from a database or a configuration file to determine what services are available.</span></span> <span data-ttu-id="0f5fd-117">검색 프록시를 채우는 방법은 전적으로 개발자의 재량에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-117">How the discovery proxy is populated is completely up to the developer.</span></span> <span data-ttu-id="0f5fd-118">클라이언트는 검색 프록시를 통해 사용 가능한 서비스에 대한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-118">Clients use the discovery proxy to retrieve information about available services.</span></span> <span data-ttu-id="0f5fd-119">클라이언트는 서비스를 검색할 때 검색 프록시로 `Probe` 메시지를 보내며, 프록시는 자신이 아는 서비스 중에 클라이언트가 검색하는 서비스와 일치하는 서비스가 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-119">When a client searches for a service it sends a `Probe` message to the discovery proxy and the proxy determines whether any of the services it knows about match the service the client is searching for.</span></span> <span data-ttu-id="0f5fd-120">일치하는 서비스가 있으면 검색 프록시는 클라이언트로 `ProbeMatch` 응답을 돌려보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-120">If there are matches the discovery proxy sends a `ProbeMatch` response back to the client.</span></span> <span data-ttu-id="0f5fd-121">그러면 클라이언트는 프록시에서 반환된 서비스 정보를 사용하여 서비스에 직접 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-121">The client can then contact the service directly using the service information returned from the proxy.</span></span> <span data-ttu-id="0f5fd-122">관리 모드의 기반이 되는 핵심 원칙은 검색 요청이 하나의 기관, 즉 검색 프록시로 유니캐스트 방식으로 전송된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-122">The key principle behind Managed mode is that the discovery requests are sent in a unicast manner to one authority, the discovery proxy.</span></span> <span data-ttu-id="0f5fd-123">.NET Framework에는 사용자가 직접 프록시를 빌드할 수 있도록 하는 주요 구성 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-123">The .NET Framework contains key components that allow you to build your own proxy.</span></span> <span data-ttu-id="0f5fd-124">클라이언트와 서비스는 다음과 같은 여러 방법으로 프록시를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-124">Clients and services can locate the proxy by multiple methods:</span></span>  
  
-   <span data-ttu-id="0f5fd-125">프록시는 애드혹 메시지에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-125">The proxy can respond to ad-hoc messages.</span></span>  
  
-   <span data-ttu-id="0f5fd-126">프록시는 시작 시 알림 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-126">The proxy can send an announcement message during start up.</span></span>  
  
-   <span data-ttu-id="0f5fd-127">잘 알려진 특정 끝점을 찾도록 클라이언트 및 서비스를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-127">Clients and services can be written to look for a specific well-known endpoint.</span></span>  
  
 <span data-ttu-id="0f5fd-128">애드혹 모드에는 중앙 서버가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-128">In Ad-Hoc mode, there is no centralized server.</span></span> <span data-ttu-id="0f5fd-129">서비스 알림 및 클라이언트 요청과 같은 모든 검색 메시지는 멀티캐스트 방식으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-129">All discovery messages such as service announcements and client requests are sent in a multicast fashion.</span></span> <span data-ttu-id="0f5fd-130">기본적으로 .NET Framework에는 UDP 프로토콜을 통한 애드혹 검색 지원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-130">By default the .NET Framework contains support for Ad-Hoc discovery over the UDP protocol.</span></span> <span data-ttu-id="0f5fd-131">예를 들어 서비스가 시작 시 Hello 알림을 보내도록 구성된 경우 이 서비스는 UDP 프로토콜을 사용하여 잘 알려진 멀티캐스트 주소를 통해 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-131">For example, if a service is configured to send out a Hello announcement on start up, it sends it out over a well-known, multicast address using the UDP protocol.</span></span> <span data-ttu-id="0f5fd-132">클라이언트는 적극적으로 이러한 알림을 수신하고 적절히 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-132">Clients have to actively listen for these announcements and process them accordingly.</span></span> <span data-ttu-id="0f5fd-133">클라이언트는 서비스에 대한 `Probe` 메시지를 보낼 때 멀티캐스트 프로토콜을 사용하여 네트워크를 통해 이 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-133">When a client sends a `Probe` message for a service it is sent over the network using a multicast protocol.</span></span> <span data-ttu-id="0f5fd-134">요청을 받는 각 서비스는 `Probe` 메시지에 포함된 조건과 자신이 일치하는지 여부를 확인하고, `ProbeMatch` 메시지에 지정된 조건과 일치하는 경우 `Probe` 메시지로 클라이언트에 직접 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-134">Each service that receives the request determines whether it matches the criteria in the `Probe` message and responds directly to the client with a `ProbeMatch` message if the service matches the criteria specified in the `Probe` message.</span></span>  
  
## <a name="benefits-of-using-wcf-discovery"></a><span data-ttu-id="0f5fd-135">WCF Discovery를 사용할 경우의 장점</span><span class="sxs-lookup"><span data-stu-id="0f5fd-135">Benefits of Using WCF Discovery</span></span>  
 <span data-ttu-id="0f5fd-136">WCF Discovery는 WS-Discovery 프로토콜을 사용하여 구현되므로 WS-Discovery를 구현하는 다른 클라이언트, 서비스 및 프록시와 상호 운용이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-136">Because WCF Discovery is implemented using the WS-Discovery protocol it is interoperable with other clients, services, and proxies that implement WS-Discovery as well.</span></span> <span data-ttu-id="0f5fd-137">WCF Discovery는 기존 WCF API를 기반으로 구축되므로 기존 서비스 및 클라이언트에 검색 기능을 손쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-137">WCF Discovery is built upon the existing WCF APIs, which makes it easy to add Discovery functionality to your existing services and clients.</span></span> <span data-ttu-id="0f5fd-138">서비스 검색 기능은 응용 프로그램 구성 설정을 통해 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-138">Service discoverability can be easily added through the application configuration settings.</span></span> <span data-ttu-id="0f5fd-139">또한 WCF Discovery는 피어 넷, 명명 오버레이 및 HTTP와 같은 다른 전송에서의 검색 프로토콜 사용도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-139">In addition, WCF Discovery also supports using the discovery protocol over other transports such as peer net, naming overlay, and HTTP.</span></span> <span data-ttu-id="0f5fd-140">WCF Discovery는 검색 프록시가 사용되는 작업의 관리 모드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-140">WCF Discovery provides support for a Managed mode of operation where a discovery proxy is used.</span></span> <span data-ttu-id="0f5fd-141">이로써 전체 네트워크로 멀티캐스트 메시지를 보내는 대신 검색 프록시로 메시지를 직접 보내게 되므로 네트워크 트래픽이 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-141">This can reduce network traffic as messages are sent directly to the discovery proxy instead of sending multicast messages to the entire network.</span></span> <span data-ttu-id="0f5fd-142">WCF Discovery는 웹 서비스와 함께 사용할 때 유연성도 더욱 높여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-142">WCF Discovery also allows for more flexibility when working with Web services.</span></span> <span data-ttu-id="0f5fd-143">예를 들어 클라이언트나 서비스를 다시 구성할 필요 없이 서비스 주소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-143">For example, you can change the address of a service without having to reconfigure the client or the service.</span></span> <span data-ttu-id="0f5fd-144">클라이언트는 서비스에 액세스해야 하는 경우 `Probe` 요청을 통해 `Find` 메시지를 발송하고 서비스가 현재 주소를 사용하여 응답하기를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-144">When a client must access the service it can issue a `Probe` message through a `Find` request and expect the service to respond with its current address.</span></span> <span data-ttu-id="0f5fd-145">WCF Discovery를 통해 클라이언트는 계약 형식, 바인딩 요소, 네임스페이스, 범위 및 키워드 또는 버전 번호와 같은 다양한 조건에 따라 서비스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-145">WCF Discovery allows a client to search for a service based on different criteria including contract types, binding elements, namespace, scope, and keywords or version numbers.</span></span> <span data-ttu-id="0f5fd-146">WCF Discovery를 사용하면 런타임 및 디자인 타임 검색이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-146">WCF Discovery enables runtime and design time discovery.</span></span> <span data-ttu-id="0f5fd-147">내결함성 및 자동 구성과 같은 다른 시나리오를 지원하기 위해 응용 프로그램에 검색 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-147">Adding discovery to your application can be used to enable other scenarios such as fault tolerance and auto configuration.</span></span>  
  
## <a name="service-publication"></a><span data-ttu-id="0f5fd-148">서비스 게시</span><span class="sxs-lookup"><span data-stu-id="0f5fd-148">Service Publication</span></span>  
 <span data-ttu-id="0f5fd-149">서비스 검색을 가능하게 하려면 서비스 호스트에 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>를 추가하고 검색 끝점을 추가하여 검색 메시지를 수신할 위치를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-149">To make a service discoverable, a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> must be added to the service host and a discovery endpoint must be added to specify where to listen for discovery messages.</span></span> <span data-ttu-id="0f5fd-150">다음 코드 예제에서는 자체 호스팅 서비스를 검색 가능하도록 수정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-150">The following code example shows how a self-hosted service can be modified to make it discoverable.</span></span>  
  
```csharp  
Uri baseAddress = new Uri(string.Format("http://{0}:8000/discovery/scenarios/calculatorservice/{1}/",  
        System.Net.Dns.GetHostName(), Guid.NewGuid().ToString()));

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    // Add calculator endpoint
    serviceHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), string.Empty);

    // ** DISCOVERY ** //
    // Make the service discoverable by adding the discovery behavior
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());

    // ** DISCOVERY ** //
    // Add the discovery endpoint that specifies where to publish the services
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());

    // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();

    // The service can now be accessed.
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
}
```  
  
 <span data-ttu-id="0f5fd-151">서비스를 검색 가능하게 하려면 서비스 설명에 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> 인스턴스를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-151">A <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instance must be added to a service description for the service to be discoverable.</span></span> <span data-ttu-id="0f5fd-152">서비스에 검색 요청을 수신할 위치를 알리려면 서비스 호스트에 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> 인스턴스를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-152">A <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instance must be added to the service host to tell the service where to listen for discovery requests.</span></span> <span data-ttu-id="0f5fd-153">이 예제에서는 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>(<xref:System.ServiceModel.Discovery.DiscoveryEndpoint>에서 파생됨)를 추가하여 서비스가 UDP 멀티캐스트 전송을 통해 검색 요청을 수신하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-153">In this example, a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> (which is derived from <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>) is added to specify that the service should listen for discovery requests over the UDP multicast transport.</span></span> <span data-ttu-id="0f5fd-154">모든 메시지가 멀티캐스트 방식으로 전송되므로 애드혹 검색을 위해 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-154">The <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> is used for Ad-Hoc discovery because all messages are sent in a multicast fashion.</span></span>  
  
## <a name="announcement"></a><span data-ttu-id="0f5fd-155">알림</span><span class="sxs-lookup"><span data-stu-id="0f5fd-155">Announcement</span></span>  
 <span data-ttu-id="0f5fd-156">기본적으로 서비스 게시는 알림 메시지를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-156">By default, service publication does not send out announcement messages.</span></span> <span data-ttu-id="0f5fd-157">알림 메시지를 보내도록 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-157">The service must be configured to send out announcement messages.</span></span> <span data-ttu-id="0f5fd-158">이렇게 하면 서비스 작성기가 검색 메시지 수신과는 별도로 서비스를 알릴 수 있으므로 유연성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-158">This provides additional flexibility for service writers because they can announce the service separately from listening for discovery messages.</span></span> <span data-ttu-id="0f5fd-159">서비스 알림은 검색 프록시 및 기타 서비스 레지스트리에 서비스를 등록하기 위한 메커니즘으로도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-159">Service announcement can also be used as a mechanism for registering services with a discovery proxy or other service registries.</span></span> <span data-ttu-id="0f5fd-160">다음 코드는 UDP 바인딩을 통해 알림 메시지를 보내도록 서비스를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-160">The following code shows how to configure a service to send announcement messages over a UDP binding.</span></span>  
  
```csharp  
Uri baseAddress = new Uri(string.Format("http://{0}:8000/discovery/scenarios/calculatorservice/{1}/",
        System.Net.Dns.GetHostName(), Guid.NewGuid().ToString()));

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    // Add calculator endpoint
    serviceHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), string.Empty);

    // ** DISCOVERY ** //
    // Make the service discoverable by adding the discovery behavior
    ServiceDiscoveryBehavior discoveryBehavior = new ServiceDiscoveryBehavior();
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());

    // Send announcements on UDP multicast transport
    discoveryBehavior.AnnouncementEndpoints.Add(
      new UdpAnnouncementEndpoint());

    // ** DISCOVERY ** //
    // Add the discovery endpoint that specifies where to publish the services
    serviceHost.Description.Endpoints.Add(new UdpDiscoveryEndpoint());

    // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();

    // The service can now be accessed.
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
}
```  
  
## <a name="service-discovery"></a><span data-ttu-id="0f5fd-161">서비스 검색</span><span class="sxs-lookup"><span data-stu-id="0f5fd-161">Service Discovery</span></span>  
 <span data-ttu-id="0f5fd-162">클라이언트 응용 프로그램은 <xref:System.ServiceModel.Discovery.DiscoveryClient> 클래스를 사용하여 서비스를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-162">A client application can use the <xref:System.ServiceModel.Discovery.DiscoveryClient> class to find services.</span></span> <span data-ttu-id="0f5fd-163">개발자는 <xref:System.ServiceModel.Discovery.DiscoveryClient> 또는 `Probe` 메시지를 보낼 위치를 지정하는 검색 끝점을 전달하는 `Resolve` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-163">The developer creates an instance of the <xref:System.ServiceModel.Discovery.DiscoveryClient> class that passes in a discovery endpoint that specifies where to send `Probe` or `Resolve` messages.</span></span> <span data-ttu-id="0f5fd-164">그러면 클라이언트가 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 인스턴스 내에서 검색 조건을 지정하는 <xref:System.ServiceModel.Discovery.FindCriteria>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-164">The client then calls <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> that specifies search criteria within a <xref:System.ServiceModel.Discovery.FindCriteria> instance.</span></span> <span data-ttu-id="0f5fd-165">일치하는 서비스가 발견되면 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>는 <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-165">If matching services are found, <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> returns a collection of <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>.</span></span> <span data-ttu-id="0f5fd-166">다음 코드는 `Find` 메서드를 호출한 다음 검색된 서비스에 연결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-166">The following code shows how to call the `Find` method and then connect to a discovered service.</span></span>  
  
```csharp  
class Client
{
    static EndpointAddress serviceAddress;
  
    static void Main()
    {  
        if (FindService()) 
        {
            InvokeService();
        }
    }  
  
    // ** DISCOVERY ** //  
    static bool FindService()  
    {  
        Console.WriteLine("\nFinding Calculator Service ..");  
        DiscoveryClient discoveryClient =   
            new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
        Collection<EndpointDiscoveryMetadata> calculatorServices =   
            (Collection<EndpointDiscoveryMetadata>)discoveryClient.Find(new FindCriteria(typeof(ICalculator))).Endpoints;  
  
        discoveryClient.Close();  
  
        if (calculatorServices.Count == 0)  
        {  
            Console.WriteLine("\nNo services are found.");  
            return false;  
        }  
        else  
        {  
            serviceAddress = calculatorServices[0].Address;  
            return true;  
        }  
    }  
  
    static void InvokeService()  
    {  
        Console.WriteLine("\nInvoking Calculator Service at {0}\n", serviceAddress);  
  
        // Create a client  
        CalculatorClient client = new CalculatorClient();  
        client.Endpoint.Address = serviceAddress;  
        client.Add(10,3);  
    }
}  
```  
  
## <a name="discovery-and-message-level-security"></a><span data-ttu-id="0f5fd-167">검색 및 메시지 수준 보안</span><span class="sxs-lookup"><span data-stu-id="0f5fd-167">Discovery and Message Level Security</span></span>  
 <span data-ttu-id="0f5fd-168">메시지 수준 보안을 사용하는 경우 서비스 검색 끝점에 <xref:System.ServiceModel.EndpointIdentity>를, 클라이언트 검색 끝점에 일치하는 <xref:System.ServiceModel.EndpointIdentity>를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-168">When using message level security it is necessary to specify an <xref:System.ServiceModel.EndpointIdentity> on the service discovery endpoint and a matching <xref:System.ServiceModel.EndpointIdentity> on the client discovery endpoint.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0f5fd-169">메시지 수준 보안, 참조 [메시지 보안](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-169"> message level security, see [Message Security](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).</span></span>  
  
## <a name="discovery-and-web-hosted-services"></a><span data-ttu-id="0f5fd-170">검색 및 웹 호스팅 서비스</span><span class="sxs-lookup"><span data-stu-id="0f5fd-170">Discovery and Web Hosted Services</span></span>  
 <span data-ttu-id="0f5fd-171">WCF 서비스가 검색 가능하려면 실행되고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-171">In order for WCF services to be discoverable they must be running.</span></span> <span data-ttu-id="0f5fd-172">IIS 또는 WAS에서 호스팅되는 WCF 서비스는 IIS/WAS가 서비스에 바인딩된 메시지를 받을 때까지 실행되지 않으므로 기본적으로 검색 가능하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-172">WCF services hosted under IIS or WAS do not run until IIS/WAS receives a message bound for the service, so they cannot be discoverable by default.</span></span>  <span data-ttu-id="0f5fd-173">웹 호스팅 서비스를 검색 가능하게 만드는 방법은 다음 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-173">There are two options for making Web-Hosted services discoverable:</span></span>  
  
1.  <span data-ttu-id="0f5fd-174">Windows Server AppFabric 자동 시작 기능 사용</span><span class="sxs-lookup"><span data-stu-id="0f5fd-174">Use the Windows Server AppFabric Auto-Start feature</span></span>  
  
2.  <span data-ttu-id="0f5fd-175">서비스 대신 통신할 검색 프록시 사용</span><span class="sxs-lookup"><span data-stu-id="0f5fd-175">Use a discovery proxy to communicate on behalf of the service</span></span>  
  
 <span data-ttu-id="0f5fd-176">Windows Server AppFabric에는 메시지를 받기 전에 서비스가 시작될 수 있도록 하는 자동 시작 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-176">Windows Server AppFabric has an Auto-Start feature that will allow a service to be started before receiving any messages.</span></span> <span data-ttu-id="0f5fd-177">이 자동 시작 집합을 사용하여 IIS/WAS에서 호스팅된 서비스가 검색 가능하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-177">With this Auto-Start set, an IIS/WAS hosted service can be configured to be discoverable.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0f5fd-178">자동 시작 기능 참조 [Windows Server AppFabric 자동 시작 기능](http://go.microsoft.com/fwlink/?LinkId=205545)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-178"> the Auto-Start feature see, [Windows Server AppFabric Auto-Start Feature](http://go.microsoft.com/fwlink/?LinkId=205545).</span></span> <span data-ttu-id="0f5fd-179">자동 시작 기능을 설정하는 것과 함께 검색에 대해 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-179">Along with turning on the Auto-Start feature, you must configure the service for discovery.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="0f5fd-180">[하는 방법: 프로그래밍 방식으로 WCF 서비스 및 클라이언트에 검색 기능을 추가](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)[구성 파일에서 검색 구성](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-180"> [How to: Programmatically Add Discoverability to a WCF Service and Client](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)[Configuring Discovery in a Configuration File](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md).</span></span>  
  
 <span data-ttu-id="0f5fd-181">WCF 서비스가 실행되지 않을 때 검색 프록시를 사용하여 WCF 서비스 대신 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-181">A discovery proxy can be used to communicate on behalf of the WCF service when the service is not running.</span></span> <span data-ttu-id="0f5fd-182">프록시는 프로브 또는 확인 메시지를 수신하고 클라이언트에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-182">The proxy can listen for probe or resolve messages and respond to the client.</span></span> <span data-ttu-id="0f5fd-183">그러면 클랑이언트에서 서비스에 직접 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-183">The client can then send messages directly to the service.</span></span> <span data-ttu-id="0f5fd-184">클라이언트에서 서비스에 메시지를 보낼 때 서비스가 메시지에 응답하기 위해 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-184">When the client sends a message to the service it will be instantiated to respond to the message.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0f5fd-185">참조 검색 프록시 구현 [검색 프록시 구현](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-185"> implementing a discovery proxy see, [Implementing a Discovery Proxy](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f5fd-186">제대로 작동 하려면 WCF 검색에 대 한 모든 Nic (네트워크 인터페이스 컨트롤러)는 IP 주소 1 하나만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f5fd-186">For WCF Discovery to work correctly, all NICs (Network Interface Controller) should only have 1 IP address.</span></span>
