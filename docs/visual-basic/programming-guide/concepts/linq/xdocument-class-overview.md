---
title: "XDocument 클래스 개요 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
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
ms.openlocfilehash: 31111b23adb019aad3ad55787c073dc02446291d
ms.lasthandoff: 03/13/2017

---
# <a name="xdocument-class-overview-visual-basic"></a>XDocument 클래스 개요 (Visual Basic)
이 항목에서는 <xref:System.Xml.Linq.XDocument>클래스</xref:System.Xml.Linq.XDocument> 소개  
  
## <a name="overview-of-the-xdocument-class"></a>XDocument 클래스 개요  
 <xref:System.Xml.Linq.XDocument>클래스는 유효한 XML 문서에 필요한 정보를 포함 합니다.</xref:System.Xml.Linq.XDocument> 여기에는 XML 선언, 처리 명령 및 주석이 포함되어 있습니다.  
  
 Note 있다고 <xref:System.Xml.Linq.XDocument> <xref:System.Xml.Linq.XDocument>클래스</xref:System.Xml.Linq.XDocument> 에서 제공 하는 특정 기능이 필요한 경우 개체를</xref:System.Xml.Linq.XDocument> 만들려면 대부분의 경우 <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 로 직접 작업할 수 있습니다. 직접 작업할 <xref:System.Xml.Linq.XElement>더 간단한 프로그래밍 모델.</xref:System.Xml.Linq.XElement>  
  
 <xref:System.Xml.Linq.XDocument><xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> 에서 파생</xref:System.Xml.Linq.XDocument> 자식 노드를 포함할 수 있습니다. 그러나 <xref:System.Xml.Linq.XDocument>개체에 자식 노드가 한 개만 가질 수 있습니다 <xref:System.Xml.Linq.XElement>노드.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> 이는 XML 문서에 루트 요소가 하나만 있어야 하는 XML 표준을 반영하는 것입니다.  
  
## <a name="components-of-xdocument"></a>XDocument의 구성 요소  
 <xref:System.Xml.Linq.XDocument>는 다음과 같은 요소가 포함 될 수 있습니다:</xref:System.Xml.Linq.XDocument>  
  
-   하나의 <xref:System.Xml.Linq.XDeclaration>개체.</xref:System.Xml.Linq.XDeclaration> <xref:System.Xml.Linq.XDeclaration>XML 선언의 관련 부분인 지정할 수 있습니다: XML 버전, 문서의 인코딩 및 XML 문서가 독립 실행형인지 여부.</xref:System.Xml.Linq.XDeclaration>  
  
-   하나의 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> 이 개체는 XML 문서의 루트 노드입니다.  
  
-   개수에 관계 없이 <xref:System.Xml.Linq.XProcessingInstruction>개체.</xref:System.Xml.Linq.XProcessingInstruction> 처리 명령은 XML을 처리하는 정보를 응용 프로그램에 전달합니다.  
  
-   개수에 관계 없이 <xref:System.Xml.Linq.XComment>개체.</xref:System.Xml.Linq.XComment> 주석은 루트 요소의 형제입니다. <xref:System.Xml.Linq.XComment>유효 하지 않은 주석으로 시작 하는 XML 문서에 대 한 개체 목록에서 첫 번째 인수 일 수 없습니다.</xref:System.Xml.Linq.XComment>  
  
-   하나의 <xref:System.Xml.Linq.XDocumentType>DTD에 대 한.</xref:System.Xml.Linq.XDocumentType>  
  
 Serialize 할 때는 <xref:System.Xml.Linq.XDocument>, 경우에 `XDocument.Declaration` 는 `null`, 작성기 있으면 출력에 XML 선언이 포함 됩니다 `Writer.Settings.OmitXmlDeclaration` 로 설정 `false` (기본값).</xref:System.Xml.Linq.XDocument>  
  
 기본적으로 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서는 버전을 "1.0"으로 설정하고 인코딩을 "utf-8"로 설정합니다.  
  
## <a name="using-xelement-without-xdocument"></a>XDocument 없이 XElement 사용  
 에서 설명한 대로 <xref:System.Xml.Linq.XElement>클래스의 기본 클래스는는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 프로그래밍 인터페이스입니다.</xref:System.Xml.Linq.XElement> 응용 프로그램에서는 대부분의 경우 문서를 만들도록 요구하지 않습니다. 사용 하 여는 <xref:System.Xml.Linq.XElement>클래스를 XML 트리를 만들고, 다른 XML 트리를 추가, XML 트리를 수정 및 저장 합니다. 수 있습니다</xref:System.Xml.Linq.XElement>  
  
## <a name="using-xdocument"></a>XDocument 사용  
 생성 하는 <xref:System.Xml.Linq.XDocument>를 생성 하려면와 마찬가지로 함수 생성을 사용 하 여 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument>  
  
 다음 코드는 <xref:System.Xml.Linq.XDocument>개체와 연결 된 포함.</xref:System.Xml.Linq.XDocument>  
  
```vb  
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>  
                       <!--This is a comment.-->  
                       <?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
                       <Pubs>  
                           <Book>  
                               <Title>Artifacts of Roman Civilization</Title>  
                               <Author>Moreno, Jordao</Author>  
                           </Book>  
                           <Book>  
                               <Title>Midieval Tools and Implements</Title>  
                               <Author>Gazit, Inbar</Author>  
                           </Book>  
                       </Pubs>  
                       <!--This is another comment.-->  
doc.Save("test.xml")  
```  
  
 test.xml 파일을 검사할 때 다음과 같은 출력이 표시됩니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML 프로그래밍 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
