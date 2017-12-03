---
title: '&lt;webSocketSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71ed2fc6e4e5407cdf8c3e2334dcc0c16a00cf83
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="ca293-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="ca293-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="ca293-103">WebSocket 설정을 지정하는 데 사용되는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="ca293-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ca293-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ca293-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="ca293-105">\<bindings></span></span>  
<span data-ttu-id="ca293-106">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="ca293-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca293-107">구문</span><span class="sxs-lookup"><span data-stu-id="ca293-107">Syntax</span></span>  
  
```xml  
<netHttpBinding>  
  <binding>   
    <webSocketSettings createNotificationOnConnection="boolean" 
                       disablePayloadMasking="boolean" 
                       keepAliveInterval="TimeSpan" 
                       maxPendingConnections="Integer" 
                       receiveBufferSize="Integer" 
                       sendBufferSize="Integer" 
                       subProtocol="String" 
                       transportUsage="WhenDuplex/Always/Never"/>
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca293-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ca293-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ca293-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca293-110">특성</span><span class="sxs-lookup"><span data-stu-id="ca293-110">Attributes</span></span>  
  
|<span data-ttu-id="ca293-111">특성</span><span class="sxs-lookup"><span data-stu-id="ca293-111">Attribute</span></span>|<span data-ttu-id="ca293-112">설명</span><span class="sxs-lookup"><span data-stu-id="ca293-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca293-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="ca293-113">createNotificationOnConnection</span></span>|<span data-ttu-id="ca293-114">연결 시 알림이 보내지는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="ca293-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="ca293-115">disablePayloadMasking</span></span>|<span data-ttu-id="ca293-116">WebSocket 마스킹을 사용하지 않도록 설정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="ca293-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="ca293-117">keepAliveInterval</span></span>|<span data-ttu-id="ca293-118">상태 유지 간격을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="ca293-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="ca293-119">maxPendingConnections</span></span>|<span data-ttu-id="ca293-120">서비스에서 디스패치를 대기하는 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="ca293-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="ca293-121">receiveBufferSize</span></span>|<span data-ttu-id="ca293-122">수신 버퍼의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="ca293-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="ca293-123">sendBufferSize</span></span>|<span data-ttu-id="ca293-124">전송 버퍼의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="ca293-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="ca293-125">subProtocol</span></span>|<span data-ttu-id="ca293-126">WebSocket 하위 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="ca293-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="ca293-127">transportUsage</span></span>|<span data-ttu-id="ca293-128">WebSocket을 사용할 시기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="ca293-129">transportUsage 특성</span><span class="sxs-lookup"><span data-stu-id="ca293-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="ca293-130">값</span><span class="sxs-lookup"><span data-stu-id="ca293-130">Value</span></span>|<span data-ttu-id="ca293-131">설명</span><span class="sxs-lookup"><span data-stu-id="ca293-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ca293-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="ca293-132">WhenDuplex</span></span>|<span data-ttu-id="ca293-133">이중 계약인 경우 WebSocket 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="ca293-134">Always</span><span class="sxs-lookup"><span data-stu-id="ca293-134">Always</span></span>|<span data-ttu-id="ca293-135">계약과 관계없이 항상 WebSocket 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="ca293-136">Never</span><span class="sxs-lookup"><span data-stu-id="ca293-136">Never</span></span>|<span data-ttu-id="ca293-137">WebSocket 프로토콜을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca293-138">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ca293-138">Child Elements</span></span>  
 <span data-ttu-id="ca293-139">없음</span><span class="sxs-lookup"><span data-stu-id="ca293-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca293-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ca293-140">Parent Elements</span></span>  
  
|<span data-ttu-id="ca293-141">요소</span><span class="sxs-lookup"><span data-stu-id="ca293-141">Element</span></span>|<span data-ttu-id="ca293-142">설명</span><span class="sxs-lookup"><span data-stu-id="ca293-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ca293-143">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="ca293-143">\<netHttpBinding></span></span>|<span data-ttu-id="ca293-144">NetHttpBinding을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ca293-145">예제</span><span class="sxs-lookup"><span data-stu-id="ca293-145">Example</span></span>  
 <span data-ttu-id="ca293-146">사용 하는 방법을 보여 주는 다음 예제는 \<webSocketSettings > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ca293-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>  
        <binding>  
          <webSocketSettings createNotificationOnConnection="true"  
                              disablePayloadMasking="false  
                              keepAliveInterval="00:10:00"  
                              maxPendingConnections="100"  
                              receiveBufferSize="1000"  
                              sendBufferSize="1000"  
                              subProtocol="Soap"  
                              transportUsage="WhenDuplex/Always/Never"/>  
  
        </binding>  
      </netHttpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca293-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca293-147">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="ca293-148">바인딩</span><span class="sxs-lookup"><span data-stu-id="ca293-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ca293-149">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="ca293-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="ca293-150">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="ca293-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="ca293-151">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="ca293-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
