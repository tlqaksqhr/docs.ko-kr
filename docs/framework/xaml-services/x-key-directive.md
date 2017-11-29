---
title: "x:Key 지시문"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
caps.latest.revision: "25"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 5e2ad03fcb52db1ffdd01849381a392187082991
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xkey-directive"></a><span data-ttu-id="1a3c9-102">x:Key 지시문</span><span class="sxs-lookup"><span data-stu-id="1a3c9-102">x:Key Directive</span></span>
<span data-ttu-id="1a3c9-103">고유 하 게 생성 되 고 XAML 정의 사전에서 참조 하는 요소를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-103">Uniquely identifies elements that are created and referenced in a XAML-defined dictionary.</span></span> <span data-ttu-id="1a3c9-104">추가 `x:Key` XAML 개체 요소 값은 예를 들어 WPF에에서 리소스 사전에 리소스를 식별 하는 가장 일반적인 방법은 <xref:System.Windows.ResourceDictionary>합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-104">Adding an `x:Key` value to a XAML object element is the most common way to identify a resource in a resource dictionary, for example in a WPF <xref:System.Windows.ResourceDictionary>.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="1a3c9-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="1a3c9-105">XAML Attribute Usage</span></span>  
  
```  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a><span data-ttu-id="1a3c9-106">XAML 특성 사용 (WPF에 따라 다름)</span><span class="sxs-lookup"><span data-stu-id="1a3c9-106">XAML Attribute Usage (WPF-specific)</span></span>  
  
```  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="1a3c9-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="1a3c9-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`stringKeyValue`|<span data-ttu-id="1a3c9-108">키로 사용 하는 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-108">A text string to use as a key.</span></span> <span data-ttu-id="1a3c9-109">텍스트 문자열을 준수 해야는 [XamlName 문법](../../../docs/framework/xaml-services/xamlname-grammar.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-109">The text string must conform to the [XamlName Grammar](../../../docs/framework/xaml-services/xamlname-grammar.md).</span></span>|  
|`markupExtensionUsage`|<span data-ttu-id="1a3c9-110">태그 확장 구분 기호 {} 내에서 키로 사용할 개체를를 제공 하는 태그 확장 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-110">Within the markup extension delimiters {}, a markup extension usage that provides an object to use as a key.</span></span> <span data-ttu-id="1a3c9-111">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-111">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a3c9-112">설명</span><span class="sxs-lookup"><span data-stu-id="1a3c9-112">Remarks</span></span>  
 <span data-ttu-id="1a3c9-113">`x:Key`XAML 리소스 사전 개념을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-113">`x:Key` supports the XAML resource dictionary concept.</span></span> <span data-ttu-id="1a3c9-114">XAML에 특정 UI 프레임 워크에 남아 있는 리소스 사전 구현을 정의 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-114">XAML as a language doesn't define a resource dictionary implementation, that is left to specific UI frameworks.</span></span> <span data-ttu-id="1a3c9-115">WPF에서 XAML 리소스 사전을 구현 되는 방식에 대 한 자세한 참조 [XAML 리소스](../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-115">To learn more about how XAML resource dictionaries are implemented in WPF, see [XAML Resources](../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="1a3c9-116">WPF 및 XAML 2006 `x:Key` 특성으로 제공 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-116">In XAML 2006 and WPF, `x:Key` must be provided as an attribute.</span></span> <span data-ttu-id="1a3c9-117">문자열이 아닌 키를 사용할 수 있습니다 있지만 특성 형식에서 문자열이 아닌 값을 제공 하기 위해 태그 확장 사용이 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-117">You can still use nonstring keys, but this requires a markup extension usage in order to provide the nonstring value in attribute form.</span></span> <span data-ttu-id="1a3c9-118">XAML 2009를 사용 하는 경우 `x:Key` 아닌 다른 개체 형식에 의해 입력 되는 사전을 명시적으로 지원 하기 위해 태그 확장 중간 필요 없이 문자열 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-118">If you are using XAML 2009, `x:Key` can be specified as an element, to explicitly support dictionaries keyed by object types other than strings without requiring a markup extension intermediate.</span></span> <span data-ttu-id="1a3c9-119">이 항목의 "XAML 2009" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-119">See the "XAML 2009" section in this topic.</span></span> <span data-ttu-id="1a3c9-120">주의 섹션의 나머지 부분에서는 XAML 2006 구현에 특별히 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-120">The remainder of the Remarks section applies specifically to the XAML 2006 implementation.</span></span>  
  
 <span data-ttu-id="1a3c9-121">특성 값 `x:Key` 모든 문자열에 정의할 수는 [XamlName 문법](../../../docs/framework/xaml-services/xamlname-grammar.md) 또는 태그 확장을 통해 평가 되는 개체가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-121">The attribute value of `x:Key` can be any string defined in the [XamlName Grammar](../../../docs/framework/xaml-services/xamlname-grammar.md) or can be an object evaluated through a markup extension.</span></span> <span data-ttu-id="1a3c9-122">WPF에서 예제를 보려면 "WPF 사용 정보"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-122">See "WPF Usage Notes" for an example from WPF.</span></span>  
  
 <span data-ttu-id="1a3c9-123">부모 요소의 자식 요소는 <xref:System.Collections.IDictionary> 구현 일반적으로 포함 되어야 합니다는 `x:Key` 해당 사전 내에서 고유 키 값을 지정 하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-123">Child elements of a parent element that is an <xref:System.Collections.IDictionary> implementation must typically include an `x:Key` attribute that specifies a unique key value within that dictionary.</span></span> <span data-ttu-id="1a3c9-124">프레임 워크에 별칭이 지정 된 키 속성에 대 한을 구현할 수 있습니다 `x:Key` 특정 종류의; 등의 속성을 정의 하는 형식 특성을 지정 해야와 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-124">Frameworks might implement aliased key properties to substitute for `x:Key` on particular types; types that define such properties should be attributed with <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.</span></span>  
  
 <span data-ttu-id="1a3c9-125">지정의 코드에 해당 하는 `x:Key` 내부에 사용 되는 키 <xref:System.Collections.IDictionary>합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-125">The code equivalent of specifying `x:Key` is the key that is used for the underlying <xref:System.Collections.IDictionary>.</span></span> <span data-ttu-id="1a3c9-126">예를 들어는 `x:Key` wpf에서 리소스의 값에 해당 하는 태그에 적용 되는 `key` 의 매개 변수 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 를 WPF 리소스를 추가 하면 <xref:System.Windows.ResourceDictionary> 코드에서.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-126">For example, an `x:Key` that is applied in markup for a resource in WPF is equivalent to the value of the `key` parameter of <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> when you add the resource to a WPF <xref:System.Windows.ResourceDictionary> in code.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="1a3c9-127">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="1a3c9-127">WPF Usage Notes</span></span>  
 <span data-ttu-id="1a3c9-128">부모의 자식 개체가 되는 개체는 <xref:System.Collections.IDictionary> WPF와 같은 구현 <xref:System.Windows.ResourceDictionary>, 일반적으로 포함 해야 합니다는 `x:Key` 특성과 키 값 해당 사전 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-128">Child objects of a parent object that is an <xref:System.Collections.IDictionary> implementation, such as the WPF <xref:System.Windows.ResourceDictionary>, must typically include an `x:Key` attribute, and the key value must be unique within that dictionary.</span></span> <span data-ttu-id="1a3c9-129">두 가지 주목할 만한 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-129">There are two notable exceptions:</span></span>  
  
