---
title: '&lt;TypeParameter&gt; 요소(.NET 네이티브)'
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cc2faf9768b60d49f573720df8763813000a6b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393870"
---
# <a name="lttypeparametergt-element-net-native"></a><span data-ttu-id="d24d6-102">&lt;TypeParameter&gt; 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="d24d6-102">&lt;TypeParameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="d24d6-103">메서드로 전달된 Type 인수가 나타내는 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d24d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="d24d6-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d24d6-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d24d6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d24d6-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d24d6-107">특성</span><span class="sxs-lookup"><span data-stu-id="d24d6-107">Attributes</span></span>  
  
|<span data-ttu-id="d24d6-108">특성</span><span class="sxs-lookup"><span data-stu-id="d24d6-108">Attribute</span></span>|<span data-ttu-id="d24d6-109">특성 형식</span><span class="sxs-lookup"><span data-stu-id="d24d6-109">Attribute type</span></span>|<span data-ttu-id="d24d6-110">설명</span><span class="sxs-lookup"><span data-stu-id="d24d6-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="d24d6-111">일반</span><span class="sxs-lookup"><span data-stu-id="d24d6-111">General</span></span>|<span data-ttu-id="d24d6-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-112">Required attribute.</span></span> <span data-ttu-id="d24d6-113"><xref:System.Type> 형식의 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="d24d6-114">예를 들어 메서드 시그니처 `Type.GetInterfaceMap(Type interfaceType)`의 경우 `Name` 특성의 값은 "interfaceType"입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="d24d6-115">반사</span><span class="sxs-lookup"><span data-stu-id="d24d6-115">Reflection</span></span>|<span data-ttu-id="d24d6-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-116">Optional attribute.</span></span> <span data-ttu-id="d24d6-117">인스턴스를 활성화할 수 있도록 생성자에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="d24d6-118">반사</span><span class="sxs-lookup"><span data-stu-id="d24d6-118">Reflection</span></span>|<span data-ttu-id="d24d6-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-119">Optional attribute.</span></span> <span data-ttu-id="d24d6-120">프로그램 요소에 대한 정보 쿼리를 제어하지만 런타임 액세스를 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="d24d6-121">반사</span><span class="sxs-lookup"><span data-stu-id="d24d6-121">Reflection</span></span>|<span data-ttu-id="d24d6-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-122">Optional attribute.</span></span> <span data-ttu-id="d24d6-123">동적 프로그래밍을 수행할 수 있도록 생성자, 메서드, 필드, 속성 및 이벤트를 비롯한 모든 형식 멤버에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="d24d6-124">Serialization</span><span class="sxs-lookup"><span data-stu-id="d24d6-124">Serialization</span></span>|<span data-ttu-id="d24d6-125">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-125">Optional attribute.</span></span> <span data-ttu-id="d24d6-126">Newtonsoft JSON serializer 등의 라이브러리를 통해 형식 인스턴스를 serialize 및 deserialize할 수 있도록 생성자, 필드 및 속성에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="d24d6-127">Serialization</span><span class="sxs-lookup"><span data-stu-id="d24d6-127">Serialization</span></span>|<span data-ttu-id="d24d6-128">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-128">Optional attribute.</span></span> <span data-ttu-id="d24d6-129"><xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 클래스를 사용하는 serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="d24d6-130">Serialization</span><span class="sxs-lookup"><span data-stu-id="d24d6-130">Serialization</span></span>|<span data-ttu-id="d24d6-131">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-131">Optional attribute.</span></span> <span data-ttu-id="d24d6-132"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> 클래스를 사용하는 JSON serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="d24d6-133">Serialization</span><span class="sxs-lookup"><span data-stu-id="d24d6-133">Serialization</span></span>|<span data-ttu-id="d24d6-134">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-134">Optional attribute.</span></span> <span data-ttu-id="d24d6-135"><xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 클래스를 사용하는 XML serialization에 대한 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="d24d6-136">Interop</span><span class="sxs-lookup"><span data-stu-id="d24d6-136">Interop</span></span>|<span data-ttu-id="d24d6-137">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-137">Optional attribute.</span></span> <span data-ttu-id="d24d6-138">Windows 런타임 및 COM에 대한 참조 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="d24d6-139">Interop</span><span class="sxs-lookup"><span data-stu-id="d24d6-139">Interop</span></span>|<span data-ttu-id="d24d6-140">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-140">Optional attribute.</span></span> <span data-ttu-id="d24d6-141">네이티브 코드에 대한 함수 포인터로 대리자 형식을 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="d24d6-142">Interop</span><span class="sxs-lookup"><span data-stu-id="d24d6-142">Interop</span></span>|<span data-ttu-id="d24d6-143">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-143">Optional attribute.</span></span> <span data-ttu-id="d24d6-144">값 형식을 네이티브 코드로 마샬링하는 정책을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="d24d6-145">Name 특성</span><span class="sxs-lookup"><span data-stu-id="d24d6-145">Name attribute</span></span>  
  
