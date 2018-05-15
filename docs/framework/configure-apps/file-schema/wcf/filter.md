---
title: '&lt;필터&gt;'
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 93d47fc6b25a75eedae43cd70582abc863a74e6c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltergt"></a><span data-ttu-id="4fed2-102">&lt;필터&gt;</span><span class="sxs-lookup"><span data-stu-id="4fed2-102">&lt;filter&gt;</span></span>

<span data-ttu-id="4fed2-103">Windows Communication Foundation (WCF)의 유형을 결정 하는 라우팅 필터를 정의<xref:System.ServiceModel.Dispatcher.MessageFilter> 잘 지원 데이터 나 매개 변수에 해당 필터에 필요한로 들어오는 메시지를 평가할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fed2-103">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="4fed2-104">\<system.serviceModel > \<라우팅 > \<필터 > \<필터 ></span><span class="sxs-lookup"><span data-stu-id="4fed2-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>

## <a name="syntax"></a><span data-ttu-id="4fed2-105">구문</span><span class="sxs-lookup"><span data-stu-id="4fed2-105">Syntax</span></span>

```xml
<routing>
  <filters>
    <filter customType="String" 
            filterData="String" 
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
            name="String" />
  </filters>
</routing>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4fed2-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4fed2-106">Attributes and elements</span></span>

<span data-ttu-id="4fed2-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4fed2-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4fed2-108">특성</span><span class="sxs-lookup"><span data-stu-id="4fed2-108">Attributes</span></span>

| <span data-ttu-id="4fed2-109">특성</span><span class="sxs-lookup"><span data-stu-id="4fed2-109">Attribute</span></span>  | <span data-ttu-id="4fed2-110">설명</span><span class="sxs-lookup"><span data-stu-id="4fed2-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="4fed2-111">customType</span><span class="sxs-lookup"><span data-stu-id="4fed2-111">customType</span></span> | <span data-ttu-id="4fed2-112">필터로 사용할 사용자 지정 형식의 정규화된 형식 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4fed2-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="4fed2-113">경우 `filterType` 로 설정 된 `custom`,이 특성 만들 클래스의 정규화 된 형식 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fed2-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="4fed2-114">`filterData` 사용자 지정 형식 필터 평가 중에 사용할 값을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fed2-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="4fed2-115">filterData</span><span class="sxs-lookup"><span data-stu-id="4fed2-115">filterData</span></span> | <span data-ttu-id="4fed2-116">필터 데이터를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4fed2-116">A string containing the filter data.</span></span> <span data-ttu-id="4fed2-117">이 특성을 지정하는 방법에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fed2-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="4fed2-118">filterType</span><span class="sxs-lookup"><span data-stu-id="4fed2-118">filterType</span></span> | <span data-ttu-id="4fed2-119">필터 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4fed2-119">A string containing the filter type.</span></span> <span data-ttu-id="4fed2-120">이 특성은 <xref:System.ServiceModel.Routing.Configuration.FilterType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4fed2-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="4fed2-121">`filterData` 특성에서 이 형식이 어떻게 작동하는지에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fed2-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="4fed2-122">name</span><span class="sxs-lookup"><span data-stu-id="4fed2-122">name</span></span>       | <span data-ttu-id="4fed2-123">이 필터 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4fed2-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="4fed2-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4fed2-124">Child elements</span></span>

<span data-ttu-id="4fed2-125">없음</span><span class="sxs-lookup"><span data-stu-id="4fed2-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4fed2-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4fed2-126">Parent elements</span></span>

| <span data-ttu-id="4fed2-127">요소</span><span class="sxs-lookup"><span data-stu-id="4fed2-127">Element</span></span> | <span data-ttu-id="4fed2-128">설명</span><span class="sxs-lookup"><span data-stu-id="4fed2-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="4fed2-129">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="4fed2-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="4fed2-130">Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션<xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fed2-130">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4fed2-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="4fed2-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
