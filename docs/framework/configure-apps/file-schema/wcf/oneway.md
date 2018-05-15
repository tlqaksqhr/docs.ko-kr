---
title: '&lt;oneWay&gt;'
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: f9a5631501b3879463606f526485314efd5eff2b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltonewaygt"></a><span data-ttu-id="fa105-102">&lt;oneWay&gt;</span><span class="sxs-lookup"><span data-stu-id="fa105-102">&lt;oneWay&gt;</span></span>
<span data-ttu-id="fa105-103">사용자 지정 바인딩에 대한 패킷 라우팅 및 단방향 메서드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa105-103">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="fa105-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fa105-104">\<system.serviceModel></span></span>  
<span data-ttu-id="fa105-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="fa105-105">\<bindings></span></span>  
<span data-ttu-id="fa105-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="fa105-106">\<customBinding></span></span>  
<span data-ttu-id="fa105-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="fa105-107">\<binding></span></span>  
<span data-ttu-id="fa105-108">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="fa105-108">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa105-109">구문</span><span class="sxs-lookup"><span data-stu-id="fa105-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">  
        <channelPoolSettings  
           idleTimeout"TimeSpan"  
          leaseTimeout"TimeSpan"  
          maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
```xml  
</oneWay>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa105-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fa105-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fa105-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa105-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa105-112">특성</span><span class="sxs-lookup"><span data-stu-id="fa105-112">Attributes</span></span>  
  
|<span data-ttu-id="fa105-113">특성</span><span class="sxs-lookup"><span data-stu-id="fa105-113">Attribute</span></span>|<span data-ttu-id="fa105-114">설명</span><span class="sxs-lookup"><span data-stu-id="fa105-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="fa105-115">패킷 라우팅 활성화 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fa105-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="fa105-116">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="fa105-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="fa105-117">수락할 수 있는 최대 채널 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="fa105-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa105-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fa105-118">Child Elements</span></span>  
  
|<span data-ttu-id="fa105-119">요소</span><span class="sxs-lookup"><span data-stu-id="fa105-119">Element</span></span>|<span data-ttu-id="fa105-120">설명</span><span class="sxs-lookup"><span data-stu-id="fa105-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa105-121">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="fa105-121">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="fa105-122">현재 채널의 채널 풀 속성을 포함하는 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fa105-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa105-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fa105-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fa105-124">요소</span><span class="sxs-lookup"><span data-stu-id="fa105-124">Element</span></span>|<span data-ttu-id="fa105-125">설명</span><span class="sxs-lookup"><span data-stu-id="fa105-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa105-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="fa105-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="fa105-127">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fa105-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa105-128">설명</span><span class="sxs-lookup"><span data-stu-id="fa105-128">Remarks</span></span>  
 <span data-ttu-id="fa105-129">패킷 라우팅을 사용하려면 이 요소에서 제공하는 단방향 변환 계층이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fa105-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="fa105-130">사용자는 세션 인식 또는 요청-회신 전송을 통해 이 바인딩을 계층화하여 패킷 라우팅이 가능한 사용자 지정 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa105-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="fa105-131">이 요소는 원래의 방식으로 단방향 메서드를 노출하려는 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa105-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="fa105-132">복합 이중, 신뢰할 수 있는 메시징 등과 같은 많은 변형을 이 계층에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa105-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa105-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa105-133">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>  
 <xref:System.ServiceModel.Configuration.OneWayElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="fa105-134">바인딩</span><span class="sxs-lookup"><span data-stu-id="fa105-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fa105-135">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="fa105-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="fa105-136">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="fa105-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="fa105-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="fa105-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
