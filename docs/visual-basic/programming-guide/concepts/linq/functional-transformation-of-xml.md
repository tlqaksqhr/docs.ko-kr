---
title: "XML (Visual Basic)의 함수 변환 | Microsoft 문서"
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
ms.assetid: fdbe5b91-f457-4b4e-a11b-def4bdd77bab
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8c41d464d5b214520ca5e36877fb59d45c851786
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="functional-transformation-of-xml-visual-basic"></a><span data-ttu-id="0dccd-102">XML (Visual Basic)의 함수 변환</span><span class="sxs-lookup"><span data-stu-id="0dccd-102">Functional Transformation of XML (Visual Basic)</span></span>
<span data-ttu-id="0dccd-103">이 항목에서는 XML 문서를 수정하는 순수 함수 변형 방법에 대해 설명하고 이 방법을 절차적 방법과 대조합니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-103">This topic discusses the pure functional transformation approach to modifying XML documents, and contrasts it with a procedural approach.</span></span>  
  
## <a name="modifying-an-xml-document"></a><span data-ttu-id="0dccd-104">XML 문서 수정</span><span class="sxs-lookup"><span data-stu-id="0dccd-104">Modifying an XML Document</span></span>  
 <span data-ttu-id="0dccd-105">XML 프로그래머의 가장 일반적인 작업 중 하나는 XML의 모양을 변환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-105">One of the most common tasks for an XML programmer is transforming XML from one shape to another.</span></span> <span data-ttu-id="0dccd-106">XML 문서의 모양은 다음이 포함된 문서의 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-106">The shape of an XML document is the structure of the document, which includes the following:</span></span>  
  
-   <span data-ttu-id="0dccd-107">문서로 표현되는 계층 구조</span><span class="sxs-lookup"><span data-stu-id="0dccd-107">The hierarchy expressed by the document.</span></span>  
  
-   <span data-ttu-id="0dccd-108">요소 및 특성의 이름</span><span class="sxs-lookup"><span data-stu-id="0dccd-108">The element and attribute names.</span></span>  
  
-   <span data-ttu-id="0dccd-109">요소 및 특성의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="0dccd-109">The data types of the elements and attributes.</span></span>  
  
 <span data-ttu-id="0dccd-110">일반적으로 XML의 모양을 변환하는 가장 효과적인 방법은 순수 함수 변환 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-110">In general, the most effective approach to transforming XML from one shape to another is that of pure functional transformation.</span></span> <span data-ttu-id="0dccd-111">이 방법에서 프로그래머의 주요 작업은 전체 XML 문서나 엄격하게 정의된 하나 이상의 노드에 적용되는 변환을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-111">In this approach, the primary programmer task is to create a transformation which is applied to the entire XML document (or to one or more strictly defined nodes).</span></span> <span data-ttu-id="0dccd-112">함수 변환은 프로그래머가 방법을 익히고 나면 코딩하기가 가장 쉽고 유지 관리가 가장 쉬운 코드를 생성하며 다른 방법보다 간단한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-112">Functional transformation is arguably the easiest to code (after a programmer is familiar with the approach), yields the most maintainable code, and is often more compact than alternative approaches.</span></span>  
  
### <a name="xml-functional-transformational-technologies"></a><span data-ttu-id="0dccd-113">XML 함수 변환 기술</span><span class="sxs-lookup"><span data-stu-id="0dccd-113">XML Functional Transformational Technologies</span></span>  
 <span data-ttu-id="0dccd-114">Microsoft는 XML 문서에서 사용할 수 있는 두 가지 함수 변형 기술인 XSLT와 LINQ to XML을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-114">Microsoft offers two functional transformation technologies for use on XML documents: XSLT and LINQ to XML.</span></span> <span data-ttu-id="0dccd-115">XSLT에서 사용할 수는 <xref:System.Xml.Xsl>관리 네임 스페이스와 MSXML의 네이티브 COM 구현.</xref:System.Xml.Xsl></span><span class="sxs-lookup"><span data-stu-id="0dccd-115">XSLT is supported in the <xref:System.Xml.Xsl> managed namespace and in the native COM implementation of MSXML.</span></span> <span data-ttu-id="0dccd-116">XSLT가 XML 문서를 조작하는 강력한 기술이긴 하지만 XSLT 언어 및 지원 API와 같은 특수화된 영역의 전문 지식을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-116">Although XSLT is a robust technology for manipulating XML documents, it requires expertise in a specialized domain, namely the XSLT language and its supporting APIs.</span></span>  
  
 <span data-ttu-id="0dccd-117">LINQ to XML은 C# 또는 Visual Basic 코드에서 표현이 다양하고 강력한 방법으로 순수 함수 변환을 코딩하는 데 필요한 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-117">LINQ to XML provides the tools necessary to code pure functional transformations in an expressive and powerful way, within C# or Visual Basic code.</span></span> <span data-ttu-id="0dccd-118">예를 들어, LINQ to XML 설명서의 많은 예제에서는 순수 함수 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-118">For example, many of the examples in the LINQ to XML documentation use a pure functional approach.</span></span> <span data-ttu-id="0dccd-119">또한는 [자습서: WordprocessingML 문서 (Visual Basic)에서 내용 조작](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) 자습서에서는 사용 하 여 LINQ to XML 함수 접근 방법에서 Microsoft Word 문서에서 정보를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-119">Also, in the [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial, we use LINQ to XML in a functional approach to manipulate information in a Microsoft Word document.</span></span>  
  
 <span data-ttu-id="0dccd-120">다른 Microsoft XML 기술과 함께 LINQ to XML의 자세한 비교를 참조 하십시오. [LINQ to XML과 합니다. 다른 XML 기술과](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-120">For a more complete comparison of LINQ to XML with other Microsoft XML technologies, see [LINQ to XML vs. Other XML Technologies](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).</span></span>  
  
 <span data-ttu-id="0dccd-121">XSLT는 소스 문서의 구조가 불규칙적인 경우 문서 중심적인 변환에 권장되는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-121">XSLT is the recommended tool for  document-centric transformations when the source document has an irregular structure.</span></span> <span data-ttu-id="0dccd-122">그러나 LINQ to XML도 문서 중심적 변형을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-122">However, LINQ to XML can also perform document-centric transforms.</span></span> <span data-ttu-id="0dccd-123">자세한 내용은 참조 [하는 방법: XSLT 스타일 (Visual Basic)에서 XML 트리를 변환 LINQ를 사용 하 여 주석을](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0dccd-123">For more information, see [How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dccd-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0dccd-124">See Also</span></span>  
 <span data-ttu-id="0dccd-125">[순수 함수 변환 (Visual Basic) 소개](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="0dccd-125">[Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span></span>  
<span data-ttu-id="0dccd-126"> [LINQ to XML과 기타 XML 기술 비교](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md) </span><span class="sxs-lookup"><span data-stu-id="0dccd-126"> [LINQ to XML vs. Other XML Technologies](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md) </span></span>  
<span data-ttu-id="0dccd-127"> [LINQ to XML과 기타 XML 기술 비교](http://msdn.microsoft.com/library/7ba1eecf-f09a-42de-bc80-22ca5b2e42d3)</span><span class="sxs-lookup"><span data-stu-id="0dccd-127"> [LINQ to XML vs. Other XML Technologies](http://msdn.microsoft.com/library/7ba1eecf-f09a-42de-bc80-22ca5b2e42d3)</span></span>
