---
title: -문서
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c77d063d64354bf4693ce82509f36be9d2e5b0c
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934481"
---
# <a name="-doc"></a>-문서
XML 파일에 대해 문서 주석을 처리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`+` &#124; `-`|선택 사항입니다. 지정 +, 또는 `-doc`, 컴파일러에서 문서 정보를 생성 하 고 XML 파일에 배치 하도록 합니다. 지정 `-` 지정 하지 않는 것과 같습니다 `-doc`, 하므로 만들 문서 정보가 없습니다.|  
|`file`|`-doc:`를 사용하는 경우 필수입니다. 컴파일의 소스 코드 파일에서 주석 사용 되는 출력 XML 파일을 지정 합니다. 파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").|  
  
## <a name="remarks"></a>설명  
 `-doc` 옵션 컴파일러 설명서 주석이 들어 있는 XML 파일을 생성 하는지 여부를 제어 합니다. 사용 하는 경우는 `-doc:file` 구문을 `file` 매개 변수는 XML 파일의 이름을 지정 합니다. 사용 하는 경우 `-doc` 또는 `-doc+`, 컴파일러는 실행 파일 또는 작성 된 라이브러리에서 XML 파일 이름을 사용 합니다. 사용 하는 경우 `-doc-` 지정 하지 마십시오는 `-doc` 옵션을 컴파일러 만들어지지는지 않습니다 XML 파일입니다.  
  
 소스 코드 파일에 문서 주석을 정의 앞에 야 수 있습니다.:  
  
-   사용자 정의 형식, 예는 [클래스](../../../visual-basic/language-reference/statements/class-statement.md) 또는 [인터페이스](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   멤버는 필드와 같이 [이벤트](../../../visual-basic/language-reference/statements/event-statement.md)를 [속성](../../../visual-basic/language-reference/statements/property-statement.md)를 [함수](../../../visual-basic/language-reference/statements/function-statement.md), 또는 [서브루틴](../../../visual-basic/language-reference/statements/sub-statement.md)합니다.  
  
 Visual Studio를 사용 하 여 생성된 된 XML 파일을 사용 하도록 [IntelliSense](/visualstudio/ide/using-intellisense) 기능에서 XML 파일의 파일 이름을 지원 하려는 어셈블리와 동일 합니다. Visual Studio 프로젝트에서 어셈블리를 참조할 때.xml 파일이 되도록 XML 파일을 어셈블리와 동일한 디렉터리에 있는지 확인 합니다. XML 설명서 파일이 프로젝트에서 참조 된 프로젝트 또는 프로젝트 내에서 코드에 대 한 작업에 IntelliSense에 대 한 필요 하지 않습니다.  
  
 사용 하 여 컴파일하지 않으면 `/target:module`, XML 파일에는 태그가 포함 `<assembly></assembly>`합니다. 이러한 태그 컴파일의 출력 파일에 대 한 어셈블리 매니페스트를 포함 하는 파일의 이름을 지정 합니다.  
  
 참조 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/index.md) 코드의 주석에서 문서를 생성 하는 방법에 대 한 합니다.  
  
|Visual studio에서 문서 통합 개발 환경 설정-|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **컴파일** 탭을 클릭합니다.<br />3.  값을 설정 합니다 **XML 문서 파일 생성** 상자입니다.|  
  
## <a name="example"></a>예  
 참조 [XML 사용 하 여 코드 문서화](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) 샘플입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [코드를 XML로 문서화](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
