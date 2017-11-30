---
title: "열거형 및 이름 한정(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cb97d6a8f4b7e81f2b759010214e200ec63ff21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>열거형 및 이름 한정(Visual Basic)
일반적으로 열거형의 멤버를 참조할 때 멤버 이름을 열거형 이름으로 정규화 해야 합니다. 예를 들어, 참조 하는 `Sunday` 소속 프로그램 `Days` 열거형에서 다음 구문을 사용:  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## <a name="using-the-imports-statement"></a>Imports 문 사용  
 추가 하 여 정규화 된 이름을 사용 하 여 방지할 수 있습니다는 `Imports` 문을 다음 예제와 같이 코드의 네임 스페이스 선언 섹션에 있습니다.  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 `Imports` 문 내에서 또는 참조 된 프로젝트 및 어셈블리에서 네임 스페이스 이름을 가져옵니다 문이 표시 되는 모듈과 동일한 프로젝트. 이 문이 추가 되 면 다음 예제와 같이 한정 하지 않고 열거형 멤버를 참조할 수 있습니다.  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 열거형에 관련 된 상수 집합을 구성 하 여 다양 한 상황에서 상수 동일한 이름을 사용할 수 있습니다. 예를 들어에서 weekday 상수에 같은 이름을 사용할 수 있습니다는 `Days` 및 `WorkDays` 열거형입니다. 사용 하는 경우는 `Imports` 열거형 문을 주의 해야 참조가 모호해 지지 않도록 합니다. 다음 예제를 참조하세요.  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 있다고 가정할 경우 `Monday` 둘 다의 구성원은 `Days` 열거형 및 `Workdays` 열거형이이 코드는 컴파일러 오류를 생성 합니다. 각 상수를 참조할 때 참조가 모호해 지지 않도록, 상수 이름을 해당 열거형으로 한정 합니다. 다음 코드를 참조 하는 `Saturday` 의 상수는 `Days` 및 `WorkDays` 열거형입니다.  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [방법: 열거형 멤버 참조](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [방법: Visual Basic에서 열거형 반복](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [방법: 열거형 값과 연결된 문자열 확인](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [열거형을 사용하는 경우](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [상수 및 리터럴 데이터 형식](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Enum 문](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
