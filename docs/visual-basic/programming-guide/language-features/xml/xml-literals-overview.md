---
title: XML 리터럴 개요(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: 03fc8c11b5553c9c3a63bdcb69bf6135050e2c89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xml-literals-overview-visual-basic"></a>XML 리터럴 개요(Visual Basic)
*XML 리터럴에* Visual Basic 코드에 직접 XML을 통합할 수 있습니다. XML 리터럴 구문을 나타내는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체는 XML 1.0 구문을 비슷합니다. 이렇게 하면 더 쉽게 코드에 최종 XML 구조가 동일 하기 때문에 XML 요소 및 문서를 프로그래밍 방식으로 만들 수 있습니다.  
  
 Visual Basic XML 리터럴을 컴파일합니다 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 와 잘 통합 만들고 XML을 조작 하기 위한 간단한 개체 모델 및이 모델을 제공 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]합니다. 자세한 내용은 <xref:System.Xml.Linq.XElement>을 참조하세요.  
  
 Xml 리터럴의 Visual Basic 식을 포함할 수 있습니다. 응용 프로그램 실행 시 만든는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 포함된 된 식의 값을 통합 하는 각 리터럴에 대 한 개체입니다. 이렇게 하면 XML 리터럴 내 동적 콘텐츠를 지정할 수 있습니다. 자세한 내용은 참조 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.  
  
 XML 리터럴 구문 및 XML 1.0 구문 차이점에 대 한 자세한 내용은 참조 [XML 리터럴 및 XML 1.0 사양](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)합니다.  
  
## <a name="simple-literals"></a>단순 리터럴  
 만들 수는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 입력 하거나 유효한 XML에 붙여 넣어 Visual Basic 코드에서 개체입니다. XML 요소 리터럴의 반환는 <xref:System.Xml.Linq.XElement> 개체입니다. 자세한 내용은 참조 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) 및 [XML 리터럴 및 XML 1.0 사양](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)합니다. 다음 예제에서는 여러 자식 요소가 있는 XML 요소를 만듭니다.  
  
 [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 XML 리터럴을 사용을 시작 하 여 XML 문서를 만들 수 `<?xml version="1.0"?>`다음 예제에 나온 것 처럼 합니다. XML 문서 리터럴의 반환는 <xref:System.Xml.Linq.XDocument> 개체입니다. 자세한 내용은 참조 [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)합니다.  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  Visual basic에서 XML 리터럴 구문을 XML 1.0 사양에 대 한 구문에 일치 하지 않습니다. 자세한 내용은 참조 [XML 리터럴 및 XML 1.0 사양](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)합니다.  
  
## <a name="line-continuation"></a>줄 연속  
 XML 리터럴은 줄 연속 문자 (공백 밑줄 enter 시퀀스)를 사용 하지 않고 여러 줄으로 나타날 수 있습니다. 이렇게 하면 보다 쉽게 XML 문서를 사용 하 여 코드에서 XML 리터럴의 비교할 수 있습니다.  
  
 컴파일러는 XML 리터럴을의 일부로 줄 연속 문자를 처리합니다. 따라서 사용할지 공간 밑줄 입력 시퀀스에 속해 있는 경우에는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다.  
  
 그러나 여러 줄의 식이 포함된 된 식에 있는 경우에 줄 연속 문자 필요지 않습니다. 자세한 내용은 참조 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.  
  
## <a name="embedding-queries-in-xml-literals"></a>XML 리터럴에 쿼리 포함  
 포함된 된 식에는 쿼리를 사용할 수 있습니다. 이렇게 하면 쿼리에서 반환 하는 요소는 XML 요소에 추가 됩니다. 이렇게 하면 XML 리터럴을에 사용자의 쿼리 결과 같은 동적 콘텐츠를 추가할 수 있습니다.  
  
 예를 들어 다음 코드를 사용 하 여 포함 된 쿼리의 멤버에서 XML 요소를 만드는 `phoneNumbers2` 배열 하 고 다음의 자식으로 해당 요소를 추가 `contact2`합니다.  
  
 [!code-vb[VbXMLSamples#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>컴파일러가는 XML 리터럴에서 개체를 만드는 방법  
 Visual Basic 컴파일러에 해당 하는 호출으로 XML 리터럴을 변환 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 생성자를 작성 하는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 개체입니다. Visual Basic 컴파일러에 대 한 호출에 다음 코드 예제는 변환 예를 들어는 <xref:System.Xml.Linq.XProcessingInstruction> XML 버전 명령에 대 한 생성자를 호출 하는 <xref:System.Xml.Linq.XElement> 에 대 한 생성자는 `<contact>`, `<name>`, 및 `<phone>` 요소 및에 대 한 호출에서 <xref:System.Xml.Linq.XAttribute> 에 대 한 생성자는 `type` 특성입니다. 특히, 다음 샘플에는 특성이 제공, Visual Basic 컴파일러를 호출 합니다는 <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> 생성자를 두 번입니다. 첫 번째 값을 전달 합니다 `type` 에 대 한는 `name` 매개 변수와 값 `home` 에 대 한는 `value` 매개 변수입니다. 두 번째 값을 전달 합니다는 `type` 에 대 한는 `name` 매개 변수를 하지만 값 `work` 에 대 한는 `value` 매개 변수입니다.  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XElement>  
 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML 리터럴](../../../../visual-basic/language-reference/xml-literals/index.md)
