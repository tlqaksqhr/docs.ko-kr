---
title: "x:Type 태그 확장명"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
caps.latest.revision: "27"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: ed0372349a08687fd83b0fc989cc4cb88c29d96c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="21986-102">x:Type 태그 확장명</span><span class="sxs-lookup"><span data-stu-id="21986-102">x:Type Markup Extension</span></span>
<span data-ttu-id="21986-103">CLR 제공 <xref:System.Type> 개체는 지정된 된 XAML 형식에 대 한 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="21986-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="21986-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="21986-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="21986-105">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="21986-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="21986-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="21986-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="21986-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="21986-107">Optional.</span></span> <span data-ttu-id="21986-108">기본이 아닌 XAML 네임 스페이스에 매핑되는 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="21986-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="21986-109">접두사 지정 자주 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21986-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="21986-110">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21986-110">See Remarks.</span></span>|  
|`typeNameValue`|<span data-ttu-id="21986-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="21986-111">Required.</span></span> <span data-ttu-id="21986-112">현재 기본 XAML 네임 스페이스;에서 확인할 수 없는 형식 이름 지정 된 매핑된 접두사 경우 또는 `prefix` 를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21986-113">설명</span><span class="sxs-lookup"><span data-stu-id="21986-113">Remarks</span></span>  
 <span data-ttu-id="21986-114">`x:Type` 태그 확장은 비슷한 기능을는 `typeof()` 연산자 [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] 또는 `GetType` 연산자 [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] or the `GetType` operator in [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)].</span></span>  
  
 <span data-ttu-id="21986-115">`x:Type` 유형을 사용 하는 속성에 대 한 문자열에서 변환 동작을 제공 <xref:System.Type>합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="21986-116">입력은 XAML 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="21986-116">The input is a XAML type.</span></span> <span data-ttu-id="21986-117">입력된 XAML 형식 및 CLR 출력 간의 관계 <xref:System.Type> 은 출력 <xref:System.Type> 는 <xref:System.Xaml.XamlType.UnderlyingType%2A> 입력의 <xref:System.Xaml.XamlType>, 필요한을 조회 한 후 <xref:System.Xaml.XamlType> XAML 스키마 컨텍스트와 기반<xref:System.Windows.Markup.IXamlTypeResolver>서비스 컨텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="21986-118">이 태그 확장에 대 한 처리 정의한.NET Framework XAML 서비스에서는 <xref:System.Windows.Markup.TypeExtension> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="21986-118">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>  
  
 <span data-ttu-id="21986-119">특정 프레임 워크 구현에서는 일부 속성 걸리는 <xref:System.Type> 값 형식의 이름을 직접 허용할 수 있습니다 (형식의 문자열 값 `Name`).</span><span class="sxs-lookup"><span data-stu-id="21986-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="21986-120">그러나 복잡 한 시나리오는이 동작을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="21986-121">예제를 보려면 다음에 나오는 "WPF 사용 정보" 섹션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>  
  
 <span data-ttu-id="21986-122">특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="21986-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="21986-123">`x:Type` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 확장 클래스의 <xref:System.Windows.Markup.TypeExtension> 값으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="21986-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="21986-124">CLR 유형 기반.NET Framework XAML 서비스에 대 한 기본 XAML 스키마 컨텍스트 내에서이 특성의 값은는 <xref:System.Reflection.MemberInfo.Name%2A> 원하는 유형의 하거나 포함 하는 <xref:System.Reflection.MemberInfo.Name%2A> 앞에 기본이 아닌 XAML 네임 스페이스에 대 한 접두사 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="21986-124">Under the default XAML schema context for .NET Framework XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>  
  
 <span data-ttu-id="21986-125">`x:Type` 개체 요소 구문에서 태그 확장을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21986-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="21986-126">이 경우의 값을 지정 하는 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 속성 확장을 제대로 초기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="21986-127">`x:Type` 태그 확장 verbose 특성으로도 사용할 수 있습니다; 그러나이 사용이 일반적인 하지 않습니다: `<``object``property``="{x:Type TypeName=``typeNameValue``}" .../>`</span><span class="sxs-lookup"><span data-stu-id="21986-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="21986-128">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="21986-128">WPF Usage Notes</span></span>  
  
### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="21986-129">기본 XAML Namespace 및 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="21986-129">Default XAML Namespace and Type Mapping</span></span>  
 <span data-ttu-id="21986-130">WPF 프로그래밍에 대 한 기본 XAML 네임 스페이스는 대부분의 일반적인 XAML 시나리오;에 필요한 XAML 형식이 포함 따라서 XAML 형식 값을 참조할 때 접두사를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21986-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="21986-131">또는 기본 XAML 네임 스페이스에 매핑되지 않은 CLR 네임 스페이스에서 있지만 WPF 어셈블리에 포함 된 형식에 대 한 사용자 지정 어셈블리에서 형식을 참조 하는 경우 접두사를 매핑해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21986-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="21986-132">매핑 CLR 네임 스페이스의 XAML 네임 스페이스 및 접두사에 대 한 자세한 내용은 참조 [XAML 네임 스페이스 및 WPF XAML에 대 한 매핑을 Namespace](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="21986-133">해당 지원 Typename 문자열로 속성 입력</span><span class="sxs-lookup"><span data-stu-id="21986-133">Type Properties That Support Typename-as-String</span></span>  
 <span data-ttu-id="21986-134">WPF 형식의 일부 속성의 값을 지정할 수 있는 기술을 지원 <xref:System.Type> 필요 없이 `x:Type` 태그 확장 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="21986-135">대신 유형 이름을 지정 하는 문자열로 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21986-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="21986-136">이 예로 <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="21986-137">이 동작에 대 한 지원 형식 변환기 또는 태그 확장을 통해 제공 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="21986-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="21986-138">대신,이를 통해 구현 deferral 동작 <xref:System.Windows.FrameworkElementFactory>합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>  
  
 <span data-ttu-id="21986-139">Silverlight 비슷한 규칙을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="21986-140">사실, Silverlight 현재 지원 하지 않는 `{x:Type}` 해당 XAML 언어 지원에 허용 하지 않습니다 `{x:Type}` 외부 Silverlight WPF XAML 마이그레이션을 지원 하기 위해 설계 된 몇 가지 상황에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="21986-141">따라서 문자열로 typename 동작 모든 Silverlight 네이티브 속성 평가에 기본 제공 되는 위치는 <xref:System.Type> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="21986-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="21986-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="21986-142">XAML 2009</span></span>  
 <span data-ttu-id="21986-143">제네릭 형식 및의 동작을 수정에 대 한 추가 지원을 제공 하는 XAML 2009 `x:TypeArguments` 및 `x:Type` 이 지원을 제공 하기 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>  
  
-   <span data-ttu-id="21986-144">`x:TypeArguments`및 일반 개체 인스턴스화의 관련된 개체 요소는 루트 이외의 요소에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21986-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="21986-145">자세한 내용은의 "XAML 2009" 섹션을 참조 하십시오. [X:typearguments 지시문](../../../docs/framework/xaml-services/x-typearguments-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).</span></span>  
  
-   <span data-ttu-id="21986-146">XAML 2009 태그에서 제네릭 형식의 제약 조건을 지정 하는 구문을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="21986-147">이에서 사용 될 `x:TypeArguments`를 위한 것 이며 `x:Type`, 또는 조합 하 여 두 가지 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="21986-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>  
  
-   <span data-ttu-id="21986-148">또한 부하 유형을 사용 하는 특정 프레임 워크에 대 한 암시적 형식 변환 동작에이 기능을 추가 대 한 XAML 2009를 처리할 때 WPF XAML 구현과 <xref:System.Type>합니다.</span><span class="sxs-lookup"><span data-stu-id="21986-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="21986-149">WPF에서 느슨한 XAML (태그 컴파일되지 않은 XAML)에 대해서만 XAML 2009 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21986-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="21986-150">WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21986-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21986-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21986-151">See Also</span></span>  
 <xref:System.Windows.Style>  
 [<span data-ttu-id="21986-152">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="21986-152">Styling and Templating</span></span>](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="21986-153">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="21986-153">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="21986-154">태그 확장 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="21986-154">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
