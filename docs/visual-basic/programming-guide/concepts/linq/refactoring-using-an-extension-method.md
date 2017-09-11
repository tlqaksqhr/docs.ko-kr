---
title: "확장 메서드 (Visual Basic)를 사용 하 여 리팩터링 | Microsoft 문서"
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
ms.assetid: d87ae99a-cfa9-4a31-a5e4-9d6437be6810
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4f84013ba1438196c80cb7835c6c8152561e5f74
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="refactoring-using-an-extension-method-visual-basic"></a><span data-ttu-id="b4e32-102">확장 메서드 (Visual Basic)를 사용 하 여 리팩터링</span><span class="sxs-lookup"><span data-stu-id="b4e32-102">Refactoring Using an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="b4e32-103">이 예제에서는 앞의 예에서 [(Visual Basic) 단락의 텍스트 검색](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), 확장 메서드로 구현 되는 순수 함수를 사용 하 여 문자열의 연결을 리팩터링 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-103">This example builds on the previous example, [Retrieving the Text of the Paragraphs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), by refactoring the concatenation of strings using a pure function that is implemented as an extension method.</span></span>  
  
 <span data-ttu-id="b4e32-104">사용 되는 이전 예제에서 <xref:System.Linq.Enumerable.Aggregate%2A>표준 쿼리 연산자를 여러 문자열을 하나의 문자열로 연결 합니다.</xref:System.Linq.Enumerable.Aggregate%2A></span><span class="sxs-lookup"><span data-stu-id="b4e32-104">The previous example used the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span> <span data-ttu-id="b4e32-105">그러나 생성되는 쿼리가 더 작고 간단하기 때문에 이 작업을 수행하는 확장명 메서드를 작성하는 것이 간편합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-105">However, it is more convenient to write an extension method to do this, because the resulting query smaller and more simple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4e32-106">예제</span><span class="sxs-lookup"><span data-stu-id="b4e32-106">Example</span></span>  
 <span data-ttu-id="b4e32-107">이 예제에서는 WordprocessingML 문서를 처리하여 단락, 각 단락의 스타일 및 각 단락의 텍스트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-107">This example processes a WordprocessingML document, retrieving the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="b4e32-108">이 예제는 이 자습서의 이전 예제를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-108">This example builds on the previous examples in this tutorial.</span></span>  
  
 <span data-ttu-id="b4e32-109">이 예제에는 `StringConcatenate` 메서드의 오버로드가 여러 개 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-109">The example contains multiple overloads of the `StringConcatenate` method.</span></span>  
  
 <span data-ttu-id="b4e32-110">이 예제에 대 한 소스 문서를 만들기 위한 지침을 찾을 수 있습니다 [원본 Office Open XML 문서 (Visual Basic)를 만드는](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-110">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="b4e32-111">이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고</span><span class="sxs-lookup"><span data-stu-id="b4e32-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="b4e32-112">형식을 사용는 <xref:System.IO.Packaging?displayProperty=fullName>네임 스페이스.</xref:System.IO.Packaging?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b4e32-112">It uses types in the <xref:System.IO.Packaging?displayProperty=fullName> namespace.</span></span>  
  
```vb  
<System.Runtime.CompilerServices.Extension()> _  
Public Function StringConcatenate(ByVal source As IEnumerable(Of String)) As String  
    Dim sb As StringBuilder = New StringBuilder()  
    For Each s As String In source  
        sb.Append(s)  
    Next  
    Return sb.ToString()  
End Function  
  
<System.Runtime.CompilerServices.Extension()> _  
Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
ByVal func As Func(Of T, String)) As String  
    Dim sb As StringBuilder = New StringBuilder()  
    For Each item As T In source  
        sb.Append(func(item))  
    Next  
    Return sb.ToString()  
End Function  
  
<System.Runtime.CompilerServices.Extension()> _  
Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
ByVal separator As String) As String  
    Dim sb As StringBuilder = New StringBuilder()  
    For Each s As T In source  
        sb.Append(s).Append(separator)  
    Next  
    Return sb.ToString()  
End Function  
  
<System.Runtime.CompilerServices.Extension()> _  
Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
ByVal func As Func(Of T, String), ByVal separator As String) As String  
    Dim sb As StringBuilder = New StringBuilder()  
    For Each item As T In source  
        sb.Append(func(item)).Append(separator)  
    Next  
    Return sb.ToString()  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="b4e32-113">예제</span><span class="sxs-lookup"><span data-stu-id="b4e32-113">Example</span></span>  
 <span data-ttu-id="b4e32-114">`StringConcatenate` 메서드의 오버로드는 네 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-114">There are four overloads of the `StringConcatenate` method.</span></span> <span data-ttu-id="b4e32-115">한 오버로드는 문자열의 컬렉션을 가져와서 단일 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-115">One overload simply takes a collection of strings and returns a single string.</span></span> <span data-ttu-id="b4e32-116">다른 오버로드는 원하는 형식의 컬렉션과 컬렉션의 singleton에서 문자열로 프로젝션하는 대리자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-116">Another overload can take a collection of any type, and a delegate that projects from a singleton of the collection to a string.</span></span> <span data-ttu-id="b4e32-117">나머지 두 오버로드는 구분 기호 문자열을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-117">There are two more overloads that allow you to specify a separator string.</span></span>  
  
 <span data-ttu-id="b4e32-118">다음 코드에서는 네 오버로드를 모두 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-118">The following code uses all four overloads.</span></span>  
  
```vb  
Dim numbers As String() = {"one", "two", "three"}  
  
Console.WriteLine("{0}", numbers.StringConcatenate())  
Console.WriteLine("{0}", numbers.StringConcatenate(":"))  
  
Dim intNumbers As Integer() = {1, 2, 3}  
Console.WriteLine("{0}", intNumbers.StringConcatenate(Function(i) i.ToString()))  
Console.WriteLine("{0}", intNumbers.StringConcatenate(Function(i) i.ToString(), ":"))  
```  
  
 <span data-ttu-id="b4e32-119">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-119">This example produces the following output:</span></span>  
  
```  
onetwothree  
one:two:three:  
123  
1:2:3:  
```  
  
## <a name="example"></a><span data-ttu-id="b4e32-120">예제</span><span class="sxs-lookup"><span data-stu-id="b4e32-120">Example</span></span>  
 <span data-ttu-id="b4e32-121">이제 새 확장명 메서드를 활용하기 위해 예제를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-121">Now, the example can be modified to take advantage of the new extension method:</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(ByVal source As IEnumerable(Of String)) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each s As String In source  
            sb.Append(s)  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal func As Func(Of T, String)) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each item As T In source  
            sb.Append(func(item))  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal separator As String) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each s As T In source  
            sb.Append(s).Append(separator)  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal func As Func(Of T, String), ByVal separator As String) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each item As T In source  
            sb.Append(func(item)).Append(separator)  
        Next  
        Return sb.ToString()  
    End Function  
  
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
  
        ' Retrieve the text of each paragraph.  
        Dim paraWithText = _  
            From para In paragraphs _  
            Select New With { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = para.ParagraphNode.<w:r>.<w:t>.StringConcatenate(Function(e) CStr(e)) _  
            }  
  
        For Each p In paraWithText  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text)  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="b4e32-122">이 예제는 다음에 설명 된 문서에 적용 하면 출력을 생성 [원본 Office Open XML 문서 (Visual Basic)를 만드는](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-122">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
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
  
 <span data-ttu-id="b4e32-123">이 리팩터링은 순수 함수로의 리팩터링에 대한 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-123">Note that this refactoring is a variant of refactoring into a pure function.</span></span> <span data-ttu-id="b4e32-124">다음 항목에서는 순수 함수로의 팩터링 개념에 대해 자세히 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-124">The next topic will introduce the idea of factoring into pure functions in more detail.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b4e32-125">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b4e32-125">Next Steps</span></span>  
 <span data-ttu-id="b4e32-126">다음 예제에서는 순수 함수를 사용하여 다른 방식으로 이 코드를 리팩터링하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4e32-126">The next example shows how to refactor this code in another way, by using pure functions:</span></span>  
  
-   [<span data-ttu-id="b4e32-127">순수 함수 (Visual Basic)를 사용 하 여 리팩터링</span><span class="sxs-lookup"><span data-stu-id="b4e32-127">Refactoring Using a Pure Function (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)  
  
## <a name="see-also"></a><span data-ttu-id="b4e32-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4e32-128">See Also</span></span>  
 <span data-ttu-id="b4e32-129">[자습서: WordprocessingML 문서 (Visual Basic)에서 내용 조작](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) </span><span class="sxs-lookup"><span data-stu-id="b4e32-129">[Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) </span></span>  
<span data-ttu-id="b4e32-130"> [(Visual Basic) 순수 함수로 리팩터링](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)</span><span class="sxs-lookup"><span data-stu-id="b4e32-130"> [Refactoring Into Pure Functions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)</span></span>
