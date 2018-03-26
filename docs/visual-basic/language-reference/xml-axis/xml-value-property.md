---
title: XML Value 속성(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9294c2d1d83dce3bca2abc22ee9c70296fc8014
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2018
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="5aa2b-102">XML Value 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5aa2b-102">XML Value Property (Visual Basic)</span></span>
<span data-ttu-id="5aa2b-103">컬렉션의 첫 번째 요소 값에 대 한 액세스를 제공 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aa2b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5aa2b-104">Syntax</span></span>  
  
```  
object.Value  
```  
  
## <a name="parts"></a><span data-ttu-id="5aa2b-105">요소</span><span class="sxs-lookup"><span data-stu-id="5aa2b-105">Parts</span></span>  
  
|<span data-ttu-id="5aa2b-106">용어</span><span class="sxs-lookup"><span data-stu-id="5aa2b-106">Term</span></span>|<span data-ttu-id="5aa2b-107">정의</span><span class="sxs-lookup"><span data-stu-id="5aa2b-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="5aa2b-108">필수.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-108">Required.</span></span> <span data-ttu-id="5aa2b-109"><xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="5aa2b-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="5aa2b-110">Return Value</span></span>  
 <span data-ttu-id="5aa2b-111">A `String` 컬렉션의 첫 번째 요소 값이 포함 된 또는 `Nothing` 컬렉션이 비어 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5aa2b-112">설명</span><span class="sxs-lookup"><span data-stu-id="5aa2b-112">Remarks</span></span>  
 <span data-ttu-id="5aa2b-113"><xref:System.Xml.Linq.XElement.Value%2A> 속성을 사용 하면 컬렉션의 첫 번째 요소 값에 액세스 하기가 쉽지 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="5aa2b-114">이 속성은 먼저는 컬렉션 개체를 하나 이상 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="5aa2b-115">이 속성을 반환 하는 경우 컬렉션은 비어, `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="5aa2b-116">이 속성의 값을 반환 하는 그렇지 않은 경우는 <xref:System.Xml.Linq.XElement.Value%2A> 속성 컬렉션의 첫 번째 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5aa2b-117">사용 하 여 XML 특성의 값에 액세스할 때는 '@' 식별자, 특성 값으로 반환 됩니다는 `String` 명시적으로 지정할 필요가 없습니다는 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-117">When you access the value of an XML attribute using the '@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="5aa2b-118">컬렉션의 다른 요소에 액세스 하려면 XML 확장 인덱서 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="5aa2b-119">자세한 내용은 참조 [확장 인덱서 속성](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-119">For more information, see [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="5aa2b-120">상속</span><span class="sxs-lookup"><span data-stu-id="5aa2b-120">Inheritance</span></span>  
 <span data-ttu-id="5aa2b-121">대부분의 사용자가 구현 하지 않아도 됩니다 <xref:System.Collections.Generic.IEnumerable%601>, 및이 섹션을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>  
  
 <span data-ttu-id="5aa2b-122"><xref:System.Xml.Linq.XElement.Value%2A> 속성을 구현 하는 형식에 대 한 확장 속성은 `IEnumerable(Of XElement)`합니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="5aa2b-123">이 확장 속성의 바인딩을 확장 메서드의 바인딩과 같은:는 형식이 인터페이스 중 하나를 구현 하는 이름이 "Value" 속성을 정의 하는 경우 해당 속성 보다 우선적으로 확장 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="5aa2b-124">즉,이 <xref:System.Xml.Linq.XElement.Value%2A> 속성을 구현 하는 클래스의 새 속성을 정의 하 여 재정의할 수 있습니다 `IEnumerable(Of XElement)`합니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5aa2b-125">예제</span><span class="sxs-lookup"><span data-stu-id="5aa2b-125">Example</span></span>  
 <span data-ttu-id="5aa2b-126">사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Xml.Linq.XElement.Value%2A> 속성 컬렉션의 첫 번째 노드에 액세스 하려면 <xref:System.Xml.Linq.XElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="5aa2b-127">이 예제에서는 자식 축 속성 이라는 모든 자식 노드의 컬렉션을 사용 하 여 `phone` 에 `contact` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 <span data-ttu-id="5aa2b-128">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-128">This code displays the following text:</span></span>  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="5aa2b-129">예제</span><span class="sxs-lookup"><span data-stu-id="5aa2b-129">Example</span></span>  
 <span data-ttu-id="5aa2b-130">다음 예제에는 컬렉션에서 XML 특성의 값을 가져오는 방법을 보여 줍니다 <xref:System.Xml.Linq.XAttribute> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="5aa2b-131">이 예제에서는 특성 축 속성을 사용 하 여의 값을 표시 하는 `type` 특성의 모든는 `phone` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 <span data-ttu-id="5aa2b-132">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5aa2b-132">This code displays the following text:</span></span>  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a><span data-ttu-id="5aa2b-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5aa2b-133">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="5aa2b-134">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="5aa2b-134">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="5aa2b-135">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="5aa2b-135">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="5aa2b-136">Visual Basic에서 XML 만들기</span><span class="sxs-lookup"><span data-stu-id="5aa2b-136">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="5aa2b-137">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="5aa2b-137">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="5aa2b-138">확장명 인덱서 속성</span><span class="sxs-lookup"><span data-stu-id="5aa2b-138">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)  
 [<span data-ttu-id="5aa2b-139">XML Child 축 속성</span><span class="sxs-lookup"><span data-stu-id="5aa2b-139">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [<span data-ttu-id="5aa2b-140">XML Attribute 축 속성</span><span class="sxs-lookup"><span data-stu-id="5aa2b-140">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
