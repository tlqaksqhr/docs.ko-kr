---
title: 이중 서비스
ms.date: 05/09/2018
dev_langs:
- csharp
- vb
ms.assetid: 396b875a-d203-4ebe-a3a1-6a330d962e95
ms.openlocfilehash: da92b8f2d1223f582677a93a8ff6fd697512d297
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34037365"
---
# <a name="duplex-services"></a><span data-ttu-id="8e7c8-102">이중 서비스</span><span class="sxs-lookup"><span data-stu-id="8e7c8-102">Duplex Services</span></span>
<span data-ttu-id="8e7c8-103">이중 서비스 계약은 양쪽 끝점에서 메시지를 다른 사용자에게 독립적으로 전송할 수 있는 메시지 교환 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-103">A duplex service contract is a message exchange pattern in which both endpoints can send messages to the other independently.</span></span> <span data-ttu-id="8e7c8-104">따라서 이중 서비스에서는 클라이언트 끝점으로 메시지를 보내 이벤트와 비슷한 동작을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-104">A duplex service, therefore, can send messages back to the client endpoint, providing event-like behavior.</span></span> <span data-ttu-id="8e7c8-105">이중 통신은 클라이언트가 서비스에 연결할 때 이루어지며, 서비스에서 클라이언트로 메시지를 다시 보낼 수 있는 채널을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-105">Duplex communication occurs when a client connects to a service and provides the service with a channel on which the service can send messages back to the client.</span></span> <span data-ttu-id="8e7c8-106">이중 서비스의 이벤트와 비슷한 동작은 세션 내에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-106">Note that the event-like behavior of duplex services only works within a session.</span></span>  
  
 <span data-ttu-id="8e7c8-107">이중 계약을 만들려면 인터페이스 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-107">To create a duplex contract you create a pair of interfaces.</span></span> <span data-ttu-id="8e7c8-108">첫 번째는 클라이언트가 호출할 수 있는 작업을 설명하는 서비스 계약 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-108">The first is the service contract interface that describes the operations that a client can invoke.</span></span> <span data-ttu-id="8e7c8-109">해당 서비스 계약을 지정 해야 합니다는 *콜백 계약* 에 <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-109">That service contract must specify a *callback contract* in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="8e7c8-110">콜백 계약은 서비스가 클라이언트 끝점에서 호출할 수 있는 작업을 정의하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-110">The callback contract is the interface that defines the operations that the service can call on the client endpoint.</span></span> <span data-ttu-id="8e7c8-111">시스템이 제공하는 이중 바인딩은 세션을 사용하지만 이중 계약에서는 세션이 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-111">A duplex contract does not require a session, although the system-provided duplex bindings make use of them.</span></span>  
  
 <span data-ttu-id="8e7c8-112">다음은 이중 계약의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-112">The following is an example of a duplex contract.</span></span>  
  
 [!code-csharp[c_DuplexServices#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#0)]
 [!code-vb[c_DuplexServices#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#0)]  
  
 <span data-ttu-id="8e7c8-113">`CalculatorService` 클래스는 기본 `ICalculatorDuplex` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-113">The `CalculatorService` class implements the primary `ICalculatorDuplex` interface.</span></span> <span data-ttu-id="8e7c8-114">서비스는 <xref:System.ServiceModel.InstanceContextMode.PerSession> 인스턴스 모드를 사용하여 각 세션의 결과를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-114">The service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the result for each session.</span></span> <span data-ttu-id="8e7c8-115">`Callback`이라는 private 속성이 클라이언트에 대한 콜백 채널에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-115">A private property named `Callback` accesses the callback channel to the client.</span></span> <span data-ttu-id="8e7c8-116">서비스는 다음 샘플 코드에 표시된 것처럼 콜백 인터페이스를 통해 클라이언트에 다시 전송하는 메시지의 콜백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-116">The service uses the callback for sending messages back to the client through the callback interface, as shown in the following sample code.</span></span>  
  
 [!code-csharp[c_DuplexServices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#1)]
 [!code-vb[c_DuplexServices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#1)]  
  
 <span data-ttu-id="8e7c8-117">클라이언트는 서비스에서 메시지를 수신하기 위해 이중 계약의 콜백 인터페이스를 구현하는 클래스를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-117">The client must provide a class that implements the callback interface of the duplex contract, for receiving messages from the service.</span></span> <span data-ttu-id="8e7c8-118">다음 샘플 코드에서는 `CallbackHandler` 인터페이스를 구현하는 `ICalculatorDuplexCallback` 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-118">The following sample code shows a `CallbackHandler` class that implements the `ICalculatorDuplexCallback` interface.</span></span>  
  
 [!code-csharp[c_DuplexServices#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#2)]
 [!code-vb[c_DuplexServices#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#2)]  
  
 <span data-ttu-id="8e7c8-119">이중 계약에 대해 생성 되는 WCF 클라이언트는 <xref:System.ServiceModel.InstanceContext> 클래스를 생성 시 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-119">The WCF client that is generated for a duplex contract requires a <xref:System.ServiceModel.InstanceContext> class to be provided upon construction.</span></span> <span data-ttu-id="8e7c8-120">이 <xref:System.ServiceModel.InstanceContext> 클래스는 콜백 인터페이스를 구현하는 개체의 사이트로 사용되고 서비스에서 다시 전송된 메시지를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-120">This <xref:System.ServiceModel.InstanceContext> class is used as the site for an object that implements the callback interface and handles messages that are sent back from the service.</span></span> <span data-ttu-id="8e7c8-121"><xref:System.ServiceModel.InstanceContext> 클래스는 `CallbackHandler` 클래스의 인스턴스를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-121">An <xref:System.ServiceModel.InstanceContext> class is constructed with an instance of the `CallbackHandler` class.</span></span> <span data-ttu-id="8e7c8-122">이 개체는 콜백 인터페이스를 통해 서비스에서 클라이언트로 전송된 메시지를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-122">This object handles messages sent from the service to the client on the callback interface.</span></span>  
  
 [!code-csharp[c_DuplexServices#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#3)]
 [!code-vb[c_DuplexServices#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#3)]  
  
 <span data-ttu-id="8e7c8-123">서비스의 구성은 세션 통신 및 이중 통신 모두를 지원하는 바인딩을 제공하도록 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-123">The configuration for the service must be set up to provide a binding that supports both session communication and duplex communication.</span></span> <span data-ttu-id="8e7c8-124">`wsDualHttpBinding` 요소는 세션 통신을 지원하며 각 방향에 대해 하나씩, 이중 HTTP 연결을 제공하여 이중 통신을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-124">The `wsDualHttpBinding` element supports session communication and allows duplex communication by providing dual HTTP connections, one for each direction.</span></span>  
  
 <span data-ttu-id="8e7c8-125">클라이언트에서는 다음 샘플 구성과 같이 서버가 클라이언트에 연결하는 데 사용할 수 있는 주소를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-125">On the client, you must configure an address that the server can use to connect to the client, as shown in the following sample configuration.</span></span>  
  
  
  
> [!NOTE]
>  <span data-ttu-id="8e7c8-126">보안 대화를 사용하여 인증할 수 없는 이중이 아닌 클라이언트는 일반적으로 <xref:System.ServiceModel.Security.MessageSecurityException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-126">Non-duplex clients that fail to authenticate using a secure conversation typically throw a <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span> <span data-ttu-id="8e7c8-127">그러나 보안 대화를 사용하는 이중 클라이언트가 인증할 수 없는 경우 클라이언트는 대신 <xref:System.TimeoutException>을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-127">However, if a duplex client that uses a secure conversation fails to authenticate, the client receives a <xref:System.TimeoutException> instead.</span></span>  
  
 <span data-ttu-id="8e7c8-128">`WSHttpBinding` 요소를 사용하여 클라이언트/서비스를 만들고 클라이언트 콜백 끝점이 없는 경우 다음 오류를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-128">If you create a client/service using the `WSHttpBinding` element and you do not include the client callback endpoint, you will receive the following error.</span></span>  
  
```  
HTTP could not register URL  
htp://+:80/Temporary_Listen_Addresses/<guid> because TCP port 80 is being used by another application.  
```  
  
 <span data-ttu-id="8e7c8-129">다음 샘플 코드에서는 클라이언트를 지정 하는 방법을 끝점 주소 프로그래밍 방식으로</span><span class="sxs-lookup"><span data-stu-id="8e7c8-129">The following sample code shows how to specify the client endpoint address programmatically.</span></span>
  
```csharp  
WSDualHttpBinding binding = new WSDualHttpBinding();  
EndpointAddress endptadr = new EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server");  
binding.ClientBaseAddress = new Uri("http://localhost:8000/DuplexTestUsingCode/Client/");  
```  
```vb
Dim binding As New WSDualHttpBinding()
Dim endptadr As New EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server")
binding.ClientBaseAddress = New Uri("http://localhost:8000/DuplexTestUsingCode/Client/")  
```

 <span data-ttu-id="8e7c8-130">다음 샘플 코드에서는 구성에서 클라이언트 끝점 주소를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-130">The following sample code shows how to specify the client endpoint address in configuration.</span></span>  
  
```xml  
<client>  
    <endpoint name ="ServerEndpoint"   
          address="http://localhost:12000/DuplexTestUsingConfig/Server"  
          bindingConfiguration="WSDualHttpBinding_IDuplexTest"   
            binding="wsDualHttpBinding"  
           contract="IDuplexTest" />  
</client>  
<bindings>  
    <wsDualHttpBinding>  
        <binding name="WSDualHttpBinding_IDuplexTest"    
          clientBaseAddress="http://localhost:8000/myClient/" >  
            <security mode="None"/>  
         </binding>  
    </wsDualHttpBinding>  
</bindings>  
```  
  
> [!WARNING]
>  <span data-ttu-id="8e7c8-131">이중 모델에서는 서비스나 클라이언트가 채널을 닫을 때를 자동으로 감지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-131">The duplex model does not automatically detect when a service or client closes its channel.</span></span> <span data-ttu-id="8e7c8-132">따라서 클라이언트가 예기치 않게 종료되는 경우 기본적으로 클라이언트가 알림을 받지 못하고, 클라이언트가 예기치 않게 종료되는 경우에는 서비스가 알림을 받지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-132">So if a client unexpectedly terminates, by default the service will not be notified, or if a client unexpectedly terminates, the service will not be notified.</span></span> <span data-ttu-id="8e7c8-133">클라이언트와 서비스는 선택하는 경우 서로에게 알리도록 자체 프로토콜을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e7c8-133">Clients and services can implement their own protocol to notify each other if they so choose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e7c8-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e7c8-134">See Also</span></span>  
 [<span data-ttu-id="8e7c8-135">이중</span><span class="sxs-lookup"><span data-stu-id="8e7c8-135">Duplex</span></span>](../../../../docs/framework/wcf/samples/duplex.md)  
 [<span data-ttu-id="8e7c8-136">클라이언트 런타임 동작 지정</span><span class="sxs-lookup"><span data-stu-id="8e7c8-136">Specifying Client Run-Time Behavior</span></span>](../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [<span data-ttu-id="8e7c8-137">방법: 채널 팩터리를 만들어 채널을 만들고 관리하는 데 사용</span><span class="sxs-lookup"><span data-stu-id="8e7c8-137">How to: Create a Channel Factory and Use it to Create and Manage Channels</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels.md)
