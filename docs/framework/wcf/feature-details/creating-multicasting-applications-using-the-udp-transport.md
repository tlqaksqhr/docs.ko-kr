---
title: "UDP 전송을 사용하여 멀티캐스트 응용 프로그램 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7485154a-6e85-4a67-a9d4-9008e741d4df
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3dde7dc8b051c4238203173bd009a8f71dd9c6c3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="creating-multicasting-applications-using-the-udp-transport"></a><span data-ttu-id="086ba-102">UDP 전송을 사용하여 멀티캐스트 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="086ba-102">Creating Multicasting Applications using the UDP Transport</span></span>
<span data-ttu-id="086ba-103">멀티캐스트 응용 프로그램은 점대점 연결을 설정하지 않고도 작은 메시지를 많은 수신자에게 동시에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-103">Multicasting applications send small messages to a large number of recipients at the same time without the need to establish point to point connections.</span></span> <span data-ttu-id="086ba-104">그러한 응용 프로그램은 신뢰성보다 속도를 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-104">The emphasis of such applications is speed over reliability.</span></span> <span data-ttu-id="086ba-105">달리 말해, 특정 메시지가 실제로 수신되었는지를 보장하는 것보다 데이터를 적시에 보내는 것이 더 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-105">In other words, it is more important to send timely data than to ensure any specific message is actually received.</span></span> <span data-ttu-id="086ba-106">WCF는 이제 <xref:System.ServiceModel.UdpBinding>을 사용한 멀티캐스트 응용 프로그램 작성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-106">WCF now supports writing multicasting applications using the <xref:System.ServiceModel.UdpBinding>.</span></span> <span data-ttu-id="086ba-107">이 전송은 서비스에서 작은 메시지를 많은 클라이언트에 동시에 보내야 할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-107">This transport is useful in scenarios where a service needs to send out small messages to a number of clients simultaneously.</span></span> <span data-ttu-id="086ba-108">이러한 서비스의 예로는 주식 시세 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-108">A stock ticker application is an example of such a service.</span></span>  
  
## <a name="implementing-a-multicast-application"></a><span data-ttu-id="086ba-109">멀티캐스트 응용 프로그램 구현</span><span class="sxs-lookup"><span data-stu-id="086ba-109">Implementing a Multicast Application</span></span>  
 <span data-ttu-id="086ba-110">멀티캐스트 응용 프로그램을 구현하려면 멀티캐스트 메시지에 응답해야 하는 각 소프트웨어 구성 요소에 대해 서비스 계약을 정의하고 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-110">To implement a multicast application, define a service contract and for each software component that needs to respond to the multicast messages, implement the service contract.</span></span> <span data-ttu-id="086ba-111">예를 들어 주식 시세 응용 프로그램에서 서비스 계약을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-111">For example, a stock ticker application might define a service contract:</span></span>  
  
```  
// Shared contracts between the client and the service  
[ServiceContract]
interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void SendStockInfo(StockInfo[] stockInfo);
}

[DataContract]
class StockInfo
{
    [DataMember]
    public string Symbol;

    [DataMember]
    public float Price;

    public StockInfo(string symbol, float price)
    {
        this.Symbol = symbol;
        this.Price = price;
    }
}
```  
  
 <span data-ttu-id="086ba-112">멀티캐스트 메시지를 수신하려는 각 응용 프로그램은 이 인터페이스를 노출하는 서비스를 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-112">Each application that wants to receive multicast messages must host a service that exposes this interface.</span></span>  <span data-ttu-id="086ba-113">예를 들어, 다음은 멀티캐스트 메시지를 수신하는 방법을 보여 주는 코드 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-113">For example, here is a code sample that illustrates how to receive multicast messages:</span></span>  
  
```  
// Service Address
string serviceAddress = "soap.udp://224.0.0.1:40000";
// Binding
UdpBinding myBinding = new UdpBinding();
// Host
ServiceHost host = new ServiceHost(typeof(StockTickerService), new Uri(serviceAddress));
// Add service endpoint
host.AddServiceEndpoint(typeof(IStockTicker), myBinding, string.Empty);
// Openup the service host
host.Open();

Console.WriteLine("Start receiving stock information");
Console.ReadLine();
```  
  
 <span data-ttu-id="086ba-114">이 응용 프로그램은 모든 서비스를 수신 대기할 UDP 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-114">The application specifies the UDP address that all services will be listening on.</span></span> <span data-ttu-id="086ba-115">새로운 <xref:System.ServiceModel.ServiceHost>가 만들어지고 <xref:System.ServiceModel.UdpBinding>을 사용해서 서비스 끝점이 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-115">A new <xref:System.ServiceModel.ServiceHost> is created and a service endpoint is exposed using the <xref:System.ServiceModel.UdpBinding>.</span></span> <span data-ttu-id="086ba-116">그런 후 <xref:System.ServiceModel.ServiceHost>가 열리고 들어오는 메시지에 대한 수신 대기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-116">The <xref:System.ServiceModel.ServiceHost> is then opened and will start listening for incoming messages.</span></span>  
  
 <span data-ttu-id="086ba-117">이러한 유형의 시나리오에서는 클라이언트가 실제로 멀티캐스트 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-117">In this type of a scenario it is the client that actually sends out multicast messages.</span></span> <span data-ttu-id="086ba-118">정확한 UDP 주소에서 수신 대기하는 각 서비스가 멀티캐스트 메시지를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-118">Each service that is listening at the correct UDP address will receive the multicast messages.</span></span> <span data-ttu-id="086ba-119">다음 예제는 멀티캐스트 메시지를 보내는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-119">Here is an example of a client that sends out multicast messages:</span></span>  
  
