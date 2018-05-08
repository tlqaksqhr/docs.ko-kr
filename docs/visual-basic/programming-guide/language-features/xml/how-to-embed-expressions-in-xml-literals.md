---
title: '방법: XML 리터럴에 식 포함(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 41dc6ef8d2ec2ffd6cd1cf793911f2e09f1a1e77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>방법: XML 리터럴에 식 포함(Visual Basic)
XML 리터럴의 XML 문서, 조각 또는 런타임 시 생성 된 콘텐츠가 포함 된 요소를 만드는 포함된 식과 결합할 수 있습니다. 다음 예제에서는 포함된 식을 사용 하 여 런타임에 요소 내용, 특성 및 요소 이름이 채우는 방법을 보여 줍니다.  
  
 포함 식 구문은 `<%=` `exp` `%>`, 동일한 구문이 되는 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 사용 합니다. 자세한 내용은 참조 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.  
  
 사용할 수도 있습니다는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 만들려는 Api [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다. 자세한 내용은 <xref:System.Xml.Linq.XElement>을 참조하세요.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-insert-text-as-element-content"></a>요소 내용으로 텍스트를 삽입 하려면  
  
-   에 포함 된 텍스트를 삽입 하는 방법을 보여 주는 다음 예제는 `contactName` 열기 및 닫기 이름 요소 간의 변수입니다.  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     이 예제는 다음과 같은 출력을 생성합니다.  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>특성 값으로 텍스트를 삽입 하려면  
  
-   에 포함 된 텍스트를 삽입 하는 방법을 보여 주는 다음 예제는 `phoneType` 변수 값으로는 `type` 특성입니다.  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     이 예제는 다음과 같은 출력을 생성합니다.  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>요소 이름에 대 한 텍스트를 삽입 하려면  
  
-   에 포함 된 텍스트를 삽입 하는 방법을 보여 주는 다음 예제는 `elementName` 요소 이름으로 변수입니다.  
  
     사용 하 여 닫아이 방법을 사용 하 여 요소를 만들 때의 \</ > 태그입니다.  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     이 예제는 다음과 같은 출력을 생성합니다.  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [방법: XML 리터럴 만들기](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)  
 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
