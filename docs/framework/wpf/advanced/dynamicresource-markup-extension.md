---
title: "DynamicResource 태그 확장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f6c8500f9b9cd6d617789a2da3444519971ae81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="dynamicresource-markup-extension"></a><span data-ttu-id="3686c-102">DynamicResource 태그 확장</span><span class="sxs-lookup"><span data-stu-id="3686c-102">DynamicResource Markup Extension</span></span>
<span data-ttu-id="3686c-103">에 대 한 값을 제공 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 정의 된 리소스에 대 한 참조가 되도록 지연 하 여 property 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by deferring that value to be a reference to a defined resource.</span></span> <span data-ttu-id="3686c-104">해당 리소스에 대 한 조회 동작은 런타임에 조회과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-104">Lookup behavior for that resource is analogous to run-time lookup.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="3686c-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="3686c-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="3686c-106">XAML 속성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="3686c-106">XAML Property Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="3686c-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="3686c-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="3686c-108">요청한 리소스의 키입니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-108">The key for the requested resource.</span></span> <span data-ttu-id="3686c-109">이 키는 처음 할당 된 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md) 리소스 태그에 작성 되거나 변수로 제공 된 경우는 `key` 를 호출할 때 매개 변수 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 코드에서 리소스를 만든 경우.</span><span class="sxs-lookup"><span data-stu-id="3686c-109">This key was initially assigned by the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3686c-110">설명</span><span class="sxs-lookup"><span data-stu-id="3686c-110">Remarks</span></span>  
 <span data-ttu-id="3686c-111">A `DynamicResource` 초기 컴파일 중에 임시 표현식은 만들고 때문 요청 된 리소스 값이 개체를 생성 하기 위해 실제로 필요할 때까지 리소스에 대 한 조회를 연기 합니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-111">A `DynamicResource` will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="3686c-112">이 수 이후는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지가 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-112">This may potentially be after the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is loaded.</span></span> <span data-ttu-id="3686c-113">리소스 값 섹션은 현재 페이지 범위에서 시작 하는 모든 활성 리소스 사전에 대해 키 검색 및 컴파일에서 자리 표시자 식에 대 한 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-113">The resource value will be found based on key search against all active resource dictionaries starting from the current page scope, and is substituted for the placeholder expression from compilation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3686c-114">종속성 속성의 우선 순위를 기준으로 한 `DynamicResource` 식은 동적 리소스 참조 적용 되는 위치에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-114">In terms of dependency property precedence, a `DynamicResource` expression is equivalent to the position where the dynamic resource reference is applied.</span></span> <span data-ttu-id="3686c-115">이전에 속성에 대 한 로컬 값을 설정 하는 경우는 `DynamicResource` 식을 로컬 값으로는 `DynamicResource` 완전히 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-115">If you set a local value for a property that previously had a `DynamicResource` expression as the local value, the `DynamicResource` is completely removed.</span></span> <span data-ttu-id="3686c-116">자세한 내용은 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3686c-116">For details, see [Dependency Property Value Precedence](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).</span></span>  
  
 <span data-ttu-id="3686c-117">특정 리소스 액세스 시나리오에 특히 적합 한는 `DynamicResource` 반대인는 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-117">Certain resource access scenarios are particularly appropriate for `DynamicResource` as opposed to a [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).</span></span> <span data-ttu-id="3686c-118">참조 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md) 관련 이점과 성능에 미치는 영향에 대 한 토론에 대 한 `DynamicResource` 및 `StaticResource`합니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-118">See [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md) for a discussion about the relative merits and performance implications of `DynamicResource` and `StaticResource`.</span></span>  
  
 <span data-ttu-id="3686c-119">지정 된 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 에 의해 결정 되는 기존 리소스에 해당 해야 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md) 특정 수준에서 페이지, 응용 프로그램, 사용 가능한 컨트롤 테마 및 외부의 리소스 또는 시스템 리소스 및 리소스 조회 순서 대로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-119">The specified <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> should correspond to an existing resource determined by [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) at some level in your page, application, the available control themes and external resources, or system resources, and the resource lookup will happen in that order.</span></span> <span data-ttu-id="3686c-120">정적 및 동적 리소스에 대 한 리소스 조회에 대 한 자세한 내용은 참조 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-120">For more information about resource lookup for static and dynamic resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="3686c-121">리소스 키에 정의 된 모든 문자열일 수 있습니다는 [XamlName 문법](../../../../docs/framework/xaml-services/xamlname-grammar.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-121">A resource key may be any string defined in the [XamlName Grammar](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="3686c-122">리소스 키 수도 있습니다 다른 개체 형식 같은 <xref:System.Type>합니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-122">A resource key may also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="3686c-123">A <xref:System.Type> 테마 컨트롤은 방식의 기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-123">A <xref:System.Type> key is fundamental to how controls can be styled by themes.</span></span> <span data-ttu-id="3686c-124">자세한 내용은 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3686c-124">For more information, see [Control Authoring Overview](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span></span>  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]<span data-ttu-id="3686c-125">리소스 값을 조회에 대 한 같은 <xref:System.Windows.FrameworkElement.FindResource%2A>에서 사용 되는 동일한 리소스 조회 논리에 따라 `DynamicResource`합니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-125"> for lookup of resource values, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, follow the same resource lookup logic as used by `DynamicResource`.</span></span>  
  
 <span data-ttu-id="3686c-126">리소스 참조 선언적 다른 방법을 사용 하는 한 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-126">The alternative declarative means of referencing a resource is as a [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="3686c-127">특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-127">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="3686c-128">`DynamicResource` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 확장 클래스의 <xref:System.Windows.DynamicResourceExtension> 값으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-128">The string token provided after the `DynamicResource` identifier string is assigned as the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.DynamicResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="3686c-129">`DynamicResource`개체 요소 구문에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-129">`DynamicResource` can be used in object element syntax.</span></span> <span data-ttu-id="3686c-130">이 경우의 값을 지정 하는 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 속성은 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-130">In this case, specifying the value of the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="3686c-131">`DynamicResource` 속성을 다음과 같이 속성=값 쌍으로 지정하는 자세한 특성 사용 구문에도 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-131">`DynamicResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="3686c-132">자세한 정보 표시는 대개 설정 가능한 속성이 둘 이상이거나 일부 속성이 선택 사항인 확장의 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-132">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="3686c-133">
          `DynamicResource`에는 설정 가능한 속성이 하나뿐이고 이 속성은 필수적 속성이므로 자세한 정보 표시를 사용하지 않는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-133">Because `DynamicResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="3686c-134">에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 구현이 태그 확장에 대 한 처리가 정의한는 <xref:System.Windows.DynamicResourceExtension> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-134">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.DynamicResourceExtension> class.</span></span>  
  
 <span data-ttu-id="3686c-135">`DynamicResource`은 태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-135">`DynamicResource` is a markup extension.</span></span> <span data-ttu-id="3686c-136">태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-136">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="3686c-137">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그 확장은 특성 구문에서 { 및 } 문자를 사용합니다. 이러한 문자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="3686c-137">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="3686c-138">자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3686c-138">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3686c-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3686c-139">See Also</span></span>  
 [<span data-ttu-id="3686c-140">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="3686c-140">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="3686c-141">리소스 및 코드</span><span class="sxs-lookup"><span data-stu-id="3686c-141">Resources and Code</span></span>](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [<span data-ttu-id="3686c-142">x:Key 지시문</span><span class="sxs-lookup"><span data-stu-id="3686c-142">x:Key Directive</span></span>](../../../../docs/framework/xaml-services/x-key-directive.md)  
 [<span data-ttu-id="3686c-143">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="3686c-143">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="3686c-144">태그 확장 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="3686c-144">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="3686c-145">StaticResource 태그 확장</span><span class="sxs-lookup"><span data-stu-id="3686c-145">StaticResource Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)  
 [<span data-ttu-id="3686c-146">태그 확장 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="3686c-146">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
