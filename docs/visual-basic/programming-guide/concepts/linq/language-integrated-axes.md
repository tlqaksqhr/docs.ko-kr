---
title: Visual Basic의 언어 통합 축(LINQ to XML)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d450a556-a134-4261-b011-44e399660894
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8360281d1d8de0cad243297cd78e97958530bae4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="language-integrated-axes-in-visual-basic-linq-to-xml"></a><span data-ttu-id="0632a-102">Visual Basic의 언어 통합 축(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="0632a-102">Language-Integrated Axes in Visual Basic (LINQ to XML)</span></span>
<span data-ttu-id="0632a-103">이 섹션에서는 쉽게 XML에 액세스할 수 있도록 Visual Basic 언어에 직접 빌드된 기능에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0632a-103">This section describes features built directly into the Visual Basic language to make it easy to access XML.</span></span> <span data-ttu-id="0632a-104">많은 예제는 linq에서 to XML 설명서에는 이러한 통합된 Visual Basic 축 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0632a-104">Many of the examples in the LINQ to XML documentation use these integrated Visual Basic axes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0632a-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0632a-105">In This Section</span></span>  
  
|<span data-ttu-id="0632a-106">항목</span><span class="sxs-lookup"><span data-stu-id="0632a-106">Topic</span></span>|<span data-ttu-id="0632a-107">설명</span><span class="sxs-lookup"><span data-stu-id="0632a-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0632a-108">XML Child 축 속성</span><span class="sxs-lookup"><span data-stu-id="0632a-108">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="0632a-109"><xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체 컬렉션 중 하나의 자식에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0632a-109">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="0632a-110">이 축은 <xref:System.Xml.Linq.XContainer.Elements%2A> 축과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0632a-110">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>|  
|[<span data-ttu-id="0632a-111">XML Descendant 축 속성</span><span class="sxs-lookup"><span data-stu-id="0632a-111">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="0632a-112"><xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체 또는 <xref:System.Xml.Linq.XElement> 개체 컬렉션의 하위 항목에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0632a-112">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="0632a-113">이 축은 <xref:System.Xml.Linq.XContainer.Descendants%2A> 축과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0632a-113">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>|  
|[<span data-ttu-id="0632a-114">XML Attribute 축 속성</span><span class="sxs-lookup"><span data-stu-id="0632a-114">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="0632a-115"><xref:System.Xml.Linq.XElement> 개체의 특성에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0632a-115">Provides access to an attribute of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="0632a-116">이 축은 <xref:System.Xml.Linq.XElement.Attribute%2A> 축과 대체로 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0632a-116">This axis is roughly equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> axis.</span></span> <span data-ttu-id="0632a-117">이 축은 <xref:System.Xml.Linq.XElement.Attribute%2A> 개체가 아니라 특성의 값을 반환한다는 점에서 <xref:System.Xml.Linq.XAttribute> 축과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0632a-117">This axis differs from the <xref:System.Xml.Linq.XElement.Attribute%2A> axis in that it returns the value of the attribute, not an <xref:System.Xml.Linq.XAttribute> object.</span></span>|  
|[<span data-ttu-id="0632a-118">확장명 인덱서 속성</span><span class="sxs-lookup"><span data-stu-id="0632a-118">Extension Indexer Property</span></span>](../../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="0632a-119">컬렉션의 개별 요소에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0632a-119">Provides access to individual elements in a collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0632a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0632a-120">See Also</span></span>  
 [<span data-ttu-id="0632a-121">LINQ to XML 축(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0632a-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
