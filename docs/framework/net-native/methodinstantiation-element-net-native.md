---
title: '&lt;MethodInstantiation&gt; 요소(.NET 네이티브)'
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d741e8df8f2b8c6d90a1d867c73495a2ffd1304
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397795"
---
# <a name="ltmethodinstantiationgt-element-net-native"></a><span data-ttu-id="93945-102">&lt;MethodInstantiation&gt; 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="93945-102">&lt;MethodInstantiation&gt; Element (.NET Native)</span></span>
<span data-ttu-id="93945-103">생성된 제네릭 메서드에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-103">Applies runtime reflection policy to a constructed generic method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93945-104">구문</span><span class="sxs-lookup"><span data-stu-id="93945-104">Syntax</span></span>  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93945-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="93945-105">Attributes and Elements</span></span>  
 <span data-ttu-id="93945-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93945-107">특성</span><span class="sxs-lookup"><span data-stu-id="93945-107">Attributes</span></span>  
  
|<span data-ttu-id="93945-108">특성</span><span class="sxs-lookup"><span data-stu-id="93945-108">Attribute</span></span>|<span data-ttu-id="93945-109">특성 형식</span><span class="sxs-lookup"><span data-stu-id="93945-109">Attribute type</span></span>|<span data-ttu-id="93945-110">설명</span><span class="sxs-lookup"><span data-stu-id="93945-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="93945-111">일반</span><span class="sxs-lookup"><span data-stu-id="93945-111">General</span></span>|<span data-ttu-id="93945-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="93945-112">Required attribute.</span></span> <span data-ttu-id="93945-113">메서드 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="93945-114">일반</span><span class="sxs-lookup"><span data-stu-id="93945-114">General</span></span>|<span data-ttu-id="93945-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="93945-115">Optional attribute.</span></span> <span data-ttu-id="93945-116">메서드의 명명된 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-116">Specifies named parameters of the method.</span></span> <span data-ttu-id="93945-117">명명된 매개 변수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-117">Multiple named parameters are separated by commas.</span></span> <span data-ttu-id="93945-118">`Signature` 특성은 오버로드된 메서드를 구별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93945-118">The `Signature` attribute is used to differentiate overloaded methods.</span></span>|  
|`Arguments`|<span data-ttu-id="93945-119">일반</span><span class="sxs-lookup"><span data-stu-id="93945-119">General</span></span>|<span data-ttu-id="93945-120">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="93945-120">Required attribute.</span></span> <span data-ttu-id="93945-121">제네릭 형식 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-121">Specifies the generic type arguments.</span></span> <span data-ttu-id="93945-122">인수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-122">If multiple arguments are present, they are separated by commas.</span></span>|  
|`Browse`|<span data-ttu-id="93945-123">반사</span><span class="sxs-lookup"><span data-stu-id="93945-123">Reflection</span></span>|<span data-ttu-id="93945-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="93945-124">Optional attribute.</span></span> <span data-ttu-id="93945-125">메서드에 대한 정보 쿼리 또는 메서드 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93945-125">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="93945-126">반사</span><span class="sxs-lookup"><span data-stu-id="93945-126">Reflection</span></span>|<span data-ttu-id="93945-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="93945-127">Optional attribute.</span></span> <span data-ttu-id="93945-128">동적 프로그래밍을 수행할 수 있도록 생성자 또는 메서드에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-128">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="93945-129">이 정책을 사용하면 런타임에 멤버를 동적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93945-129">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="93945-130">Name 특성</span><span class="sxs-lookup"><span data-stu-id="93945-130">Name attribute</span></span>  
  
|<span data-ttu-id="93945-131">값</span><span class="sxs-lookup"><span data-stu-id="93945-131">Value</span></span>|<span data-ttu-id="93945-132">설명</span><span class="sxs-lookup"><span data-stu-id="93945-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93945-133">*method_name*</span><span class="sxs-lookup"><span data-stu-id="93945-133">*method_name*</span></span>|<span data-ttu-id="93945-134">메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93945-134">The method name.</span></span> <span data-ttu-id="93945-135">메서드의 형식은 부모 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 또는 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="93945-135">The type of the method is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="93945-136">시그니처 특성</span><span class="sxs-lookup"><span data-stu-id="93945-136">Signature attribute</span></span>  
  
