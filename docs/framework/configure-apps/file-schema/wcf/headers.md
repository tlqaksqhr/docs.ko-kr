---
title: "&lt;헤더&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bcc81c0dd0628a6c5cab93841665b416f18a5bff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltheadersgt"></a><span data-ttu-id="68a7f-102">&lt;헤더&gt;</span><span class="sxs-lookup"><span data-stu-id="68a7f-102">&lt;headers&gt;</span></span>
<span data-ttu-id="68a7f-103">하나 이상의 SOAP 헤더와 해당 기본 URI로 끝점에 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a7f-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="68a7f-104">이 유용한 하나의 시나리오 집합이 SOAP 매개 시나리오 집합입니다. 이 시나리오 집합에서는 끝점에 매개자를 대상으로 한 SOAP 헤더를 포함할 해당 끝점의 클라이언트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="68a7f-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="68a7f-105">이 구성 요소는 그러한 사용자 지정 주소 헤더를 정의하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a7f-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="68a7f-106">끝점 헤더 컬렉션의 항목은 사용자 정의 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="68a7f-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="68a7f-107">각 요소는 올바른 형식의 XML이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a7f-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="68a7f-108">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="68a7f-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="68a7f-109">\<클라이언트 ></span><span class="sxs-lookup"><span data-stu-id="68a7f-109">\<client></span></span>  
<span data-ttu-id="68a7f-110">\<끝점 ></span><span class="sxs-lookup"><span data-stu-id="68a7f-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68a7f-111">구문</span><span class="sxs-lookup"><span data-stu-id="68a7f-111">Syntax</span></span>  
  
```xml  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68a7f-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="68a7f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="68a7f-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68a7f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68a7f-114">특성</span><span class="sxs-lookup"><span data-stu-id="68a7f-114">Attributes</span></span>  
 <span data-ttu-id="68a7f-115">없음</span><span class="sxs-lookup"><span data-stu-id="68a7f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="68a7f-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="68a7f-116">Child Elements</span></span>  
  
|<span data-ttu-id="68a7f-117">요소</span><span class="sxs-lookup"><span data-stu-id="68a7f-117">Element</span></span>|<span data-ttu-id="68a7f-118">설명</span><span class="sxs-lookup"><span data-stu-id="68a7f-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="68a7f-119">Region</span><span class="sxs-lookup"><span data-stu-id="68a7f-119">Region</span></span>||  
|<span data-ttu-id="68a7f-120">멤버</span><span class="sxs-lookup"><span data-stu-id="68a7f-120">Member</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="68a7f-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="68a7f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="68a7f-122">요소</span><span class="sxs-lookup"><span data-stu-id="68a7f-122">Element</span></span>|<span data-ttu-id="68a7f-123">설명</span><span class="sxs-lookup"><span data-stu-id="68a7f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68a7f-124">\<끝점 ></span><span class="sxs-lookup"><span data-stu-id="68a7f-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="68a7f-125">다양한 형식의 끝점을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="68a7f-125">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68a7f-126">설명</span><span class="sxs-lookup"><span data-stu-id="68a7f-126">Remarks</span></span>  
 <span data-ttu-id="68a7f-127">선택적 헤더는 끝점을 확인하거나 상호 작용하는 데 필요한 자세한 주소 지정 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="68a7f-127">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="68a7f-128">예를 들어 헤더는 들어오는 메시지를 처리하는 방법, 끝점이 회신 메시지를 보내야 하는 위치 또는 여러 인스턴스를 사용할 수 있는 경우 특정 사용자의 들어오는 메시지를 처리하는 데 사용할 서비스 인스턴스를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a7f-128">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a7f-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68a7f-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [<span data-ttu-id="68a7f-130">끝점: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="68a7f-130">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
