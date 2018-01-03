---
title: "&lt;GenericParameter&gt; 요소(.NET 네이티브)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 601118d2dcc42f9e35da0e24c782b218efd7a025
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltgenericparametergt-element-net-native"></a><span data-ttu-id="30ce6-102">&lt;GenericParameter&gt; 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="30ce6-102">&lt;GenericParameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="30ce6-103">제네릭 형식 또는 메서드의 매개 변수 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30ce6-104">구문</span><span class="sxs-lookup"><span data-stu-id="30ce6-104">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type" />  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type"  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30ce6-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="30ce6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="30ce6-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30ce6-107">특성</span><span class="sxs-lookup"><span data-stu-id="30ce6-107">Attributes</span></span>  
  
|<span data-ttu-id="30ce6-108">특성</span><span class="sxs-lookup"><span data-stu-id="30ce6-108">Attribute</span></span>|<span data-ttu-id="30ce6-109">특성 형식</span><span class="sxs-lookup"><span data-stu-id="30ce6-109">Attribute type</span></span>|<span data-ttu-id="30ce6-110">설명</span><span class="sxs-lookup"><span data-stu-id="30ce6-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="30ce6-111">일반</span><span class="sxs-lookup"><span data-stu-id="30ce6-111">General</span></span>|<span data-ttu-id="30ce6-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-112">Required attribute.</span></span> <span data-ttu-id="30ce6-113">제네릭 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-113">The name of the generic parameter.</span></span> <span data-ttu-id="30ce6-114">예를 들어 <xref:System.Func%603> 제네릭 대리자의 경우 런타임 정책을 대리자의 반환 값에 적용할 수 있도록 `Name` 특성의 값은 "TResult"입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="30ce6-115">반사</span><span class="sxs-lookup"><span data-stu-id="30ce6-115">Reflection</span></span>|<span data-ttu-id="30ce6-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-116">Optional attribute.</span></span> <span data-ttu-id="30ce6-117">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="30ce6-118">반사</span><span class="sxs-lookup"><span data-stu-id="30ce6-118">Reflection</span></span>|<span data-ttu-id="30ce6-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-119">Optional attribute.</span></span> <span data-ttu-id="30ce6-120">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="30ce6-121">반사</span><span class="sxs-lookup"><span data-stu-id="30ce6-121">Reflection</span></span>|<span data-ttu-id="30ce6-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-122">Optional attribute.</span></span> <span data-ttu-id="30ce6-123">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="30ce6-124">Serialization</span><span class="sxs-lookup"><span data-stu-id="30ce6-124">Serialization</span></span>|<span data-ttu-id="30ce6-125">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-125">Optional attribute.</span></span> <span data-ttu-id="30ce6-126">Newtonsoft JSON serializer 등의 라이브러리를 통해 형식 인스턴스를 serialize 및 deserialize할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="30ce6-127">Serialization</span><span class="sxs-lookup"><span data-stu-id="30ce6-127">Serialization</span></span>|<span data-ttu-id="30ce6-128">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-128">Optional attribute.</span></span> <span data-ttu-id="30ce6-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="30ce6-130">Serialization</span><span class="sxs-lookup"><span data-stu-id="30ce6-130">Serialization</span></span>|<span data-ttu-id="30ce6-131">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-131">Optional attribute.</span></span> <span data-ttu-id="30ce6-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="30ce6-133">Serialization</span><span class="sxs-lookup"><span data-stu-id="30ce6-133">Serialization</span></span>|<span data-ttu-id="30ce6-134">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-134">Optional attribute.</span></span> <span data-ttu-id="30ce6-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="30ce6-136">Interop</span><span class="sxs-lookup"><span data-stu-id="30ce6-136">Interop</span></span>|<span data-ttu-id="30ce6-137">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-137">Optional attribute.</span></span> <span data-ttu-id="30ce6-138">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="30ce6-139">Interop</span><span class="sxs-lookup"><span data-stu-id="30ce6-139">Interop</span></span>|<span data-ttu-id="30ce6-140">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-140">Optional attribute.</span></span> <span data-ttu-id="30ce6-141">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="30ce6-142">Interop</span><span class="sxs-lookup"><span data-stu-id="30ce6-142">Interop</span></span>|<span data-ttu-id="30ce6-143">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-143">Optional attribute.</span></span> <span data-ttu-id="30ce6-144">값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="30ce6-145">Name 특성</span><span class="sxs-lookup"><span data-stu-id="30ce6-145">Name attribute</span></span>  
  
