---
title: (Visual Basic) 단락의 텍스트 검색
ms.date: 07/20/2015
ms.assetid: 095fa0d9-7b1b-4cbb-9c13-e2c9d8923d31
ms.openlocfilehash: f1a7bc607fb51a8dca6121ee950af0252ab4722e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647152"
---
# <a name="retrieving-the-text-of-the-paragraphs-visual-basic"></a>(Visual Basic) 단락의 텍스트 검색
이 예제에서는 앞의 예에서 [단락 및 (Visual Basic) 해당 스타일 검색](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)합니다. 이 새 예제에서는 각 단락의 텍스트를 문자열로 검색합니다.  
  
 이 예제에서는 텍스트를 검색하기 위해 익명 형식의 컬렉션을 반복하는 추가 쿼리를 추가하고 새 멤버 `Text`가 추가된 익명 형식의 새 컬렉션을 프로젝션합니다. 또한 <xref:System.Linq.Enumerable.Aggregate%2A> 표준 쿼리 연산자를 사용하여 여러 문자열을 한 문자열로 연결합니다.  
  
 먼저 익명 형식의 컬렉션을 프로젝션한 다음 이 컬렉션을 사용하여 익명 형식의 새 컬렉션을 프로젝션하는 방법은 일반적이고 유용합니다. 이 쿼리는 첫 번째 익명 형식으로 프로젝션하지 않고 작성될 수도 있습니다. 그러나 지연 계산 때문에 이렇게 해도 추가 처리 능력이 많이 사용되지 않습니다. 이 방법은 힙에서 수명이 짧은 개체를 더 많이 만들지만 이로 인해 성능이 크게 저하되지는 않습니다.  
  
 물론 단락, 각 단락의 스타일 및 각 단락의 텍스트를 검색하는 기능이 포함된 단일 쿼리를 작성할 수도 있습니다. 그러나 복잡한 쿼리를 여러 쿼리로 나누면 생성되는 코드가 더욱 모듈화되고 유지 관리가 쉬워지기 때문에 유용한 경우가 많습니다. 또한 쿼리의 일부를 다시 사용해야 하는 경우 쿼리가 이런 방식으로 작성되면 리팩터링하기가 더 쉽습니다.  
  
 이 항목에서 자세히 검사 하는 처리 모델을 사용 하는 모두 연결 되어 있는 이러한 쿼리 [자습서: 지연 된 실행 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 WordprocessingML 문서를 처리하여 요소 노드, 스타일 이름 및 각 단락의 텍스트를 확인합니다. 이 예제는 이 자습서의 이전 예제를 기반으로 합니다. 새 쿼리는 아래에 있는 코드의 주석에서 호출됩니다.  
  
 이 예제에 대 한 소스 문서를 만들기 위한 지침은 [원본 Office Open XML 문서 (Visual Basic)를 만드는](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)합니다.  
  
 이 예제에서는 WindowsBase 어셈블리의 클래스를 사용하고 <xref:System.IO.Packaging?displayProperty=nameWithType> 네임스페이스의 형식을 사용합니다.  
  
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
  
 이 예제는 다음에 설명 된 문서에 적용 하면 출력 [원본 Office Open XML 문서 (Visual Basic)를 만드는](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)합니다.  
  
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
  
## <a name="next-steps"></a>다음 단계  
 다음 예제에서는 <xref:System.Linq.Enumerable.Aggregate%2A> 대신 확장 메서드를 사용하여 여러 문자열을 하나의 문자열로 연결하는 방법을 보여 줍니다.  
  
-   [확장 메서드 (Visual Basic)를 사용 하 여 리팩터링](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a>참고 항목  
 [자습서: WordprocessingML 문서 (Visual Basic)에서 내용 조작](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)  
 [지연 된 실행과 지연 계산은 linq to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