|<span data-ttu-id="d24d6-146">값</span><span class="sxs-lookup"><span data-stu-id="d24d6-146">Value</span></span>|<span data-ttu-id="d24d6-147">설명</span><span class="sxs-lookup"><span data-stu-id="d24d6-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d24d6-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="d24d6-148">*parameter_name*</span></span>|<span data-ttu-id="d24d6-149"><xref:System.Type> 형식의 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="d24d6-150">예를 들어 메서드 시그니처 `Type.GetInterfaceMap(Type interfaceType)`의 경우 `Name` 특성의 값은 "interfaceType"입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="d24d6-151">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="d24d6-151">All other attributes</span></span>  
  
|<span data-ttu-id="d24d6-152">값</span><span class="sxs-lookup"><span data-stu-id="d24d6-152">Value</span></span>|<span data-ttu-id="d24d6-153">설명</span><span class="sxs-lookup"><span data-stu-id="d24d6-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d24d6-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="d24d6-154">*policy_setting*</span></span>|<span data-ttu-id="d24d6-155">이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="d24d6-156">가능한 값은 `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` 및 `Required All`입니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="d24d6-157">자세한 내용은 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d24d6-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d24d6-158">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d24d6-158">Child Elements</span></span>  
 <span data-ttu-id="d24d6-159">없음</span><span class="sxs-lookup"><span data-stu-id="d24d6-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d24d6-160">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d24d6-160">Parent Elements</span></span>  
  
|<span data-ttu-id="d24d6-161">요소</span><span class="sxs-lookup"><span data-stu-id="d24d6-161">Element</span></span>|<span data-ttu-id="d24d6-162">설명</span><span class="sxs-lookup"><span data-stu-id="d24d6-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d24d6-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="d24d6-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="d24d6-164">생성자 또는 메서드에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d24d6-165">설명</span><span class="sxs-lookup"><span data-stu-id="d24d6-165">Remarks</span></span>  
 <span data-ttu-id="d24d6-166">`<TypeParameter>` 요소는 <xref:System.Type> 형식 매개 변수에만 적용할 수 있다는 점을 제외하면 [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md) 요소와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-166">The `<TypeParameter>` element is similar to the [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="d24d6-167">이 요소는 `Name` 특성으로 지정된 형식 인수에 의해 런타임에 표시되는 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-167">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="d24d6-168">예를 들어 NewtonSoft JSON serializer는 정적 `JsonConvert.DeserializeObject(String value, Type type)` 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-168">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="d24d6-169">다음 리플렉션 지시문은</span><span class="sxs-lookup"><span data-stu-id="d24d6-169">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="d24d6-170">`type` 인수가 나타내는 런타임 형식에 대한 메타데이터를 serialization에 사용할 수 있도록 제공해야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-170">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="d24d6-171">이러한 런타임 지시문이 다음 소스 코드를 포함하는 프로젝트에 적용되는 경우</span><span class="sxs-lookup"><span data-stu-id="d24d6-171">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="d24d6-172">리플렉션 지시문은 런타임에 `StockQuote` 형식의 메타데이터를 NewtonSoft JSON serializer에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d24d6-172">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d24d6-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d24d6-173">See Also</span></span>  
 [<span data-ttu-id="d24d6-174">\<Method> 요소</span><span class="sxs-lookup"><span data-stu-id="d24d6-174">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="d24d6-175">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="d24d6-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="d24d6-176">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="d24d6-176">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="d24d6-177">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="d24d6-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
