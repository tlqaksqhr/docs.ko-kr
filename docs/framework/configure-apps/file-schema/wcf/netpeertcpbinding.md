---
title: '&lt;netPeerTcpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35dfb3eee5a01d5fed21bda59f1cab5eb09a1401
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltnetpeertcpbindinggt"></a><span data-ttu-id="5d547-102">&lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="5d547-102">&lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="5d547-103">피어 채널 전용 TCP 메시징의 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-103">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
 <span data-ttu-id="5d547-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5d547-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5d547-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="5d547-105">\<bindings></span></span>  
<span data-ttu-id="5d547-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="5d547-106">\<netPeerTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d547-107">구문</span><span class="sxs-lookup"><span data-stu-id="5d547-107">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding name="string"  
         closeTimeout="TimeSpan"  
         openTimeout="TimeSpan"   
         receiveTimeout="TimeSpan"  
         sendTimeout="TimeSpan"  
         listenIPAddress="String"  
          maxBufferPoolSize="integer"  
         maxReceiveMessageSize="Integer"   
         port="Integer"  
         <security mode="None/Transport/Message/TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d547-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5d547-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5d547-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d547-110">특성</span><span class="sxs-lookup"><span data-stu-id="5d547-110">Attributes</span></span>  
  
|<span data-ttu-id="5d547-111">특성</span><span class="sxs-lookup"><span data-stu-id="5d547-111">Attribute</span></span>|<span data-ttu-id="5d547-112">설명</span><span class="sxs-lookup"><span data-stu-id="5d547-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d547-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="5d547-113">closeTimeout</span></span>|<span data-ttu-id="5d547-114">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="5d547-115">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5d547-116">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="5d547-117">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="5d547-117">listenIPAddress</span></span>|<span data-ttu-id="5d547-118">피어 노드가 TCP 메시지를 수신하는 IP 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-118">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="5d547-119">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-119">The default is `null`.</span></span>|  
|<span data-ttu-id="5d547-120">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="5d547-120">maxBufferPoolSize</span></span>|<span data-ttu-id="5d547-121">이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="5d547-122">기본값은 524,288바이트(512 * 1024)입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-122">The default is 524,288 bytes (512 * 1024).</span></span> <span data-ttu-id="5d547-123">WCF(Windows Communication Foundation)의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="5d547-124">버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="5d547-125">버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="5d547-126">따라서 버퍼를 만들고 삭제하는 데 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="5d547-127">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="5d547-127">maxReceivedMessageSize</span></span>|<span data-ttu-id="5d547-128">헤더를 비롯하여 이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기(바이트)를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-128">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="5d547-129">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-129">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="5d547-130">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-130">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="5d547-131">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-131">The default is 65536.</span></span>|  
|<span data-ttu-id="5d547-132">name</span><span class="sxs-lookup"><span data-stu-id="5d547-132">name</span></span>|<span data-ttu-id="5d547-133">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-133">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="5d547-134">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-134">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="5d547-135">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-135">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5d547-136">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-136">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="5d547-137">openTimeout</span><span class="sxs-lookup"><span data-stu-id="5d547-137">openTimeout</span></span>|<span data-ttu-id="5d547-138">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-138">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="5d547-139">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-139">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5d547-140">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-140">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="5d547-141">포트</span><span class="sxs-lookup"><span data-stu-id="5d547-141">port</span></span>|<span data-ttu-id="5d547-142">이 바인딩이 피어 채널 TCP 메시지를 처리할 네트워크 인터페이스 포트를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-142">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="5d547-143">이 값은 <xref:System.Net.IPEndPoint.MinPort>와 <xref:System.Net.IPEndPoint.MaxPort> 사이의 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-143">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="5d547-144">기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-144">The default is 0.</span></span>|  
|<span data-ttu-id="5d547-145">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="5d547-145">receiveTimeout</span></span>|<span data-ttu-id="5d547-146">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-146">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="5d547-147">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-147">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5d547-148">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-148">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="5d547-149">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="5d547-149">sendTimeout</span></span>|<span data-ttu-id="5d547-150">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="5d547-151">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5d547-152">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-152">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d547-153">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5d547-153">Child Elements</span></span>  
  
