---
title: XML 파일 처리(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 6be7597f1c03d8aa044eba70ef6287cfc07d9b84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="processing-the-xml-file-visual-basic"></a>XML 파일 처리(Visual Basic)
컴파일러는 문서 생성을 위해 태그가 지정되는 코드의 각 구문에 대해 ID 문자열을 생성합니다. (코드에 태그를 하는 방법에 대 한 정보를 참조 하십시오. [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) ID 문자열은 구문을 고유하게 식별합니다. XML 파일을 처리 하는 프로그램 해당 식별 하는 ID 문자열을 사용할 수 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 메타 데이터/리플렉션 항목입니다.  
  
 XML 파일의 코드; 계층적 나타내지는 않습니다. 각 요소에 대해 생성된 된 ID로 단순 목록입니다.  
  
 컴파일러는 ID 문자열을 생성할 때 다음 규칙을 관찰합니다.  
  
-   문자열에 공백이 없습니다 배치 됩니다.  
  
-   ID 문자열의 첫 번째 부분 뒤에 콜론을 단일 문자로 식별 되 고 멤버의 종류를 식별 합니다. 다음과 같은 멤버 형식은 사용 합니다.  
  
|문자|설명|  
|---|---|  
|N|네임스페이스(namespace)<br /><br /> 네임 스페이스 문서 주석을 추가할 수 없지만, CREF 참조를 만들 수 있습니다 지원 되는 경우.|  
|T|형식: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|F|필드: `Dim`|  
|P|속성: `Property` (기본 속성 포함)|  
|M|방법: `Sub`, `Function`, `Declare`, `Operator`|  
|E|이벤트: `Event`|  
|!|오류 문자열<br /><br /> 문자열의 나머지 부분은 오류에 대한 정보를 제공합니다. Visual Basic 컴파일러는 확인할 수 없는 링크에 대 한 오류 정보를 생성 합니다.|  
  
-   두 번째 부분에서 `String` 네임 스페이스의 루트에서 시작 하는 항목의 정규화 된 이름입니다. 이름, 해당 바깥쪽 형식 항목과의 네임 스페이스는 마침표로 구분 됩니다. 항목 이름에 마침표가 하는 경우에 숫자 기호 대체 (#). 항목이 직접 이름에에서 숫자 기호 간주 됩니다. 정규화 된 이름 예를 들어는 `String` 생성자 것 `System.String.#ctor`합니다.  
  
-   속성 및 메서드의 경우 메서드에 대한 인수가 있으면 괄호로 묶인 인수 목록이 문자열 뒤에 붙습니다. 인수가 없으면 괄호도 없습니다. 인수는 쉼표로 구분됩니다. 각 인수의 인코딩은 뒤에 오는 직접에서 인코딩하는 방법을 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 서명 합니다.  
  
## <a name="example"></a>예제  
 다음 코드는 클래스에 대 한 ID 문자열 하는 방법을 보여 줍니다. 및 해당 멤버 생성 됩니다.  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
