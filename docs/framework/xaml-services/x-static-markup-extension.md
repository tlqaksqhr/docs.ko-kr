---
title: "x:Static 태그 확장명"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
caps.latest.revision: "25"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 647bfed7b321a949090f6da047f9b8105d335101
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="12e7d-102">x:Static 태그 확장명</span><span class="sxs-lookup"><span data-stu-id="12e7d-102">x:Static Markup Extension</span></span>
<span data-ttu-id="12e7d-103">에 정의 된 모든 값으로 정적 코드 엔터티 참조는 [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]– 규정을 준수 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-103">References any static by-value code entity that is defined in a [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]–compliant way.</span></span> <span data-ttu-id="12e7d-104">참조 되는 정적 속성 XAML에서 속성의 값을 제공 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="12e7d-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="12e7d-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="12e7d-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="12e7d-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="12e7d-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-107">Optional.</span></span> <span data-ttu-id="12e7d-108">매핑된, 기본이 아닌 XAML 네임 스페이스를 참조 하는 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="12e7d-109">`prefix`명시적으로 표시 사용에서 기본 XAML 네임 스페이스에서 제공 하는 정적 속성을 거의 참조 하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="12e7d-110">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12e7d-110">See Remarks.</span></span>|  
|`typeName`|<span data-ttu-id="12e7d-111">필수.</span><span class="sxs-lookup"><span data-stu-id="12e7d-111">Required.</span></span> <span data-ttu-id="12e7d-112">원하는 정적 멤버를 정의 하는 유형의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-112">The name of the type that defines the desired static member.</span></span>|  
|`staticMemberName`|<span data-ttu-id="12e7d-113">필수.</span><span class="sxs-lookup"><span data-stu-id="12e7d-113">Required.</span></span> <span data-ttu-id="12e7d-114">원하는 정적 값 멤버 (상수, 정적 속성, 필드 또는 열거형 값)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12e7d-115">설명</span><span class="sxs-lookup"><span data-stu-id="12e7d-115">Remarks</span></span>  
 <span data-ttu-id="12e7d-116">참조 되는 코드 엔터티는 다음 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-116">The code entity that is referenced must be one of the following:</span></span>  
  
-   <span data-ttu-id="12e7d-117">상수</span><span class="sxs-lookup"><span data-stu-id="12e7d-117">A constant</span></span>  
  
-   <span data-ttu-id="12e7d-118">정적 속성</span><span class="sxs-lookup"><span data-stu-id="12e7d-118">A static property</span></span>  
  
-   <span data-ttu-id="12e7d-119">필드</span><span class="sxs-lookup"><span data-stu-id="12e7d-119">A field</span></span>  
  
