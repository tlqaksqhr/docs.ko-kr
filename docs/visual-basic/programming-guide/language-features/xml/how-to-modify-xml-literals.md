---
title: "How to: Modify XML Literals (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML axis [Visual Basic], Value"
  - "XML literals [Visual Basic]"
  - "XML literals [Visual Basic], modifying"
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# How to: Modify XML Literals (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 XML 리터럴을 수정하는 편리한 방법을 제공합니다.  요소와 속성을 추가하거나 삭제할 수 있으며 기존 요소를 새 XML 요소로 바꿀 수도 있습니다.  이 항목에서는 기존 XML 리터럴을 수정하는 방법의 몇 가지 예제를 보여 줍니다.  
  
### XML 리터럴의 값을 수정하려면  
  
1.  XML 리터럴의 값을 수정하려면 XML 리터럴에 대한 참조를 가져오고 `Value` 속성을 원하는 값으로 설정합니다.  
  
     다음 코드 예제에서는 XML 문서에 있는 모든 \<Price\> 요소의 값을 업데이트합니다.  
  
     [!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]  
  
     다음은 샘플 소스 XML과 이 코드 예제에서 수정된 XML입니다.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>47.20</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>48.25</Price>  
      </Book>  
    </Catalog>  
    ```  
  
    > [!NOTE]
    >  `Value` 속성은 컬렉션에서 첫 번째 XML 요소를 참조합니다.  컬렉션에서 이름이 같은 요소가 두 개 이상인 경우 `Value` 속성을 설정하면 컬렉션의 첫 번째 요소에만 영향을 미칩니다.  
  
### XML 리터럴에 특성을 추가하려면  
  
1.  XML 리터럴에 특성을 추가하려면 먼저 XML 리터럴에 대한 참조를 가져옵니다.  그런 다음 XML 특성 축 속성을 새로 추가하여 특성을 추가할 수 있습니다.  또한 <xref:System.Xml.Linq.XContainer.Add%2A> 메서드를 사용하여 새 <xref:System.Xml.Linq.XAttribute> 개체를 XML 리터럴에 추가할 수 있습니다.  다음 예제에서는 두 옵션에 대해 설명합니다.  
  
     [!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]  
  
     다음은 샘플 소스 XML과 이 코드 예제에서 수정된 XML입니다.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
    ```  
  
     XML 특성 축 속성을 사용하는 방법에 대한 자세한 내용은 [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)을 참조하십시오.  
  
### XML 리터럴에 요소를 추가하려면  
  
1.  XML 리터럴에 요소를 추가하려면 먼저 XML 리터럴에 대한 참조를 가져옵니다.  그런 다음 <xref:System.Xml.Linq.XContainer.Add%2A> 메서드를 사용하여 새 <xref:System.Xml.Linq.XElement> 개체를 요소의 마지막 하위 요소로 추가할 수 있습니다.  <xref:System.Xml.Linq.XContainer.AddFirst%2A> 메서드를 사용하여 새 <xref:System.Xml.Linq.XElement> 개체를 첫 번째 하위 요소로 추가할 수 있습니다.  
  
     다른 하위 요소에 상대적인 특정 위치에 새 요소를 추가하려면 먼저 인접 하위 요소에 대한 참조를 가져옵니다.  그런 다음 <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> 메서드를 사용하여 새 <xref:System.Xml.Linq.XElement> 개체를 인접한 하위 요소 앞에 추가할 수 있습니다.  또한 <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> 메서드를 사용하여 새 <xref:System.Xml.Linq.XElement> 개체를 인접한 하위 요소 뒤에 추가할 수 있습니다.  
  
     다음 예제에서는 이러한 기술 각각에 대한 예를 보여 줍니다.  
  
     [!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]  
  
     다음은 샘플 소스 XML과 이 코드 예제에서 수정된 XML입니다.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331">  
        <Publisher>Microsoft Press</Publisher>  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <PublishDate>2005-2-14</PublishDate>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
    ```  
  
### XML 리터럴에서 요소나 특성을 제거하려면  
  
1.  XML 리터럴에서 요소나 특성을 제거하려면 다음 예제에 표시된 대로 요소나 특성에 대한 참조를 가져오고 `Remove` 메서드를 호출합니다.  
  
     [!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]  
  
     다음은 샘플 소스 XML과 이 코드 예제에서 수정된 XML입니다.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book> </Catalog>  
    ```  
  
     XML 리터럴에서 모든 요소나 특성을 제거하려면 XML 리터럴에 대한 참조를 가져오고 <xref:System.Xml.Linq.XElement.RemoveAll%2A> 메서드를 호출합니다.  
  
### XML 리터럴을 수정하려면  
  
1.  XML 요소의 이름을 변경하려면 먼저 요소에 대한 참조를 가져옵니다.  그런 다음 새 이름의 새 <xref:System.Xml.Linq.XElement> 개체를 만들고 새 <xref:System.Xml.Linq.XElement> 개체를 기존 <xref:System.Xml.Linq.XElement> 개체의 <xref:System.Xml.Linq.XNode.ReplaceWith%2A> 메서드에 전달합니다.  
  
     바꾸는 요소에 유지해야 할 하위 요소가 있는 경우 새 <xref:System.Xml.Linq.XElement> 개체의 값을 기존 요소의 <xref:System.Xml.Linq.XContainer.Nodes%2A> 속성으로 설정합니다.  이렇게 하면 새 요소의 값이 기존 요소의 내부 XML로 설정됩니다.  그렇지 않은 경우 새 요소의 값을 기존 요소의 `Value` 속성으로 설정할 수 있습니다.  
  
     다음 코드 예제에서는 모든 \<Description\> 요소를 \<Abstract\> 요소로 바꿉니다.  \<Description\> <xref:System.Xml.Linq.XElement> 개체의 <xref:System.Xml.Linq.XContainer.Nodes%2A> 속성을 사용하여 \<Description\> 요소의 내용을 새 \<Abstract\> 요소에서 유지할 수 있습니다.  
  
     [!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]  
  
     다음은 샘플 소스 XML과 이 코드 예제에서 수정된 XML입니다.  
  
    ```  
    Source XML:  
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
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Description>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <MSRP>44.95</MSRP>     <Abstract>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Abstract>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <MSRP>45.95</MSRP>     <Abstract>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Abstract>  
      </Book>  
    </Catalog>  
    ```  
  
## 참고 항목  
 [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)