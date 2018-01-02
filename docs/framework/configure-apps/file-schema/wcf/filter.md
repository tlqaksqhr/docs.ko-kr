---
title: "&lt;필터&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 186c511cd8a69cef5e30e369641628a10a0972d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltergt"></a><span data-ttu-id="f54f7-102">&lt;필터&gt;</span><span class="sxs-lookup"><span data-stu-id="f54f7-102">&lt;filter&gt;</span></span>

<span data-ttu-id="f54f7-103">들어오는 메시지를 평가할 때 사용되는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter>의 형식 및 해당 필터에 필요한 지원 데이터나 매개 변수를 결정하는 라우팅 필터를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f54f7-103">Defines a routing filter, which determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="f54f7-104">\<system.serviceModel > \<라우팅 > \<필터 > \<필터 ></span><span class="sxs-lookup"><span data-stu-id="f54f7-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>

## <a name="syntax"></a><span data-ttu-id="f54f7-105">구문</span><span class="sxs-lookup"><span data-stu-id="f54f7-105">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="f54f7-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f54f7-106">Attributes and elements</span></span>

<span data-ttu-id="f54f7-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f54f7-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f54f7-108">특성</span><span class="sxs-lookup"><span data-stu-id="f54f7-108">Attributes</span></span>

| <span data-ttu-id="f54f7-109">특성</span><span class="sxs-lookup"><span data-stu-id="f54f7-109">Attribute</span></span>  | <span data-ttu-id="f54f7-110">설명</span><span class="sxs-lookup"><span data-stu-id="f54f7-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="f54f7-111">customType</span><span class="sxs-lookup"><span data-stu-id="f54f7-111">customType</span></span> | <span data-ttu-id="f54f7-112">필터로 사용할 사용자 지정 형식의 정규화된 형식 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f54f7-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="f54f7-113">경우 `filterType` 로 설정 된 `custom`,이 특성 만들 클래스의 정규화 된 형식 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f54f7-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="f54f7-114">`filterData`사용자 지정 형식 필터 평가 중에 사용할 값을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f54f7-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="f54f7-115">filterData</span><span class="sxs-lookup"><span data-stu-id="f54f7-115">filterData</span></span> | <span data-ttu-id="f54f7-116">필터 데이터를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f54f7-116">A string containing the filter data.</span></span> <span data-ttu-id="f54f7-117">이 특성을 지정하는 방법에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f54f7-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="f54f7-118">filterType</span><span class="sxs-lookup"><span data-stu-id="f54f7-118">filterType</span></span> | <span data-ttu-id="f54f7-119">필터 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f54f7-119">A string containing the filter type.</span></span> <span data-ttu-id="f54f7-120">이 특성은 <xref:System.ServiceModel.Routing.Configuration.FilterType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f54f7-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="f54f7-121">`filterData` 특성에서 이 형식이 어떻게 작동하는지에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f54f7-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="f54f7-122">name</span><span class="sxs-lookup"><span data-stu-id="f54f7-122">name</span></span>       | <span data-ttu-id="f54f7-123">이 필터 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f54f7-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="f54f7-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f54f7-124">Child elements</span></span>

<span data-ttu-id="f54f7-125">없음</span><span class="sxs-lookup"><span data-stu-id="f54f7-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f54f7-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f54f7-126">Parent elements</span></span>

| <span data-ttu-id="f54f7-127">요소</span><span class="sxs-lookup"><span data-stu-id="f54f7-127">Element</span></span> | <span data-ttu-id="f54f7-128">설명</span><span class="sxs-lookup"><span data-stu-id="f54f7-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="f54f7-129">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="f54f7-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="f54f7-130">들어오는 메시지를 평가할 때 사용되는 [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> 형식을 결정하는 라우팅 필터 집합을 정의하기 위한 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="f54f7-130">A configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f54f7-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f54f7-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
