---
title: '&lt;pnrpPeerResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 223a66dd21305a4cbb6bb434f553e821037e7cb0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltpnrppeerresolvergt"></a><span data-ttu-id="8941a-102">&lt;pnrpPeerResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="8941a-102">&lt;pnrpPeerResolver&gt;</span></span>
<span data-ttu-id="8941a-103">PNRP(피어 이름 확인 프로토콜)가 확인자로 사용되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8941a-103">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="8941a-104">PNRP가 기본 확인자이므로 이 요소는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="8941a-104">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="8941a-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8941a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="8941a-106">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="8941a-106">\<bindings></span></span>  
<span data-ttu-id="8941a-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8941a-107">\<customBinding></span></span>  
<span data-ttu-id="8941a-108">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="8941a-108">\<binding></span></span>  
<span data-ttu-id="8941a-109">\<pnrpResolver ></span><span class="sxs-lookup"><span data-stu-id="8941a-109">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8941a-110">구문</span><span class="sxs-lookup"><span data-stu-id="8941a-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8941a-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8941a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8941a-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8941a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8941a-113">특성</span><span class="sxs-lookup"><span data-stu-id="8941a-113">Attributes</span></span>  
  
|<span data-ttu-id="8941a-114">특성</span><span class="sxs-lookup"><span data-stu-id="8941a-114">Attribute</span></span>|<span data-ttu-id="8941a-115">설명</span><span class="sxs-lookup"><span data-stu-id="8941a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8941a-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="8941a-116">resolverType</span></span>|<span data-ttu-id="8941a-117">사용할 확인자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8941a-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="8941a-118">이 특성은 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8941a-118">This attribute is optional.</span></span> <span data-ttu-id="8941a-119">이 특성을 설정하지 않거나 빈 문자열로 설정하면 PNRP가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8941a-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8941a-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8941a-120">Child Elements</span></span>  
 <span data-ttu-id="8941a-121">없음</span><span class="sxs-lookup"><span data-stu-id="8941a-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8941a-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8941a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8941a-123">요소</span><span class="sxs-lookup"><span data-stu-id="8941a-123">Element</span></span>|<span data-ttu-id="8941a-124">설명</span><span class="sxs-lookup"><span data-stu-id="8941a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8941a-125">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="8941a-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8941a-126">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8941a-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8941a-127">예제</span><span class="sxs-lookup"><span data-stu-id="8941a-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="8941a-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8941a-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>  
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="8941a-129">바인딩</span><span class="sxs-lookup"><span data-stu-id="8941a-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8941a-130">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="8941a-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="8941a-131">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="8941a-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="8941a-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8941a-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="8941a-133">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="8941a-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
