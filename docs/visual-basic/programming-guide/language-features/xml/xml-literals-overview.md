---
title: "XML Literals Overview (Visual Basic) | Microsoft Docs"
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
  - "XML literals [Visual Basic], about XML literals"
  - "declaring XML literals [Visual Basic]"
  - "LINQ to XML [Visual Basic], XML literals"
  - "literals [Visual Basic], XML"
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# XML Literals Overview (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*XML 리터럴*을 사용하면 XML을 사용자의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 코드에 직접 통합할 수 있습니다. XML 리터럴 구문은 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] 개체를 나타내고 XML 1.0 구문과 유사합니다. XML 리터럴 구문을 사용하면 사용자 코드와 최종 XML의 구조가 같기 때문에 프로그래밍 방식으로 XML 요소 및 문서를 쉽게 만들 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]은 XML 리터럴을 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] 개체로 컴파일합니다.  [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)]은 XML을 만들고 조작하기 위한 간단한 개체 모델을 제공하며 이 모델은 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)]와 잘 통합됩니다.  자세한 내용은 <xref:System.Xml.Linq.XElement>를 참조하십시오.  
  
 XML 리터럴에 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 식을 포함시킬 수 있습니다.  실행 시 사용자 응용 프로그램은 각 리터럴에 대해 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] 개체를 만들고 포함된 식의 값을 통합합니다.  이를 통해 XML 리터럴 내에 동적 콘텐츠를 지정할 수 있습니다.  자세한 내용은 [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)을 참조하십시오.  
  
 XML 리터럴 구문과 XML 1.0 구문의 차이점에 대한 자세한 내용은 [XML Literals and the XML 1.0 Specification](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)을 참조하십시오.  
  
## 단순 리터럴  
 유효한 XML을 입력하거나 붙여 넣어 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 코드에서 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] 개체를 만들 수 있습니다.  XML 요소 리터럴은 <xref:System.Xml.Linq.XElement> 개체를 반환합니다.  자세한 내용은 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) 및 [XML Literals and the XML 1.0 Specification](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)을 참조하십시오.  다음 예제에서는 여러 개의 자식 요소를 갖는 XML 요소를 만듭니다.  
  
 [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 다음 예제에서와 같이 `<?xml version="1.0"?>`을 사용하여 XML 리터럴을 시작하여 XML 문서를 만들 수 있습니다.  XML 문서 리터럴은 <xref:System.Xml.Linq.XDocument> 개체를 반환합니다.  자세한 내용은 [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)을 참조하십시오.  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]의 XML 리터럴 구문은 XML 1.0 사양의 구문과 동일하지 않습니다.  자세한 내용은 [XML Literals and the XML 1.0 Specification](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)을 참조하십시오.  
  
## 줄 연속  
 XML 리터럴은 줄 연속 문자\(공백\-밑줄\-Enter 키 시퀀스\)를 사용하지 않고 여러 줄로 나타날 수 있습니다.  이를 통해 코드의 XML 리터럴을 XML 문서와 보다 쉽게 비교할 수 있습니다.  
  
 컴파일러는 줄 연속 문자를 XML 리터럴의 일부로 처리합니다.  따라서 공백\-밑줄\-Enter 키 시퀀스는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] 개체에 속해 있을 때만 사용해야 합니다.  
  
 그러나 포함된 식에 여러 줄의 식이 들어 있는 경우 줄 연속 문자가 필요합니다.  자세한 내용은 [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)을 참조하십시오.  
  
## XML 리터럴에 쿼리 포함  
 포함된 식에서 쿼리를 사용할 수 있습니다.  포함된 식에 쿼리를 사용할 때 쿼리에 의해 반환되는 요소는 XML 요소에 추가됩니다.  이를 통해 사용자 쿼리의 결과와 같은 동적 콘텐츠를 XML 리터럴에 추가할 수 있습니다.  
  
 예를 들어 다음 코드는 포함된 쿼리를 사용하여 `phoneNumbers2` 배열의 멤버로부터 XML 요소를 만든 다음 이 요소들을 `contact2`의 자식으로 추가합니다.  
  
 [!code-vb[VbXMLSamples#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## 컴파일러가 XML 리터럴로부터 개체를 만드는 방법  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러는 XML 리터럴을 그에 해당하는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] 생성자에 대한 호출로 변환하여 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] 개체를 빌드합니다.  예를 들어 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에서는 다음 코드 예제를 XML 버전 명령의 <xref:System.Xml.Linq.XProcessingInstruction> 생성자에 대한 호출, `<contact>`, `<name>` 및 `<phone>` 요소의 <xref:System.Xml.Linq.XElement> 생성자에 대한 호출, `type` 특성의 <xref:System.Xml.Linq.XAttribute> 생성자에 대한 호출로 변환합니다.  특히 다음 샘플에서의 특성을 사용할 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러는 <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> 생성자를 두 번 호출합니다.  첫 번째는 `name` 매개 변수의 `type` 값과 `value` 매개 변수의 `home` 값을 전달합니다.  두 번째에서는 `name` 매개 변수의 `type` 값과 `value` 매개 변수의 `work` 값을 전달합니다.  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## 참고 항목  
 <xref:System.Xml.Linq.XElement>   
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md)