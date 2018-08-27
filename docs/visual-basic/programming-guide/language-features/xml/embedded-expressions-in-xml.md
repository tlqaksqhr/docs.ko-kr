---
title: XML의 포함 식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: f99735df2512fd4b1477bab9126e18f5afbbfa8c
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932931"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>XML의 포함 식(Visual Basic)
포함 식을 통해 식을 런타임에 계산 되는 식을 포함 하는 XML 리터럴을 만들 수 있습니다. 포함된 식에 대 한 구문은 `<%=` `expression` `%>`는 동일한 구문을 사용 하는 대로 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]입니다.  
  
 예를 들어 만들면 XML 요소 리터럴 리터럴 텍스트 콘텐츠를 사용 하 여 포함 된 식을 결합 합니다.  
  
 [!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 하는 경우 `isbnNumber` 12345 정수를 포함 하 고 `modifiedDate` 날짜가 포함 3 5 2006 년 월을 경우이 코드가 실행 되는 값 `book` 는:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>포함된 식 위치 및 유효성 검사  
 포함된 식은 XML 리터럴 식 내의 특정 위치에만 나타날 수 있습니다. 식 형식는 식 위치 컨트롤을 반환할 수 있습니다 방법과 `Nothing` 처리 됩니다. 다음 표에서 허용 되는 위치 및 포함 된 식의 형식에 설명합니다.  
  
|리터럴에 위치|식의 형식|처리 `Nothing`|  
|---|---|---|  
|XML 요소 이름|<xref:System.Xml.Linq.XName>|Error|  
|XML 요소 내용|`Object` 또는 배열 `Object`|무시됨|  
|XML 요소 특성 이름|<xref:System.Xml.Linq.XName>|오류를 특성 값도 아닌 `Nothing`|  
|XML 요소 특성 값|`Object`|특성 선언이 무시 됩니다.|  
|XML 요소 특성|<xref:System.Xml.Linq.XAttribute> 또는 컬렉션 <xref:System.Xml.Linq.XAttribute>|무시됨|  
|XML 문서 루트 요소|<xref:System.Xml.Linq.XElement> 또는 하나의 컬렉션 <xref:System.Xml.Linq.XElement> 개체와 임의 개수의 <xref:System.Xml.Linq.XProcessingInstruction> 고 <xref:System.Xml.Linq.XComment> 개체|무시됨|  
  
-   XML 요소 이름에 포함 된 식의 예:  
  
     [!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   XML 요소의 내용에 포함 된 식의 예:  
  
     [!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   XML 요소 특성 이름에 포함 된 식의 예:  
  
     [!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   XML 요소 특성 값에 포함 된 식의 예:  
  
     [!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   XML 요소 특성에 포함 된 식의 예:  
  
     [!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   XML 문서 루트 요소에 포함 된 식의 예:  
  
     [!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 사용 하도록 설정 하면 `Option Strict`, 컴파일러는 각 포함 된 식의 형식을 필요한 형식으로 확대를 확인 합니다. 유일한 예외는 코드를 실행할 때 확인 되는 XML 문서의 루트 요소입니다. 없이 컴파일하면 `Option Strict`, 식의 형식 포함할 수 있습니다 `Object` 런타임에 해당 형식을 검증 됩니다.  
  
 콘텐츠는 선택 사항이 위치에 포함 된 식을 포함 `Nothing` 무시 됩니다. 즉, 요소 콘텐츠, 특성 값을 확인 해야 하 고 배열 요소에는 없는 `Nothing` XML 리터럴의 사용 하기 전에 합니다. 요소 및 특성 이름과 같은 값이 될 수 없습니다. 필요한 `Nothing`합니다.  
  
 리터럴의 특정 형식에 포함 된 식을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)하십시오 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.  
  
## <a name="scoping-rules"></a>범위 지정 규칙  
 컴파일러는 적절 한 리터럴 형식에 대 한 생성자 호출으로 각 XML 리터럴을 변환합니다. 리터럴 내용과 XML 리터럴에 식 포함 된 생성자에 인수로 전달 됩니다. 즉, XML 리터럴을 사용할 수 있는 모든 Visual Basic 프로그래밍 요소는 해당 포함 된 식에 사용할 수 있습니다.  
  
 XML 리터럴 내에서 사용 하 여 접두사를 선언 하는 XML 네임 스페이스에 액세스할 수 있습니다는 `Imports` 문입니다. 새 XML 네임 스페이스 접두사를 선언 하거나 기존 XML 네임 스페이스 접두사를 사용 하 여 요소에서를 숨길 수 있습니다는 `xmlns` 특성입니다. 새 네임 스페이스는 해당 요소의 자식 노드가 아니라 XML 리터럴을 포함 된 식에서 사용할 수 있습니다.  
  
> [!NOTE]
>  XML 네임 스페이스 접두사를 사용 하 여 선언 되는 경우는 `xmlns` 네임 스페이스 특성을 특성 값을 상수 문자열 이어야 합니다. 이런 점에서 사용 하 여는 `xmlns` 사용과 같은 특성은는 `Imports` XML 네임 스페이스를 선언 하는 문입니다. XML 네임 스페이스 값을 지정 하려면 포함 된 식을 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [XML 리터럴 개요](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
