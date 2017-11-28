---
title: '&lt;tcpTransport&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3c9bb9619cf076f6d6053e1936f989b169ebec4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lttcptransportgt"></a><span data-ttu-id="8ea13-102">&lt;tcpTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="8ea13-102">&lt;tcpTransport&gt;</span></span>
<span data-ttu-id="8ea13-103">사용자 지정 바인딩에 대한 메시지를 전송하기 위해 채널이 사용할 수 있는 TCP 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-103">Defines a TCP transport that can be used by a channel to transfers messages for a custom binding.</span></span>  
  
 <span data-ttu-id="8ea13-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8ea13-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8ea13-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="8ea13-105">\<bindings></span></span>  
<span data-ttu-id="8ea13-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8ea13-106">\<customBinding></span></span>  
<span data-ttu-id="8ea13-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="8ea13-107">\<binding></span></span>  
<span data-ttu-id="8ea13-108">\<tcpTransport ></span><span class="sxs-lookup"><span data-stu-id="8ea13-108">\<tcpTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ea13-109">구문</span><span class="sxs-lookup"><span data-stu-id="8ea13-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ea13-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8ea13-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8ea13-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ea13-112">특성</span><span class="sxs-lookup"><span data-stu-id="8ea13-112">Attributes</span></span>  
  
