---
title: "XML 자식 축 속성 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyChildAxis
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
caps.latest.revision: 18
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
ms.openlocfilehash: 97b92f9e94ad709c4d8ce944577eb23edc84b328
ms.lasthandoff: 03/13/2017

---
# <a name="xml-child-axis-property-visual-basic"></a>XML 자식 축 속성(Visual Basic)
다음 중 하나의 자식에 액세스할 수:는 <xref:System.Xml.Linq.XElement>개체는 <xref:System.Xml.Linq.XDocument>개체, 컬렉션을 <xref:System.Xml.Linq.XElement>개체 또는 컬렉션을 <xref:System.Xml.Linq.XDocument>개체.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
## <a name="syntax"></a>구문  
  
```  
  
object.<child>  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`object`|필수 요소. <xref:System.Xml.Linq.XElement>개체는 <xref:System.Xml.Linq.XDocument>개체, 컬렉션을 <xref:System.Xml.Linq.XElement>개체 또는 컬렉션을 <xref:System.Xml.Linq.XDocument>개체.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>|  
|.<|필수 요소. 자식 축 속성의 시작을 나타냅니다.|  
|`child`|필수 요소. 폼의 액세스 하는 자식 노드의 이름 [`prefix``:`]`name`합니다.<br /><br /> -   `Prefix`-선택 사항입니다. 자식 노드에 대한 XML 네임스페이스 접두사입니다. `Imports` 문으로 정의되는 전역 XML 네임스페이스여야 합니다.<br />-   `Name`-필요합니다. 로컬 자식 노드 이름입니다. 참조 [선언 된 XML 요소 및 특성의 이름을](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.|  
|>|필수 요소. 자식 축 속성의 끝을 나타냅니다.|  
  
## <a name="return-value"></a>반환 값  
 컬렉션을 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement>  
  
## <a name="remarks"></a>주의  
 이름을 사용 하 여 자식 노드에 액세스할 수 있는 XML 자식 축 속성을 사용할 수는 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>개체 또는 컬렉션에서 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>개체.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> XML을 `Value` 속성을 사용하여 반환 모음에 있는 첫 번째 자식 노드의 값에 액세스합니다. 자세한 내용은 참조 [XML 값 속성](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)합니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 변환 자식 축 속성에 대 한 호출에서 <xref:System.Xml.Linq.XContainer.Elements%2A>메서드.</xref:System.Xml.Linq.XContainer.Elements%2A>  
  
## <a name="xml-namespaces"></a>XML 네임스페이스  
 자식 축 속성의 이름은 `Imports` 문을 사용해 전역적으로 선언된 XML 네임스페이스 접두사만 사용할 수 있습니다. XML 요소 리터럴 내에서 로컬로 선언된 XML 네임스페이스 접두사를 사용할 수 없습니다. 자세한 내용은 참조 [Imports 문 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `contact` 개체에서 이름이 `phone`인 자식 노드에 액세스하는 방법을 보여 줍니다.  
  
 [!code-vb[VbXMLSamples #&17;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>예제  
 다음 예제에서는 `contacts` 개체의 `contact` 자식 축 속성에서 반환된 모음에서 이름이 `phone`인 자식 노드에 액세스하는 방법을 보여 줍니다.  
  
 [!code-vb[VbXMLSamples #&18;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>예제  
 다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음 네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름 `ns:name`을 가진 첫 번째 자식 노드에 액세스합니다.  
  
 [!code-vb[VbXMLSamples #&19;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XElement>   
 [XML 축 속성](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [선언된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
