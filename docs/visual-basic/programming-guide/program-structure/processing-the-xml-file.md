---
title: XML 파일 처리(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 524a54443b8f2365252f11282ca29fc492bef351
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000235"
---
# <a name="processing-the-xml-file-visual-basic"></a>XML 파일 처리(Visual Basic)
컴파일러는 문서 생성을 위해 태그가 지정되는 코드의 각 구문에 대해 ID 문자열을 생성합니다. (코드에 태그를 하는 방법에 대 한 자세한 내용은 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md).) ID 문자열은 구문을 고유하게 식별합니다. XML 파일을 처리 하는 프로그램은 해당 하는 데 ID 문자열을 사용할 수 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 메타 데이터/리플렉션 항목입니다.  
  
 XML 파일에 코드의 계층적 표현이 아닙니다. 각 요소에 대해 생성 된 ID 사용 하 여 플랫 목록입니다.  
  
 컴파일러는 ID 문자열을 생성할 때 다음 규칙을 관찰합니다.  
  
-   문자열에 공백이 배치되지 않았습니다.  
  
-   ID 문자열의 첫 부분이 뒤에 콜론이 붙은 한 글자로 식별 대상 멤버를 식별합니다. 멤버 유형은 사용 됩니다.  
  
|문자|설명|  
|---|---|  
|N|네임스페이스(namespace)<br /><br /> 네임 스페이스에 문서 주석을 추가할 수는 없지만,에 대 한 CREF 참조를 만들 수 있습니다 지원 되는 경우.|  
|T|형식: `Class`, `Module`를 `Interface`합니다 `Structure`, `Enum`, `Delegate`|  
|F|필드: `Dim`|  
|P|속성: `Property` (기본 속성 포함)|  
|M|메서드: `Sub`하십시오 `Function`, `Declare`, `Operator`|  
|E|이벤트: `Event`|  
|!|오류 문자열<br /><br /> 문자열의 나머지 부분은 오류에 대한 정보를 제공합니다. Visual Basic 컴파일러는 확인할 수 없는 링크에 대 한 오류 정보를 생성 합니다.|  
  
-   두 번째 부분을 `String` 네임 스페이스의 루트에서 시작 하는 항목의 정규화 된 이름입니다. 이름 항목, 해당 바깥쪽 형식 및 네임 스페이스는 마침표로 구분 됩니다. 마침표를 포함 하는 항목 자체의 이름, 숫자 기호에서 대체 됩니다 (#). 항목이 직접 해당 이름에에서 숫자 기호 간주 됩니다. 정규화 된 이름에 예를 들어 합니다 `String` 생성자 것 `System.String.#ctor`입니다.  
  
-   속성 및 메서드의 경우 메서드에 대한 인수가 있으면 괄호로 묶인 인수 목록이 문자열 뒤에 붙습니다. 인수가 없으면 괄호도 없습니다. 인수는 쉼표로 구분됩니다. 각 인수의 인코딩은 그대로 따릅니다에서 인코딩하는 방법을 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 서명 합니다.  
  
## <a name="example"></a>예제  
 다음 코드는 클래스에 대 한 ID 문자열 하는 방법을 보여 줍니다. 하 고 해당 멤버 생성 됩니다.  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [방법: XML 문서 만들기](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
