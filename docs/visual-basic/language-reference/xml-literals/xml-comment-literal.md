---
title: "XML 주석 리터럴 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralComment
dev_langs:
- VB
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
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
ms.openlocfilehash: 88cfb984be42345ae1e5c998cf82aa1415d2455e
ms.lasthandoff: 03/13/2017

---
# <a name="xml-comment-literal-visual-basic"></a>XML 주석 리터럴(Visual Basic)
리터럴 나타내는 <xref:System.Xml.Linq.XComment>개체.</xref:System.Xml.Linq.XComment>  
  
## <a name="syntax"></a>구문  
  
```  
<!-- content -->  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`<!--`|필수 요소. XML 주석 시작을 나타냅니다.|  
|`content`|필수 요소. XML 설명에 표시할 텍스트입니다. 일련의 두 개의 하이픈 (-) 또는 닫는 태그에 인접 한 하이픈으로 끝날을 포함할 수 없습니다.|  
|`-->`|필수 요소. XML 주석 끝을 나타냅니다.|  
  
## <a name="return-value"></a>반환 값  
 <xref:System.Xml.Linq.XComment>개체.</xref:System.Xml.Linq.XComment>  
  
## <a name="remarks"></a>주의  
 XML 주석 리터럴 문서 콘텐츠가; 포함 되어 있지 않습니다. 문서에 대 한 정보를 포함 합니다. XML 주석 섹션 시퀀스 "-->"로 끝납니다. 이 다음 사항을 의미합니다.  
  
-   포함된 식 구분 기호는 유효한 XML 주석 내용 때문에 XML 주석 리터럴 포함된 식을 사용할 수 없습니다.  
  
-   XML 주석 섹션 중첩 될 수 없으므로 때문에 `content` "-->" 값을 포함할 수 없습니다.  
  
 XML 주석 리터럴를 변수에 할당할 수 있습니다 또는 리터럴 XML 요소에 포함할 수 있습니다.  
  
> [!NOTE]
>  XML 리터럴 줄 연속 문자를 사용 하지 않고 여러 줄을 확장할 수 있습니다. 이 기능을 사용 하는 XML 문서에서 콘텐츠를 복사 하 고에 직접 붙여넣을 수는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램입니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 호출을 XML 주석 리터럴 변환 하는 <xref:System.Xml.Linq.XComment.%23ctor%2A>생성자.</xref:System.Xml.Linq.XComment.%23ctor%2A>  
  
## <a name="example"></a>예제  
 다음 예제에서는 "This is a comment" 텍스트를 포함 하는 XML 주석을 만듭니다.  
  
 [!code-vb[VbXMLSamples #&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment>   
 [XML 요소 리터럴](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
