---
title: "&lt;MethodInstantiation&gt; 요소(.NET 네이티브)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c888bf806744c5c62d130ec00b89838c52f67d0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltmethodinstantiationgt-element-net-native"></a><span data-ttu-id="53512-102">&lt;MethodInstantiation&gt; 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="53512-102">&lt;MethodInstantiation&gt; Element (.NET Native)</span></span>
<span data-ttu-id="53512-103">생성된 제네릭 메서드에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53512-104">구문</span><span class="sxs-lookup"><span data-stu-id="53512-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53512-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="53512-105">Attributes and Elements</span></span>  
 <span data-ttu-id="53512-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53512-107">특성</span><span class="sxs-lookup"><span data-stu-id="53512-107">Attributes</span></span>  
  
|<span data-ttu-id="53512-108">특성</span><span class="sxs-lookup"><span data-stu-id="53512-108">Attribute</span></span>|<span data-ttu-id="53512-109">특성 형식</span><span class="sxs-lookup"><span data-stu-id="53512-109">Attribute type</span></span>|<span data-ttu-id="53512-110">설명</span><span class="sxs-lookup"><span data-stu-id="53512-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="53512-111">일반</span><span class="sxs-lookup"><span data-stu-id="53512-111">General</span></span>|<span data-ttu-id="53512-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="53512-112">Required attribute.</span></span> <span data-ttu-id="53512-113">메서드 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="53512-114">일반</span><span class="sxs-lookup"><span data-stu-id="53512-114">General</span></span>|<span data-ttu-id="53512-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="53512-115">Optional attribute.</span></span> <span data-ttu-id="53512-116">메서드의 명명된 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="53512-117">명명된 매개 변수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="53512-118">`Signature` 특성은 오버로드된 메서드를 구별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="53512-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="53512-119">일반</span><span class="sxs-lookup"><span data-stu-id="53512-119">General</span></span>|<span data-ttu-id="53512-120">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="53512-120">Required attribute.</span></span> <span data-ttu-id="53512-121">제네릭 형식 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="53512-122">인수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="53512-123">반사</span><span class="sxs-lookup"><span data-stu-id="53512-123">Reflection</span></span>|<span data-ttu-id="53512-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="53512-124">Optional attribute.</span></span> <span data-ttu-id="53512-125">메서드에 대한 정보 쿼리 또는 메서드 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53512-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="53512-126">반사</span><span class="sxs-lookup"><span data-stu-id="53512-126">Reflection</span></span>|<span data-ttu-id="53512-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="53512-127">Optional attribute.</span></span> <span data-ttu-id="53512-128">동적 프로그래밍을 수행할 수 있도록 생성자 또는 메서드에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="53512-129">이 정책을 사용하면 런타임에 멤버를 동적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53512-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="53512-130">Name 특성</span><span class="sxs-lookup"><span data-stu-id="53512-130">Name attribute</span></span>  
  
|<span data-ttu-id="53512-131">값</span><span class="sxs-lookup"><span data-stu-id="53512-131">Value</span></span>|<span data-ttu-id="53512-132">설명</span><span class="sxs-lookup"><span data-stu-id="53512-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53512-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="53512-133">*method_name*</span></span>|<span data-ttu-id="53512-134">메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="53512-134">The method name.</span></span> <span data-ttu-id="53512-135">메서드의 형식은 부모 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 또는 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="53512-135">The type of the method is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="53512-136">시그니처 특성</span><span class="sxs-lookup"><span data-stu-id="53512-136">Signature attribute</span></span>  
  
|<span data-ttu-id="53512-137">값</span><span class="sxs-lookup"><span data-stu-id="53512-137">Value</span></span>|<span data-ttu-id="53512-138">설명</span><span class="sxs-lookup"><span data-stu-id="53512-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53512-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="53512-139">*method_signature*</span></span>|<span data-ttu-id="53512-140">메서드의 명명된 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="53512-141">매개 변수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="53512-142">인수 특성</span><span class="sxs-lookup"><span data-stu-id="53512-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="53512-143">값</span><span class="sxs-lookup"><span data-stu-id="53512-143">Value</span></span>|<span data-ttu-id="53512-144">설명</span><span class="sxs-lookup"><span data-stu-id="53512-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53512-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="53512-145">*method_arguments*</span></span>|<span data-ttu-id="53512-146">제네릭 형식 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="53512-147">인수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="53512-148">각 인수는 정규화된 형식 이름으로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="53512-149">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="53512-149">All other attributes</span></span>  
  
|<span data-ttu-id="53512-150">값</span><span class="sxs-lookup"><span data-stu-id="53512-150">Value</span></span>|<span data-ttu-id="53512-151">설명</span><span class="sxs-lookup"><span data-stu-id="53512-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53512-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="53512-152">*policy_setting*</span></span>|<span data-ttu-id="53512-153">메서드에 대해 이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="53512-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="53512-154">가능한 값은 `Auto`, `Excluded`, `Included` 및 `Required`입니다.</span><span class="sxs-lookup"><span data-stu-id="53512-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="53512-155">자세한 내용은 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="53512-155">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53512-156">자식 요소</span><span class="sxs-lookup"><span data-stu-id="53512-156">Child Elements</span></span>  
 <span data-ttu-id="53512-157">없음</span><span class="sxs-lookup"><span data-stu-id="53512-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53512-158">부모 요소</span><span class="sxs-lookup"><span data-stu-id="53512-158">Parent Elements</span></span>  
  
|<span data-ttu-id="53512-159">요소</span><span class="sxs-lookup"><span data-stu-id="53512-159">Element</span></span>|<span data-ttu-id="53512-160">설명</span><span class="sxs-lookup"><span data-stu-id="53512-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53512-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="53512-161">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="53512-162">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="53512-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="53512-163">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="53512-164">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53512-165">설명</span><span class="sxs-lookup"><span data-stu-id="53512-165">Remarks</span></span>  
 <span data-ttu-id="53512-166">`<MethodInstantiation>` 요소는 해당 개방형 제네릭 메서드의 런타임 리플렉션 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="53512-166">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53512-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53512-167">See Also</span></span>  
 [<span data-ttu-id="53512-168">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="53512-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="53512-169">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="53512-169">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="53512-170">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="53512-170">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="53512-171">\<Method> 요소</span><span class="sxs-lookup"><span data-stu-id="53512-171">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
