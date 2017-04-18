---
title: "방법: LINQ (Visual Basic)를 사용 하 여 XML 변환 | Microsoft 문서"
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
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
caps.latest.revision: 14
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9f97466727064ea275c051b5916b0fb297e9e23a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>방법: LINQ를 사용하여 XML 변형(Visual Basic)
[XML 리터럴](../../../../visual-basic/language-reference/xml-literals/index.md) 쉽게 한 소스에서 XML을 읽고 새 XML 형식으로 변환 합니다. 콘텐츠를 변환 하 고, 검색에 대 한 LINQ 쿼리를 활용 하거나 새로운 XML 형식으로 기존 문서에서 콘텐츠를 변경할 수 있습니다.  
  
 이 항목의 예제 HTML 브라우저에 표시 되는 XML 소스 문서에서 콘텐츠를 변환 합니다.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-transform-an-xml-document"></a>XML 문서를 변환 하려면  
  
1.  Visual Studio에서 새 Visual Basic 프로젝트에서 만들기는 **콘솔 응용 프로그램** 프로젝트 템플릿.  
  
2.  Visual Basic 코드를 수정 하는 프로젝트에서 생성 된 Module1.vb 파일을 두 번 클릭 합니다. 다음 코드를 추가 하는 `Sub Main` 의 `Module1` 모듈입니다. 이 코드는 소스 XML 문서를 만듭니다는 <xref:System.Xml.Linq.XDocument>개체.</xref:System.Xml.Linq.XDocument>  
  
    ```vb  
    Dim catalog =   
      <?xml version="1.0"?>  
        <Catalog>  
          <Book id="bk101">  
            <Author>Garghentini, Davide</Author>  
            <Title>XML Developer's Guide</Title>  
            <Price>44.95</Price>  
            <Description>  
              An in-depth look at creating applications  
              with <technology>XML</technology>. For   
              <audience>beginners</audience> or   
              <audience>advanced</audience> developers.  
            </Description>  
          </Book>  
          <Book id="bk331">  
            <Author>Spencer, Phil</Author>  
            <Title>Developing Applications with Visual Basic .NET</Title>  
            <Price>45.95</Price>  
            <Description>  
              Get the expert insights, practical code samples,   
              and best practices you need   
              to advance your expertise with <technology>Visual   
              Basic .NET</technology>.   
              Learn how to create faster, more reliable applications  
              based on professional,   
              pragmatic guidance by today's top <audience>developers</audience>.  
            </Description>  
          </Book>  
        </Catalog>  
    ```  
  
     [방법: 파일, 문자열 또는 스트림에서 XML 로드](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)합니다.  
  
3.  소스 XML 문서를 만드는 코드 뒤 모두 검색 하려면 다음 코드를 추가 \<책 > 개체에서 요소는 HTML 문서를 변환 하 고 있습니다. 목록이 \<책 > 요소 컬렉션을 반환 하는 LINQ 쿼리를 사용 하 여 만들어집니다 <xref:System.Xml.Linq.XElement>변환된 된 HTML을 포함 하는 개체입니다.</xref:System.Xml.Linq.XElement> 새 XML 형식에서 소스 문서에서의 끝에 포함 된 식을 사용할 수 있습니다.  
  
     결과 HTML 문서를 사용 하 여 파일에 기록 되는 <xref:System.Xml.Linq.XElement.Save%2A>메서드.</xref:System.Xml.Linq.XElement.Save%2A>  
  
    ```vb  
    Dim htmlOutput =   
      <html>  
        <body>  
          <%= From book In catalog.<Catalog>.<Book>   
              Select <div>  
                       <h1><%= book.<Title>.Value %></h1>  
                       <h3><%= "By " & book.<Author>.Value %></h3>  
                        <h3><%= "Price = " & book.<Price>.Value %></h3>  
                        <h2>Description</h2>  
                        <%= TransformDescription(book.<Description>(0)) %>  
                        <hr/>  
                      </div> %>  
        </body>  
      </html>  
  
    htmlOutput.Save("BookDescription.html")  
    ```  
  
4.  후 `Sub Main` 의 `Module1`, 새 메서드 추가 (`Sub`) 변환 하는 \<설명 > 지정한 HTML 형식으로 노드. 이 메서드는 이전 단계에서 코드에 의해 호출 되며의 형식을 유지 하는 데 사용 됩니다는 \<설명 > 요소입니다.  
  
     하위 요소를 대체 하는이 메서드는 \<설명 > html 요소입니다. `ReplaceWith` 메서드는 하위 요소의 위치를 유지 하기 위해 사용 됩니다. 변환된 된 내용을 \<설명 > 요소가 HTML 단락에 포함 되어 (\<p >) 요소입니다. <xref:System.Xml.Linq.XContainer.Nodes%2A>속성은 변환된 된 내용을 검색 하는 데 사용 된 \<설명 > 요소.</xref:System.Xml.Linq.XContainer.Nodes%2A> 이렇게 하면 하위 요소는 변환된 된 내용에 포함 합니다.  
  
     다음 코드를 추가 `Sub Main` 의 `Module1`합니다.  
  
    ```vb  
    Public Function TransformDescription(ByVal desc As XElement) As XElement  
  
      ' Replace <technology> elements with <b>.  
      Dim content = (From element In desc...<technology>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<b><%= content(i).Value %></b>)  
        Next  
      End If  
  
      ' Replace <audience> elements with <i>.  
      content = (From element In desc...<audience>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<i><%= content(i).Value %></i>)  
        Next  
      End If  
  
      ' Return the updated contents of the <Description> element.  
      Return <p><%= desc.Nodes %></p>  
    End Function  
    ```  
  
5.  변경 내용을 저장합니다.  
  
6.  F5 키를 눌러 코드를 실행 합니다. 문서를 저장 된 결과 다음과 유사 합니다.  
  
    ```  
    <?xml version="1.0"?>  
    <html>  
      <body>  
        <div>  
          <h1>XML Developer's Guide</h1>  
          <h3>By Garghentini, Davide</h3>  
          <h3>Price = 44.95</h3>  
          <h2>Description</h2>  
          <p>  
            An in-depth look at creating applications  
            with <b>XML</b>. For   
            <i>beginners</i> or   
            <i>advanced</i> developers.  
          </p>  
          <hr />  
        </div>  
        <div>  
          <h1>Developing Applications with Visual Basic .NET</h1>  
          <h3>By Spencer, Phil</h3>  
          <h3>Price = 45.95</h3>  
          <h2>Description</h2>  
          <p>  
            Get the expert insights, practical code   
            samples, and best practices you need   
            to advance your expertise with <b>Visual   
            Basic .NET</b>. Learn how to create faster,  
            more reliable applications based on  
            professional, pragmatic guidance by today's   
            top <i>developers</i>.  
          </p>  
          <hr />  
        </div>  
      </body>  
    </html>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [XML 리터럴](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [Visual Basic에서 XML 조작](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [방법: 파일, 문자열 또는 스트림에서 XML 로드](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)