-   <span data-ttu-id="1a3c9-130">일부 WPF 형식 사전 사용에 대 한 암시적 키를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-130">Some WPF types declare an implicit key for dictionary usage.</span></span> <span data-ttu-id="1a3c9-131">예를 들어 한 <xref:System.Windows.Style> 와 <xref:System.Windows.Style.TargetType%2A>, 또는 <xref:System.Windows.DataTemplate> 와 <xref:System.Windows.DataTemplate.DataType%2A>에 있을 수 있습니다는 <xref:System.Windows.ResourceDictionary> 암시적 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-131">For example, a <xref:System.Windows.Style> with a <xref:System.Windows.Style.TargetType%2A>, or a <xref:System.Windows.DataTemplate> with a <xref:System.Windows.DataTemplate.DataType%2A>, can be  in a <xref:System.Windows.ResourceDictionary> and use the implicit key.</span></span>  
  
-   <span data-ttu-id="1a3c9-132">WPF는 병합 된 리소스 사전 개념을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-132">WPF supports a merged resource dictionary concept.</span></span> <span data-ttu-id="1a3c9-133">키 병합된 된 사전 간에 공유할 수 있으며를 사용 하 여 공유 키 동작에 액세스할 수 있습니다 <xref:System.Windows.FrameworkContentElement.FindResource%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-133">Keys can be shared between the merged dictionaries, and the shared key behavior can be accessed using <xref:System.Windows.FrameworkContentElement.FindResource%2A>.</span></span> <span data-ttu-id="1a3c9-134">자세한 내용은 [병합된 리소스 사전](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-134">For more information, see [Merged Resource Dictionaries](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
 <span data-ttu-id="1a3c9-135">전체 WPF XAML 구현과 응용 프로그램 모델에서 키 고유성 XAML 태그 컴파일러에 의해 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-135">In the overall WPF XAML implementation and application model, key uniqueness is not checked by the XAML markup compiler.</span></span> <span data-ttu-id="1a3c9-136">대신, 누락 되었거나 고유 하지 않은 `x:Key` 값 로드할 때 XAML 파서 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-136">Instead, missing or nonunique `x:Key` values cause load-time XAML parser errors.</span></span> <span data-ttu-id="1a3c9-137">그러나 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] WPF 설계 단계에서 이러한 오류를 기록할 종종 수에 대 한 사전 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-137">However, [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] handling of dictionaries for WPF can often note such errors in the design phase.</span></span>  
  
 <span data-ttu-id="1a3c9-138">표시 된 구문을는 <xref:System.Windows.ResourceDictionary> 개체는 암시적 WPF XAML 프로세서에서 채우는 데 컬렉션을 생성 하는 방법에 <xref:System.Windows.FrameworkElement.Resources%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-138">Note that in the syntax shown, the <xref:System.Windows.ResourceDictionary> object is implicit in how the WPF XAML processor produces a collection to populate a <xref:System.Windows.FrameworkElement.Resources%2A> collection.</span></span> <span data-ttu-id="1a3c9-139">A <xref:System.Windows.ResourceDictionary> 제공 하지 않으면 일반적으로 명시적으로 태그의 요소로 쉽게 구별할 수 있도록 원하는 경우에 따라 사용할 수 있지만 (간의 컬렉션 object 요소는 것은 <xref:System.Windows.FrameworkElement.Resources%2A> 채울 속성 요소 및 해당 항목 내에 사전)입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-139">A <xref:System.Windows.ResourceDictionary> is not typically provided explicitly as an element in markup, although it can be in some cases if wanted for clarity (it would be a collection object element between the <xref:System.Windows.FrameworkElement.Resources%2A> property element and the items within that populate the dictionary).</span></span> <span data-ttu-id="1a3c9-140">이유는 컬렉션 개체는 거의 항상 암시적 태그 요소에에서 대 한 정보를 참조 하십시오. [XAML 구문에서 세부](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-140">For information about why a collection object is almost always an implicit element in markup, see [XAML Syntax In Detail](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).</span></span>  
  
 <span data-ttu-id="1a3c9-141">리소스 사전 키에 대 한 처리 정의한 WPF XAML 구현에는 <xref:System.Windows.ResourceKey> 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-141">In the WPF XAML implementation, the handling for resource dictionary keys is defined by the <xref:System.Windows.ResourceKey> abstract class.</span></span> <span data-ttu-id="1a3c9-142">그러나 WPF XAML 프로세서는 용도에 따라 키에 대 한 서로 다른 기본 확장 형식을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-142">However the WPF XAML processor produces different underlying extension types for keys based on their usages.</span></span> <span data-ttu-id="1a3c9-143">예를 들어에 대 한 키를 <xref:System.Windows.DataTemplate> 파생된 클래스 개별적으로 처리 되 고 고유한 생성 또는 <xref:System.Windows.DataTemplateKey> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-143">For example, the key for a <xref:System.Windows.DataTemplate> or any derived class is handled separately, and produces a distinct <xref:System.Windows.DataTemplateKey> object.</span></span>  
  
 <span data-ttu-id="1a3c9-144">키 및 이름을 사용 하 여 다른 지시문 및 언어 요소 (`x:Key` 비교 `x:Name`)의 기본 XAML 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-144">Keys and names use different directives and language elements (`x:Key` versus `x:Name`) in the basic XAML definition.</span></span> <span data-ttu-id="1a3c9-145">키와 이름 WPF 정의와 이러한 개념 중 응용 프로그램에서 다양 한 상황에 사용도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-145">Keys and names are also used in different situations by the WPF definition and application of these concepts.</span></span> <span data-ttu-id="1a3c9-146">자세한 내용은 참조 [WPF XAML 이름 범위](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-146">For details, see [WPF XAML Namescopes](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).</span></span>  
  
 <span data-ttu-id="1a3c9-147">앞서 설명한 것 처럼 키의 값 태그 확장을 통해 제공 될 수 있습니다 및 문자열 값이 아닌 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-147">As stated previously, the value of a key can be supplied through a markup extension and can be other than a string value.</span></span> <span data-ttu-id="1a3c9-148">값은 예제 WPF 시나리오 `x:Key` 될 수 있습니다는[ComponentResourceKey](../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-148">An example WPF scenario is that the value of `x:Key` may be a[ComponentResourceKey](../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md).</span></span> <span data-ttu-id="1a3c9-149">특정 컨트롤의 스타일을 완전히 바꾸지 않고 모양과 및 해당 컨트롤의 동작에 영향을 주는 사용자 지정 스타일 리소스에 대 한 해당 유형의 스타일 키를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-149">Certain controls expose a style key of that type for a custom style resource that influences part of the appearance and behavior of that control without totally replacing the style.</span></span> <span data-ttu-id="1a3c9-150">이러한 키의 예로 <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-150">An example of such a key is <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.</span></span>  
  
 <span data-ttu-id="1a3c9-151">WPF 병합 된 사전 기능 키 고유성 및 키 조회 동작에 대 한 추가 고려 사항을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-151">The WPF merged dictionary feature introduces additional considerations for key uniqueness and key lookup behavior.</span></span> <span data-ttu-id="1a3c9-152">자세한 내용은 [병합된 리소스 사전](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-152">For more information, see [Merged Resource Dictionaries](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="1a3c9-153">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="1a3c9-153">XAML 2009</span></span>  
 <span data-ttu-id="1a3c9-154">XAML 2009는 제한을 완화 하는 `x:Key` 항상 특성 형태로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-154">XAML 2009 relaxes the restriction that `x:Key` always be provided in attribute form.</span></span>  
  
 <span data-ttu-id="1a3c9-155">WPF에서 XAML 2009 기능을 있지만 태그 컴파일되지 않은 XAML에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-155">In WPF, you can use XAML 2009 features, but only for XAML that is not markup-compiled.</span></span> <span data-ttu-id="1a3c9-156">WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-156">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
 <span data-ttu-id="1a3c9-157">XAML 2009에서 지정할 수 있습니다 `x:Key` 요소는 다음을 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="1a3c9-157">Under XAML 2009, you can specify `x:Key` elements through the following usage:</span></span>  
  
### <a name="xaml-element-usage-xaml-2009-only"></a><span data-ttu-id="1a3c9-158">XAML 요소 사용 (XAML 2009에만 해당)</span><span class="sxs-lookup"><span data-stu-id="1a3c9-158">XAML Element Usage (XAML 2009 only)</span></span>  
  
```  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a><span data-ttu-id="1a3c9-159">XAML 값</span><span class="sxs-lookup"><span data-stu-id="1a3c9-159">XAML Values</span></span>  
  
|||  
|-|-|  
|`keyObject`|<span data-ttu-id="1a3c9-160">에 대 한 키로 사용 되는 개체에 대 한 object 요소는 주어진 `object` 특수 사전에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-160">Object element for the object that is used as the key for a given `object` in a specialized dictionary.</span></span>|  
  
-   <span data-ttu-id="1a3c9-161">이러한 종류의 사용에 대 한 부모 컨테이너/여기 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-161">The container/parent for this kind of use is not shown here.</span></span> <span data-ttu-id="1a3c9-162">`object`특수 사전 구현을 나타내는 object 요소 자식이 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-162">`object` is expected to be a child of an object element that represents a specialized dictionary implementation.</span></span> <span data-ttu-id="1a3c9-163">`keyObject`개체 인스턴스 (또는 값 형식의 값)으로 예상 되는 특정 특수 사전 구현 위한 키로 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-163">`keyObject` is expected to be an object instance (or a value of a value type) that is appropriate as the key for that particular specialized dictionary implementation.</span></span>  
  
-   <span data-ttu-id="1a3c9-164">WPF에는이 사용법을 필요로 하는 사전을 구현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-164">WPF does not implement dictionaries that require this usage.</span></span> <span data-ttu-id="1a3c9-165">개체 키는 XAML 언어 XAML의 사전을 만드는 바람직한 특정 사용자 지정 사전 시나리오에 대 한 가능한 유용한의 일반 기능 더입니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-165">Object keys is more a general feature of the XAML language, possibly useful for certain custom dictionary scenarios where creating the dictionary in XAML is desirable.</span></span> <span data-ttu-id="1a3c9-166">문자열이 아닌 키를 사용 하 여 리소스에 대 한 암시적 스타일과 같은 WPF 기능에 대 한 설정 하거나 키를 지정 하는 다른 기술을 존재 하므로 개체 키를 사용 하 여 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-166">For WPF features such as implicit styles that use non-string keys for resources, other techniques for establishing or specifying the keys exist, so using an object key is not necessary.</span></span>  
  
-   <span data-ttu-id="1a3c9-167">*keyObject* 직접 개체 인스턴스가 아닌 개체 요소 형태에서 태그 확장 사용이 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-167">*keyObject* could also be a markup extension usage in object element form, rather than a direct object instance.</span></span>  
  
## <a name="silverlight-usage-notes"></a><span data-ttu-id="1a3c9-168">Silverlight 사용 정보</span><span class="sxs-lookup"><span data-stu-id="1a3c9-168">Silverlight Usage Notes</span></span>  
 <span data-ttu-id="1a3c9-169">`x:Key`Silverlight 용은 별도로 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-169">`x:Key` for Silverlight is documented separately.</span></span> <span data-ttu-id="1a3c9-170">자세한 내용은 참조 [XAML Namespace (x:) 언어 기능 (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081)합니다.</span><span class="sxs-lookup"><span data-stu-id="1a3c9-170">For more information, see [XAML Namespace (x:) Language Features (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a3c9-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a3c9-171">See Also</span></span>  
 [<span data-ttu-id="1a3c9-172">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="1a3c9-172">XAML Resources</span></span>](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="1a3c9-173">리소스 및 코드</span><span class="sxs-lookup"><span data-stu-id="1a3c9-173">Resources and Code</span></span>](../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [<span data-ttu-id="1a3c9-174">StaticResource 태그 확장</span><span class="sxs-lookup"><span data-stu-id="1a3c9-174">StaticResource Markup Extension</span></span>](../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)
