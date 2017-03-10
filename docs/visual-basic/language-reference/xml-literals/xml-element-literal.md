---
title: "XML 요소 리터럴(Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralElement"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML 요소 리터럴[Visual Basic]"
  - "요소 리터럴[Visual Basic]"
  - "요소, XML 리터럴 [Visual Basic]"
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: 32
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 32
---
# XML 요소 리터럴(Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

나타내는 리터럴입니다는 <xref:System.Xml.Linq.XElement> 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a>요소  
  
-   `<`  
  
     필수 요소. 시작 요소 태그를 엽니다.  
  
-   `name`  
  
     필수 요소. 요소 이름입니다. 형식은 다음 중 하나입니다.  
  
    -   폼의 요소 이름에 대 한 리터럴 텍스트 [`ePrefix``:`]`eName`, 위치:  
  
        |||  
        |-|-|  
        |파트|설명|  
        |`ePrefix`|선택적 요소. 요소에 대 한 XML 네임 스페이스 접두사입니다. 전역으로 정의 된 XML 네임 스페이스 여야는 `Imports` 파일 또는 프로젝트 수준 또는 로컬이 요소 또는 부모 요소에 정의 된 XML 네임 스페이스에서 문입니다.|  
        |`eName`|필수 요소. 요소 이름입니다. 형식은 다음 중 하나입니다.<br /><br /> -리터럴 텍스트입니다. 참조 [선언 된 XML 요소 및 특성의 이름을](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.<br />포함 형식의 식이 `<%=` e`NameExp` `%>`합니다. 유형의 `eNameExp` 해야 `String` 또는 형식으로 암시적으로 변환할 수 있는 <xref:System.Xml.Linq.XName>합니다.|  
  
    -   형식의 식이 포함 된 `<%=` `nameExp` `%>`합니다. 유형의 `nameExp` 해야 `String` 또는 형식으로 암시적으로 변환할 <xref:System.Xml.Linq.XName>합니다. 요소의 닫는 태그에서 포함된 식을 허용 되지 않습니다.  
  
-   `attributeList`  
  
     선택적 요소. 리터럴에서 선언 된 특성의 목록입니다.  
  
     `attribute [ attribute ... ]`  
  
     각 `attribute` 에 다음 구문 중 하나:  
  
    -   특성 형식의 할당 [`aPrefix``:`]`aName``=``aValue`, 위치:  
  
        |||  
        |-|-|  
        |파트|설명|  
        |`aPrefix`|선택적 요소. 특성에 대 한 XML 네임 스페이스 접두사입니다. 전역으로 정의 된 XML 네임 스페이스 여야는 `Imports` 문 또는이 요소 또는 부모 요소에 정의 된 로컬 XML 네임 스페이스입니다.|  
        |`aName`|필수 요소. 특성의 이름입니다. 형식은 다음 중 하나입니다.<br /><br /> -리터럴 텍스트입니다. 참조 [선언 된 XML 요소 및 특성의 이름을](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다.<br />포함 형식의 식이 `<%=` `aNameExp` `%>`합니다. 유형의 `aNameExp` 해야 `String` 또는 형식으로 암시적으로 변환할 수 있는 <xref:System.Xml.Linq.XName>합니다.|  
        |`aValue`|선택적 요소. 특성의 값입니다. 형식은 다음 중 하나입니다.<br /><br /> -따옴표로 묶인 리터럴 텍스트입니다.<br />포함 형식의 식이 `<%=` `aValueExp` `%>`합니다. 모든 형식이 허용 됩니다.|  
  
    -   형식의 식이 포함 된 `<%=` `aExp` `%>`합니다.  
  
-   `/>`  
  
     선택적 요소. 요소 콘텐츠가 없는 빈 요소를 나타냅니다.  
  
-   `>`  
  
     필수 요소. 이상 버전 또는 빈 요소 태그를 종료합니다.  
  
-   `elementContents`  
  
     선택적 요소. 요소 콘텐츠입니다.  
  
     `content [ content ... ]`  
  
     각 `content` 다음 중 하나일 수 있습니다.  
  
    -   리터럴 텍스트입니다. 에 있는 모든 공백을 `elementContents` 리터럴 텍스트가 있으면 의미를 갖습니다.  
  
    -   형식의 식이 포함 된 `<%=` `contentExp` `%>`합니다.  
  
    -   XML 요소 리터럴입니다.  
  
    -   XML 주석 리터럴입니다. 참조 [XML 주석 리터럴](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)합니다.  
  
    -   XML 처리 명령 리터럴입니다. 참조 [XML 처리 명령 리터럴](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)합니다.  
  
    -   XML CDATA 리터럴입니다. 참조 [XML CDATA 리터럴](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)합니다.  
  
-   `</`[`name`]`>`  
  
     선택 사항입니다. 닫는 태그를 요소를 나타냅니다. 선택적 `name` 포함된 된 식의 결과 경우에 매개 변수가 허용 되지 않습니다.  
  
## <a name="return-value"></a>반환 값  
  <xref:System.Xml.Linq.XElement> 개체입니다.  
  
## <a name="remarks"></a>설명  
 XML 요소 리터럴 구문을 사용 하 여 만들려는 <xref:System.Xml.Linq.XElement> 코드에서 개체입니다.  
  
> [!NOTE]
>  XML 리터럴 줄 연속 문자를 사용 하지 않고 여러 줄을 확장할 수 있습니다. 이 기능을 사용 하는 XML 문서에서 콘텐츠를 복사 하 고에 직접 붙여넣을 수는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 프로그램입니다.  
  
 포함 형식의 식이 `<%=` `exp` `%>` 리터럴 XML 요소에 동적 정보를 추가할 수 있도록 합니다. 자세한 내용은 참조 [XML의 포함 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)합니다.  
  
  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러는 XML 요소 리터럴 호출으로 변환 된 <xref:System.Xml.Linq.XElement.%23ctor%2A> 생성자 및 필요한 경우는 <xref:System.Xml.Linq.XAttribute.%23ctor%2A> 생성자입니다.  
  
## <a name="xml-namespaces"></a>XML 네임스페이스  
 XML 네임 스페이스 접두사는 XML 리터럴을 여러 번 코드에서에서 동일한 네임 스페이스의에서 요소를 만들 수 있는 경우에 유용 합니다. 사용 하 여 정의 하는 전역 XML 네임 스페이스 접두사를 사용할 수는 `Imports` 문 또는 로컬 접두사를 사용 하 여 정의 `xmlns:``xmlPrefix`= "`xmlNamespace`" 특성 구문입니다. 자세한 내용은 참조 [Imports 문 (XML 네임 스페이스)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)합니다.  
  
 XML 네임 스페이스에 대 한 범위 지정 규칙에 따라 로컬 접두사 전역 접두사 보다 우선합니다. 그러나 XML 리터럴과 XML 네임 스페이스를 정의 하는 경우 해당 네임 스페이스 사용할 수 없는 경우 포함된 된 식에 표시 되는 식 포함된 식에 전역 XML 네임 스페이스에만 액세스할 수 있습니다.  
  
  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러는 XML 리터럴을에서 생성된 된 코드에서 하나의 로컬 네임 스페이스 정의로 사용 되는 각 글로벌 XML 네임 스페이스를 변환 합니다. 사용 되지 않는 전역 XML 네임 스페이스는 생성된 된 코드에 표시 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 개의 중첩 된 빈 요소가 포함 된 간단한 XML 요소를 만드는 방법을 보여 줍니다.  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-element-literal_1.vb)]  
  
 다음 텍스트를 표시합니다. 공지 리터럴 빈 요소의 구조를 유지 합니다.  
  
```  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 포함된 식을 사용 하 여 요소 이름을 지정 하 고 속성을 작성 하는 방법을 보여 줍니다.  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-element-literal_2.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
```  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 선언한 다음 그런 다음 XML 리터럴을 만드는 데 네임 스페이스의 접두사 값을 사용 하 고 요소의 최종 폼이 표시 됩니다.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-element-literal_3.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 컴파일러 전역 XML 네임 스페이스의 접두사는 XML 네임 스페이스에 대 한 접두사 정의로 변환 함을 알 수 있습니다. \< Ns:middle > 요소의 \< ns:inner1 > 요소에 대 한 XML 네임 스페이스 접두사를 재정의합니다. \< Ns:inner2 > 요소에 정의 된 네임 스페이스를 사용 하는 반면는 `Imports` 문입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XElement>   
 [선언 된 XML 요소 및 특성의 이름](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)   
 [XML 주석 리터럴](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)   
 [XML CDATA 리터럴](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)   
 [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML의 포함된 식](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Imports 문 (XML 네임 스페이스)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)