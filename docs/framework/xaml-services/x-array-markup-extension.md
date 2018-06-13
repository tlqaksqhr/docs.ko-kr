---
title: x:Array 태그 확장명
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: 7c728b63c16d8f24c4ad68d07e6d174f510204ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565015"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="d722f-102">x:Array 태그 확장명</span><span class="sxs-lookup"><span data-stu-id="d722f-102">x:Array Markup Extension</span></span>
<span data-ttu-id="d722f-103">태그 확장을 통해 XAML에서 개체의 배열에 대 한 일반 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="d722f-104">이에 해당 하는 `x:ArrayExtension` [MS XAML]에서 XAML 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="d722f-105">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="d722f-105">XAML Object Element Usage</span></span>  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d722f-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="d722f-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`typeName`|<span data-ttu-id="d722f-107">형식의 이름을 하 여 `x:Array` 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="d722f-108">`typeName` 수 있습니다 (및 종종) XAML에 대 한 접두사로 XAML이 포함 된 네임 스페이스 정의 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|  
|`arrayContents`|<span data-ttu-id="d722f-109">내장 함수에 할당 된 항목 콘텐츠 `ArrayExtension.Items` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="d722f-110">일반적으로 이러한 항목 내에 포함 된 하나 이상의 개체 요소로 지정 되는 `x:Array` 태그 및 닫는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="d722f-111">지정 된 개체에 지정 된 XAML 형식에 할당할 수 예상 여기 `typeName`합니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d722f-112">설명</span><span class="sxs-lookup"><span data-stu-id="d722f-112">Remarks</span></span>  
 <span data-ttu-id="d722f-113">`Type` 모든 필수 특성은 `x:Array` 개체 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="d722f-114">A `Type` 매개 변수 값을 사용 하 여 않아도 `x:Type` 태그 확장;에 대 한 단기는 형식의 이름은 문자열로 지정할 수 있는 XAML 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>  
  
 <span data-ttu-id="d722f-115">.NET Framework XAML 서비스 구현, 입력된 XAML 형식 및 CLR 출력 간의 관계에서 <xref:System.Type> 만들어진된 배열을의 영향을 받습니다 태그 확장에 대 한 서비스 컨텍스트.</span><span class="sxs-lookup"><span data-stu-id="d722f-115">In the .NET Framework XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="d722f-116">출력 <xref:System.Type> 는 <xref:System.Xaml.XamlType.UnderlyingType%2A> 필요한을 조회 한 후 입력 XAML 형식의 <xref:System.Xaml.XamlType> XAML 스키마 컨텍스트에 따라 및 <xref:System.Windows.Markup.IXamlTypeResolver> 서비스 컨텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="d722f-117">배열 콘텐츠가에 할당 된 처리 될 때는 `ArrayExtension.Items` 내장 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="d722f-118">에 <xref:System.Windows.Markup.ArrayExtension> 구현에서이 표현 됩니다 <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="d722f-119">이 태그 확장에 대 한 처리 정의한.NET Framework XAML 서비스 구현에는 <xref:System.Windows.Markup.ArrayExtension> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-119">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="d722f-120"><xref:System.Windows.Markup.ArrayExtension> 봉인 및 사용자 지정 배열 형식에 대 한 태그 확장 구현에 대 한 기준으로 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>  
  
 <span data-ttu-id="d722f-121">`x:Array` 일반 xaml에서 언어 확장성.</span><span class="sxs-lookup"><span data-stu-id="d722f-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="d722f-122">하지만 `x:Array` XAML 구조적된 속성 내용으로 XAML 지원 컬렉션을 사용 하는 특정 속성 값을 지정 하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="d722f-123">예를 들어의 내용을 지정할 수 있습니다는 <xref:System.Collections.IEnumerable> 속성으로는 `x:Array` 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>  
  
 <span data-ttu-id="d722f-124">`x:Array`은 태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="d722f-125">태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="d722f-126">`x:Array` 부분적으로 해당 규칙에 예외 때문에 다른 특성 값 처리를 제공 하는 대신 `x:Array` 내부 텍스트 내용의 처리 대안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="d722f-127">이 동작을 통해 배열에 그룹화 하 고 명명 된 배열;에 액세스 하 여 코드 숨김에서 나중에 참조 하도록 기존 콘텐츠 모델에서 지원 되지 않는 형식 호출할 수 있습니다 <xref:System.Array> 메서드 개별 배열 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>  
  
 <span data-ttu-id="d722f-128">XAML의 모든 태그 확장 사용 중괄호 ({,} `)` 는 XAML 프로세서는 기준인 태그 확장 특성 값을 처리 해야 한다는 것을 인식 하는 규칙의 특성 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="d722f-129">태그 확장에에서 대 한 자세한 내용은 참조 하십시오. [형식 변환기 및 XAML 태그 확장명](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).</span></span>  
  
 <span data-ttu-id="d722f-130">XAML 2009에서 `x:Array` 언어 태그 확장 하는 대신 기본 형식으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="d722f-131">자세한 내용은 참조 [일반 XAML 언어 기본 형식에 대 한 기본 제공 형식](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-131">For more information, see [Built-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="d722f-132">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="d722f-132">WPF Usage Notes</span></span>  
 <span data-ttu-id="d722f-133">채울 개체 요소 일반적으로 `x:Array` 에 존재 하는 요소가 없는 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML 네임 스페이스에 기본이 아닌 XAML 네임 스페이스에 접두사 매핑이 필요 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>  
  
 <span data-ttu-id="d722f-134">예를 들어, 다음을 간단한 두 문자열의 배열에서 `sys` 접두사 (그리고 `x`) 배열 수준에서 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>  
  
 <span data-ttu-id="d722f-135">[xaml]</span><span class="sxs-lookup"><span data-stu-id="d722f-135">[xaml]</span></span>  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 <span data-ttu-id="d722f-136">배열 요소로 사용 되는 사용자 지정 형식에 대 한 클래스가 개체 요소로 XAML에서 인스턴스화하기 되 고에 대 한 요구 사항을 지원도 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-136">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="d722f-137">자세한 내용은 참조 [XAML을 WPF에 대 한 사용자 지정 클래스](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d722f-137">For more information, see [XAML and Custom Classes for WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d722f-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d722f-138">See Also</span></span>  
 [<span data-ttu-id="d722f-139">태그 확장 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="d722f-139">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="d722f-140">WPF에서 System.Xaml로 마이그레이션된 형식</span><span class="sxs-lookup"><span data-stu-id="d722f-140">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
