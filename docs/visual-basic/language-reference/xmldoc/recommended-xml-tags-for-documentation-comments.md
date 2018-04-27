---
title: 문서 주석에 대한 권장 XML 태그(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7815d4c9fddc4e760c7495ef7a2509c55141e96e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>문서 주석에 대한 권장 XML 태그(Visual Basic)
Visual Basic 컴파일러에는 XML 파일에 코드에서 문서 주석을 처리할 수 있습니다. 문서에 XML 파일을 처리 하려면 추가 도구를 사용할 수 있습니다.  
  
 XML 주석 형식 등과 같은 코드 구문에서 허용 하 고 멤버를 입력 합니다. 부분 형식에 대 한 종류의 한 부분일 뿐 해당 멤버의 주석 처리에 제한이 없으며 있지만 XML 주석을 가질 수 있습니다.  
  
> [!NOTE]
>  문서 주석에 네임 스페이스에 적용할 수 없습니다. 이유는 네임 스페이스가 하나 여러 어셈블리에 확장 수 모든 어셈블리를 동시에 로드할 수 해야 합니다.  
  
 컴파일러는 유효한 XML 태그를 모두 처리 합니다. 다음과 같은 태그는 사용자 용 설명 문서에 자주 사용 되는 기능을 제공합니다.  
  
||||  
|---|---|---|  
|[\<c>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<예외 >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<포함 >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<사용 권한 >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<참조 >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> 컴파일러 구문을 확인 합니다.)  
  
> [!NOTE]
>  꺾쇠 괄호에 문서 주석의 텍스트를 원하는 경우 사용 하 여 `<` 및 `>`합니다. 예를 들어 문자열 `"<text in angle brackets>"` 로 표시 됩니다 `<text in angle``brackets>`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드를 XML로 문서화](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
