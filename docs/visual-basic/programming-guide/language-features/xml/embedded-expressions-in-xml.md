---
title: "Embedded Expressions in XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlEmbeddedExpression"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "embedded expressions [Visual Basic]"
  - "LINQ to XML [Visual Basic], embedded expressions"
  - "XML literals [Visual Basic], embedded expressions"
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Embedded Expressions in XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

포함 식을 사용하여 런타임에 평가되는 식을 포함하는 XML 리터럴을 만들 수 있습니다.  포함 식의 구문은 `<%=` `expression` `%>`이며 [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)]에서 사용하는 구문과 같습니다.  
  
 예를 들어 포함 식과 리터럴 텍스트 콘텐츠를 결합하여 XML 요소 리터럴을 만들 수 있습니다.  
  
 [!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 `isbnNumber`에 정수 12345가 포함되고 `modifiedDate`에 날짜 3\/5\/2006이 포함된 경우 이 코드가 실행될 때 `book`의 값이 다음과 같습니다.  
  
```  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## 포함 식 위치 및 유효성 검사  
 포함 식은 XML 리터럴 식에서의 특정 위치에만 나타낼 수 있습니다.  식 위치는 식이 반환할 수 있는 형식과 `Nothing`의 처리 방법을 제어합니다.  다음 표에서는 포함 식의 허용되는 위치 및 형식을 설명합니다.  
  
||||  
|-|-|-|  
|리터럴에서의 위치|식 형식|`Nothing`의 처리|  
|XML 요소 이름|<xref:System.Xml.Linq.XName>|오류|  
|XML 요소 콘텐츠|`Object` 또는 `Object`의 배열|무시|  
|XML 요소 특성 이름|<xref:System.Xml.Linq.XName>|오류, 특성 값도 `Nothing`인 경우는 제외|  
|XML 요소 특성 값|`Object`|특성 선언 무시됨|  
|XML 요소 특성|<xref:System.Xml.Linq.XAttribute> 또는 <xref:System.Xml.Linq.XAttribute>의 컬렉션|무시|  
|XML 문서 루트 요소|<xref:System.Xml.Linq.XElement> 또는 한 개의 <xref:System.Xml.Linq.XElement> 개체와 임의 개수의 <xref:System.Xml.Linq.XProcessingInstruction> 및 <xref:System.Xml.Linq.XComment> 개체의 컬렉션|무시|  
  
-   XML 요소 이름에 있는 포함 식의 예제  
  
     [!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   XML 요소 콘텐츠에 있는 포함 식의 예제  
  
     [!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   XML 요소 특성 이름에 있는 포함 식의 예제  
  
     [!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   XML 요소 특성 값에 있는 포함 식의 예제  
  
     [!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   XML 요소 특성에 있는 포함 식의 예제  
  
     [!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   XML 문서 루트 요소에 있는 포함 식의 예제  
  
     [!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 `Option Strict`를 사용하면 컴파일러가 각 포함 식의 형식이 필요한 형식으로 확장되는지를 확인합니다.  유일한 예외는 코드가 실행될 때 확인되는 XML 문서 루트 요소의 경우입니다.  `Option Strict` 없이 컴파일하면 `Object` 형식의 식을 포함할 수 있으며 해당 형식이 런타임에 확인됩니다.  
  
 콘텐츠가 선택적인 위치에서는 `Nothing`을 포함하는 포함 식이 무시됩니다.  즉, XML 리터럴을 사용하기 전에 요소 콘텐츠, 특성 값 및 배열 요소가 `Nothing`이 아닌지를 확인할 필요가 없습니다.  요소 및 특성 이름과 같은 필요한 값은 `Nothing`이 될 수 없습니다.  
  
 특정 형식의 리터럴에서 포함 식을 사용하는 방법에 대한 자세한 내용은 [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) 및 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)을 참조하십시오.  
  
## 범위 지정 규칙  
 컴파일러는 각 XML 리터럴을 해당 리터럴 형식에 대한 생성자 호출로 변환합니다.  XML 리터럴에 있는 리터럴 콘텐츠 및 포함 식은 생성자에 인수로 전달됩니다.  즉, XML 리터럴에서 사용할 수 있는 모든 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 프로그래밍 요소를 해당 포함 식에서도 사용할 수 있습니다.  
  
 XML 리터럴 내에서 `Imports` 문을 사용하여 선언한 XML 네임스페이스 접두사에 액세스할 수 있습니다.  `xmlns` 특성을 사용하여 요소에서 새 XML 네임스페이스 접두사를 선언하거나 기존 XML 네임스페이스 접두사를 숨길 수 있습니다.  새 네임스페이스는 해당 요소의 자식 노드에서는 사용 가능하지만 포함 식의 XML 리터럴에서는 사용할 수 없습니다.  
  
> [!NOTE]
>  `xmlns` 네임스페이스 특성을 사용하여 XML 네임스페이스 접두사를 선언할 때는 특성 값이 상수 문자열이어야 합니다.  따라서 `xmlns` 특성을 사용하는 것은 `Imports` 문을 사용하여 XML 네임스페이스를 선언하는 것과 같습니다.  포함 식을 사용하여 XML 네임스페이스 값을 지정할 수는 없습니다.  
  
## 참고 항목  
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [XML Literals Overview](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)