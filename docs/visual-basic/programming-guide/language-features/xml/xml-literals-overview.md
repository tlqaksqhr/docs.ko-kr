---
title: "XML 리터럴 개요 (Visual Basic) | Microsoft 문서"
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
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
caps.latest.revision: 27
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
ms.openlocfilehash: 57d036910ba9e49385caca28de222a8a8e28ec56
ms.lasthandoff: 03/13/2017

---
# <a name="xml-literals-overview-visual-basic"></a>XML 리터럴 개요(Visual Basic)
*XML 리터럴* 으로 XML을 직접 통합할 수 여 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드입니다. XML 리터럴 구문을 나타내는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 개체는 XML 1.0 구문을 비슷합니다. 이렇게 하면 보다 쉽게 코드에 동일한 최종 XML 구조 때문에 XML 요소와 문서를 프로그래밍 방식으로 만들 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]XML 리터럴을에 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 개체입니다. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]와 잘 통합 만들고 XML을 조작 하기 위한 간단한 개체 모델 및이 모델을 제공 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]합니다. 자세한 내용은 <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 을 참조 하십시오.  
  
 포함할 수는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] XML 리터럴에 식입니다. 런타임 시 응용 프로그램 만들기는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 각 리터럴, 포함된 된 식의 값을 통합에 대 한 개체입니다. 이렇게 하면 XML 리터럴 내 동적 콘텐츠를 지정할 수 있습니다. 자세한 내용은 참조 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.  
  
 XML 리터럴 구문 및 XML 1.0 구문 차이점에 대 한 자세한 내용은 참조 [XML 리터럴 및 XML 1.0 사양](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)합니다.  
  
## <a name="simple-literals"></a>단순 리터럴  
 만들 수는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 개체 프로그램 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 유효한 XML에 입력 하거나 붙여 하 여 코드입니다. XML 요소 리터럴 반환는 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> 자세한 내용은 참조 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) 및 [XML 리터럴 및 XML 1.0 사양](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)합니다. 다음 예제에서는 여러 자식 요소가 있는 XML 요소를 만듭니다.  
  
 [!code-vb[VbXMLSamples #&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 XML 리터럴을 사용을 시작 하 여 XML 문서를 만들 수 `<?xml version="1.0"?>`다음 예제와 같이 합니다. XML 문서 리터럴 반환는 <xref:System.Xml.Linq.XDocument>개체.</xref:System.Xml.Linq.XDocument> 자세한 내용은 참조 [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)합니다.  
  
 [!code-vb[VbXMLSamples #&6;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  XML 리터럴 구문을 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] XML 1.0 사양에 대 한 구문에 일치 하지 않습니다. 자세한 내용은 참조 [XML 리터럴 및 XML 1.0 사양](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)합니다.  
  
## <a name="line-continuation"></a>줄 연속 문자  
 XML 리터럴은 줄 연속 문자 (공백 밑줄 enter 시퀀스)를 사용 하지 않고 여러 줄으로 나타날 수 있습니다. 이렇게 하면 보다 쉽게 XML 문서를 사용 하 여 코드에서 XML 리터럴의 비교할 수 있습니다.  
  
 컴파일러는 XML 리터럴을의 일부로 줄 연속 문자를 처리합니다. 따라서를 사용 해야 공간 밑줄 입력 시퀀스에 포함 되어 있는 경우에는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 개체입니다.  
  
 그러나, 여러 줄의 식이 포함된 된 식에 있는 경우 줄 연속 문자가 필요 합니다. 자세한 내용은 참조 [XML의 포함 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.  
  
## <a name="embedding-queries-in-xml-literals"></a>XML 리터럴에 쿼리를 포함합니다.  
 포함된 된 식에는 쿼리를 사용할 수 있습니다. 이렇게 하면 쿼리에서 반환 되는 요소는 XML 요소에 추가 됩니다. 이 방법으로 xml 리터럴에서 사용자의 쿼리 결과 같은 동적 콘텐츠를 추가할 수 있습니다.  
  
 예를 들어 다음 코드를 사용 하 여 포함 된 쿼리는의 멤버에서 XML 요소를 만드는 `phoneNumbers2` 배열 하 고 다음 요소 자식으로 추가 `contact2`합니다.  
  
 [!code-vb[VbXMLSamples #&7;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>컴파일러에서 XML 리터럴을 개체를 만드는 방법  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러는 XML 리터럴을 해당 하는 호출으로 변환 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 생성자 작성 하는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 개체입니다. 예를 들어는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에 대 한 호출에 다음 코드 예제에서는 변환 됩니다는 <xref:System.Xml.Linq.XProcessingInstruction>XML 버전 명령에 대 한 생성자를 호출 하는 <xref:System.Xml.Linq.XElement>에 대 한 생성자는 `<contact>`, `<name>`, 및 `<phone>` 요소 및에 대 한 호출의 <xref:System.Xml.Linq.XAttribute>에 대 한 생성자는 `type` 특성.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XProcessingInstruction> 특히, 다음 샘플에 특성을 지정 된는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러를 호출 하는 <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29>생성자를 두 번.</xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> 첫 번째 값을 전달 합니다 `type` 에 대 한는 `name` 매개 변수와 값은 `home` 에 대 한는 `value` 매개 변수입니다. 두 번째는 값을 전달 합니다 `type` 에 대 한는 `name` 매개 변수를 하지만 값 `work` 에 대 한는 `value` 매개 변수입니다.  
  
 [!code-vb[VbXMLSamples #&6;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XElement>   
 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML의 포함된 식](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [XML 문서 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML 리터럴](../../../../visual-basic/language-reference/xml-literals/index.md)
