---
title: "&lt;라이브러리&gt; 요소(.NET 네이티브)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b93335d0d5d1524c9a0b955d1ea279be8c0f243
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltlibrarygt-element-net-native"></a><span data-ttu-id="58b73-102">&lt;라이브러리&gt; 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="58b73-102">&lt;Library&gt; Element (.NET Native)</span></span>
<span data-ttu-id="58b73-103">런타임에 해당 메타데이터를 리플렉션에 사용할 수 있는 형식 및 형식 멤버가 포함된 어셈블리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="58b73-104">\<Directives> 요소</span><span class="sxs-lookup"><span data-stu-id="58b73-104">\<Directives> Element</span></span>  
<span data-ttu-id="58b73-105">\<Library> 요소</span><span class="sxs-lookup"><span data-stu-id="58b73-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b73-106">구문</span><span class="sxs-lookup"><span data-stu-id="58b73-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58b73-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="58b73-107">Attributes and Elements</span></span>  
 <span data-ttu-id="58b73-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58b73-109">특성</span><span class="sxs-lookup"><span data-stu-id="58b73-109">Attributes</span></span>  
  
|<span data-ttu-id="58b73-110">특성</span><span class="sxs-lookup"><span data-stu-id="58b73-110">Attribute</span></span>|<span data-ttu-id="58b73-111">설명</span><span class="sxs-lookup"><span data-stu-id="58b73-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="58b73-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-112">Required attribute.</span></span> <span data-ttu-id="58b73-113">어셈블리의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="58b73-114">이 `<Library>` 요소의 자식 요소는 이 어셈블리에 있는 형식 및 형식 멤버에 대한 런타임 리플렉션 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="58b73-115">Name 특성</span><span class="sxs-lookup"><span data-stu-id="58b73-115">Name attribute</span></span>  
  
|<span data-ttu-id="58b73-116">값</span><span class="sxs-lookup"><span data-stu-id="58b73-116">Value</span></span>|<span data-ttu-id="58b73-117">설명</span><span class="sxs-lookup"><span data-stu-id="58b73-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="58b73-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="58b73-118">*assembly_name*</span></span>|<span data-ttu-id="58b73-119">파일 확장명이 없는 어셈블리의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="58b73-120">이 특성은 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="58b73-121">예를 들어 Extensions.dll 어셈블리의 이름은 "Extensions"입니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="58b73-122">어셈블리에서 조건부 메타데이터 포함을 지원하는 특수 *assembly_name* 형식에 대한 내용은 설명 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58b73-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58b73-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="58b73-123">Child Elements</span></span>  
  
|<span data-ttu-id="58b73-124">요소</span><span class="sxs-lookup"><span data-stu-id="58b73-124">Element</span></span>|<span data-ttu-id="58b73-125">설명</span><span class="sxs-lookup"><span data-stu-id="58b73-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58b73-126">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="58b73-126">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)|<span data-ttu-id="58b73-127">특정 어셈블리의 모든 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-127">Applies policy to all the types in a particular assembly.</span></span>|  
|[<span data-ttu-id="58b73-128">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="58b73-128">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)|<span data-ttu-id="58b73-129">특정 네임스페이스의 모든 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-129">Applies policy to all the types in a particular namespace.</span></span>|  
|[<span data-ttu-id="58b73-130">\<Type></span><span class="sxs-lookup"><span data-stu-id="58b73-130">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="58b73-131">클래스 또는 구조체와 같은 특정 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-131">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[<span data-ttu-id="58b73-132">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="58b73-132">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="58b73-133">생성된 제네릭 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-133">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="58b73-134">예를 들어 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소를 사용하면 `List<String>` 형식에 대한 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-134">For example, a [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58b73-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="58b73-135">Parent Elements</span></span>  
  
|<span data-ttu-id="58b73-136">요소</span><span class="sxs-lookup"><span data-stu-id="58b73-136">Element</span></span>|<span data-ttu-id="58b73-137">설명</span><span class="sxs-lookup"><span data-stu-id="58b73-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58b73-138">\<Directives></span><span class="sxs-lookup"><span data-stu-id="58b73-138">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)|<span data-ttu-id="58b73-139">런타임 지시문 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-139">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58b73-140">설명</span><span class="sxs-lookup"><span data-stu-id="58b73-140">Remarks</span></span>  
 <span data-ttu-id="58b73-141">[\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) 요소는 `<Library>` 요소를 포함하지 않을 수도 있고 하나 이상 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-141">The [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="58b73-142">`<Library>` 요소는 런타임에 해당 메타데이터가 필요한 프로그램 요소를 정의하는 컨테이너로 사용되며 정책을 표현하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-142">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="58b73-143">컴파일 타임에 컴파일러 도구는 `<Library>` 요소로 지정된 라이브러리에서만 자식 요소가 식별한 프로그램 요소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-143">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="58b73-144">반면 .NET Framework 핵심 라이브러리를 비롯한 모든 라이브러리에서 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 요소의 자식 요소가 식별한 프로그램 요소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-144">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="58b73-145">`<Library>` 지시문은 조건부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-145">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="58b73-146">`<Library>` 요소의 이름이 별표(*)로 시작되고 끝나는 경우에는 별표 사이에 지정된 어셈블리를 앱이 참조하는 경우에만 `<Library>` 지시문이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-146">If the name of the `<Library>` element starts and ends with an asterisk (*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="58b73-147">예를 들어 다음 런타임 지시문은 Utilities.dll 어셈블리를 앱이 참조하는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58b73-147">For example, the following runtime directive applies only if the Utillities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="58b73-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58b73-148">See Also</span></span>  
 [<span data-ttu-id="58b73-149">\<응용 프로그램 > 요소</span><span class="sxs-lookup"><span data-stu-id="58b73-149">\<Application> Element</span></span>](../../../docs/framework/net-native/application-element-net-native.md)  
 [<span data-ttu-id="58b73-150">\<지시문 > 요소</span><span class="sxs-lookup"><span data-stu-id="58b73-150">\<Directives> Element</span></span>](../../../docs/framework/net-native/directives-element-net-native.md)  
 [<span data-ttu-id="58b73-151">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="58b73-151">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="58b73-152">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="58b73-152">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
