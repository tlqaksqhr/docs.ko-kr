---
title: "문서 주석 (Visual Basic)에 대 한 권장 XML 태그 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
dev_langs:
- VB
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
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
ms.openlocfilehash: c6a47c12bc24864ef6ac9f80054becad98ec97f1
ms.lasthandoff: 03/13/2017

---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>문서 주석에 대한 권장 XML 태그(Visual Basic)
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러는 XML 파일에 코드의 문서 주석 처리할 수 있습니다. 문서에 XML 파일을 처리 하려면 추가 도구를 사용할 수 있습니다.  
  
 XML 주석 형식 등과 같은 코드 구문에 대 한 허용 하 고 멤버를 입력 합니다. 부분 형식에 대 한 형식의 일부에 지나지 포함할 수 XML 주석, 있지만 해당 멤버의 주석 처리에 대 한 제한은 없습니다.  
  
> [!NOTE]
>  문서 주석 네임 스페이스에 적용할 수 없습니다. 이유는 하나의 네임 스페이스가 여러 어셈블리에 걸쳐 있을 수 모든 어셈블리를 동시에 로드할 필요가 있습니다.  
  
 컴파일러는 유효한 XML 태그를 모두 처리 합니다. 다음과 같은 태그는 사용자 설명서에서 자주 사용 되는 기능을 제공합니다.  
  
||||  
|---|---|---|  
|[\<c >](../../../visual-basic/language-reference/xmldoc/c.md)|[\<코드 >](../../../visual-basic/language-reference/xmldoc/code.md)|[\<예제 >](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<예외 >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<포함 >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<p a r a >](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref >](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<사용 권한 >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<설명 >](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<반환 >](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<요약 >](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<값 >](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> 는 컴파일러가 구문을 확인 합니다.)  
  
> [!NOTE]
>  사용 하 여 꺾쇠 괄호 문서 주석의 텍스트를 원한다 면 `<` 및 `>`합니다. 예를 들어, 문자열 `"<text in angle brackets>"` 로 나타납니다 `<text in angle``brackets>`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 사용 하 여 코드 문서화](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
