---
title: '&lt;r t&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7c9c01e997e3ba804eae3036e94f2e2e1b951b25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltpeertransportgt"></a><span data-ttu-id="08820-102">&lt;r t&gt;</span><span class="sxs-lookup"><span data-stu-id="08820-102">&lt;peerTransport&gt;</span></span>
<span data-ttu-id="08820-103">사용자 지정 바인딩에 대한 피어 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="08820-103">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="08820-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="08820-104">\<system.serviceModel></span></span>  
<span data-ttu-id="08820-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="08820-105">\<bindings></span></span>  
<span data-ttu-id="08820-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="08820-106">\<customBinding></span></span>  
<span data-ttu-id="08820-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="08820-107">\<binding></span></span>  
<span data-ttu-id="08820-108">\<r t ></span><span class="sxs-lookup"><span data-stu-id="08820-108">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08820-109">구문</span><span class="sxs-lookup"><span data-stu-id="08820-109">Syntax</span></span>  
  
```xml  
<peerTransport   
    listenIpAddress="String"  
    maxBufferPoolSize="Integer"  
    maxReceivedMessageSize="Integer"  
    port="Integer"  
        <security>  
    </security>  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08820-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="08820-110">Attributes and Elements</span></span>  
 <span data-ttu-id="08820-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08820-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08820-112">특성</span><span class="sxs-lookup"><span data-stu-id="08820-112">Attributes</span></span>  
  
|<span data-ttu-id="08820-113">특성</span><span class="sxs-lookup"><span data-stu-id="08820-113">Attribute</span></span>|<span data-ttu-id="08820-114">설명</span><span class="sxs-lookup"><span data-stu-id="08820-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08820-115">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="08820-115">listenIpAddress</span></span>|<span data-ttu-id="08820-116">피어 노드가 TCP 메시지를 수신하는 IP 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="08820-116">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="08820-117">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="08820-117">The default is `null`.</span></span>|  
|<span data-ttu-id="08820-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="08820-118">maxBufferPoolSize</span></span>|<span data-ttu-id="08820-119">버퍼 풀의 최대 크기를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="08820-119">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="08820-120">기본값은 524288입니다.</span><span class="sxs-lookup"><span data-stu-id="08820-120">The default is 524288.</span></span><br /><br /> <span data-ttu-id="08820-121">WCF의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08820-121">Many parts of WCF use buffers.</span></span> <span data-ttu-id="08820-122">버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="08820-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="08820-123">버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08820-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="08820-124">따라서 버퍼를 만들고 삭제하는 데 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08820-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="08820-125">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="08820-125">maxReceivedMessageSize</span></span>|<span data-ttu-id="08820-126">헤더를 포함하는 최대 메시지 크기(바이트)를 정의하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="08820-126">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="08820-127">수신자에게 너무 큰 메시지를 보내면 메시지의 발신자에게 SOAP 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="08820-127">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="08820-128">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="08820-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="08820-129">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="08820-129">The default is 65536.</span></span>|  
|<span data-ttu-id="08820-130">포트</span><span class="sxs-lookup"><span data-stu-id="08820-130">port</span></span>|<span data-ttu-id="08820-131">이 바인딩이 피어 채널 TCP 메시지를 처리할 네트워크 인터페이스 포트를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="08820-131">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="08820-132">이 값은 <xref:System.Net.IPEndPoint.MinPort>와 <xref:System.Net.IPEndPoint.MaxPort> 사이의 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08820-132">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="08820-133">기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="08820-133">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08820-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="08820-134">Child Elements</span></span>  
  
|<span data-ttu-id="08820-135">요소</span><span class="sxs-lookup"><span data-stu-id="08820-135">Element</span></span>|<span data-ttu-id="08820-136">설명</span><span class="sxs-lookup"><span data-stu-id="08820-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08820-137">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="08820-137">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="08820-138">이 전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="08820-138">Defines the security settings for this transport.</span></span> <span data-ttu-id="08820-139">이 요소는 <xref:System.ServiceModel.Configuration.PeerSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="08820-139">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08820-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="08820-140">Parent Elements</span></span>  
  
|<span data-ttu-id="08820-141">요소</span><span class="sxs-lookup"><span data-stu-id="08820-141">Element</span></span>|<span data-ttu-id="08820-142">설명</span><span class="sxs-lookup"><span data-stu-id="08820-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08820-143">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="08820-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="08820-144">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="08820-144">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08820-145">설명</span><span class="sxs-lookup"><span data-stu-id="08820-145">Remarks</span></span>  
 <span data-ttu-id="08820-146">request/reply 작업이 있는 계약에서는 이 전송을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08820-146">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08820-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08820-147">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportElement>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="08820-148">전송</span><span class="sxs-lookup"><span data-stu-id="08820-148">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="08820-149">전송 선택</span><span class="sxs-lookup"><span data-stu-id="08820-149">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="08820-150">바인딩</span><span class="sxs-lookup"><span data-stu-id="08820-150">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="08820-151">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="08820-151">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="08820-152">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="08820-152">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="08820-153">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="08820-153">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
