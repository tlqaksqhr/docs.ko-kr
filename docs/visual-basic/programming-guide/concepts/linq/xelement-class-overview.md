---
title: "XElement 클래스 개요 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4b46f3cb5e0d59105fbc31424a0408c3421d9cac
ms.lasthandoff: 03/13/2017

---
# <a name="xelement-class-overview-visual-basic"></a>XElement 클래스 개요 (Visual Basic)
<xref:System.Xml.Linq.XElement>클래스의 기본 클래스 중 하나는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</xref:System.Xml.Linq.XElement> XML 요소를 나타냅니다. 이 클래스를 사용하여 요소를 만들거나, 요소의 내용을 변경하거나, 자식 요소를 추가, 변경 또는 삭제하거나, 특성을 요소에 추가하거나, 요소의 내용을 텍스트 형태로 serialize할 수 있습니다. 다른 클래스와 상호 운용할 수도 있습니다 <xref:System.Xml?displayProperty=fullName>, 예: <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, 및 <xref:System.Xml.Xsl.XslCompiledTransform>.</xref:System.Xml.Xsl.XslCompiledTransform> </xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> </xref:System.Xml?displayProperty=fullName>  
  
## <a name="xelement-functionality"></a>XElement 기능  
 이 항목에서는 <xref:System.Xml.Linq.XElement>클래스</xref:System.Xml.Linq.XElement> 에서 제공 하는 기능 설명  
  
### <a name="constructing-xml-trees"></a>XML 트리 생성  
 다음과 같은 다양한 방법으로 XML 트리를 생성할 수 있습니다.  
  
-   코드에서 XML 트리를 생성할 수 있습니다. 자세한 내용은 참조 [XML 트리 만들기 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)합니다.  
  
-   같은 다양 한 소스에서에서 XML을 구문 분석할 수는 <xref:System.IO.TextReader>, 텍스트 파일 또는 웹 주소 (URL).</xref:System.IO.TextReader> 자세한 내용은 참조 [XML 구문 분석 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)합니다.  
  
-   사용할 수는 <xref:System.Xml.XmlReader>트리를 채우는.</xref:System.Xml.XmlReader> 자세한 내용은 <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</xref:System.Xml.Linq.XNode.ReadFrom%2A> 을 참조 하십시오.  
  
-   콘텐츠를 쓸 수 있는 모듈이 있는 경우는 <xref:System.Xml.XmlWriter>를 사용할 수는 <xref:System.Xml.Linq.XContainer.CreateWriter%2A>메서드를 만들어를 작성기는 모듈에 작성기를 전달한 다음에 기록 된 콘텐츠를 사용 하 여는 <xref:System.Xml.XmlWriter>XML 트리를 채우는.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XContainer.CreateWriter%2A> </xref:System.Xml.XmlWriter>  
  
 그러나 XML 트리를 만드는 가장 일반적인 방법은 다음과 같습니다.  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 XML 트리를 만드는 또 다른 일반적인 방법에는 다음 예제에서와 같이 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리의 결과를 사용하여 XML 트리를 채우는 작업이 포함됩니다.  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where el.Value > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a>XML 트리 serialization  
 XML 트리를 serialize 할 수는 <xref:System.IO.File>, <xref:System.IO.TextWriter>, 또는 <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File>  
  
 자세한 내용은 참조 [XML 트리를 직렬화 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)합니다.  
  
### <a name="retrieving-xml-data-via-axis-methods"></a>축 메서드를 통해 XML 데이터 검색  
 축 메서드를 사용하여 특성, 자식 요소, 하위 요소 및 상위 요소를 검색할 수 있습니다. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리는 축 메서드에 대해 작동하며 XML 트리를 탐색하고 처리하는 융통성 있고 강력한 몇 가지 방법을 제공합니다.  
  
 자세한 내용은 참조 [LINQ to XML 축 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)합니다.  
  
### <a name="querying-xml-trees"></a>XML 트리 쿼리  
 XML 트리에서 데이터를 추출하는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리를 작성할 수 있습니다.  
  
 자세한 내용은 참조 [XML 트리 쿼리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)합니다.  
  
### <a name="modifying-xml-trees"></a>XML 트리 수정  
 내용이나 특성을 변경하는 등의 다양한 방법으로 요소를 수정할 수 있습니다. 또한 부모에서 요소를 제거할 수도 있습니다.  
  
 자세한 내용은 참조 [XML 트리 수정 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML 프로그래밍 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