-   <span data-ttu-id="12e7d-120">열거형 값</span><span class="sxs-lookup"><span data-stu-id="12e7d-120">An enumeration value</span></span>  
  
 <span data-ttu-id="12e7d-121">비정적 속성 같은 기타 코드 엔터티를 지정 하면 인지 XAML 태그 컴파일된 XAML 로드 시간 구문 분석 예외를 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>  
  
 <span data-ttu-id="12e7d-122">그러나 만들 수 있습니다 `x:Static` 정적 필드 또는 현재 XAML 문서에 대 한 기본 XAML 네임 스페이스에 없는 속성에 대 한 참조 접두사 매핑이 이렇게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="12e7d-123">XAML 네임 스페이스는 거의 항상 XAML 문서의 루트 요소에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>  
  
 <span data-ttu-id="12e7d-124">기본 XAML 스키마 컨텍스트를 실행 하는 경우.NET Framework XAML 서비스 XAML 판독기 및 XAML 작성기에서 정적 속성에 대 한 조회 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-124">The lookup operations for static properties can be performed by .NET Framework XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="12e7d-125">이 XAML 스키마 컨텍스트는 CLR 리플렉션을 사용 하 여 개체 그래프 생성에 필요한 정적 값을 제공 하도록 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="12e7d-126">`typeName` 지정는 실제로 XAML 형식 이름, CLR 형식 이름이 아니라 이름이 같은 기본적으로 모든 기존 CLR 기반 XAML 구현 프레임 워크를 사용 하는 경우 또는 기본 XAML 스키마 컨텍스트를 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="12e7d-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>  
  
 <span data-ttu-id="12e7d-127">주의 해야 할 때 사용 하 여 `x:Static` 는 속성의 값의 형식을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="12e7d-128">XAML에서 처리는 태그 확장에서 값을 제공 하는 시퀀스는 가치를 더하는 변환을 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="12e7d-129">이 true 인 경우에 프로그램 `x:Static` 참조 텍스트 문자열을 생성 하 고 일반적으로 텍스트 문자열에 따라 특성 값에 대 한 값 변환 발생 또는 해당 특정 멤버에 대 한 반환 형식의 모든 멤버 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>  
  
 <span data-ttu-id="12e7d-130">특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="12e7d-131">`x:Static` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.Markup.StaticExtension.Member%2A> 확장 클래스의 <xref:System.Windows.Markup.StaticExtension> 값으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>  
  
 <span data-ttu-id="12e7d-132">두 개의 다른 XAML 용도 기술적으로 가능 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="12e7d-133">그러나이 사용은 덜 일반적인 불필요 하 게 자세한 정보 표시 되기 때문에:</span><span class="sxs-lookup"><span data-stu-id="12e7d-133">However, these usages are less common because they are unnecessarily verbose:</span></span>  
  
 <span data-ttu-id="12e7d-134">**개체 요소 구문:** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName``" .../>`</span><span class="sxs-lookup"><span data-stu-id="12e7d-134">**Object element syntax:** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName` `" .../>`</span></span>  
  
 <span data-ttu-id="12e7d-135">**초기화 문자열에 대 한 명시적 멤버 속성이 있는 특성 구문:** `<` `object`  ``  `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName``}" .../>`</span><span class="sxs-lookup"><span data-stu-id="12e7d-135">**Attribute syntax with explicit Member property for initialization string:** `<` `object` `` `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName` `}" .../>`</span></span>  
  
 <span data-ttu-id="12e7d-136">이 태그 확장에 대 한 처리 정의한.NET Framework XAML 서비스 구현에는 <xref:System.Windows.Markup.StaticExtension> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-136">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>  
  
 <span data-ttu-id="12e7d-137">`x:Static`은 태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="12e7d-138">XAML 용도에서 모든 마크업 확장의 `{` 및 `}` 는 XAML 프로세서 함을 인식 하는 태그 확장 값을 제공 해야 하는 규칙의 특성 구문에는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="12e7d-139">태그 확장에 대한 자세한 내용은 [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12e7d-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="12e7d-140">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="12e7d-140">WPF Usage Notes</span></span>  
 <span data-ttu-id="12e7d-141">WPF 프로그래밍에 사용할 기본 XAML 네임 스페이스에는 많은 유용한 정적 속성이 있고 대부분의 유용한 정적 속성이 필요 없이 쉽게 사용할 수 있는 형식 변환기와 같은 지원 `{x:Static}` 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="12e7d-142">정적 속성에는 다음 중 하나는 XAML 네임 스페이스에 대 한 접두사를 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>  
  
-   <span data-ttu-id="12e7d-143">WPF에 존재 하 고 WPF에 대 한 기본 XAML 네임 스페이스에 속하지 않는 형식을 참조 하는 ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="12e7d-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span></span> <span data-ttu-id="12e7d-144">이것은 사용 하기 위한 매우 일반적인 시나리오 `x:Static`합니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="12e7d-145">예를 들어, 사용할 수는 `x:Static` 에 XAML 네임 스페이스 매핑 사용 하 여 참조는 <xref:System> 의 정적 속성을 참조 하기 위해 CLR 네임 스페이스 및 mscorlib 어셈블리는 <xref:System.Environment> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>  
  
-   <span data-ttu-id="12e7d-146">사용자 지정 어셈블리에서 형식을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-146">You are referencing a type from a custom assembly.</span></span>  
  
-   <span data-ttu-id="12e7d-147">했지만 해당 형식이 WPF 기본 XAML 네임 스페이스의 일부가 되도록 매핑되지 않은 CLR 네임 스페이스 내에서 WPF 어셈블리에 있는 유형을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="12e7d-148">WPF에 대 한 기본 XAML 네임 스페이스에 CLR 네임 스페이스 매핑은 다양 한 WPF 어셈블리에 대 한 정의 통해 수행 됩니다 (이 개념에 대 한 자세한 내용은 참조 [XAML 네임 스페이스 및 WPF XAML에 대 한 매핑을 Namespace](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span><span class="sxs-lookup"><span data-stu-id="12e7d-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="12e7d-149">매핑되지 않은 CLR 네임 스페이스는 해당 CLR 네임 스페이스가 클래스 정의 되지 않는 일반적으로 xaml의 경우와 같은 대부분의 구성 된 경우에 존재할 수 <xref:System.Windows.Threading>합니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>  
  
 <span data-ttu-id="12e7d-150">WPF에 대 한 XAML 네임 스페이스 및 접두사를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [XAML 네임 스페이스 및 WPF XAML에 대 한 매핑 Namespace](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="12e7d-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e7d-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12e7d-151">See Also</span></span>  
 [<span data-ttu-id="12e7d-152">x:Type 태그 확장</span><span class="sxs-lookup"><span data-stu-id="12e7d-152">x:Type Markup Extension</span></span>](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [<span data-ttu-id="12e7d-153">WPF에서 System.Xaml로 마이그레이션된 형식</span><span class="sxs-lookup"><span data-stu-id="12e7d-153">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