|<span data-ttu-id="93945-137">값</span><span class="sxs-lookup"><span data-stu-id="93945-137">Value</span></span>|<span data-ttu-id="93945-138">설명</span><span class="sxs-lookup"><span data-stu-id="93945-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93945-139">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="93945-139">*method_signature*</span></span>|<span data-ttu-id="93945-140">메서드의 명명된 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-140">Specifies the named parameters of the method.</span></span> <span data-ttu-id="93945-141">매개 변수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-141">If multiple parameters are present, they are separated by commas.</span></span>|  
  
## <a name="arguments-attribute"></a><span data-ttu-id="93945-142">인수 특성</span><span class="sxs-lookup"><span data-stu-id="93945-142">Arguments attribute</span></span>  
  
|<span data-ttu-id="93945-143">값</span><span class="sxs-lookup"><span data-stu-id="93945-143">Value</span></span>|<span data-ttu-id="93945-144">설명</span><span class="sxs-lookup"><span data-stu-id="93945-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93945-145">*method_arguments*</span><span class="sxs-lookup"><span data-stu-id="93945-145">*method_arguments*</span></span>|<span data-ttu-id="93945-146">제네릭 형식 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-146">Specifies the generic type arguments.</span></span> <span data-ttu-id="93945-147">인수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-147">If multiple arguments are present, they are separated by commas.</span></span> <span data-ttu-id="93945-148">각 인수는 정규화된 형식 이름으로 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-148">Each argument must consist of the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="93945-149">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="93945-149">All other attributes</span></span>  
  
|<span data-ttu-id="93945-150">값</span><span class="sxs-lookup"><span data-stu-id="93945-150">Value</span></span>|<span data-ttu-id="93945-151">설명</span><span class="sxs-lookup"><span data-stu-id="93945-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93945-152">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="93945-152">*policy_setting*</span></span>|<span data-ttu-id="93945-153">메서드에 대해 이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="93945-153">The setting to apply to this policy type for the method.</span></span> <span data-ttu-id="93945-154">가능한 값은 `Auto`, `Excluded`, `Included` 및 `Required`입니다.</span><span class="sxs-lookup"><span data-stu-id="93945-154">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="93945-155">자세한 내용은 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93945-155">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93945-156">자식 요소</span><span class="sxs-lookup"><span data-stu-id="93945-156">Child Elements</span></span>  
 <span data-ttu-id="93945-157">없음</span><span class="sxs-lookup"><span data-stu-id="93945-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93945-158">부모 요소</span><span class="sxs-lookup"><span data-stu-id="93945-158">Parent Elements</span></span>  
  
|<span data-ttu-id="93945-159">요소</span><span class="sxs-lookup"><span data-stu-id="93945-159">Element</span></span>|<span data-ttu-id="93945-160">설명</span><span class="sxs-lookup"><span data-stu-id="93945-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93945-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="93945-161">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="93945-162">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="93945-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="93945-163">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="93945-164">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93945-165">설명</span><span class="sxs-lookup"><span data-stu-id="93945-165">Remarks</span></span>  
 <span data-ttu-id="93945-166">`<MethodInstantiation>` 요소는 해당 개방형 제네릭 메서드의 런타임 리플렉션 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="93945-166">The `<MethodInstantiation>` element overrides the runtime reflection policy of its corresponding open generic method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93945-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93945-167">See Also</span></span>  
 [<span data-ttu-id="93945-168">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="93945-168">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="93945-169">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="93945-169">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="93945-170">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="93945-170">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="93945-171">\<Method> 요소</span><span class="sxs-lookup"><span data-stu-id="93945-171">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)
