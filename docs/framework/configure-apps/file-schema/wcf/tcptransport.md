---
title: '&lt;tcpTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
ms.openlocfilehash: 4141b0f6493c51048ad60accdc1d5ee9bac01231
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="lttcptransportgt"></a><span data-ttu-id="3262b-102">&lt;tcpTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="3262b-102">&lt;tcpTransport&gt;</span></span>
<span data-ttu-id="3262b-103">사용자 지정 바인딩에 대한 메시지를 전송하기 위해 채널이 사용할 수 있는 TCP 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-103">Defines a TCP transport that can be used by a channel to transfers messages for a custom binding.</span></span>  
  
 <span data-ttu-id="3262b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3262b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3262b-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="3262b-105">\<bindings></span></span>  
<span data-ttu-id="3262b-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3262b-106">\<customBinding></span></span>  
<span data-ttu-id="3262b-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="3262b-107">\<binding></span></span>  
<span data-ttu-id="3262b-108">\<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="3262b-108">\<tcpTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3262b-109">구문</span><span class="sxs-lookup"><span data-stu-id="3262b-109">Syntax</span></span>  
  
```xml  
<tcpTransport   
      channelInitializationTimeout="TimeSpan"   
      connectionBufferSize="Integer"   
      hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
      listenBacklog="Integer"  
      manualAddressing="Boolean"   
      maxBufferPoolSize="Integer"  
      maxBufferSize="Integer"  
      maxOutputDelay="TimeSpan"  
      maxPendingAccepts="Integer"   
      maxPendingConnections="Integer"  
      maxReceivedMessageSize="Integer"   
      portSharingEnabled="Boolean"  
      teredoEnabled="Boolean"  
      transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse" >  
      <connectionPoolSettings  
            groupName="String"  
            idleTimeout"TimeSpan"  
            leaseTimeout="TimeSpan"  
            maxOutboundConnectionsPerEndpopint="Integer" />  
</tcpTransport>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3262b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3262b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3262b-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3262b-112">특성</span><span class="sxs-lookup"><span data-stu-id="3262b-112">Attributes</span></span>  
  
|<span data-ttu-id="3262b-113">특성</span><span class="sxs-lookup"><span data-stu-id="3262b-113">Attribute</span></span>|<span data-ttu-id="3262b-114">설명</span><span class="sxs-lookup"><span data-stu-id="3262b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3262b-115">channelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="3262b-115">channelInitializationTimeout</span></span>|<span data-ttu-id="3262b-116">수락할 채널을 초기화하기 위한 시간 제한을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-116">Gets or sets the time limit for initializing a channel to be accepted.</span></span>  <span data-ttu-id="3262b-117">연결이 끊어지기 전에 채널이 초기화 상태를 유지할 수 있는 최대 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-117">The maximum time a channel can be in the initialization state before being disconnected in seconds.</span></span> <span data-ttu-id="3262b-118">이 할당량에는 TCP 연결이 .Net 메시지 프레이밍 프로토콜을 사용하여 자체 인증하는 데 걸릴 수 있는 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-118">This quota includes the time a TCP connection can take to authenticate itself using the .Net Message Framing protocol.</span></span> <span data-ttu-id="3262b-119">서버가 인증을 수행하는 데 충분한 정보를 가지려면 클라이언트가 몇 가지 초기 데이터를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-119">A client needs to send some initial data before the server has enough information to perform authentication.</span></span> <span data-ttu-id="3262b-120">기본값은 30초입니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-120">The default is 30 seconds.</span></span>|  
|<span data-ttu-id="3262b-121">connectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="3262b-121">connectionBufferSize</span></span>|<span data-ttu-id="3262b-122">통신 중에 클라이언트나 서비스로부터 serialize된 메시지 청크를 전송할 때 사용되는 버퍼의 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-122">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="3262b-123">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="3262b-123">hostNameComparisonMode</span></span>|<span data-ttu-id="3262b-124">URI 비교 시 서비스에 액세스하는 데 호스트 이름이 사용되는지 여부를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-124">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="3262b-125">listenBacklog</span><span class="sxs-lookup"><span data-stu-id="3262b-125">listenBacklog</span></span>|<span data-ttu-id="3262b-126">웹 서비스에 대해 보류할 수 있는 최대 대기 중인 연결 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-126">The maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="3262b-127">`connectionLeaseTimeout` 특성은 연결 예외가 throw되기 전에 클라이언트가 연결을 대기하는 시간을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-127">The `connectionLeaseTimeout` attribute limits the duration the client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="3262b-128">웹 서비스에 대해 보류할 수 있는 최대 대기 중인 연결 요청 수를 제어하는 소켓 수준 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-128">This is a socket level property which controls the maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="3262b-129">ListenBacklog 값이 너무 낮으면 WCF는 요청 수락을 중지하므로 서버가 기존의 대기 중인 연결 일부를 인식할 때까지 새 연결을 삭제합니다. 기본값은 16 \* 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-129">When ListenBacklog is too low, WCF will stop accepting requests and therefore drop new connections until the server acknowledges some of the existing queued connections .The default is 16 \* number of processors.</span></span>|  
|<span data-ttu-id="3262b-130">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="3262b-130">manualAddressing</span></span>|<span data-ttu-id="3262b-131">메시지의 주소를 수동으로 지정해야 하는지 여부를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-131">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="3262b-132">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="3262b-132">maxBufferPoolSize</span></span>|<span data-ttu-id="3262b-133">전송에 사용되는 최대 버퍼 풀 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-133">Gets or sets the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="3262b-134">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="3262b-134">maxBufferSize</span></span>|<span data-ttu-id="3262b-135">사용할 버퍼의 최대 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-135">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="3262b-136">스트리밍된 메시지의 경우 이 값은 버퍼링된 모드에서 읽어오는 메시지 헤더의 최대 예상 크기 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-136">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="3262b-137">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="3262b-137">maxOutputDelay</span></span>|<span data-ttu-id="3262b-138">메시지 청크 또는 전체 메시지를 보내기 전에 메모리에 버퍼링된 상태로 유지할 수 있는 최대 시간 간격을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-138">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="3262b-139">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="3262b-139">maxPendingAccepts</span></span>|<span data-ttu-id="3262b-140">서비스에 들어오는 연결을 처리하는 데 사용할 수 있는 보류 중인 최대 비동기 수락 작업 수를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-140">Gets or sets the maximum number of pending asynchronous accept operations that are available for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="3262b-141">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="3262b-141">maxPendingConnections</span></span>|<span data-ttu-id="3262b-142">서비스에서 디스패치를 대기하는 최대 연결 수를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-142">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="3262b-143">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="3262b-143">maxReceivedMessageSize</span></span>|<span data-ttu-id="3262b-144">받을 수 있는 최대 메시지 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-144">Gets and sets the maximum allowable message size that can be received.</span></span>|  
|<span data-ttu-id="3262b-145">portSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="3262b-145">portSharingEnabled</span></span>|<span data-ttu-id="3262b-146">이 연결에서 TCP 포트 공유를 사용하는지를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-146">A Boolean value that specifies if TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="3262b-147">이 값이 `false`이면 바인딩마다 자체 단독 포트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-147">If this is `false`, each binding will use its own exclusive port.</span></span> <span data-ttu-id="3262b-148">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-148">The default is `false`.</span></span><br /><br /> <span data-ttu-id="3262b-149">이 설정은 서비스에만 적용되며,</span><span class="sxs-lookup"><span data-stu-id="3262b-149">This setting is relevant only to services.</span></span> <span data-ttu-id="3262b-150">클라이언트는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-150">Clients are not affected.</span></span><br /><br /> <span data-ttu-id="3262b-151">이 설정을 사용하려면 WCF(Windows Communication Foundation) TCP 포트 공유 서비스의 시작 유형을 수동 또는 자동으로 변경하여 서비스를 사용하도록 설정해야 합니다</span><span class="sxs-lookup"><span data-stu-id="3262b-151">Using this setting requires enabling the Windows Communication Foundation (WCF) TCP Port Sharing Service by changing its Startup Type to Manual or Automatic</span></span>|  
|<span data-ttu-id="3262b-152">teredoEnabled</span><span class="sxs-lookup"><span data-stu-id="3262b-152">teredoEnabled</span></span>|<span data-ttu-id="3262b-153">Teredo(방화벽으로 보호되는 클라이언트의 주소를 지정하는 기술)의 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-153">A Boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span> <span data-ttu-id="3262b-154">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-154">The default is `false`.</span></span><br /><br /> <span data-ttu-id="3262b-155">이 속성은 내부 TCP 소켓에 대해 Teredo를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-155">This property enables Teredo for the underlying TCP socket.</span></span> <span data-ttu-id="3262b-156">자세한 내용은 참조 [Teredo 개요](http://go.microsoft.com/fwlink/?LinkId=95339)합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-156">For more information, see [Teredo Overview](http://go.microsoft.com/fwlink/?LinkId=95339).</span></span><br /><br /> <span data-ttu-id="3262b-157">이 속성은 [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] 및 [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)]에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-157">This property is applicable only on [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] and [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)].</span></span> [!INCLUDE[wv](../../../../../includes/wv-md.md)]<span data-ttu-id="3262b-158">에는 시스템 수준의 Teredo 구성 옵션이 있으므로 Vista를 실행할 경우 이 속성이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-158"> has a machine-wide configuration option for Teredo, so when running Vista, this property is ignored.</span></span> <span data-ttu-id="3262b-159">Teredo를 사용할 경우 클라이언트와 서비스 시스템 모두에 Microsoft IPv6 스택을 설치하고 Teredo 사용에 적합하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-159">Teredo requires that the client and service machines both have the Microsoft IPv6 stack installed and correctly configured for Teredo usage.</span></span> <span data-ttu-id="3262b-160">Teredo 구성에 대 한 자세한 내용은 참조 [Teredo 개요](http://go.microsoft.com/fwlink/?LinkId=95339)합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-160">For more information about configuring Teredo, see [Teredo Overview](http://go.microsoft.com/fwlink/?LinkId=95339).</span></span> <span data-ttu-id="3262b-161">자세한 내용은 참조 [Windows Server 2003 기술 센터](http://go.microsoft.com/fwlink/?LinkId=49888)합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-161">For more information, see [Windows Server 2003 Technology Centers](http://go.microsoft.com/fwlink/?LinkId=49888).</span></span>|  
|<span data-ttu-id="3262b-162">transferMode</span><span class="sxs-lookup"><span data-stu-id="3262b-162">transferMode</span></span>|<span data-ttu-id="3262b-163">메시지가 연결 지향 전송을 사용하여 버퍼링되는지 아니면 스트리밍되는지를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-163">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|<span data-ttu-id="3262b-164">connectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="3262b-164">connectionPoolSettings</span></span>|<span data-ttu-id="3262b-165">명명된 파이프 바인딩의 추가 연결 풀 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-165">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3262b-166">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3262b-166">Child Elements</span></span>  
 <span data-ttu-id="3262b-167">없음</span><span class="sxs-lookup"><span data-stu-id="3262b-167">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3262b-168">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3262b-168">Parent Elements</span></span>  
  
|<span data-ttu-id="3262b-169">요소</span><span class="sxs-lookup"><span data-stu-id="3262b-169">Element</span></span>|<span data-ttu-id="3262b-170">설명</span><span class="sxs-lookup"><span data-stu-id="3262b-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3262b-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="3262b-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="3262b-172">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-172">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3262b-173">설명</span><span class="sxs-lookup"><span data-stu-id="3262b-173">Remarks</span></span>  
 <span data-ttu-id="3262b-174">이 전송은 "net.tcp://hostname:port/path" 형식의 URI를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-174">This transport uses URIs of the form "net.tcp://hostname:port/path".</span></span> <span data-ttu-id="3262b-175">다른 URI 구성 요소는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-175">Other URI components are optional.</span></span>  
  
 <span data-ttu-id="3262b-176">`tcpTransport` 요소는 TCP 전송 프로토콜을 구현하는 사용자 지정 바인딩을 만들기 위한 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-176">The `tcpTransport` element is the starting point for creating a custom binding that implements the TCP transport protocol.</span></span> <span data-ttu-id="3262b-177">이 전송은 WCF와 WCF 사이의 통신을 위해 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3262b-177">This transport is optimized for WCF-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3262b-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3262b-178">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TcpTransportElement>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="3262b-179">전송</span><span class="sxs-lookup"><span data-stu-id="3262b-179">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="3262b-180">전송 선택</span><span class="sxs-lookup"><span data-stu-id="3262b-180">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="3262b-181">바인딩</span><span class="sxs-lookup"><span data-stu-id="3262b-181">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3262b-182">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="3262b-182">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="3262b-183">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="3262b-183">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="3262b-184">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3262b-184">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
