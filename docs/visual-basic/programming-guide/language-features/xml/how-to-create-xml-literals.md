---
title: '방법: XML 리터럴 만들기(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: e5f8429b3ff02678bf8bf3e9e32bef6eb1a56831
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-xml-literals-visual-basic"></a>방법: XML 리터럴 만들기(Visual Basic)
코드에서 직접 XML 리터럴을 사용 하 여 XML 문서, 조각 또는 요소를 만들 수 있습니다. 이 항목의 예제 XML 문서를 만드는 방법과 세 개의 자식 요소를 포함 하는 XML 요소를 만드는 방법을 보여 줍니다.  
  
 사용할 수도 있습니다는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 만들려는 Api [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다. 자세한 내용은 <xref:System.Xml.Linq.XElement>을 참조하세요.  
  
### <a name="to-create-an-xml-element"></a>XML 요소를 만들려면  
  
-   실제 XML 구문으로 동일한 XML 리터럴 구문을 사용 하 여 XML 인라인을 만듭니다.  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     코드를 실행 합니다. 이 코드의 출력은입니다.  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a>XML 문서를 만들려면  
  
-   XML 문서 인라인을 만듭니다. 다음 코드는 XML 문서를 리터럴 구문, XML 선언, 처리 명령, 설명 및 다른 요소를 포함 하는 요소를 만듭니다.  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     코드를 실행 합니다. 이 코드의 출력은입니다.  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a>참고 항목  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
