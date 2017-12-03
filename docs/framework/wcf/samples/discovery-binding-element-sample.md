---
title: "Discovery 바인딩 Element 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af513015-85bf-417b-8729-1bdff77ff6d6
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b658cc481d3ca5e87b5b9e2aab6b7561be2c65b1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="discovery-binding-element-sample"></a><span data-ttu-id="07d48-102">Discovery 바인딩 Element 샘플</span><span class="sxs-lookup"><span data-stu-id="07d48-102">Discovery Binding Element Sample</span></span>
<span data-ttu-id="07d48-103">이 샘플에서는 검색 클라이언트 바인딩 요소를 사용하여 서비스를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-103">This sample demonstrates how to use the discovery client binding element to discover a service.</span></span> <span data-ttu-id="07d48-104">개발자는 이 기능을 사용하여 기존 클라이언트 채널 스택에 검색 클라이언트 채널을 추가할 수 있으므로 프로그래밍 모델을 매우 직관적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-104">This feature enables developers to add a discovery client channel to their existing client channel stack, making the programming model very intuitive.</span></span> <span data-ttu-id="07d48-105">연결된 채널이 열리면 검색을 사용하여 서비스의 주소가 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-105">When the associated channel is opened, the address of the service is resolved using discovery.</span></span> <span data-ttu-id="07d48-106">이 샘플은 다음 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-106">This sample consists of the following projects:</span></span>  
  
-   <span data-ttu-id="07d48-107">**CalculatorService**: 검색 가능한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-107">**CalculatorService**: A discoverable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
-   <span data-ttu-id="07d48-108">**CalculatorClient**: A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] discovery 클라이언트 채널을 사용 하 여 검색 하 고 CalculatorService를 호출 하는 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-108">**CalculatorClient**: A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application that uses the discovery client channel to search for and call the CalculatorService.</span></span>  
  
-   <span data-ttu-id="07d48-109">**DynamicCalculatorClient**: A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 동적 끝점을 사용 하 여 검색 하 고 CalculatorService를 호출 하는 클라이언트 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-109">**DynamicCalculatorClient**: A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application that uses a dynamic endpoint to search for and call the CalculatorService.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="07d48-110">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="07d48-111">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="07d48-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="07d48-112">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="07d48-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="07d48-113">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryBindingElement`  
  
## <a name="calculatorservice"></a><span data-ttu-id="07d48-114">CalculatorService</span><span class="sxs-lookup"><span data-stu-id="07d48-114">CalculatorService</span></span>  
 <span data-ttu-id="07d48-115">이 프로젝트에는 `ICalculatorService` 계약을 구현하는 간단한 계산기 서비스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-115">This project contains a simple calculator service that implements the `ICalculatorService` contract.</span></span>  
  
 <span data-ttu-id="07d48-116">다음 App.config 파일은 서비스 동작과 검색 끝점에 `<serviceDiscovery>` 동작을 추가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-116">The following App.config file is used to add a `<serviceDiscovery>` behavior in the service behaviors as well as the discovery endpoint.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">  
        <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <!--Enable discovery through configuration.-->  
      <serviceBehaviors>  
        <behavior name="CalculatorBehavior">  
          <serviceDiscovery>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="07d48-117">이렇게 하면 서비스와 해당 끝점이 검색 가능하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-117">This makes the service and its endpoints discoverable.</span></span> <span data-ttu-id="07d48-118">CalculatorService는 NetTcpBinding 바인딩을 사용하여 하나의 끝점을 추가하는 자체 호스팅 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-118">The CalculatorService is a self-hosted service that adds one endpoint using the NetTcpBinding binding.</span></span> <span data-ttu-id="07d48-119">또한 다음 코드와 같이 끝점에 `EndpointDiscoveryBehavior`를 추가하고 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-119">It also adds an `EndpointDiscoveryBehavior` to the endpoint and specifies a scope as shown in the following code.</span></span>  
  
```  
// Add a NET.TCP endpoint and add a scope to that endpoint.  
ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new NetTcpBinding(), netTcpAddress);  
EndpointDiscoveryBehavior netTctEndpointBehavior = new EndpointDiscoveryBehavior();  
netTctEndpointBehavior.Scopes.Add(new Uri("ldap:///ou=engineering,o=exampleorg,c=us"));  
netTcpEndpoint.Behaviors.Add(netTctEndpointBehavior);  
serviceHost.Open();  
```  
  
## <a name="calculatorclient"></a><span data-ttu-id="07d48-120">CalculatorClient</span><span class="sxs-lookup"><span data-stu-id="07d48-120">CalculatorClient</span></span>  
 <span data-ttu-id="07d48-121">이 프로젝트에는 CalculatorService에 메시지를 보내는 클라이언트 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-121">This project contains a client implementation that sends messages to the CalculatorService.</span></span> <span data-ttu-id="07d48-122">이 프로그램에서는 `CreateCustomBindingWithDiscoveryElement()` 메서드를 사용하여 검색 클라이언트 채널을 사용하는 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-122">This program uses the `CreateCustomBindingWithDiscoveryElement()` method to create a custom binding that uses the Discovery Client Channel.</span></span>  
  
