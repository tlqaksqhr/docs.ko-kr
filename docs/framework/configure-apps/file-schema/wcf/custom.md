---
title: '&lt;custom&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ba9c8f6fa5bf574bdcaa9cb46b6c666e7117a9a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ltcustomgt"></a><span data-ttu-id="8e725-102">&lt;custom&gt;</span><span class="sxs-lookup"><span data-stu-id="8e725-102">&lt;custom&gt;</span></span>
<span data-ttu-id="8e725-103">사용자 지정 피어 확인자 서비스의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e725-103">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="8e725-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8e725-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8e725-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8e725-105">\<bindings></span></span>  
<span data-ttu-id="8e725-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="8e725-106">\<netPeerBinding></span></span>  
<span data-ttu-id="8e725-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="8e725-107">\<binding></span></span>  
<span data-ttu-id="8e725-108">\<resolver></span><span class="sxs-lookup"><span data-stu-id="8e725-108">\<resolver></span></span>  
<span data-ttu-id="8e725-109">\<custom></span><span class="sxs-lookup"><span data-stu-id="8e725-109">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e725-110">구문</span><span class="sxs-lookup"><span data-stu-id="8e725-110">Syntax</span></span>  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e725-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8e725-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8e725-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8e725-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e725-113">특성</span><span class="sxs-lookup"><span data-stu-id="8e725-113">Attributes</span></span>  
  
|<span data-ttu-id="8e725-114">특성</span><span class="sxs-lookup"><span data-stu-id="8e725-114">Attribute</span></span>|<span data-ttu-id="8e725-115">설명</span><span class="sxs-lookup"><span data-stu-id="8e725-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="8e725-116">사용자 지정 피어 확인자 서비스를 호스트하는 피어 노드의 끝점 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="8e725-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="8e725-117">사용자 지정 피어 확인자 서비스의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8e725-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e725-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8e725-118">Child Elements</span></span>  
  
|<span data-ttu-id="8e725-119">요소</span><span class="sxs-lookup"><span data-stu-id="8e725-119">Element</span></span>|<span data-ttu-id="8e725-120">설명</span><span class="sxs-lookup"><span data-stu-id="8e725-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e725-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="8e725-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="8e725-122">이 요소로 구성된 사용자 지정 피어 확인자의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e725-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="8e725-123">이 요소는 <xref:System.ServiceModel.Configuration.IdentityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8e725-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="8e725-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="8e725-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="8e725-125">사용자 지정 피어 확인자에서 처리하는 SOAP 메시지에 사용되는 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8e725-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8e725-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8e725-126">Parent Elements</span></span>  
  
|<span data-ttu-id="8e725-127">요소</span><span class="sxs-lookup"><span data-stu-id="8e725-127">Element</span></span>|<span data-ttu-id="8e725-128">설명</span><span class="sxs-lookup"><span data-stu-id="8e725-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e725-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="8e725-129">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="8e725-130">메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 대한 피어 메시 ID를 확인하는 데 사용되는 피어 확인자입니다.</span><span class="sxs-lookup"><span data-stu-id="8e725-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e725-131">설명</span><span class="sxs-lookup"><span data-stu-id="8e725-131">Remarks</span></span>  
 <span data-ttu-id="8e725-132">이 요소는 서비스를 호스트하는 피어의 끝점 주소 및 모든 특정 바인딩 설정을 포함하여 사용자 지정 피어 확인자 서비스에 대한 기본 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8e725-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="8e725-133">사용자 지정 해결 프로그램을 만드는 방법에 대 한 자세한 내용은 참조 하십시오. [PeerChannel 응용 프로그램에 사용자 지정 해결 프로그램을 추가](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e725-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e725-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e725-134">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [<span data-ttu-id="8e725-135">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="8e725-135">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="8e725-136">Peerchannel은 응용 프로그램에 사용자 지정 해결 프로그램 추가</span><span class="sxs-lookup"><span data-stu-id="8e725-136">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
