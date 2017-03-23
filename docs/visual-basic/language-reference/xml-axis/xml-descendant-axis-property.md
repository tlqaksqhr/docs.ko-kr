---
title: "XML 하위 항목 축 속성 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyDescendantsAxis
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 434dc90c643381bdc27b2da54a7418e39bf15e98
ms.lasthandoff: 03/13/2017

---
# <a name="xml-descendant-axis-property-visual-basic"></a>XML 하위 항목 축 속성(Visual Basic)
다음의 하위 항목에 대 한 액세스를 제공:는 <xref:System.Xml.Linq.XElement>개체는 <xref:System.Xml.Linq.XDocument>개체, 컬렉션을 <xref:System.Xml.Linq.XElement>개체 또는 컬렉션을 <xref:System.Xml.Linq.XDocument>개체.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
## <a name="syntax"></a>구문  
  
```  
  
object...<descendant>  
```  
  
## <a name="parts"></a>요소  
 `object`  
 필수 요소. <xref:System.Xml.Linq.XElement>개체는 <xref:System.Xml.Linq.XDocument>개체, 컬렉션을 <xref:System.Xml.Linq.XElement>개체 또는 컬렉션을 <xref:System.Xml.Linq.XDocument>개체.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
 ...<  
 필수 요소. 하위 항목 축 속성의 시작을 나타냅니다.  
  
 `descendant`  
 필수 요소. 폼에 액세스 하려면 하위 노드의 이름 [`prefix``:`]`name`합니다.  
  
|파트|설명|  
|----------|-----------------|  
|`prefix`|선택적 요소. 하위 노드에 대 한 XML 네임 스페이스 접두사입니다. 사용 하 여 정의 된 전역 XML 네임 스페이스 여야는 `Imports` 문입니다.|  
|`name`|필수 요소. 하위 노드의 로컬 이름입니다. 참조 [선언 된 XML 요소 및 특성의 이름을](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.|  
  
 \>  
 필수 요소. 하위 항목 축 속성의 끝을 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 컬렉션을 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement>  
  
## <a name="remarks"></a>주의  
 XML 하위 항목 축 속성을 사용 하 여 하위 노드 이름을 사용 하 여 액세스는 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>개체 또는 컬렉션에서 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>개체.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> XML을 사용 하 여 `Value` 반환된 된 컬렉션의 첫 번째 하위 노드의 값에 액세스 하는 속성입니다. 자세한 내용은 참조 [XML 값 속성](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)합니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러는 하위 항목 축 속성에 대 한 호출으로 변환 된 <xref:System.Xml.Linq.XContainer.Descendants%2A>메서드.</xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
## <a name="xml-namespaces"></a>XML 네임스페이스  
 하위 항목 축 속성의 이름은 전역적으로 선언 된 XML 네임 스페이스만 사용할 수는 `Imports` 문입니다. XML 요소 리터럴 내에서 로컬로 선언 된 XML 네임 스페이스를 사용할 수 없습니다. 자세한 내용은 참조 [Imports 문 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에 라는 첫 번째 하위 노드의 값에 액세스 하는 방법을 보여 줍니다 `name` 및 명명 된 모든 하위 노드의 값 `phone` 에서 `contacts` 개체입니다.  
  
 [!code-vb[VbXMLSamples #&25;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>예제  
 다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음 다음 네임 스페이스의 접두사는 XML 리터럴을 만들고 정규화 된 이름 가진 첫 번째 자식 노드 값에 액세스를 사용 하 여 `ns:name`합니다.  
  
 [!code-vb[VbXMLSamples #&26;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XElement>   
 [XML 축 속성](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [선언된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
