---
title: "Visual Basic (LINQ to XML)의 언어 통합 축 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d450a556-a134-4261-b011-44e399660894
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7ca88aed0772f4fb93ab561af4bd9a1129cbf3c5
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="language-integrated-axes-in-visual-basic-linq-to-xml"></a><span data-ttu-id="fce5d-102">Visual Basic의 언어 통합 축(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="fce5d-102">Language-Integrated Axes in Visual Basic (LINQ to XML)</span></span>
<span data-ttu-id="fce5d-103">이 섹션에 직접 빌드된 기능에 설명 된 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 쉽게 XML에 액세스 하는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="fce5d-103">This section describes features built directly into the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] language to make it easy to access XML.</span></span> <span data-ttu-id="fce5d-104">LINQ to XML 설명서의 많은 예제에서는 이러한 통합된 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 축을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fce5d-104">Many of the examples in the LINQ to XML documentation use these integrated [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] axes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fce5d-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="fce5d-105">In This Section</span></span>  
  
|<span data-ttu-id="fce5d-106">항목</span><span class="sxs-lookup"><span data-stu-id="fce5d-106">Topic</span></span>|<span data-ttu-id="fce5d-107">설명</span><span class="sxs-lookup"><span data-stu-id="fce5d-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fce5d-108">XML Child 축 속성</span><span class="sxs-lookup"><span data-stu-id="fce5d-108">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="fce5d-109">다음 중 하나의 자식에 액세스할 수:는 <xref:System.Xml.Linq.XElement>개체는 <xref:System.Xml.Linq.XDocument>개체, 컬렉션을 <xref:System.Xml.Linq.XElement>개체 또는 컬렉션을 <xref:System.Xml.Linq.XDocument>개체.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="fce5d-109">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="fce5d-110">이 축이에 해당 하는 <xref:System.Xml.Linq.XContainer.Elements%2A>축.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="fce5d-110">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>|  
|[<span data-ttu-id="fce5d-111">XML Descendant 축 속성</span><span class="sxs-lookup"><span data-stu-id="fce5d-111">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="fce5d-112">다음의 하위 항목에 대 한 액세스를 제공:는 <xref:System.Xml.Linq.XElement>개체는 <xref:System.Xml.Linq.XDocument>개체 또는 컬렉션을 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="fce5d-112">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="fce5d-113">이 축이에 해당 하는 <xref:System.Xml.Linq.XContainer.Descendants%2A>축.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="fce5d-113">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>|  
|[<span data-ttu-id="fce5d-114">XML Attribute 축 속성</span><span class="sxs-lookup"><span data-stu-id="fce5d-114">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="fce5d-115">특성에 대 한 액세스를 제공 된 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="fce5d-115">Provides access to an attribute of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="fce5d-116">이 축은 거의 동일한는 <xref:System.Xml.Linq.XElement.Attribute%2A>축.</xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="fce5d-116">This axis is roughly equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> axis.</span></span> <span data-ttu-id="fce5d-117">이 축에서 다른는 <xref:System.Xml.Linq.XElement.Attribute%2A>축에는 특성의 값을 아니라 반환 한다는 <xref:System.Xml.Linq.XAttribute>개체.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="fce5d-117">This axis differs from the <xref:System.Xml.Linq.XElement.Attribute%2A> axis in that it returns the value of the attribute, not an <xref:System.Xml.Linq.XAttribute> object.</span></span>|  
|[<span data-ttu-id="fce5d-118">확장명 인덱서 속성</span><span class="sxs-lookup"><span data-stu-id="fce5d-118">Extension Indexer Property</span></span>](../../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="fce5d-119">컬렉션의 개별 요소에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fce5d-119">Provides access to individual elements in a collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fce5d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fce5d-120">See Also</span></span>  
 [<span data-ttu-id="fce5d-121">LINQ to XML 축 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fce5d-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