|<span data-ttu-id="30ce6-146">값</span><span class="sxs-lookup"><span data-stu-id="30ce6-146">Value</span></span>|<span data-ttu-id="30ce6-147">설명</span><span class="sxs-lookup"><span data-stu-id="30ce6-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="30ce6-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="30ce6-148">*generic_parameter_name*</span></span>|<span data-ttu-id="30ce6-149">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-149">Required attribute.</span></span> <span data-ttu-id="30ce6-150">제네릭 형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-150">The name of the generic type parameter.</span></span> <span data-ttu-id="30ce6-151">예를 들어 <xref:System.Func%603> 제네릭 대리자의 경우 *generic_parameter_name*의 값이 “TResult”이면 런타임 정책이 대리자의 반환 값에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="30ce6-152">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="30ce6-152">All other attributes</span></span>  
  
|<span data-ttu-id="30ce6-153">값</span><span class="sxs-lookup"><span data-stu-id="30ce6-153">Value</span></span>|<span data-ttu-id="30ce6-154">설명</span><span class="sxs-lookup"><span data-stu-id="30ce6-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="30ce6-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="30ce6-155">*policy_setting*</span></span>|<span data-ttu-id="30ce6-156">이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="30ce6-157">가능한 값은 `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="30ce6-158">자세한 내용은 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30ce6-158">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30ce6-159">자식 요소</span><span class="sxs-lookup"><span data-stu-id="30ce6-159">Child Elements</span></span>  
 <span data-ttu-id="30ce6-160">없음</span><span class="sxs-lookup"><span data-stu-id="30ce6-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30ce6-161">부모 요소</span><span class="sxs-lookup"><span data-stu-id="30ce6-161">Parent Elements</span></span>  
  
|<span data-ttu-id="30ce6-162">요소</span><span class="sxs-lookup"><span data-stu-id="30ce6-162">Element</span></span>|<span data-ttu-id="30ce6-163">설명</span><span class="sxs-lookup"><span data-stu-id="30ce6-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30ce6-164">\<Method></span><span class="sxs-lookup"><span data-stu-id="30ce6-164">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="30ce6-165">생성자 또는 메서드에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[<span data-ttu-id="30ce6-166">\<Type></span><span class="sxs-lookup"><span data-stu-id="30ce6-166">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="30ce6-167">클래스 또는 구조체와 같은 특정 형식에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-167">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30ce6-168">설명</span><span class="sxs-lookup"><span data-stu-id="30ce6-168">Remarks</span></span>  
 <span data-ttu-id="30ce6-169">`<GenericParameter>` 요소는 [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) 또는 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 요소의 자식이며, 제네릭 형식 또는 메서드 시그니처에서 해당 이름으로 지정되는 특정 제네릭 형식 매개 변수에 정책을 적용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-169">The `<GenericParameter>` element is a child of either the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) or [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="30ce6-170">`<GenericParameter>` 요소는 serializer와 함께 사용하면 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-170">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="30ce6-171">다음 예제에서는 `<GenericParameter>` 요소를 사용하여 NewtonSoft JSON 직렬 변환기의 [JsonConvert.DeserializeObject\<T>(String)](http://james.newtonking.com/json/help/index.html?topic=html/T_Newtonsoft_Json_JsonConvert.htm) 메서드 오버로드에 대한 호출에서 `T` 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="30ce6-171">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](http://james.newtonking.com/json/help/index.html?topic=html/T_Newtonsoft_Json_JsonConvert.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="30ce6-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30ce6-172">See Also</span></span>  
 [<span data-ttu-id="30ce6-173">\<Method> 요소</span><span class="sxs-lookup"><span data-stu-id="30ce6-173">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="30ce6-174">\<형식 > 요소</span><span class="sxs-lookup"><span data-stu-id="30ce6-174">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 [<span data-ttu-id="30ce6-175">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="30ce6-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="30ce6-176">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="30ce6-176">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="30ce6-177">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="30ce6-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
