---
title: "자습서: WordprocessingML 문서에서 내용 조작(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bc9815f8-13d2-4f50-a4d1-b1c0d50d37b3
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3ddd3f35d1a1b6761aace8460aceda638f169f05
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="tutorial-manipulating-content-in-a-wordprocessingml-document-c"></a><span data-ttu-id="e4033-102">자습서: WordprocessingML 문서에서 내용 조작(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-102">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>
<span data-ttu-id="e4033-103">이 자습서에서는 함수 변환 방법과 LINQ to XML을 적용하여 XML 문서를 조작하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4033-103">This tutorial shows how to apply the functional transformational approach and LINQ to XML to manipulate XML documents.</span></span> <span data-ttu-id="e4033-104">C# 예제에서는 Microsoft Word에서 저장한 Office Open XML WordprocessingML 문서의 정보를 쿼리하고 조작합니다.</span><span class="sxs-lookup"><span data-stu-id="e4033-104">The C# examples query and manipulate information in Office Open XML WordprocessingML documents that are saved by Microsoft Word.</span></span>  
  
 <span data-ttu-id="e4033-105">자세한 내용은 [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) 웹 사이트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4033-105">For more information, see the [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) Web site.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4033-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="e4033-106">In This Section</span></span>  
  
|<span data-ttu-id="e4033-107">항목</span><span class="sxs-lookup"><span data-stu-id="e4033-107">Topic</span></span>|<span data-ttu-id="e4033-108">설명</span><span class="sxs-lookup"><span data-stu-id="e4033-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e4033-109">WordprocessingML 문서의 모양(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-109">Shape of WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md)|<span data-ttu-id="e4033-110">WordprocessingML 문서에 대해 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e4033-110">Provides a quick explanation of details of a WordprocessingML document.</span></span>|  
|[<span data-ttu-id="e4033-111">원본 Office Open XML 문서 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-111">Creating the Source Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)|<span data-ttu-id="e4033-112">이 자습서의 쿼리에 대한 소스 문서를 만드는 단계별 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4033-112">Provides step-by-step instructions to create the source document for queries in this tutorial.</span></span>|  
|[<span data-ttu-id="e4033-113">기본 단락 스타일 찾기(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-113">Finding the Default Paragraph Style (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)|<span data-ttu-id="e4033-114">문서에 대한 기본 스타일의 이름을 찾는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4033-114">Shows a query to find the name of the default style for a document.</span></span>|  
|[<span data-ttu-id="e4033-115">단락 및 해당 스타일 검색(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-115">Retrieving the Paragraphs and Their Styles (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)|<span data-ttu-id="e4033-116">문서의 단락 컬렉션을 검색하는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4033-116">Shows a query that retrieves a collection of the paragraphs of a document.</span></span>|  
|[<span data-ttu-id="e4033-117">단락의 텍스트 검색(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-117">Retrieving the Text of the Paragraphs (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)|<span data-ttu-id="e4033-118">이전 쿼리를 확대하여 각 단락의 텍스트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e4033-118">Augments the previous query to retrieve the text of each paragraph.</span></span>|  
|[<span data-ttu-id="e4033-119">확장 메서드를 사용하여 리팩터링(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-119">Refactoring Using an Extension Method (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)|<span data-ttu-id="e4033-120">확장명 메서드를 통해 리팩터링하여 코드를 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="e4033-120">Simplifies the code by refactoring using an extension method.</span></span>|  
|[<span data-ttu-id="e4033-121">순수 함수를 사용하여 리팩터링(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-121">Refactoring Using a Pure Function (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)|<span data-ttu-id="e4033-122">순수 함수를 통해 리팩터링하여 코드를 더 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="e4033-122">Further simplifies the code by refactoring using a pure function.</span></span>|  
|[<span data-ttu-id="e4033-123">다른 모양으로 XML 프로젝션(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-123">Projecting XML in a Different Shape (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projecting-xml-in-a-different-shape.md)|<span data-ttu-id="e4033-124">원래 문서와 다른 모양으로 XML을 프로젝션하여 XML 변환을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="e4033-124">Completes an XML transformation by projecting XML in a different shape than the original document.</span></span>|  
|[<span data-ttu-id="e4033-125">Word 문서에서 텍스트 찾기(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-125">Finding Text in Word Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/finding-text-in-word-documents.md)|<span data-ttu-id="e4033-126">이전 쿼리를 사용하여 문서에서 지정된 텍스트 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e4033-126">Uses the previous queries to find a specified text string in a document.</span></span>|  
|[<span data-ttu-id="e4033-127">Office Open XML WordprocessingML 문서 정보(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-127">Details of Office Open XML WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)|<span data-ttu-id="e4033-128">Office Open XML WordprocessingML 문서에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e4033-128">Provides some details of Office Open XML WordprocessingML documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4033-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4033-129">See Also</span></span>  
 [<span data-ttu-id="e4033-130">XML의 순수 함수 변환(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-130">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)  
 [<span data-ttu-id="e4033-131">순수 함수 변환 소개(C#)</span><span class="sxs-lookup"><span data-stu-id="e4033-131">Introduction to Pure Functional Transformations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
