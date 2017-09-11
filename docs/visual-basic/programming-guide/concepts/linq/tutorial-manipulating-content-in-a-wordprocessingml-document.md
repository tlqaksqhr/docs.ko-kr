---
title: "자습서: WordprocessingML 문서 (Visual Basic)에서 내용 조작 | Microsoft 문서"
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
ms.assetid: f8028ba8-2dd1-4425-930c-8cc23176ebbc
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 28ab2d19cba0344868061fbe1f59c546a569fbdc
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="tutorial-manipulating-content-in-a-wordprocessingml-document-visual-basic"></a><span data-ttu-id="36bc0-102">자습서: WordprocessingML 문서 (Visual Basic)에서 내용 조작</span><span class="sxs-lookup"><span data-stu-id="36bc0-102">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>
<span data-ttu-id="36bc0-103">이 자습서에서는 함수 변형 방법과 LINQ to XML을 적용하여 XML 문서를 조작하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-103">This tutorial shows how to apply the functional transformational approach and LINQ to XML to manipulate XML documents.</span></span> <span data-ttu-id="36bc0-104">Visual Basic 예제 쿼리 및 Microsoft Word에서 저장 하는 Office Open XML WordprocessingML 문서에서 정보를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-104">The Visual Basic examples query and manipulate information in Office Open XML WordprocessingML documents that are saved by Microsoft Word.</span></span>  
  
 <span data-ttu-id="36bc0-105">자세한 내용은 참조는 [OpenXML 개발자](http://go.microsoft.com/fwlink/?LinkID=95573) 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-105">For more information, see the [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) Web site.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36bc0-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="36bc0-106">In This Section</span></span>  
  
|<span data-ttu-id="36bc0-107">항목</span><span class="sxs-lookup"><span data-stu-id="36bc0-107">Topic</span></span>|<span data-ttu-id="36bc0-108">설명</span><span class="sxs-lookup"><span data-stu-id="36bc0-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="36bc0-109">(Visual Basic) WordprocessingML 문서의 모양</span><span class="sxs-lookup"><span data-stu-id="36bc0-109">Shape of WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md)|<span data-ttu-id="36bc0-110">WordprocessingML 문서에 대해 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-110">Provides a quick explanation of details of a WordprocessingML document.</span></span>|  
|[<span data-ttu-id="36bc0-111">원본 Office Open XML 문서 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="36bc0-111">Creating the Source Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)|<span data-ttu-id="36bc0-112">이 자습서의 쿼리에 대한 소스 문서를 만드는 단계별 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-112">Provides step-by-step instructions to create the source document for queries in this tutorial.</span></span>|  
|[<span data-ttu-id="36bc0-113">(Visual Basic)의 기본 단락 스타일 찾기</span><span class="sxs-lookup"><span data-stu-id="36bc0-113">Finding the Default Paragraph Style (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)|<span data-ttu-id="36bc0-114">문서에 대한 기본 스타일의 이름을 찾는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-114">Shows a query to find the name of the default style for a document.</span></span>|  
|[<span data-ttu-id="36bc0-115">단락 및 해당 스타일 (Visual Basic) 검색</span><span class="sxs-lookup"><span data-stu-id="36bc0-115">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)|<span data-ttu-id="36bc0-116">문서의 단락 컬렉션을 검색하는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-116">Shows a query that retrieves a collection of the paragraphs of a document.</span></span>|  
|[<span data-ttu-id="36bc0-117">(Visual Basic) 단락의 텍스트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-117">Retrieving the Text of the Paragraphs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)|<span data-ttu-id="36bc0-118">이전 쿼리를 확대하여 각 단락의 텍스트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-118">Augments the previous query to retrieve the text of each paragraph.</span></span>|  
|[<span data-ttu-id="36bc0-119">확장 메서드 (Visual Basic)를 사용 하 여 리팩터링</span><span class="sxs-lookup"><span data-stu-id="36bc0-119">Refactoring Using an Extension Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)|<span data-ttu-id="36bc0-120">확장명 메서드를 통해 리팩터링하여 코드를 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-120">Simplifies the code by refactoring using an extension method.</span></span>|  
|[<span data-ttu-id="36bc0-121">순수 함수 (Visual Basic)를 사용 하 여 리팩터링</span><span class="sxs-lookup"><span data-stu-id="36bc0-121">Refactoring Using a Pure Function (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)|<span data-ttu-id="36bc0-122">순수 함수를 통해 리팩터링하여 코드를 더 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-122">Further simplifies the code by refactoring using a pure function.</span></span>|  
|[<span data-ttu-id="36bc0-123">(Visual Basic)을 다른 모양으로 XML 프로젝션</span><span class="sxs-lookup"><span data-stu-id="36bc0-123">Projecting XML in a Different Shape (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projecting-xml-in-a-different-shape.md)|<span data-ttu-id="36bc0-124">원래 문서와 다른 모양으로 XML을 프로젝션하여 XML 변환을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-124">Completes an XML transformation by projecting XML in a different shape than the original document.</span></span>|  
|[<span data-ttu-id="36bc0-125">(Visual Basic) Word 문서에서 텍스트 찾기</span><span class="sxs-lookup"><span data-stu-id="36bc0-125">Finding Text in Word Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/finding-text-in-word-documents.md)|<span data-ttu-id="36bc0-126">이전 쿼리를 사용하여 문서에서 지정된 텍스트 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-126">Uses the previous queries to find a specified text string in a document.</span></span>|  
|[<span data-ttu-id="36bc0-127">세부 정보는 Office Open XML WordprocessingML 문서 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36bc0-127">Details of Office Open XML WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)|<span data-ttu-id="36bc0-128">Office Open XML WordprocessingML 문서에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="36bc0-128">Provides some details of Office Open XML WordprocessingML documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36bc0-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36bc0-129">See Also</span></span>  
 <span data-ttu-id="36bc0-130">[(Visual Basic) XML의 순수 함수 변환](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span><span class="sxs-lookup"><span data-stu-id="36bc0-130">[Pure Functional Transformations of XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span></span>  
<span data-ttu-id="36bc0-131"> [순수 함수 변환 (Visual Basic) 소개](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)</span><span class="sxs-lookup"><span data-stu-id="36bc0-131"> [Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)</span></span>
