---
title: "How to: Create XML Literals (Visual Basic) | Microsoft Docs"
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
  - "XML literals [Visual Basic], creating"
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# How to: Create XML Literals (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

XML 리터럴을 사용하여 코드에서 직접 XML 문서, 조각 또는 요소를 만들 수 있습니다.  이 항목의 예제에서는 세 개의 자식 요소가 있는 XML 요소를 만드는 방법과 XML 문서를 만드는 방법을 보여 줍니다.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] API를 사용하여 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] 개체를 만들 수도 있습니다.  자세한 내용은 <xref:System.Xml.Linq.XElement>를 참조하십시오.  
  
### XML 요소를 만들려면  
  
-   실제 XML 구문과 같은 XML 리터럴 구문을 사용하여 XML 인라인을 만듭니다.  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     코드를 실행합니다.  이 코드는 다음과 같이 출력됩니다.  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### XML 문서를 만들려면  
  
-   XML 문서 인라인을 만듭니다.  다음 코드에서는 리터럴 구문, XML 선언, 처리 명령, 주석 및 다른 요소를 포함하는 요소가 있는 XML 문서를 만듭니다.  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     코드를 실행합니다.  이 코드는 다음과 같이 출력됩니다.  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works.  -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## 참고 항목  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)