```  
// Multicast Address
string serviceAddress = "soap.udp://224.0.0.1:40000";

// Binding
UdpBinding myBinding = new UdpBinding();

// Channel factory
ChannelFactory<IStockTicker> factory 
    = new ChannelFactory<IStockTicker>(myBinding,
                new EndpointAddress(serviceAddress));

// Call service
IStockTicker proxy = factory.CreateChannel();

while (true)
{
    // This will continue to mulicast stock information
    proxy.SendStockInfo(GetStockInfo());
    Console.WriteLine(String.Format("sent stock info at {0}", DateTime.Now));
    // Wait for one second before sending another update
    System.Threading.Thread.Sleep(new TimeSpan(0, 0, 1));
}
```  
  
 <span data-ttu-id="086ba-120">이 코드는 주식 정보를 생성한 다음 IStockTicker 서비스 계약을 사용하여 정확한 UDP 주소에서 수신 대기하는 호출 서비스에 멀티캐스트 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-120">This code generates stock information and then uses the service contract IStockTicker to send multicast messages to call services listening on the correct UDP address.</span></span>  
  
### <a name="udp-and-reliable-messaging"></a><span data-ttu-id="086ba-121">UDP 및 신뢰할 수 있는 메시징</span><span class="sxs-lookup"><span data-stu-id="086ba-121">UDP and Reliable Messaging</span></span>  
 <span data-ttu-id="086ba-122">UDP 프로토콜은 가볍기 때문에 UDP 바인딩은 신뢰할 수 있는 메시징을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-122">The UDP binding does not support reliable messaging because of the lightweight nature of the UDP protocol.</span></span> <span data-ttu-id="086ba-123">원격 끝점에서 메시지를 수신했는지 확인해야 할 경우 HTTP 또는 TCP와 같이 신뢰할 수 있는 메시지를 지원하는 전송을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="086ba-123">If you need to confirm that messages are received by a remote endpoint, use a transport that supports reliable messaging like  HTTP or TCP.</span></span> <span data-ttu-id="086ba-124">신뢰할 수 있는 메시지에 대한 자세한 내용은 http://go.microsoft.com/fwlink/?LinkId=231830을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="086ba-124">For more information about reliable messaging see http://go.microsoft.com/fwlink/?LinkId=231830</span></span>  
  
### <a name="two-way-multicast-messaging"></a><span data-ttu-id="086ba-125">양방향 멀티캐스트 메시징</span><span class="sxs-lookup"><span data-stu-id="086ba-125">Two-way Multicast Messaging</span></span>  
 <span data-ttu-id="086ba-126">멀티캐스트 메시지가 일반적으로 단방향이지만, UdpBinding은 요청/회신 메시지 교환을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-126">While multicast messages are generally one-way, the UdpBinding does support request/reply message exchange.</span></span> <span data-ttu-id="086ba-127">UDP 전송을 사용하여 보낸 메시지에는 보낸 사람 및 받는 사람 주소가 모두 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-127">Messages sent using the UDP transport contain both a From and To address.</span></span> <span data-ttu-id="086ba-128">보낸 사람 주소를 사용할 때는 도중에 악의적으로 변경될 수 있으므로 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-128">Care must be taken when using the From address as it could be maliciously changed en-route.</span></span>  <span data-ttu-id="086ba-129">이 주소는 다음 코드를 사용하여 점검할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-129">The address can be checked using the following code:</span></span>  
  
```  
if (address.AddressFamily == AddressFamily.InterNetwork)
{
    // IPv4
    byte[] addressBytes = address.GetAddressBytes();
    return ((addressBytes[0] & 0xE0) == 0xE0);
}
else
{
    // IPv6
    return address.IsIPv6Multicast;
}
```  
  
 <span data-ttu-id="086ba-130">이 코드는 보낸 사람 주소의 첫 번째 바이트를 보고 멀티캐스트 주소인지를 나타내는 0xE0이 들어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-130">This code checks the first byte of the From address to see if it contains 0xE0 which signifies that the address is a multi-cast address.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="086ba-131">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="086ba-131">Security Considerations</span></span>  
 <span data-ttu-id="086ba-132">멀티캐스트 메시지를 수신 대기하는 경우 ICMP 패킷을 라우터로 전송하여 멀티캐스트 주소에서 수신 대기 중임을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-132">When listening for multicast messages an ICMP packet is sent to the router notifying it you are listening on the multicast address.</span></span> <span data-ttu-id="086ba-133">로컬 서브넷에서 권한이 있는 모든 사용자는 이러한 형식의 패킷을 수신 대기하고 수신 대기할 멀티캐스트 주소와 포트를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-133">Anyone on the local subnet who has permissions could listen for these types of packets and determine which multicast address and port you are listening on.</span></span>  
  
 <span data-ttu-id="086ba-134">보안 목적을 위해 보낸 사람의 IP 주소를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="086ba-134">Do not use the IP address of the sender for any security purposes.</span></span> <span data-ttu-id="086ba-135">이 정보가 스푸핑되면 응용 프로그램이 잘못된 컴퓨터로 응답을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-135">This information can be spoofed and can cause an application to send responses to the wrong machine.</span></span> <span data-ttu-id="086ba-136">이 위협을 줄이는 한 가지 방법은 메시지 수준 보안을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-136">One way to mitigate this threat is to enable message level security.</span></span> <span data-ttu-id="086ba-137">네트워크 수준 IPSec(Internet Protocol Security) 및/또는 NAP(Network Access Protection)에서도 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="086ba-137">At the network level IPSec  (Internet Protocol Security) and/or NAP (Network Access Protection) could also be used.</span></span>
