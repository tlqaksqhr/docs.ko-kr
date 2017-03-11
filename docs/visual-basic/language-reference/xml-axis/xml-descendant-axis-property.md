---
title: "XML Descendant Axis Property (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyDescendantsAxis"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, accessing XML"
  - "XML descendant axis property [Visual Basic]"
  - "descendant axis property [Visual Baisc]"
  - "XML axis [Visual Basic], descendant"
  - "XML [Visual Basic], accessing"
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# XML Descendant Axis Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체에 대한 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체에 대한 컬렉션의 하위 항목에 대한 액세스를 제공합니다.  
  
## 구문  
  
```  
  
object...<descendant>  
```  
  
## 요소  
 `object`  
 필수 요소.  <xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체에 대한 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체에 대한 컬렉션으로 구성되어 있습니다.  
  
 ...\<  
 필수 요소.  하위 항목 축 속성의 시작을 나타냅니다.  
  
 `descendant`  
 필수 요소.  \[`prefix``:`\]`name` 형식의 액세스할 하위 항목 노드의 이름입니다.  
  
|파트|설명|  
|--------|--------|  
|`prefix`|선택적 요소.  하위 항목 노드의 XML 네임스페이스 접두사입니다.  `Imports` 문을 사용하여 정의된 전역 XML 네임스페이스여야 합니다.|  
|`name`|필수 요소.  하위 항목 노드의 로컬 이름입니다.  자세한 내용은 [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)를 참조하십시오.|  
  
 \>  
 필수 요소.  하위 항목 축 속성의 끝을 나타냅니다.  
  
## 반환 값  
 <xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.  
  
## 설명  
 XML 하위 항목 축 속성을 사용하여 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체의 이름 또는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체에 대한 컬렉션의 이름으로 하위 항목 노드에 액세스할 수 있습니다.  XML `Value` 속성을 사용하여 반환된 컬렉션의 첫 번째 하위 항목 노드의 값에 액세스할 수 있습니다.  자세한 내용은 [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)를 참조하십시오.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에서는 하위 항목 축 속성을 <xref:System.Xml.Linq.XContainer.Descendants%2A> 메서드에 대한 호출로 변환합니다.  
  
## XML 네임스페이스  
 하위 항목 축 속성의 이름은 `Imports` 문을 사용하여 전역으로 선언된 XML 네임스페이스만 사용할 수 있습니다.  XML 요소 리터럴 내에 로컬로 선언된 XML 네임스페이스는 사용할 수 없습니다.  자세한 내용은 [Imports Statement \(XML Namespace\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `contacts` 개체의 `name`이라는 첫 번째 하위 항목 노드의 값과 `phone`이라는 모든 하위 항목 노드의 값에 액세스하는 방법을 보여 줍니다.  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-descendant-axis-prop_1.vb)]  
  
 이 코드가 표시하는 텍스트는 다음과 같습니다.  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## 예제  
 다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언합니다.  그런 다음 네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름인 `ns:name`을 사용하여 첫 번째 자식 노드의 값에 액세스합니다.  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-descendant-axis-prop_2.vb)]  
  
 이 코드가 표시하는 텍스트는 다음과 같습니다.  
  
 `Name: Patrick Hines`  
  
## 참고 항목  
 <xref:System.Xml.Linq.XElement>   
 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)