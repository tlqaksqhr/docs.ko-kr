---
title: '&lt;pnrpPeerResolver&gt;'
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: f0874d38c3432f066d1bec5cc84f53e1f3730180
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747982"
---
# <a name="ltpnrppeerresolvergt"></a><span data-ttu-id="086b2-102">&lt;pnrpPeerResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="086b2-102">&lt;pnrpPeerResolver&gt;</span></span>
<span data-ttu-id="086b2-103">PNRP(피어 이름 확인 프로토콜)가 확인자로 사용되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="086b2-103">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="086b2-104">PNRP가 기본 확인자이므로 이 요소는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="086b2-104">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="086b2-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="086b2-105">\<system.serviceModel></span></span>  
<span data-ttu-id="086b2-106">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="086b2-106">\<bindings></span></span>  
<span data-ttu-id="086b2-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="086b2-107">\<customBinding></span></span>  
<span data-ttu-id="086b2-108">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="086b2-108">\<binding></span></span>  
<span data-ttu-id="086b2-109">\<pnrpResolver ></span><span class="sxs-lookup"><span data-stu-id="086b2-109">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="086b2-110">구문</span><span class="sxs-lookup"><span data-stu-id="086b2-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="086b2-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="086b2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="086b2-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="086b2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="086b2-113">특성</span><span class="sxs-lookup"><span data-stu-id="086b2-113">Attributes</span></span>  
  
|<span data-ttu-id="086b2-114">특성</span><span class="sxs-lookup"><span data-stu-id="086b2-114">Attribute</span></span>|<span data-ttu-id="086b2-115">설명</span><span class="sxs-lookup"><span data-stu-id="086b2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="086b2-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="086b2-116">resolverType</span></span>|<span data-ttu-id="086b2-117">사용할 확인자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="086b2-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="086b2-118">이 특성은 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="086b2-118">This attribute is optional.</span></span> <span data-ttu-id="086b2-119">이 특성을 설정하지 않거나 빈 문자열로 설정하면 PNRP가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="086b2-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="086b2-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="086b2-120">Child Elements</span></span>  
 <span data-ttu-id="086b2-121">없음</span><span class="sxs-lookup"><span data-stu-id="086b2-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="086b2-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="086b2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="086b2-123">요소</span><span class="sxs-lookup"><span data-stu-id="086b2-123">Element</span></span>|<span data-ttu-id="086b2-124">설명</span><span class="sxs-lookup"><span data-stu-id="086b2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="086b2-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="086b2-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="086b2-126">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="086b2-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="086b2-127">예제</span><span class="sxs-lookup"><span data-stu-id="086b2-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="086b2-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="086b2-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>  
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="086b2-129">바인딩</span><span class="sxs-lookup"><span data-stu-id="086b2-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="086b2-130">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="086b2-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="086b2-131">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="086b2-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="086b2-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="086b2-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="086b2-133">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="086b2-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
