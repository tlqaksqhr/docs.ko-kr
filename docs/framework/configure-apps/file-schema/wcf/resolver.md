---
title: "&lt;해결 프로그램&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5734a985c4941a12be5032c254a75987f2074da6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltresolvergt"></a><span data-ttu-id="14305-102">&lt;해결 프로그램&gt;</span><span class="sxs-lookup"><span data-stu-id="14305-102">&lt;resolver&gt;</span></span>
<span data-ttu-id="14305-103">피어 메시 ID를 확인하는 데 사용되는 피어 확인자를 메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14305-103">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="14305-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="14305-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="14305-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="14305-105">\<bindings></span></span>  
<span data-ttu-id="14305-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="14305-106">\<netPeerBinding></span></span>  
<span data-ttu-id="14305-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="14305-107">\<binding></span></span>  
<span data-ttu-id="14305-108">\<해결 프로그램 ></span><span class="sxs-lookup"><span data-stu-id="14305-108">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14305-109">구문</span><span class="sxs-lookup"><span data-stu-id="14305-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14305-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="14305-110">Attributes and Elements</span></span>  
 <span data-ttu-id="14305-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14305-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14305-112">특성</span><span class="sxs-lookup"><span data-stu-id="14305-112">Attributes</span></span>  
  
|<span data-ttu-id="14305-113">특성</span><span class="sxs-lookup"><span data-stu-id="14305-113">Attribute</span></span>|<span data-ttu-id="14305-114">설명</span><span class="sxs-lookup"><span data-stu-id="14305-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="14305-115">이 서비스와 연결된 피어 확인자 인스턴스가 PNRP 관련 사용자 지정 확인자인지 아니면 자동으로 결정되는지 여부를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="14305-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="14305-116">이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerResolverMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="14305-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="14305-117">피어 간에 조회를 공유하는 방법을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="14305-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="14305-118">이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="14305-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14305-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="14305-119">Child Elements</span></span>  
  
|<span data-ttu-id="14305-120">요소</span><span class="sxs-lookup"><span data-stu-id="14305-120">Element</span></span>|<span data-ttu-id="14305-121">설명</span><span class="sxs-lookup"><span data-stu-id="14305-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14305-122">\<헤더 ></span><span class="sxs-lookup"><span data-stu-id="14305-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="14305-123">사용자 지정 피어 확인자 서비스의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14305-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14305-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="14305-124">Parent Elements</span></span>  
  
|<span data-ttu-id="14305-125">요소</span><span class="sxs-lookup"><span data-stu-id="14305-125">Element</span></span>|<span data-ttu-id="14305-126">설명</span><span class="sxs-lookup"><span data-stu-id="14305-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14305-127">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="14305-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="14305-128">모든 바인딩 기능을 정의 [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="14305-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14305-129">설명</span><span class="sxs-lookup"><span data-stu-id="14305-129">Remarks</span></span>  
 <span data-ttu-id="14305-130">피어 이름 확인자는 피어 메시에 참여하는 피어 노드를 찾기 위해 피어 채널에서 사용하는 검색 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="14305-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="14305-131">또한 이 확인자는 피어 노드가 알려지고 피어 메시에서 사용할 수 있게 되는 메커니즘인 피어 메시를 통해 노드를 "등록"하는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14305-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="14305-132">피어 확인자에 대 한 자세한 내용은 참조 하십시오. [피어 확인 자의](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="14305-132">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14305-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14305-133">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [<span data-ttu-id="14305-134">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="14305-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="14305-135">Peerchannel은 응용 프로그램에 사용자 지정 해결 프로그램 추가</span><span class="sxs-lookup"><span data-stu-id="14305-135">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419)
