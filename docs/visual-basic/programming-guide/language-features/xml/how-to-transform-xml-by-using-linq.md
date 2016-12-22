---
title: "How to: Transform XML by Using LINQ (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML [Visual Basic], transforming"
  - "LINQ to XML [Visual Basic], transforming XML"
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Transform XML by Using LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md)을 사용하면 하나의 소스에서 XML을 읽고 이를 새 XML 형식으로 쉽게 변환할 수 있습니다.  LINQ 쿼리를 사용하여 변환할 내용을 검색하거나 기존 문서의 내용을 새 XML 형식으로 변경할 수 있습니다.  
  
 이 항목의 예제에서는 XML 소스 문서의 내용을 브라우저에서 볼 수 있는 HTML로 변환합니다.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### XML 문서를 변환하려면  
  
1.  Visual Studio의 **콘솔 응용 프로그램** 프로젝트 템플릿에서 새 Visual Basic 프로젝트를 만듭니다.  
  
2.  프로젝트에서 만든 Module1.vb 파일을 두 번 클릭하여 Visual Basic 코드를 수정합니다.  다음 코드를 `Module1` 모듈의 `Sub Main`에 추가합니다.  이 코드는 소스 XML 문서를 <xref:System.Xml.Linq.XDocument> 개체로 만듭니다.  
  
    ```vb#  
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
  
     [How to: Load XML from a File, String, or Stream](../Topic/How%20to:%20Load%20XML%20from%20a%20File,%20String,%20or%20Stream%20\(Visual%20Basic\).md).  
  
3.  소스 XML 문서를 만드는 코드 뒤에 다음 코드를 추가하여 개체에서 모든 \<Book\> 요소를 검색하고 이를 HTML 문서로 변환합니다.  \<Book\> 요소 목록은 변환된 HTML이 포함된 <xref:System.Xml.Linq.XElement> 개체의 컬렉션을 반환하는 LINQ 쿼리를 사용하여 만듭니다.  포함 식을 사용하여 소스 문서의 값을 새 XML 형식으로 저장할 수 있습니다.  
  
     <xref:System.Xml.Linq.XElement.Save%2A> 메서드를 사용하여 결과 HTML 문서를 파일에 씁니다.  
  
    ```vb#  
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
  
4.  `Module1`의 `Sub Main` 뒤에 새 메서드\(`Sub`\)를 추가하여 \<Description\> 노드를 지정한 HTML 형식으로 변환합니다.  이 메서드는 이전 단계의 코드에서 호출되며 \<Description\> 요소의 형식을 유지하는 데 사용됩니다.  
  
     다음 메서드는 \<Description\> 요소의 하위 요소를 HTML로 바꿉니다.  `ReplaceWith` 메서드는 하위 요소의 위치를 유지하는 데 사용됩니다.  \<Description\> 요소의 변환된 내용은 HTML 단락\(\<p\>\) 요소에 포함됩니다.  <xref:System.Xml.Linq.XContainer.Nodes%2A> 속성은 \<Description\> 요소의 변환된 내용을 검색하는 데 사용됩니다.  따라서 하위 요소가 변환된 내용에 포함됩니다.  
  
     `Module1`의 `Sub Main` 뒤에 다음 코드를 추가합니다.  
  
    ```vb#  
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
  
5.  변경 사항을 저장합니다.  
  
6.  F5 키를 눌러 코드를 실행합니다.  저장된 결과 문서는 다음과 비슷합니다.  
  
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
  
## 참고 항목  
 [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [How to: Load XML from a File, String, or Stream](../Topic/How%20to:%20Load%20XML%20from%20a%20File,%20String,%20or%20Stream%20\(Visual%20Basic\).md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)