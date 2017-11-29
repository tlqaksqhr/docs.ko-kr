---
title: "&lt;매개 변수&gt; 요소(.NET 네이티브)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f603f795682c7ea1f48e5d9356af6e0477246da1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltparametergt-element-net-native"></a><span data-ttu-id="b170f-102">&lt;매개 변수&gt; 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="b170f-102">&lt;Parameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="b170f-103">메서드에 전달된 인수의 형식에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b170f-104">구문</span><span class="sxs-lookup"><span data-stu-id="b170f-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b170f-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b170f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b170f-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b170f-107">특성</span><span class="sxs-lookup"><span data-stu-id="b170f-107">Attributes</span></span>  
  
|<span data-ttu-id="b170f-108">특성</span><span class="sxs-lookup"><span data-stu-id="b170f-108">Attribute</span></span>|<span data-ttu-id="b170f-109">특성 형식</span><span class="sxs-lookup"><span data-stu-id="b170f-109">Attribute type</span></span>|<span data-ttu-id="b170f-110">설명</span><span class="sxs-lookup"><span data-stu-id="b170f-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="b170f-111">일반</span><span class="sxs-lookup"><span data-stu-id="b170f-111">General</span></span>|<span data-ttu-id="b170f-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-112">Required attribute.</span></span> <span data-ttu-id="b170f-113">매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-113">The parameter name.</span></span> <span data-ttu-id="b170f-114">예를 들어 메서드 시그니처 `String.CompareTo(Object value)`의 경우 `Name` 특성의 값은 "value"입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="b170f-115">반사</span><span class="sxs-lookup"><span data-stu-id="b170f-115">Reflection</span></span>|<span data-ttu-id="b170f-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-116">Optional attribute.</span></span> <span data-ttu-id="b170f-117">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="b170f-118">반사</span><span class="sxs-lookup"><span data-stu-id="b170f-118">Reflection</span></span>|<span data-ttu-id="b170f-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-119">Optional attribute.</span></span> <span data-ttu-id="b170f-120">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="b170f-121">반사</span><span class="sxs-lookup"><span data-stu-id="b170f-121">Reflection</span></span>|<span data-ttu-id="b170f-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-122">Optional attribute.</span></span> <span data-ttu-id="b170f-123">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="b170f-124">Serialization</span><span class="sxs-lookup"><span data-stu-id="b170f-124">Serialization</span></span>|<span data-ttu-id="b170f-125">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-125">Optional attribute.</span></span> <span data-ttu-id="b170f-126">Newtonsoft JSON serializer 등의 라이브러리를 통해 형식 인스턴스를 serialize 및 deserialize할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="b170f-127">Serialization</span><span class="sxs-lookup"><span data-stu-id="b170f-127">Serialization</span></span>|<span data-ttu-id="b170f-128">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-128">Optional attribute.</span></span> <span data-ttu-id="b170f-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="b170f-130">Serialization</span><span class="sxs-lookup"><span data-stu-id="b170f-130">Serialization</span></span>|<span data-ttu-id="b170f-131">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-131">Optional attribute.</span></span> <span data-ttu-id="b170f-132"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="b170f-133">Serialization</span><span class="sxs-lookup"><span data-stu-id="b170f-133">Serialization</span></span>|<span data-ttu-id="b170f-134">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-134">Optional attribute.</span></span> <span data-ttu-id="b170f-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="b170f-136">Interop</span><span class="sxs-lookup"><span data-stu-id="b170f-136">Interop</span></span>|<span data-ttu-id="b170f-137">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-137">Optional attribute.</span></span> <span data-ttu-id="b170f-138">WinRT 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="b170f-139">Interop</span><span class="sxs-lookup"><span data-stu-id="b170f-139">Interop</span></span>|<span data-ttu-id="b170f-140">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-140">Optional attribute.</span></span> <span data-ttu-id="b170f-141">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="b170f-142">Interop</span><span class="sxs-lookup"><span data-stu-id="b170f-142">Interop</span></span>|<span data-ttu-id="b170f-143">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-143">Optional attribute.</span></span> <span data-ttu-id="b170f-144">값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="b170f-145">Name 특성</span><span class="sxs-lookup"><span data-stu-id="b170f-145">Name attribute</span></span>  
  
|<span data-ttu-id="b170f-146">값</span><span class="sxs-lookup"><span data-stu-id="b170f-146">Value</span></span>|<span data-ttu-id="b170f-147">설명</span><span class="sxs-lookup"><span data-stu-id="b170f-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b170f-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="b170f-148">*parameter_name*</span></span>|<span data-ttu-id="b170f-149">정책이 적용되는 메서드 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="b170f-150">예를 들어 메서드 시그니처 `String.CompareTo(Object value)`의 경우 `Name` 특성의 값은 "value"입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="b170f-151">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="b170f-151">All other attributes</span></span>  
  
|<span data-ttu-id="b170f-152">값</span><span class="sxs-lookup"><span data-stu-id="b170f-152">Value</span></span>|<span data-ttu-id="b170f-153">설명</span><span class="sxs-lookup"><span data-stu-id="b170f-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b170f-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="b170f-154">*policy_setting*</span></span>|<span data-ttu-id="b170f-155">이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="b170f-156">가능한 값은 `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="b170f-157">자세한 내용은 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b170f-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b170f-158">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b170f-158">Child Elements</span></span>  
 <span data-ttu-id="b170f-159">없음</span><span class="sxs-lookup"><span data-stu-id="b170f-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b170f-160">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b170f-160">Parent Elements</span></span>  
  
|<span data-ttu-id="b170f-161">요소</span><span class="sxs-lookup"><span data-stu-id="b170f-161">Element</span></span>|<span data-ttu-id="b170f-162">설명</span><span class="sxs-lookup"><span data-stu-id="b170f-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b170f-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="b170f-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="b170f-164">생성자 또는 메서드에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b170f-165">설명</span><span class="sxs-lookup"><span data-stu-id="b170f-165">Remarks</span></span>  
 <span data-ttu-id="b170f-166">`<Parameter>` 요소는 [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) 요소의 자식이며 특정 메서드 매개 변수에 정책을 적용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-166">The `<Parameter>` element is a child of the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="b170f-167">특정 메서드 매개 변수는 형식이 아닌 이름으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-167">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="b170f-168">정책 형식을 나타내는 `Activate` 또는 `Dynamic`과 같은 특성이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b170f-168">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b170f-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b170f-169">See Also</span></span>  
 [<span data-ttu-id="b170f-170">\<Method> 요소</span><span class="sxs-lookup"><span data-stu-id="b170f-170">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="b170f-171">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="b170f-171">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="b170f-172">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="b170f-172">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="b170f-173">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="b170f-173">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
