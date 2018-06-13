---
title: '&lt;이벤트&gt; 요소(.NET 네이티브)'
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7ccf013398420dbeb7918f99baa922aa1bc89db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395556"
---
# <a name="lteventgt-element-net-native"></a><span data-ttu-id="4e611-102">&lt;이벤트&gt; 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="4e611-102">&lt;Event&gt; Element (.NET Native)</span></span>
<span data-ttu-id="4e611-103">런타임 리플렉션 정책을 이벤트에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e611-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e611-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e611-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4e611-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4e611-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e611-107">특성</span><span class="sxs-lookup"><span data-stu-id="4e611-107">Attributes</span></span>  
  
|<span data-ttu-id="4e611-108">특성</span><span class="sxs-lookup"><span data-stu-id="4e611-108">Attribute</span></span>|<span data-ttu-id="4e611-109">특성 형식</span><span class="sxs-lookup"><span data-stu-id="4e611-109">Attribute type</span></span>|<span data-ttu-id="4e611-110">설명</span><span class="sxs-lookup"><span data-stu-id="4e611-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="4e611-111">일반</span><span class="sxs-lookup"><span data-stu-id="4e611-111">General</span></span>|<span data-ttu-id="4e611-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-112">Required attribute.</span></span> <span data-ttu-id="4e611-113">이벤트 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="4e611-114">반사</span><span class="sxs-lookup"><span data-stu-id="4e611-114">Reflection</span></span>|<span data-ttu-id="4e611-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-115">Optional attribute.</span></span> <span data-ttu-id="4e611-116">이벤트에 대한 정보 쿼리 또는 이벤트 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="4e611-117">반사</span><span class="sxs-lookup"><span data-stu-id="4e611-117">Reflection</span></span>|<span data-ttu-id="4e611-118">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-118">Optional attribute.</span></span> <span data-ttu-id="4e611-119">동적 프로그래밍을 수행할 수 있도록 이벤트에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="4e611-120">이 정책을 사용하면 런타임에 이벤트를 동적으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="4e611-121">Name 특성</span><span class="sxs-lookup"><span data-stu-id="4e611-121">Name attribute</span></span>  
  
|<span data-ttu-id="4e611-122">값</span><span class="sxs-lookup"><span data-stu-id="4e611-122">Value</span></span>|<span data-ttu-id="4e611-123">설명</span><span class="sxs-lookup"><span data-stu-id="4e611-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4e611-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="4e611-124">*method_name*</span></span>|<span data-ttu-id="4e611-125">이벤트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-125">The event name.</span></span> <span data-ttu-id="4e611-126">이벤트의 형식은 부모 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 또는 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-126">The type of the event is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="4e611-127">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="4e611-127">All other attributes</span></span>  
  
|<span data-ttu-id="4e611-128">값</span><span class="sxs-lookup"><span data-stu-id="4e611-128">Value</span></span>|<span data-ttu-id="4e611-129">설명</span><span class="sxs-lookup"><span data-stu-id="4e611-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4e611-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="4e611-130">*policy_setting*</span></span>|<span data-ttu-id="4e611-131">이벤트에 대해 이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="4e611-132">가능한 값은 `Auto`, `Excluded`, `Included` 및 `Required`입니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="4e611-133">자세한 내용은 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e611-133">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e611-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4e611-134">Child Elements</span></span>  
 <span data-ttu-id="4e611-135">없음</span><span class="sxs-lookup"><span data-stu-id="4e611-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e611-136">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4e611-136">Parent Elements</span></span>  
  
|<span data-ttu-id="4e611-137">요소</span><span class="sxs-lookup"><span data-stu-id="4e611-137">Element</span></span>|<span data-ttu-id="4e611-138">설명</span><span class="sxs-lookup"><span data-stu-id="4e611-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e611-139">\<Type></span><span class="sxs-lookup"><span data-stu-id="4e611-139">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="4e611-140">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-140">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="4e611-141">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="4e611-141">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="4e611-142">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-142">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e611-143">설명</span><span class="sxs-lookup"><span data-stu-id="4e611-143">Remarks</span></span>  
 <span data-ttu-id="4e611-144">이벤트의 정책이 명시적으로 정의되어 있지 않으면 부모 요소의 런타임 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="4e611-144">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e611-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e611-145">See Also</span></span>  
 [<span data-ttu-id="4e611-146">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="4e611-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="4e611-147">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="4e611-147">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="4e611-148">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="4e611-148">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
