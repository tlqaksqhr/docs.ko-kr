---
title: Visual Basic 명명 규칙
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: cb7e9f2a577e95e09fde885df1a78aea4e7fa466
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651920"
---
# <a name="visual-basic-naming-conventions"></a>Visual Basic 명명 규칙
Visual Basic 응용 프로그램의 요소 이름을 지정할 때 해당 이름의 첫 번째 문자는 영문자 또는 밑줄 이어야 합니다. 단, 이름이 밑줄로 시작 준수 하지 않는 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 다음 제안 사항을 명명에 적용 됩니다.  
  
-   각 단어에는 대문자를 사용 하 여 이름 시작 `FindLastRecord` 및 `RedrawMyForm`합니다.  
  
-   와 같이 동사, 함수 및 메서드 이름은 시작 `InitNameArray` 또는 `CloseDialog`합니다.  
  
-   클래스, 구조체, 모듈 및 명사 속성 이름에서와 같이 시작 `EmployeeName` 또는 `CarAccessory`합니다.  
  
-   인터페이스 이름을 접두사로 시작 "I"는 명사 또는 명사구를 같은 뒤 `IComponent`, 또는 같은 인터페이스의 동작을 설명 하는 형용사와 `IPersistable`합니다. 약어 혼동 될 수 있기 때문 약어를 제한적으로 사용, 사용 및 밑줄을 사용 하지 않는 합니다.  
  
-   이벤트 처리기의 이름은 다음 이벤트의 유형을 설명 하는 명사로 시작는 "`EventHandler`"에서처럼: 접미사"`MouseEventHandler`"입니다.  
  
-   이벤트 인수 클래스의 이름에 포함 된 "`EventArgs`" 접미사입니다.  
  
-   이벤트 "before" 또는 "after"의 개념에, 하는 경우의 접미사를 사용 현재 또는 과거 시제에서와 같이 "`ControlAdd`"또는"`ControlAdded`"입니다.  
  
-   Long 또는 자주 사용 되는 용어에 대 한 예를 들어, "HTML", "Hypertext Markup Language" 하는 대신, 적절 한 이름 길이 유지 하려면 약어를 사용 합니다. 일반적으로 변수 이름은 32 자 보다 큰 낮은 해상도로 설정 된 모니터에 대 한 읽기 하기 어렵습니다. 프로그램 약어는 전체 응용 프로그램 전체에서 일치 하는지 확인 합니다. 임의로 전환 "HTML"과 "Hypertext Markup Language" 프로젝트에서 혼란이 발생할 수 있습니다.  
  
-   내부 범위에서 외부 범위에서 이름으로 동일한 이름을 사용 하지 마십시오. 잘못 된 변수에 액세스 하는 경우 오류가 발생할 수 있습니다. 변수와 동일한 이름 가진 키워드 사이 충돌이 발생 하는 경우에 앞에 적절 한 형식 라이브러리 키워드를 식별 해야 합니다. 예를 들어, 라는 변수를 설정한 경우 `Date`, 내장 함수를 사용할 수 있습니다 `Date` 함수를 호출 하 여만 <xref:System.DateTime.Date%2A?displayProperty=nameWithType>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드에서 요소 이름으로 사용되는 키워드](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 [Me, My, MyBase 및 MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Visual Basic 언어 참조](../../../visual-basic/language-reference/index.md)
