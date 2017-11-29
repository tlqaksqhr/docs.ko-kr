---
title: "&lt;필드&gt; 요소(.NET 네이티브)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a3a928185146ac90ec4c3a905bf4f0e69e0e8d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltfieldgt-element-net-native"></a><span data-ttu-id="0d9e1-102">&lt;필드&gt; 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="0d9e1-102">&lt;Field&gt; Element (.NET Native)</span></span>
<span data-ttu-id="0d9e1-103">런타임 리플렉션 정책을 필드에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d9e1-104">구문</span><span class="sxs-lookup"><span data-stu-id="0d9e1-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d9e1-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0d9e1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0d9e1-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d9e1-107">특성</span><span class="sxs-lookup"><span data-stu-id="0d9e1-107">Attributes</span></span>  
  
|<span data-ttu-id="0d9e1-108">특성</span><span class="sxs-lookup"><span data-stu-id="0d9e1-108">Attribute</span></span>|<span data-ttu-id="0d9e1-109">특성 형식</span><span class="sxs-lookup"><span data-stu-id="0d9e1-109">Attribute type</span></span>|<span data-ttu-id="0d9e1-110">설명</span><span class="sxs-lookup"><span data-stu-id="0d9e1-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="0d9e1-111">일반</span><span class="sxs-lookup"><span data-stu-id="0d9e1-111">General</span></span>|<span data-ttu-id="0d9e1-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-112">Required attribute.</span></span> <span data-ttu-id="0d9e1-113">필드 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="0d9e1-114">반사</span><span class="sxs-lookup"><span data-stu-id="0d9e1-114">Reflection</span></span>|<span data-ttu-id="0d9e1-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-115">Optional attribute.</span></span> <span data-ttu-id="0d9e1-116">필드에 대한 정보 쿼리 또는 필드 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="0d9e1-117">반사</span><span class="sxs-lookup"><span data-stu-id="0d9e1-117">Reflection</span></span>|<span data-ttu-id="0d9e1-118">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-118">Optional attribute.</span></span> <span data-ttu-id="0d9e1-119">동적 프로그래밍을 수행할 수 있도록 필드에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="0d9e1-120">이 정책을 통해 런타임에 필드를 동적으로 설정하거나 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="0d9e1-121">Serialization</span><span class="sxs-lookup"><span data-stu-id="0d9e1-121">Serialization</span></span>|<span data-ttu-id="0d9e1-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-122">Optional attribute.</span></span> <span data-ttu-id="0d9e1-123">Newtonsoft JSON serializer 등의 라이브러리를 통해 형식 인스턴스를 serialize하거나 데이터 바인딩에 사용할 수 있도록 필드에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="0d9e1-124">Name 특성</span><span class="sxs-lookup"><span data-stu-id="0d9e1-124">Name attribute</span></span>  
  
|<span data-ttu-id="0d9e1-125">값</span><span class="sxs-lookup"><span data-stu-id="0d9e1-125">Value</span></span>|<span data-ttu-id="0d9e1-126">설명</span><span class="sxs-lookup"><span data-stu-id="0d9e1-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0d9e1-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="0d9e1-127">*method_name*</span></span>|<span data-ttu-id="0d9e1-128">필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-128">The field name.</span></span> <span data-ttu-id="0d9e1-129">필드의 형식은 부모 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 또는 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-129">The type of the field is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="0d9e1-130">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="0d9e1-130">All other attributes</span></span>  
  
|<span data-ttu-id="0d9e1-131">값</span><span class="sxs-lookup"><span data-stu-id="0d9e1-131">Value</span></span>|<span data-ttu-id="0d9e1-132">설명</span><span class="sxs-lookup"><span data-stu-id="0d9e1-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0d9e1-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="0d9e1-133">*policy_setting*</span></span>|<span data-ttu-id="0d9e1-134">필드에 대해 이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="0d9e1-135">가능한 값은 `Auto`, `Excluded`, `Included` 및 `Required`입니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="0d9e1-136">자세한 내용은 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d9e1-137">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0d9e1-137">Child Elements</span></span>  
 <span data-ttu-id="0d9e1-138">없음</span><span class="sxs-lookup"><span data-stu-id="0d9e1-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d9e1-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0d9e1-139">Parent Elements</span></span>  
  
|<span data-ttu-id="0d9e1-140">요소</span><span class="sxs-lookup"><span data-stu-id="0d9e1-140">Element</span></span>|<span data-ttu-id="0d9e1-141">설명</span><span class="sxs-lookup"><span data-stu-id="0d9e1-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d9e1-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="0d9e1-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="0d9e1-143">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="0d9e1-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="0d9e1-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="0d9e1-145">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d9e1-146">설명</span><span class="sxs-lookup"><span data-stu-id="0d9e1-146">Remarks</span></span>  
 <span data-ttu-id="0d9e1-147">필드의 정책이 명시적으로 정의되어 있지 않으면 부모 요소의 런타임 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="0d9e1-147">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d9e1-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d9e1-148">See Also</span></span>  
 [<span data-ttu-id="0d9e1-149">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="0d9e1-149">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="0d9e1-150">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="0d9e1-150">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="0d9e1-151">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0d9e1-151">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