|<span data-ttu-id="5d547-154">요소</span><span class="sxs-lookup"><span data-stu-id="5d547-154">Element</span></span>|<span data-ttu-id="5d547-155">설명</span><span class="sxs-lookup"><span data-stu-id="5d547-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d547-156">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="5d547-156">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="5d547-157">이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-157">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5d547-158">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-158">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="5d547-159">\<해결 프로그램 ></span><span class="sxs-lookup"><span data-stu-id="5d547-159">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="5d547-160">피어 메시 내에서 노드의 끝점 IP 주소에 대해 피어 메시 ID를 확인하기 위해 이 바인딩에서 사용하는 피어 확인자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-160">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="5d547-161">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="5d547-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="5d547-162">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-162">Defines the security settings for the message.</span></span> <span data-ttu-id="5d547-163">이 요소는 <xref:System.ServiceModel.Configuration.PeerSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-163">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d547-164">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5d547-164">Parent Elements</span></span>  
  
|<span data-ttu-id="5d547-165">요소</span><span class="sxs-lookup"><span data-stu-id="5d547-165">Element</span></span>|<span data-ttu-id="5d547-166">설명</span><span class="sxs-lookup"><span data-stu-id="5d547-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d547-167">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="5d547-167">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="5d547-168">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-168">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d547-169">설명</span><span class="sxs-lookup"><span data-stu-id="5d547-169">Remarks</span></span>  
 <span data-ttu-id="5d547-170">이 바인딩은 TCP를 통한 피어 전송을 사용하여 피어 투 피어 다자 간 응용 프로그램을 만들 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-170">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="5d547-171">각 피어 노드는 이 바인딩 형식으로 정의된 여러 피어 채널을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-171">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d547-172">예제</span><span class="sxs-lookup"><span data-stu-id="5d547-172">Example</span></span>  
 <span data-ttu-id="5d547-173">다음 예제에서는 피어 채널을 사용하여 여러 상대방과의 통신을 제공하는 NetPeerTcpBinding binding 바인딩 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-173">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="5d547-174">이 바인딩을 사용 하 여의 자세한 시나리오에 대 한 참조 [Net 피어 TCP](http://msdn.microsoft.com/en-us/31f4db66-edb2-40a6-b92a-14098e92acae)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d547-174">For a detailed scenario of using this binding, see [Net Peer TCP](http://msdn.microsoft.com/en-us/31f4db66-edb2-40a6-b92a-14098e92acae).</span></span>  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<netPeerBinding>  
    <binding   
         closeTimeout="00:00:10"  
         openTimeout="00:00:20"   
         receiveTimeout="00:00:30"  
         sendTimeout="00:00:40"  
         maxBufferSize="1001"  
         maxConnections="123"   
         maxReceiveMessageSize="1000">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00"  
            enabled="true" />  
        <security mode="TransportWithMessageCredential">  
            <message clientCredentialType="CardSpace" />  
        </security>  
    </binding>  
</netPeerBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d547-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d547-175">See Also</span></span>  
 <xref:System.ServiceModel.NetPeerTcpBinding>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>  
 [<span data-ttu-id="5d547-176">바인딩</span><span class="sxs-lookup"><span data-stu-id="5d547-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5d547-177">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="5d547-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="5d547-178">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="5d547-178">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="5d547-179">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="5d547-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="5d547-180">Net 피어 TCP</span><span class="sxs-lookup"><span data-stu-id="5d547-180">Net Peer TCP</span></span>](http://msdn.microsoft.com/en-us/31f4db66-edb2-40a6-b92a-14098e92acae)  
 [<span data-ttu-id="5d547-181">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="5d547-181">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
