---
title: '&lt;connectionPoolSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 11500830c7c5fd75a9e2880a5875bd21fb070634
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltconnectionpoolsettingsgt"></a><span data-ttu-id="e4230-102">&lt;connectionPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="e4230-102">&lt;connectionPoolSettings&gt;</span></span>
<span data-ttu-id="e4230-103">명명된 파이프 바인딩의 추가 연결 풀 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-103">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="e4230-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e4230-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e4230-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="e4230-105">\<bindings></span></span>  
<span data-ttu-id="e4230-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e4230-106">\<customBinding></span></span>  
<span data-ttu-id="e4230-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="e4230-107">\<binding></span></span>  
<span data-ttu-id="e4230-108">\<namePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="e4230-108">\<namePipeTransport></span></span>  
<span data-ttu-id="e4230-109">\<connectionPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="e4230-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4230-110">구문</span><span class="sxs-lookup"><span data-stu-id="e4230-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings  
        groupName="String"  
    idleTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4230-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e4230-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e4230-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4230-113">특성</span><span class="sxs-lookup"><span data-stu-id="e4230-113">Attributes</span></span>  
  
|<span data-ttu-id="e4230-114">특성</span><span class="sxs-lookup"><span data-stu-id="e4230-114">Attribute</span></span>|<span data-ttu-id="e4230-115">설명</span><span class="sxs-lookup"><span data-stu-id="e4230-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="e4230-116">나가는 채널에 사용되는 연결 풀의 이름을 정의하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="e4230-117">스트리밍 모드에서는 연결이 공유되지 않습니다. 즉 연결 풀링이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="e4230-118">기본값은 "default" 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-118">The default is a "default" string.</span></span> <span data-ttu-id="e4230-119">이 값을 수정하여 특정 클라이언트의 연결을 별도의 그룹으로 격리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="e4230-120">연결이 끊어지기 전에 유휴 상태를 유지할 수 있는 최대 시간을 지정하는 <xref:System.TimeSpan>(양수)입니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="e4230-121">기본값은 00:02:00입니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-121">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="e4230-122">서비스에서 시작된 원격 끝점과의 최대 연결 수를 지정하는 양의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-122">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="e4230-123">이 제한을 초과하는 연결은 채널 수가 제한 아래로 내려갈 때까지 큐에 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-123">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="e4230-124">`idleTimeout`은 예외가 throw되기 전에 연결이 큐에 대기할 수 있는 시간을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-124">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="e4230-125">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-125">The default is 10.</span></span><br /><br /> <span data-ttu-id="e4230-126">이 특성은 클라이언트에서 특정 서비스 끝점으로의 동시 활성 연결 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-126">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="e4230-127">활성 클라이언트 연결 수가 이 값을 초과할 경우 해당 서비스가 클라이언트에 응답하지 않는 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-127">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="e4230-128">이러한 경우 이 값을 특정 끝점에 대해 예상되는 동시 클라이언트 최대 연결 수보다 크게 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-128">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4230-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e4230-129">Child Elements</span></span>  
 <span data-ttu-id="e4230-130">없음</span><span class="sxs-lookup"><span data-stu-id="e4230-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4230-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e4230-131">Parent Elements</span></span>  
  
|<span data-ttu-id="e4230-132">요소</span><span class="sxs-lookup"><span data-stu-id="e4230-132">Element</span></span>|<span data-ttu-id="e4230-133">설명</span><span class="sxs-lookup"><span data-stu-id="e4230-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4230-134">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="e4230-134">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="e4230-135">채널이 명명된 파이프를 사용하여 메시지를 전송하게 하는 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e4230-135">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4230-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4230-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="e4230-137">전송</span><span class="sxs-lookup"><span data-stu-id="e4230-137">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="e4230-138">전송 선택</span><span class="sxs-lookup"><span data-stu-id="e4230-138">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="e4230-139">바인딩</span><span class="sxs-lookup"><span data-stu-id="e4230-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e4230-140">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="e4230-140">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="e4230-141">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="e4230-141">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="e4230-142">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e4230-142">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
