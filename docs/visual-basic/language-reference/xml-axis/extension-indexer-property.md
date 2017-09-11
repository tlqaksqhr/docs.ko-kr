---
title: "확장 인덱서 속성 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 71c16d3f1b93647154bdead4a85d1117b5f6c463
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="fd13d-102">확장명 인덱서 속성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd13d-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="fd13d-103">컬렉션의 개별 요소에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd13d-104">구문</span><span class="sxs-lookup"><span data-stu-id="fd13d-104">Syntax</span></span>  
  
```  
  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="fd13d-105">요소</span><span class="sxs-lookup"><span data-stu-id="fd13d-105">Parts</span></span>  
  
|<span data-ttu-id="fd13d-106">용어</span><span class="sxs-lookup"><span data-stu-id="fd13d-106">Term</span></span>|<span data-ttu-id="fd13d-107">정의</span><span class="sxs-lookup"><span data-stu-id="fd13d-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="fd13d-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fd13d-108">Required.</span></span> <span data-ttu-id="fd13d-109">쿼리 가능 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-109">A queryable collection.</span></span> <span data-ttu-id="fd13d-110"><xref:System.Collections.Generic.IEnumerable%601>또는 <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> 를 구현 하는 컬렉션, 즉</span><span class="sxs-lookup"><span data-stu-id="fd13d-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="fd13d-111">(</span><span class="sxs-lookup"><span data-stu-id="fd13d-111">(</span></span>|<span data-ttu-id="fd13d-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fd13d-112">Required.</span></span> <span data-ttu-id="fd13d-113">인덱서 속성의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="fd13d-114">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fd13d-114">Required.</span></span> <span data-ttu-id="fd13d-115">컬렉션에 있는 요소의&0;부터 시작 위치를 지정 하는 정수 식입니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="fd13d-116">)</span><span class="sxs-lookup"><span data-stu-id="fd13d-116">)</span></span>|<span data-ttu-id="fd13d-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fd13d-117">Required.</span></span> <span data-ttu-id="fd13d-118">인덱서 속성의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="fd13d-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="fd13d-119">Return Value</span></span>  
 <span data-ttu-id="fd13d-120">컬렉션에서 지정된 된 위치에서 개체 또는 `Nothing` 경우 인덱스가 범위를 벗어났습니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd13d-121">주의</span><span class="sxs-lookup"><span data-stu-id="fd13d-121">Remarks</span></span>  
 <span data-ttu-id="fd13d-122">컬렉션의 개별 요소에 액세스 하는 확장 인덱서 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="fd13d-123">이 인덱서 속성은 일반적으로 XML 축 속성의 출력에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="fd13d-124">XML 자식 및 XML 하위 축 속성의 컬렉션을 반환 합니다. <xref:System.Xml.Linq.XElement>개체 또는 특성 값입니다.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="fd13d-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="fd13d-125">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에 대 한 호출을 확장 인덱서 속성을 변환의`ElementAtOrDefault` 메서드.</span><span class="sxs-lookup"><span data-stu-id="fd13d-125">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts extension indexer properties to calls to the`ElementAtOrDefault` method.</span></span> <span data-ttu-id="fd13d-126">배열 인덱서 달리는`ElementAtOrDefault` 메서드가 반환 `Nothing` 경우 인덱스가 범위를 벗어났습니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-126">Unlike an array indexer, the`ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="fd13d-127">이 동작은 컬렉션의 요소 수를 쉽게 확인할 수 없는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="fd13d-128">이 인덱서 속성을 구현 하는 컬렉션에 대 한 확장 속성 처럼 <xref:System.Collections.Generic.IEnumerable%601>또는 <xref:System.Linq.IQueryable%601>: 인덱서 또는 기본 속성 컬렉션에 없는 경우에 사용 됩니다.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="fd13d-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="fd13d-129">컬렉션의 첫 번째 요소 값에 액세스 하려면 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XAttribute>개체, XML을 사용할 수 있습니다 `Value` 속성.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="fd13d-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="fd13d-130">자세한 내용은 참조 [XML 값 속성](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd13d-131">예제</span><span class="sxs-lookup"><span data-stu-id="fd13d-131">Example</span></span>  
 <span data-ttu-id="fd13d-132">다음 예제에서는 컬렉션의 두 번째 자식 노드에 액세스 하는 확장 인덱서를 사용 하 여 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="fd13d-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="fd13d-133">이라는 모든 자식 요소를 가져오는 자식 축 속성을 사용 하 여 액세스 됩니다 `phone` 에 `contact` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 <span data-ttu-id="fd13d-134">[!code-vb[VbXMLSamples #&24;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="fd13d-134">[!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]</span></span>  
  
 <span data-ttu-id="fd13d-135">이 코드의 텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fd13d-135">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="fd13d-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd13d-136">See Also</span></span>  
 <span data-ttu-id="fd13d-137"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="fd13d-137"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="fd13d-138"> [XML 축 속성](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fd13d-138"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="fd13d-139"> [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="fd13d-139"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="fd13d-140"> [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="fd13d-140"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="fd13d-141"> [XML 값 속성](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)</span><span class="sxs-lookup"><span data-stu-id="fd13d-141"> [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)</span></span>
