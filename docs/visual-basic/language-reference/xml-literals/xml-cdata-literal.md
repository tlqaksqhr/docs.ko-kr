---
title: "XML CDATA 리터럴 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralCdata
dev_langs:
- VB
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: 16
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
ms.openlocfilehash: 24e52bf203ff3df57e26137da24abcc2cb7e8e20
ms.lasthandoff: 03/13/2017

---
# <a name="xml-cdata-literal-visual-basic"></a>XML CDATA 리터럴(Visual Basic)
리터럴 나타내는 <xref:System.Xml.Linq.XCData>개체.</xref:System.Xml.Linq.XCData>  
  
## <a name="syntax"></a>구문  
  
```  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>요소  
 `<![CDATA[`  
 필수 요소. XML CDATA 섹션의 시작을 나타냅니다.  
  
 `content`  
 필수 요소. XML CDATA 섹션에 표시할 텍스트 내용입니다.  
  
 `]]>`  
 필수 요소. 섹션의 끝을 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 <xref:System.Xml.Linq.XCData>개체.</xref:System.Xml.Linq.XCData>  
  
## <a name="remarks"></a>주의  
 XML CDATA 섹션이 포함 되어 있기는 하지만 구문 분석 되지 포함 된 XML로 해야 하는 원시 텍스트를 포함 합니다. XML CDATA 섹션에는 모든 텍스트 포함 될 수 있습니다. 예약 된 XML 문자가 포함 됩니다. XML CDATA 섹션 순서와 함께 종료 "]] >"입니다. 이 다음 사항을 의미합니다.  
  
-   포함된 식 구분 기호는 유효한 XML CDATA 내용 때문에 XML 주석 리터럴 포함된 식을 사용할 수 없습니다.  
  
-   XML CDATA 섹션 중첩 될 수 없으므로 때문에 `content` 값을 포함할 수 없습니다 "]] >"입니다.  
  
 XML 주석 리터럴를 변수에 할당 하거나 리터럴 XML 요소에 포함할 수 있습니다.  
  
> [!NOTE]
>  XML 리터럴 여러 줄으로 나누어 입력할 수 있지만 줄 연속 문자를 사용 하지 않습니다. 이렇게 하면 XML 문서에서 콘텐츠를 복사 하 고에 직접 붙여넣을 수 있습니다는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램입니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 변환에 대 한 호출 하는 XML CDATA 리터럴는 <xref:System.Xml.Linq.XCData.%23ctor%2A>생성자.</xref:System.Xml.Linq.XCData.%23ctor%2A>  
  
## <a name="example"></a>예제  
 다음 예제에서는 텍스트를 포함 하는 CDATA 섹션 "리터럴을 포함 될 수 있습니다 \<XML > 태그"입니다.  
  
 [!code-vb[VbXMLSamples&23;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XCData></xref:System.Xml.Linq.XCData>   
 [XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
