---
title: XML 특성 축 속성(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 3e02fd2ddc3928bdd2e9741737fc31fb2b16901c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604915"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>XML 특성 축 속성(Visual Basic)
에 대 한 특성의 값에 액세스할 수는 <xref:System.Xml.Linq.XElement> 개체 또는 컬렉션의 첫 번째 요소로 <xref:System.Xml.Linq.XElement> 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>요소  
 `object`  
 필수. <xref:System.Xml.Linq.XElement> 개체 또는 컬렉션 <xref:System.Xml.Linq.XElement> 개체입니다.  
  
 .@  
 필수 요소. 특성 축 속성의 시작을 나타냅니다.  
  
 <  
 선택 사항입니다. 특성의 이름의 시작 부분을 나타내는 경우 `attribute` Visual Basic에서 유효한 식별자가 아닙니다.  
  
 `attribute`  
 필수. 폼의에 액세스 하려면 특성의 이름을 [`prefix`:]`name`합니다.  
  
|파트|설명|  
|----------|-----------------|  
|`prefix`|선택 사항입니다. 특성에 대 한 XML 네임 스페이스 접두사입니다. `Imports` 문으로 정의되는 전역 XML 네임스페이스여야 합니다.|  
|`name`|필수. 로컬 특성 이름입니다. 참조 [선언 된 XML 요소 및 특성의 이름을](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.|  
  
 \>  
 선택 사항입니다. 특성의 이름의 끝을 나타냅니다 때 `attribute` Visual Basic에서 유효한 식별자가 아닙니다.  
  
## <a name="return-value"></a>반환 값  
 값을 포함 하는 문자열 `attribute`합니다. 특성 이름이 없으면 `Nothing` 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이름을 기준으로 특성의 값에 액세스 하는 XML 특성 축 속성을 사용할 수 있습니다는 <xref:System.Xml.Linq.XElement> 개체 또는 컬렉션의 첫 번째 요소에서 <xref:System.Xml.Linq.XElement> 개체입니다. 이름으로 특성 값을 검색 하거나 앞에 새 이름을 지정 하 여 요소에 새 특성을 추가할 수 있습니다는 @ 식별자입니다.  
  
 사용 하 여 XML 특성을 참조 하는 경우는 @ 식별자, 특성 값을 문자열로 반환 되 고 명시적으로 지정할 필요가 없습니다는 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성입니다.  
  
 Visual Basic 식별자에 대 한 명명 규칙에서 XML 특성에 대 한 명명 규칙은 서로 다릅니다. 이름이 유효한 Visual Basic 식별자가 아닌 XML 특성에 액세스 하려면 이름을 꺾쇠 괄호로 묶습니다 (\< 및 >).  
  
## <a name="xml-namespaces"></a>XML 네임스페이스  
 특성 축 속성의 이름을 사용 하 여 전역적으로 선언 된 XML 네임 스페이스 접두사만 사용할 수는 `Imports` 문. XML 요소 리터럴 내에서 로컬로 선언된 XML 네임스페이스 접두사를 사용할 수 없습니다. 자세한 내용은 참조 [Imports 문 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.  
  
## <a name="example"></a>예제  
 라는 XML 특성의 값을 가져오는 방법을 보여 주는 다음 예제 `type` 라고 하는 XML 요소의 컬렉션에서 `phone`합니다.  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 XML 요소에 대 한 특성을 선언적으로 XML의 그 특성의 인스턴스를 추가 하 여 동적으로 만드는 방법을 보여 줍니다는 <xref:System.Xml.Linq.XElement> 개체입니다. `type` 특성을 선언적으로 만든 및 `owner` 특성이 동적으로 만들어집니다.  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 꺾쇠 괄호 구문 라는 XML 특성의 값을 사용 하 여 `number-type`는 Visual Basic에서 유효한 식별자가 아닙니다.  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Phone type: work`  
  
## <a name="example"></a>예제  
 다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음 다음 네임 스페이스의 접두사는 XML 리터럴을 만들고 정규화 된 이름 가진 첫 번째 자식 노드에 액세스를 사용 하 여 "`ns:name`"입니다.  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Phone type: home`  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XElement>  
 [XML 축 속성](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [선언된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
