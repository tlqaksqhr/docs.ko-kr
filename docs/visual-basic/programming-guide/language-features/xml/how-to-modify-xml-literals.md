---
title: "방법: XML 리터럴 수정 (Visual Basic) | Microsoft 문서"
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
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
caps.latest.revision: 11
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
ms.openlocfilehash: 0ff2eba693862154d9c402748fb6797d10c4a1f8
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-modify-xml-literals-visual-basic"></a>방법: XML 리터럴 수정(Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]XML 리터럴 수정 하는 편리한 방법을 제공 합니다. 추가 하거나 요소 및 특성을 삭제할 수 있으며 기존 요소를 새 XML 요소로 바꿀 수도 있습니다. 이 항목에서는 기존 XML 리터럴 수정 하는 방법의 몇 가지 예제를 제공 합니다.  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a>XML 리터럴 값을 수정 하려면  
  
1.  XML 리터럴의 값을 수정 하려면 XML 리터럴 및 설정에 대 한 참조를 가져올는 `Value` 속성을 원하는 값입니다.  
  
     다음 코드 예제에서는 모든 값이 업데이트는 \<가격 > XML 문서의 요소입니다.  
  
     [!code-vb[VbXmlSamples&#2;&4;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]  
  
     다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.  
  
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
    >  `Value` 속성은 컬렉션의 첫 번째 XML 요소를 나타냅니다. 컬렉션에 같은 이름을 가진 요소가 둘 이상 있으면 설정 된 `Value` 속성 컬렉션의 첫 번째 요소에만 영향을 줍니다.  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a>XML 리터럴에서 특성을 추가 하려면  
  
1.  XML 리터럴 특성을 추가 하려면 먼저 리터럴 XML에 대 한 참조를 가져옵니다. 그런 다음 새 XML 특성 축 속성을 추가 하 여 특성을 추가할 수 있습니다. 추가할 수도 있습니다 새 <xref:System.Xml.Linq.XAttribute>개체를 사용 하 여 리터럴 XML의 <xref:System.Xml.Linq.XContainer.Add%2A>메서드.</xref:System.Xml.Linq.XContainer.Add%2A> </xref:System.Xml.Linq.XAttribute> 다음 예제에서는 두 옵션을 보여 줍니다.  
  
     [!code-vb[VbXmlSamples&#2;&5;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]  
  
     다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.  
  
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
  
     XML 특성 축 속성에 대 한 자세한 내용은 참조 [XML 특성 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)합니다.  
  
### <a name="to-add-an-element-to-an-xml-literal"></a>XML 리터럴에서 요소를 추가 하려면  
  
1.  리터럴 xml 요소를 추가 하려면 먼저 리터럴 XML에 대 한 참조를 가져옵니다. 추가할 수 있습니다 새 <xref:System.Xml.Linq.XElement>개체를 사용 하 여 요소의 마지막 하위 요소로 <xref:System.Xml.Linq.XContainer.Add%2A>메서드.</xref:System.Xml.Linq.XContainer.Add%2A> </xref:System.Xml.Linq.XElement> 새 추가할 수 있습니다 <xref:System.Xml.Linq.XElement>개체를 사용 하 여 첫 번째 하위 요소로 <xref:System.Xml.Linq.XContainer.AddFirst%2A>메서드.</xref:System.Xml.Linq.XContainer.AddFirst%2A> </xref:System.Xml.Linq.XElement>  
  
     다른 하위 요소를 기준으로 특정 위치에 새 요소를 추가 하려면 먼저 인접 하위 요소에 대 한 참조를 가져옵니다. 추가할 수 있습니다 새 <xref:System.Xml.Linq.XElement>개체를 사용 하 여 인접 한 하위 요소 앞의 <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>메서드.</xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> </xref:System.Xml.Linq.XElement> 추가할 수도 있습니다 새 <xref:System.Xml.Linq.XElement>인접 한 하위 요소를 사용 하 여 다음 개체는 <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>메서드.</xref:System.Xml.Linq.XNode.AddAfterSelf%2A> </xref:System.Xml.Linq.XElement>  
  
     다음 예제에서는 이러한 기술을 각각의 예를 보여 줍니다.  
  
     [!code-vb[VbXmlSamples&#2;&6;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]  
  
     다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.  
  
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
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a>XML 리터럴에서 요소 또는 특성을 제거 하려면  
  
1.  XML 리터럴에서 요소 또는 특성을 제거 하 고 요소 또는 특성 호출에 대 한 참조를 가져올는 `Remove` 메서드를 다음 예와에서 같이 합니다.  
  
     [!code-vb[VbXmlSamples&#2;&7;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]  
  
     다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.  
  
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
      </Book></Catalog>  
    ```  
  
     XML 리터럴에서 모든 요소 또는 특성을 제거 하려면 리터럴 XML에 대 한 참조 가져오기 및 호출 된 <xref:System.Xml.Linq.XElement.RemoveAll%2A>메서드.</xref:System.Xml.Linq.XElement.RemoveAll%2A>  
  
### <a name="to-modify-an-xml-literal"></a>XML 리터럴 수정 하려면  
  
1.  XML 요소의 이름을 변경 하려면 먼저 요소에 대 한 참조를 가져옵니다. 만들 수 있습니다 새 <xref:System.Xml.Linq.XElement>새 이름을 지정 하 고 새 전달 된 개체 <xref:System.Xml.Linq.XElement>개체는 <xref:System.Xml.Linq.XNode.ReplaceWith%2A>기존 방식의 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode.ReplaceWith%2A> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement>  
  
     대체 하는 요소를 유지 해야 하는 하위 요소가 있으면, 새 값을 설정 합니다. <xref:System.Xml.Linq.XElement>개체는 <xref:System.Xml.Linq.XContainer.Nodes%2A>기존 요소의 속성입니다.</xref:System.Xml.Linq.XContainer.Nodes%2A> </xref:System.Xml.Linq.XElement> 기존 요소의 내부 XML을 새 요소의 값을 설정 합니다. 새 요소의 값을 설정할 수는 그렇지 않은 경우는 `Value` 기존 요소의 속성입니다.  
  
     다음 코드 예제에서는 모든 대체 \<설명 > 요소는 \<추상 > 요소입니다. 콘텐츠는 \<설명 > 요소는 새 유지 됩니다 \<추상 > 요소를 사용 하 여는 <xref:System.Xml.Linq.XContainer.Nodes%2A>의 속성은 \<설명 > <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer.Nodes%2A>  
  
     [!code-vb[VbXmlSamples&#2;&8;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]  
  
     다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.  
  
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
        <MSRP>44.95</MSRP>    <Abstract>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Abstract>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <MSRP>45.95</MSRP>    <Abstract>  
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
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic에서 XML 조작](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [방법: 파일, 문자열 또는 스트림에서 XML 로드](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