```  
static CustomBinding CreateCustomBindingWithDiscoveryElement()  
 {  
      DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
            // Provide the search criteria and the endpoint over which the probe is sent  
            discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
            discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
            CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
            // Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
            // An exception is thrown if this binding element is not at the top  
            customBinding.Elements.Insert(0, discoveryBindingElement);  
  
            return customBinding; }  
```  
  
 <span data-ttu-id="07d48-123"><xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>가 인스턴스화된 후 개발자는 서비스를 검색할 때 사용할 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-123">After the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> is instantiated, the developer specifies the criteria to use when searching for a service.</span></span> <span data-ttu-id="07d48-124">이 경우 검색 찾기 조건은 `ICalculatorService` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-124">In this case, the discovery find criterion is the `ICalculatorService` type.</span></span> <span data-ttu-id="07d48-125">또한 개발자는 서비스를 찾을 위치를 지정하는 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>를 반환하는 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-125">Additionally, the developer specifies a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> which returns a <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> that specifies where to look for the services.</span></span> <span data-ttu-id="07d48-126"><xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>는 새 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-126">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> returns a new <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instance.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="07d48-127">[검색 클라이언트 채널을 사용 하 여 사용자 지정 바인딩을 사용](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-127"> [Using a Custom Binding with the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md).</span></span>  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
    // to the DiscoveryClientBindingElement. The Discovery ClientChannel   
    // uses this endpoint to send Probe message.  
    public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
    {  
        public override DiscoveryEndpoint GetDiscoveryEndpoint()  
        {  
            return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
        }  
    }  
```  
  
 <span data-ttu-id="07d48-128">이 경우 클라이언트에서는 검색 프로토콜에 의해 정의된 UDP 멀티캐스트 메커니즘을 사용하여 로컬 서브넷의 서비스를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-128">In this case, the client uses the UDP multicast mechanism defined by the Discovery protocol to search for services on the local subnet.</span></span> <span data-ttu-id="07d48-129">메서드의 나머지 부분에서는 사용자 지정 바인딩을 만들고 스택의 맨 위에 검색 바인딩 요소를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-129">The remainder of the method creates a custom binding and inserts the Discovery binding element at the top of the stack.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07d48-130"><xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>는 바인딩 스택의 맨 위에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-130">The <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must be placed on the top of the binding stack.</span></span> <span data-ttu-id="07d48-131">실제 주소는 검색 클라이언트 채널에만 있으므로 <xref:System.ServiceModel.Channels.BindingElement>의 맨 위에 있는 모든 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>는 만드는 채널 팩터리나 채널에서 `EndpointAddress` 또는 `Via` 속성을 사용하지 않는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-131">Any <xref:System.ServiceModel.Channels.BindingElement> on top of <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must make sure that the channel factory or channel it creates does not use the `EndpointAddress` or `Via` properties, because the actual address is found only at the Discovery client channel.</span></span>  
  
 <span data-ttu-id="07d48-132">그런 다음 이 사용자 지정 바인딩과 끝점 주소를 전달하여 `CalculatorClient`를 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-132">Next, the `CalculatorClient` can be instantiated by passing in this custom binding as well as an endpoint address.</span></span>  
  
```  
CalculatorServiceClient client = new CalculatorServiceClient(CreateCustomBindingWithDiscoveryElement(), DiscoveryClientBindingElement.DiscoveryEndpointAddress);  
```  
  
 <span data-ttu-id="07d48-133">Discovery 클라이언트 채널을 사용하는 경우 이전에 지정한 상수 끝점 주소가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-133">When using the Discovery Client Channel, the constant endpoint address specified previously is passed in.</span></span> <span data-ttu-id="07d48-134">이제 런타임 시 Discovery 클라이언트 채널이 검색 조건으로 지정한 서비스를 찾아서 연결해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-134">Now at runtime, the Discovery Client Channel finds the service specified by the find criteria and connects to it.</span></span> <span data-ttu-id="07d48-135">서비스 및 클라이언트에서 연결을 설정하려면 동일한 기본 바인딩 스택도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-135">For the service and the client to establish a connection, they must also have the same underlying binding stack.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="07d48-136">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="07d48-136">To use this sample</span></span>  
  
1.  <span data-ttu-id="07d48-137">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-137">Open the solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="07d48-138">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-138">Build the solution.</span></span>  
  
3.  <span data-ttu-id="07d48-139">서비스 응용 프로그램과 각 클라이언트 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-139">Run the service application and each of the client applications.</span></span>  
  
4.  <span data-ttu-id="07d48-140">클라이언트에서 주소를 모르고도 서비스를 찾을 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="07d48-140">Observe that the client was able to find the service without knowing its address.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d48-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07d48-141">See Also</span></span>
