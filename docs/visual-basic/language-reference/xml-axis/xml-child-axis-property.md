---
title: "XML Child Axis Property (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyChildAxis"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, accessing XML"
  - "XML axis [Visual Basic], child"
  - "child axis property [Visual Basic]"
  - "XML child axis property [Visual Basic]"
  - "XML [Visual Basic], accessing"
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# XML Child Axis Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체 컬렉션 또는 <xref:System.Xml.Linq.XDocument> 개체 컬렉션 중 하나의 자식에 액세스할 수 있도록 합니다.  
  
## 구문  
  
```  
  
object.<child>  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`object`|필수.  <xref:System.Xml.Linq.XElement> 개체, <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 개체의 모음 또는 <xref:System.Xml.Linq.XDocument> 개체의 모음입니다.|  
|.\<|필수 요소.  자식 축 속성의 시작을 나타냅니다.|  
|`child`|필수.  액세스할 자식 노드의 이름이며 \[`prefix``:`\]`name`의 형식입니다.<br /><br /> -   `Prefix` \- 선택적 요소로서,  자식 노드에 대한 XML 네임스페이스 접두사입니다.  `Imports` 문으로 정의되는 전역 XML 네임스페이스여야 합니다.<br />-   `Name` \- 필수입니다.  로컬 자식 노드 이름입니다.  [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)을 참조하세요.|  
|\>|필수 요소.  자식 축 속성의 끝을 나타냅니다.|  
  
## 반환 값  
 <xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.  
  
## 설명  
 XML 자식 축 속성을 사용하여 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체, <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체 모음에서 이름을 기준으로 자식 노드에 액세스할 수 있습니다.  XML을 `Value` 속성을 사용하여 반환 모음에 있는 첫 번째 자식 노드의 값에 액세스합니다.  자세한 내용은 [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)을 참조하세요.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러는 자식 축 속성을 <xref:System.Xml.Linq.XContainer.Elements%2A> 메서드 호출로 변환합니다.  
  
## XML 네임스페이스  
 자식 축 속성의 이름은 `Imports` 문을 사용해 전역적으로 선언된 XML 네임스페이스 접두사만 사용할 수 있습니다.  XML 요소 리터럴 내에서 로컬로 선언된 XML 네임스페이스 접두사를 사용할 수 없습니다.  자세한 내용은 [Imports Statement \(XML Namespace\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)을 참조하세요.  
  
## 예제  
 다음 예제에서는 `contact` 개체에서 이름이 `phone`인 자식 노드에 액세스하는 방법을 보여 줍니다.  
  
 [!code-vb[VbXMLSamples#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Home Phone = 206-555-0144`  
  
## 예제  
 다음 예제에서는 `contacts` 개체의 `contact` 자식 축 속성에서 반환된 모음에서 이름이 `phone`인 자식 노드에 액세스하는 방법을 보여 줍니다.  
  
 [!code-vb[VbXMLSamples#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Home Phone = 206-555-0144`  
  
## 예제  
 다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음  네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름 `ns:name`을 가진 첫 번째 자식 노드에 액세스합니다.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Patrick Hines`  
  
## 참고 항목  
 <xref:System.Xml.Linq.XElement>   
 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)