|<span data-ttu-id="8ea13-113">특성</span><span class="sxs-lookup"><span data-stu-id="8ea13-113">Attribute</span></span>|<span data-ttu-id="8ea13-114">설명</span><span class="sxs-lookup"><span data-stu-id="8ea13-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ea13-115">channelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="8ea13-115">channelInitializationTimeout</span></span>|<span data-ttu-id="8ea13-116">수락할 채널을 초기화하기 위한 시간 제한을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-116">Gets or sets the time limit for initializing a channel to be accepted.</span></span>  <span data-ttu-id="8ea13-117">연결이 끊어지기 전에 채널이 초기화 상태를 유지할 수 있는 최대 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-117">The maximum time a channel can be in the initialization state before being disconnected in seconds.</span></span> <span data-ttu-id="8ea13-118">이 할당량에는 TCP 연결이 .Net 메시지 프레이밍 프로토콜을 사용하여 자체 인증하는 데 걸릴 수 있는 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-118">This quota includes the time a TCP connection can take to authenticate itself using the .Net Message Framing protocol.</span></span> <span data-ttu-id="8ea13-119">서버가 인증을 수행하는 데 충분한 정보를 가지려면 클라이언트가 몇 가지 초기 데이터를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-119">A client needs to send some initial data before the server has enough information to perform authentication.</span></span> <span data-ttu-id="8ea13-120">기본값은 30초입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-120">The default is 30 seconds.</span></span>|  
|<span data-ttu-id="8ea13-121">connectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="8ea13-121">connectionBufferSize</span></span>|<span data-ttu-id="8ea13-122">통신 중에 클라이언트나 서비스로부터 serialize된 메시지 청크를 전송할 때 사용되는 버퍼의 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-122">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="8ea13-123">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="8ea13-123">hostNameComparisonMode</span></span>|<span data-ttu-id="8ea13-124">URI 비교 시 서비스에 액세스하는 데 호스트 이름이 사용되는지 여부를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-124">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="8ea13-125">listenBacklog</span><span class="sxs-lookup"><span data-stu-id="8ea13-125">listenBacklog</span></span>|<span data-ttu-id="8ea13-126">웹 서비스에 대해 보류할 수 있는 최대 대기 중인 연결 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-126">The maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="8ea13-127">`connectionLeaseTimeout` 특성은 연결 예외가 throw되기 전에 클라이언트가 연결을 대기하는 시간을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-127">The `connectionLeaseTimeout` attribute limits the duration the client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="8ea13-128">웹 서비스에 대해 보류할 수 있는 최대 대기 중인 연결 요청 수를 제어하는 소켓 수준 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-128">This is a socket level property which controls the maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="8ea13-129">ListenBacklog 값이 너무 낮으면 WCF는 요청 수락을 중지하므로 서버가 기존의 대기 중인 연결 일부를 인식할 때까지 새 연결을 삭제합니다. 기본값은 16 * 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-129">When ListenBacklog is too low, WCF will stop accepting requests and therefore drop new connections until the server acknowledges some of the existing queued connections .The default is 16 * number of processors.</span></span>|  
|<span data-ttu-id="8ea13-130">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="8ea13-130">manualAddressing</span></span>|<span data-ttu-id="8ea13-131">메시지의 주소를 수동으로 지정해야 하는지 여부를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-131">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="8ea13-132">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="8ea13-132">maxBufferPoolSize</span></span>|<span data-ttu-id="8ea13-133">전송에 사용되는 최대 버퍼 풀 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-133">Gets or sets the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="8ea13-134">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="8ea13-134">maxBufferSize</span></span>|<span data-ttu-id="8ea13-135">사용할 버퍼의 최대 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-135">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="8ea13-136">스트리밍된 메시지의 경우 이 값은 버퍼링된 모드에서 읽어오는 메시지 헤더의 최대 예상 크기 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-136">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="8ea13-137">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="8ea13-137">maxOutputDelay</span></span>|<span data-ttu-id="8ea13-138">메시지 청크 또는 전체 메시지를 보내기 전에 메모리에 버퍼링된 상태로 유지할 수 있는 최대 시간 간격을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-138">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="8ea13-139">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="8ea13-139">maxPendingAccepts</span></span>|<span data-ttu-id="8ea13-140">서비스에 들어오는 연결을 처리하는 데 사용할 수 있는 보류 중인 최대 비동기 수락 작업 수를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-140">Gets or sets the maximum number of pending asynchronous accept operations that are available for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="8ea13-141">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="8ea13-141">maxPendingConnections</span></span>|<span data-ttu-id="8ea13-142">서비스에서 디스패치를 대기하는 최대 연결 수를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-142">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="8ea13-143">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="8ea13-143">maxReceivedMessageSize</span></span>|<span data-ttu-id="8ea13-144">받을 수 있는 최대 메시지 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-144">Gets and sets the maximum allowable message size that can be received.</span></span>|  
|<span data-ttu-id="8ea13-145">portSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="8ea13-145">portSharingEnabled</span></span>|<span data-ttu-id="8ea13-146">이 연결에서 TCP 포트 공유를 사용하는지를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-146">A Boolean value that specifies if TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="8ea13-147">이 값이 `false`이면 바인딩마다 자체 단독 포트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-147">If this is `false`, each binding will use its own exclusive port.</span></span> <span data-ttu-id="8ea13-148">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-148">The default is `false`.</span></span><br /><br /> <span data-ttu-id="8ea13-149">이 설정은 서비스에만 적용되며,</span><span class="sxs-lookup"><span data-stu-id="8ea13-149">This setting is relevant only to services.</span></span> <span data-ttu-id="8ea13-150">클라이언트는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-150">Clients are not affected.</span></span><br /><br /> <span data-ttu-id="8ea13-151">이 설정을 사용하려면 WCF(Windows Communication Foundation) TCP 포트 공유 서비스의 시작 유형을 수동 또는 자동으로 변경하여 서비스를 사용하도록 설정해야 합니다</span><span class="sxs-lookup"><span data-stu-id="8ea13-151">Using this setting requires enabling the Windows Communication Foundation (WCF) TCP Port Sharing Service by changing its Startup Type to Manual or Automatic</span></span>|  
|<span data-ttu-id="8ea13-152">teredoEnabled</span><span class="sxs-lookup"><span data-stu-id="8ea13-152">teredoEnabled</span></span>|<span data-ttu-id="8ea13-153">Teredo(방화벽으로 보호되는 클라이언트의 주소를 지정하는 기술)의 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-153">A Boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span> <span data-ttu-id="8ea13-154">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-154">The default is `false`.</span></span><br /><br /> <span data-ttu-id="8ea13-155">이 속성은 내부 TCP 소켓에 대해 Teredo를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-155">This property enables Teredo for the underlying TCP socket.</span></span> <span data-ttu-id="8ea13-156">자세한 내용은 참조 [Teredo 개요](http://go.microsoft.com/fwlink/?LinkId=95339)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-156">For more information, see [Teredo Overview](http://go.microsoft.com/fwlink/?LinkId=95339).</span></span><br /><br /> <span data-ttu-id="8ea13-157">이 속성은 [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] 및 [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)]에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-157">This property is applicable only on [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] and [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)].</span></span> [!INCLUDE[wv](../../../../../includes/wv-md.md)]<span data-ttu-id="8ea13-158">에는 시스템 수준의 Teredo 구성 옵션이 있으므로 Vista를 실행할 경우 이 속성이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-158"> has a machine-wide configuration option for Teredo, so when running Vista, this property is ignored.</span></span> <span data-ttu-id="8ea13-159">Teredo를 사용할 경우 클라이언트와 서비스 시스템 모두에 Microsoft IPv6 스택을 설치하고 Teredo 사용에 적합하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-159">Teredo requires that the client and service machines both have the Microsoft IPv6 stack installed and correctly configured for Teredo usage.</span></span> <span data-ttu-id="8ea13-160">Teredo 구성에 대 한 자세한 내용은 참조 [Teredo 개요](http://go.microsoft.com/fwlink/?LinkId=95339)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-160">For more information about configuring Teredo, see [Teredo Overview](http://go.microsoft.com/fwlink/?LinkId=95339).</span></span> <span data-ttu-id="8ea13-161">자세한 내용은 참조 [Windows Server 2003 기술 센터](http://go.microsoft.com/fwlink/?LinkId=49888)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-161">For more information, see [Windows Server 2003 Technology Centers](http://go.microsoft.com/fwlink/?LinkId=49888).</span></span>|  
|<span data-ttu-id="8ea13-162">transferMode</span><span class="sxs-lookup"><span data-stu-id="8ea13-162">transferMode</span></span>|<span data-ttu-id="8ea13-163">메시지가 연결 지향 전송을 사용하여 버퍼링되는지 아니면 스트리밍되는지를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-163">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|<span data-ttu-id="8ea13-164">connectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8ea13-164">connectionPoolSettings</span></span>|<span data-ttu-id="8ea13-165">명명된 파이프 바인딩의 추가 연결 풀 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-165">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ea13-166">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8ea13-166">Child Elements</span></span>  
 <span data-ttu-id="8ea13-167">없음</span><span class="sxs-lookup"><span data-stu-id="8ea13-167">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ea13-168">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8ea13-168">Parent Elements</span></span>  
  
|<span data-ttu-id="8ea13-169">요소</span><span class="sxs-lookup"><span data-stu-id="8ea13-169">Element</span></span>|<span data-ttu-id="8ea13-170">설명</span><span class="sxs-lookup"><span data-stu-id="8ea13-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ea13-171">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="8ea13-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8ea13-172">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-172">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ea13-173">설명</span><span class="sxs-lookup"><span data-stu-id="8ea13-173">Remarks</span></span>  
 <span data-ttu-id="8ea13-174">이 전송은 "net.tcp://hostname:port/path" 형식의 URI를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-174">This transport uses URIs of the form "net.tcp://hostname:port/path".</span></span> <span data-ttu-id="8ea13-175">다른 URI 구성 요소는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-175">Other URI components are optional.</span></span>  
  
 <span data-ttu-id="8ea13-176">`tcpTransport` 요소는 TCP 전송 프로토콜을 구현하는 사용자 지정 바인딩을 만들기 위한 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-176">The `tcpTransport` element is the starting point for creating a custom binding that implements the TCP transport protocol.</span></span> <span data-ttu-id="8ea13-177">이 전송은 WCF와 WCF 사이의 통신을 위해 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ea13-177">This transport is optimized for WCF-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea13-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ea13-178">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TcpTransportElement>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="8ea13-179">전송</span><span class="sxs-lookup"><span data-stu-id="8ea13-179">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="8ea13-180">전송 선택</span><span class="sxs-lookup"><span data-stu-id="8ea13-180">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="8ea13-181">바인딩</span><span class="sxs-lookup"><span data-stu-id="8ea13-181">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8ea13-182">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="8ea13-182">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="8ea13-183">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="8ea13-183">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="8ea13-184">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8ea13-184">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
