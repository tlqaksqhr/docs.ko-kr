---
title: x:XData 내장 XAML 형식
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: 3a16379fd6104342529723bf6d0bc9fb4762cf92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565365"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="16f6e-102">x:XData 내장 XAML 형식</span><span class="sxs-lookup"><span data-stu-id="16f6e-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="16f6e-103">XAML 프로덕션 내에서 XML 데이터 아일랜드를 배치할을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="16f6e-104">내에서 XML 요소 `x:XData` 기본 XAML 네임 스페이스의 일부 인지 XAML 네임 스페이스 마치 XAML 프로세서에서 처리 되지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="16f6e-105">`x:XData` 임의의 올바른 형식의 XML을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="16f6e-106">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="16f6e-106">XAML Object Element Usage</span></span>  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="16f6e-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="16f6e-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="16f6e-108">포함 된 데이터 아일랜드의 단일 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="16f6e-109">대부분의 최종 소비자에 대 한 단일 루트 하지 않은 XML이 잘못 되었습니다. 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="16f6e-110">특히 하나의 루트는 나중에 필요한 경우는 `x:XData` WPF 또는 데이터 바인딩에 대 한 XML 원본을 사용 하는 다른 많은 기술에 대 한 XML 데이터 소스로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="16f6e-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-111">Optional.</span></span> <span data-ttu-id="16f6e-112">XML 데이터를 나타내는 XML입니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-112">XML that represents the XML data.</span></span> <span data-ttu-id="16f6e-113">원하는 수의 요소는 요소 데이터로 포함 될 수 있으며 다른 요소에 중첩 된 요소가 포함 될 수 있는 그러나 XML의 일반적인 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16f6e-114">설명</span><span class="sxs-lookup"><span data-stu-id="16f6e-114">Remarks</span></span>  
 <span data-ttu-id="16f6e-115">내에서 XML 요소는 `x:XData` 모든 가능한 네임 스페이스 및 접두사 포함 된 XMLDOM 데이터 내에서 개체 다시 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="16f6e-116">XML 데이터에 프로그래밍 방식 액세스 및 `x:XData` 내장 XAML 형식을 확장할 수를 통해.NET Framework XAML 서비스는 <xref:System.Windows.Markup.XData> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="16f6e-117">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="16f6e-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="16f6e-118">`x:XData` 의 자식 개체로 개체는 <xref:System.Windows.Data.XmlDataProvider>, 또는 또는의 자식 개체는 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 속성 (XAML에서이 일반적으로 표시 된 속성 요소 구문으로).</span><span class="sxs-lookup"><span data-stu-id="16f6e-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="16f6e-119">일반적으로 데이터 (빈 문자열로 설정)를 새 기본 XML 네임 스페이스는 데이터 아일랜드 내에서 기본 XML 네임 스페이스로 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="16f6e-120">간단한 데이터 아일랜드 때문에이 방법이 간편는 <xref:System.Windows.Data.Binding.XPath%2A> 참조 하 고 데이터에 바인딩 사용 되는 식 접두사 포함을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="16f6e-121">더 복잡 한 데이터 아일랜드 데이터에 대 한 여러 개의 접두사를 정의 하 고 루트에 XML 네임 스페이스에 대 한 특정 접두사를 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="16f6e-122">이 경우 모든 <xref:System.Windows.Data.Binding.XPath%2A> 식 참조는 적절 한 네임 스페이스 매핑 접두사를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="16f6e-123">자세한 내용은 [데이터 바인딩 개요](../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16f6e-123">For more information, see [Data Binding Overview](../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="16f6e-124">기술적으로 `x:XData` 유형의 속성의 내용으로 사용할 수 <xref:System.Xml.Serialization.IXmlSerializable>합니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="16f6e-125">그러나 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 주로 사용 되는 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="16f6e-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f6e-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16f6e-126">See Also</span></span>  
 <xref:System.Windows.Data.XmlDataProvider>  
 [<span data-ttu-id="16f6e-127">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="16f6e-127">Data Binding Overview</span></span>](../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="16f6e-128">Binding 태그 확장</span><span class="sxs-lookup"><span data-stu-id="16f6e-128">Binding Markup Extension</span></span>](../../../docs/framework/wpf/advanced/binding-markup-extension.md)
