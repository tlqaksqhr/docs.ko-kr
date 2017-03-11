---
title: "XML Attribute Axis Property (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlPropertyAttributeAxis"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "attribute axis property [Visual Basic]"
  - "Visual Basic code, accessing XML"
  - "XML attribute axis property [Visual Basic]"
  - "XML axis [Visual Basic], attribute"
  - "XML [Visual Basic], accessing"
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# XML Attribute Axis Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:System.Xml.Linq.XElement> 개체의 특성이나 <xref:System.Xml.Linq.XElement> 개체의 컬렉션에 있는 첫 번째 요소의 값에 대한 액세스를 제공합니다.  
  
## 구문  
  
```  
  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## 요소  
 `object`  
 필수 요소.  <xref:System.Xml.Linq.XElement> 개체 또는 <xref:System.Xml.Linq.XElement> 개체의 컬렉션입니다.  
  
 .@  
 필수 요소.  특성 축 속성의 시작을 나타냅니다.  
  
 \<  
 선택적 요소.  `attribute`가 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 유효한 식별자가 아닌 경우 특성 이름의 시작 부분을 나타냅니다.  
  
 `attribute`  
 필수 요소.  \[`prefix`:\]`name` 폼에서 액세스할 특성의 이름입니다.  
  
|파트|설명|  
|--------|--------|  
|`prefix`|선택적 요소.  특성의 XML 네임스페이스 접두사입니다.  `Imports` 문을 사용하여 정의된 전역 XML 네임스페이스여야 합니다.|  
|`name`|필수 요소.  지역 특성 이름입니다.  자세한 내용은 [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)를 참조하십시오.|  
  
 \>  
 선택적 요소.  `attribute`가 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 유효한 식별자가 아닌 경우 특성 이름의 끝 부분을 나타냅니다.  
  
## 반환 값  
 `attribute`의 값을 포함하는 문자열입니다.  특성 이름이 없으면 `Nothing`이 반환됩니다.  
  
## 설명  
 XML 특성 축 속성을 사용하여 <xref:System.Xml.Linq.XElement> 개체 또는 <xref:System.Xml.Linq.XElement> 개체의 컬렉션에 있는 첫 번째 요소에서 이름으로 특성의 값에 액세스할 수 있습니다.  이름으로 특성 값을 검색하거나 새 이름 앞에 @ 식별자를 지정하여 요소에 새 특성을 추가할 수 있습니다.  
  
 @ 식별자를 사용하여 XML 특성을 참조하는 경우 특성 값은 문자열로 반환되며 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성을 명시적으로 지정할 필요가 없습니다.  
  
 XML 특성의 명명 규칙이 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 식별자의 명명 규칙과 다릅니다. 유효한 Visual Basic 식별자가 아닌 이름의 XML 특성에 액세스하려면 꺾쇠 괄호\(\< 및 \>\)로 이름을 묶습니다.  
  
## XML 네임스페이스  
 특성 축 속성의 이름은 `Imports` 문을 사용하여 전역으로 선언된 XML 네임스페이스 접두사만 사용할 수 있으며  XML 요소 리터럴 내에서 로컬로 선언된 XML 네임스페이스 접두사를 사용할 수 없습니다.  자세한 내용은 [Imports Statement \(XML Namespace\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `phone`이라는 XML 요소의 컬렉션에서 `type`이라는 XML 특성의 값을 가져오는 방법을 보여 줍니다.  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-attribute-axis-prope_1.vb)]  
  
 이 코드가 표시하는 텍스트는 다음과 같습니다.  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## 예제  
 다음 예제에서는 XML 요소에 대한 특성을 XML의 일부로 선언적으로 그리고 <xref:System.Xml.Linq.XElement> 개체의 인스턴스에 특성을 추가하여 동적으로 만드는 방법을 모두 보여 줍니다.  `type` 특성은 선언적으로 생성되며 `owne` 특성은 동적으로 생성됩니다.  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-attribute-axis-prope_2.vb)]  
  
 이 코드가 표시하는 텍스트는 다음과 같습니다.  
  
```  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## 예제  
 다음 예제에서는 꺾쇠 괄호 구문을 사용하여 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 유효한 식별자가 아닌 `number-type`이라는 XML 특성의 값을 가져옵니다.  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-attribute-axis-prope_3.vb)]  
  
 이 코드가 표시하는 텍스트는 다음과 같습니다.  
  
 `Phone type: work`  
  
## 예제  
 다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언합니다.  그런 다음 네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름인 "`ns:name`"을 사용하여 첫 번째 자식 노드에 액세스합니다.  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-attribute-axis-prope_4.vb)]  
  
 이 코드가 표시하는 텍스트는 다음과 같습니다.  
  
 `Phone type: home`  
  
## 참고 항목  
 <xref:System.Xml.Linq.XElement>   
 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)