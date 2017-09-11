---
title: "(Visual Basic)의 기본 단락 스타일 찾기 | Microsoft 문서"
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
ms.assetid: 9d094a4a-ec8c-41b0-b7ab-a3deb2a01d45
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 22d97c95a1dec52c0290555daeedce51c5a567e3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="finding-the-default-paragraph-style-visual-basic"></a><span data-ttu-id="f90ac-102">(Visual Basic)의 기본 단락 스타일 찾기</span><span class="sxs-lookup"><span data-stu-id="f90ac-102">Finding the Default Paragraph Style (Visual Basic)</span></span>
<span data-ttu-id="f90ac-103">WordprocessingML 문서 자습서에서 정보 조작는 첫 번째 작업은 문서에서 단락의 기본 스타일을 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f90ac-103">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f90ac-104">예제</span><span class="sxs-lookup"><span data-stu-id="f90ac-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f90ac-105">설명</span><span class="sxs-lookup"><span data-stu-id="f90ac-105">Description</span></span>  
 <span data-ttu-id="f90ac-106">다음 예제에서는 Office Open XML WordprocessingML 문서를 열고 패키지의 문서 및 스타일 부분을 찾은 다음 기본 스타일 이름을 찾는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f90ac-106">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="f90ac-107">Office Open XML 문서 패키지와 패키지의 구성 하는 부분에 대 한 정보를 참조 하십시오. [세부 정보 Office Open XML WordprocessingML 문서의 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f90ac-107">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span></span>  
  
 <span data-ttu-id="f90ac-108">쿼리에서는 값이 "paragraph"인 `w:style` 특성과 값이 "1"인 `w:type` 특성을 가진 `w:default`이라는 노드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f90ac-108">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="f90ac-109">쿼리를 사용 하는 이기 때문에 이러한 특성이 XML 노드를 하나만는 <xref:System.Linq.Enumerable.First%2A?displayProperty=fullName>컬렉션을 singleton으로 변환 하는 연산자입니다.</xref:System.Linq.Enumerable.First%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f90ac-109">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=fullName> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="f90ac-110">그런 다음 이름이 `w:styleId`인 특성의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f90ac-110">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="f90ac-111">이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고</span><span class="sxs-lookup"><span data-stu-id="f90ac-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="f90ac-112">형식을 사용는 <xref:System.IO.Packaging?displayProperty=fullName>네임 스페이스.</xref:System.IO.Packaging?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f90ac-112">It uses types in the <xref:System.IO.Packaging?displayProperty=fullName> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f90ac-113">코드</span><span class="sxs-lookup"><span data-stu-id="f90ac-113">Code</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
  
    Sub Main()  
  
        Const fileName As String = "SampleDoc.docx"  
  
        Const documentRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Const stylesRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If docPackageRelationship IsNot Nothing Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                ' Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                ' Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If styleRelation IsNot Nothing Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    ' Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        ' The following query finds all the paragraphs that have the default style.  
        Dim defParas As IEnumerable(Of XElement) = _  
            From style In styleDoc.Root.<w:style> _  
            Where style.@w:type.Equals("paragraph") And _  
                   style.@w:default.Equals("1") _  
            Select style  
        ' Then find the style of the first.  
        Dim defaultStyle As String = defParas.First().@w:styleId  
  
        Console.WriteLine("The default style is: " & defaultStyle)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="f90ac-114">설명</span><span class="sxs-lookup"><span data-stu-id="f90ac-114">Comments</span></span>  
 <span data-ttu-id="f90ac-115">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f90ac-115">This example produces the following output:</span></span>  
  
```  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="f90ac-116">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f90ac-116">Next Steps</span></span>  
 <span data-ttu-id="f90ac-117">다음 예제에서는 문서 및 해당 스타일에 있는 모든 단락을 발견 하는 비슷한 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f90ac-117">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
-   [<span data-ttu-id="f90ac-118">단락 및 해당 스타일 (Visual Basic) 검색</span><span class="sxs-lookup"><span data-stu-id="f90ac-118">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a><span data-ttu-id="f90ac-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f90ac-119">See Also</span></span>  
 [<span data-ttu-id="f90ac-120">자습서: WordprocessingML 문서 (Visual Basic)에서 내용 조작</span><span class="sxs-lookup"><span data-stu-id="f90ac-120">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
