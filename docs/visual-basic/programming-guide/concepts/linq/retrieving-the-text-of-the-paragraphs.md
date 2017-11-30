---
title: "(Visual Basic) 단락의 텍스트 검색"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 095fa0d9-7b1b-4cbb-9c13-e2c9d8923d31
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 492fc0dffd007f0ccdb7454c62e86cac753ca06b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-the-text-of-the-paragraphs-visual-basic"></a><span data-ttu-id="05c39-102">(Visual Basic) 단락의 텍스트 검색</span><span class="sxs-lookup"><span data-stu-id="05c39-102">Retrieving the Text of the Paragraphs (Visual Basic)</span></span>
<span data-ttu-id="05c39-103">이 예제에서는 앞의 예에서 [단락 및 (Visual Basic) 해당 스타일 검색](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-103">This example builds on the previous example, [Retrieving the Paragraphs and Their Styles (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md).</span></span> <span data-ttu-id="05c39-104">이 새 예제에서는 각 단락의 텍스트를 문자열로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-104">This new example retrieves the text of each paragraph as a string.</span></span>  
  
 <span data-ttu-id="05c39-105">이 예제에서는 텍스트를 검색하기 위해 익명 형식의 컬렉션을 반복하는 추가 쿼리를 추가하고 새 멤버 `Text`가 추가된 익명 형식의 새 컬렉션을 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-105">To retrieve the text, this example adds an additional query that iterates through the collection of anonymous types and projects a new collection of an anonymous type with the addition of a new member, `Text`.</span></span> <span data-ttu-id="05c39-106">또한 <xref:System.Linq.Enumerable.Aggregate%2A> 표준 쿼리 연산자를 사용하여 여러 문자열을 한 문자열로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-106">It uses the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span>  
  
 <span data-ttu-id="05c39-107">먼저 익명 형식의 컬렉션을 프로젝션한 다음 이 컬렉션을 사용하여 익명 형식의 새 컬렉션을 프로젝션하는 방법은 일반적이고 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-107">This technique (that is, first projecting to a collection of an anonymous type, then using this collection to project to a new collection of an anonymous type) is a common and useful idiom.</span></span> <span data-ttu-id="05c39-108">이 쿼리는 첫 번째 익명 형식으로 프로젝션하지 않고 작성될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-108">This query could have been written without projecting to the first anonymous type.</span></span> <span data-ttu-id="05c39-109">그러나 지연 계산 때문에 이렇게 해도 추가 처리 능력이 많이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-109">However, because of lazy evaluation, doing so does not use much additional processing power.</span></span> <span data-ttu-id="05c39-110">이 방법은 힙에서 수명이 짧은 개체를 더 많이 만들지만 이로 인해 성능이 크게 저하되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-110">The idiom creates more short lived objects on the heap, but this does not substantially degrade performance.</span></span>  
  
 <span data-ttu-id="05c39-111">물론 단락, 각 단락의 스타일 및 각 단락의 텍스트를 검색하는 기능이 포함된 단일 쿼리를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-111">Of course, it would be possible to write a single query that contains the functionality to retrieve the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="05c39-112">그러나 복잡한 쿼리를 여러 쿼리로 나누면 생성되는 코드가 더욱 모듈화되고 유지 관리가 쉬워지기 때문에 유용한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-112">However, it often is useful to break up a more complicated query into multiple queries because the resulting code is more modular and easier to maintain.</span></span> <span data-ttu-id="05c39-113">또한 쿼리의 일부를 다시 사용해야 하는 경우 쿼리가 이런 방식으로 작성되면 리팩터링하기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-113">Furthermore, if you need to reuse a portion of the query, it is easier to refactor if the queries are written in this manner.</span></span>  
  
 <span data-ttu-id="05c39-114">이 항목에서 자세히 검사 하는 처리 모델을 사용 하는 모두 연결 되어 있는 이러한 쿼리 [자습서: 지연 된 실행 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-114">These queries, which are chained together, use the processing model that is examined in detail in the topic [Tutorial: Deferred Execution (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="05c39-115">예제</span><span class="sxs-lookup"><span data-stu-id="05c39-115">Example</span></span>  
 <span data-ttu-id="05c39-116">이 예제에서는 WordprocessingML 문서를 처리하여 요소 노드, 스타일 이름 및 각 단락의 텍스트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-116">This example processes a WordprocessingML document, determining the element node, the style name, and the text of each paragraph.</span></span> <span data-ttu-id="05c39-117">이 예제는 이 자습서의 이전 예제를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-117">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="05c39-118">새 쿼리는 아래에 있는 코드의 주석에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-118">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="05c39-119">이 예제에 대 한 소스 문서를 만들기 위한 지침은 [원본 Office Open XML 문서 (Visual Basic)를 만드는](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-119">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="05c39-120">이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고</span><span class="sxs-lookup"><span data-stu-id="05c39-120">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="05c39-121"><xref:System.IO.Packaging?displayProperty=nameWithType> 네임스페이스의 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-121">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    ' Following function is required because VB does not support short circuit evaluation  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, _  
                                         ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = _  
          "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    '  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        Dim defaultStyle As String = _  
            ( _  
                From style In styleDoc.Root.<w:style> _  
                Where style.@w:type = "paragraph" And _  
                      style.@w:default = "1" _  
                Select style _  
            ).First().@w:styleId  
  
        ' Find all paragraphs in the document.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        ' Following is the new query that retrieves the text of  
        ' each paragraph.  
        Dim paraWithText = _  
            From para In paragraphs _  
            Select New With { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = para.ParagraphNode.<w:r>.<w:t> _  
                    .Aggregate(New StringBuilder(), _  
                               Function(s As StringBuilder, i As String) s.Append(CStr(i)), _  
                               Function(s As StringBuilder) s.ToString) _  
            }  
  
        For Each p In paraWithText  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text)  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="05c39-122">이 예제는 다음에 설명 된 문서에 적용 하면 출력 [원본 Office Open XML 문서 (Visual Basic)를 만드는](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-122">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
```  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >Imports System<  
StyleName:Code ><  
StyleName:Code >Class Program<  
StyleName:Code >    Public Shared  Sub Main(ByVal args() As String)<  
StyleName:Code >        Console.WriteLine("Hello World")<  
StyleName:Code >   End Sub<  
StyleName:Code >End Class<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
## <a name="next-steps"></a><span data-ttu-id="05c39-123">다음 단계</span><span class="sxs-lookup"><span data-stu-id="05c39-123">Next Steps</span></span>  
 <span data-ttu-id="05c39-124">다음 예제에서는 <xref:System.Linq.Enumerable.Aggregate%2A> 대신 확장 메서드를 사용하여 여러 문자열을 하나의 문자열로 연결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05c39-124">The next example shows how to use an extension method, instead of <xref:System.Linq.Enumerable.Aggregate%2A>, to concatenate multiple strings into a single string.</span></span>  
  
-   [<span data-ttu-id="05c39-125">확장 메서드 (Visual Basic)를 사용 하 여 리팩터링</span><span class="sxs-lookup"><span data-stu-id="05c39-125">Refactoring Using an Extension Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="05c39-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05c39-126">See Also</span></span>  
 [<span data-ttu-id="05c39-127">자습서: WordprocessingML 문서 (Visual Basic)에서 내용 조작</span><span class="sxs-lookup"><span data-stu-id="05c39-127">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)  
 [<span data-ttu-id="05c39-128">지연 된 실행과 지연 계산은 linq to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05c39-128">Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
