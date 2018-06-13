---
title: 사용자 정의 상수(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: b4a7e2b63b930b98ee082c0104c24f6857b5b35b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648777"
---
# <a name="user-defined-constants-visual-basic"></a>사용자 정의 상수(Visual Basic)
상수는 숫자 또는 변경 되지 않는 문자열의 일어나는 의미 있는 이름입니다. 상수는 응용 프로그램 실행 중 변함없이 유지되는 값을 저장합니다. 컨트롤이 나 함께 작업 하는 구성 요소에 정의 된 상수를 사용할 수 하거나 직접 만들 수 있습니다. 직접 만든 상수를 상수 라고 *사용자 정의*합니다.  
  
 상수를 선언에서 `Const` 문을, 변수 이름을 만들 때와 동일한 방법 사용 합니다. 경우 `Option Strict` 은 `On`, 상수 형식을 명시적으로 선언 해야 합니다.  
  
## <a name="const-statement-usage"></a>Const 문 사용  
 A `Const` 문 수 수치 나타낼 또는 날짜/시간 값:  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 정의할 수도 있습니다 `String` 상수:  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 등호 기호의 오른쪽에 있는 식 ( `=` )는 숫자 또는 문자열 리터럴, 주로 발생 하지만 (하지만 식에 함수 호출이 포함 될 수 없습니다) 숫자 또는 문자열에 테이블이 되는 식이 될 수 있습니다. 이전에 정의 된 상수를 기준으로 상수를 정의할 수도 있습니다.  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a>사용자 정의 상수의 범위  
 A `Const` 문의 범위는 같은 위치에 선언 된 변수에 동일 합니다. 다음과 같은 방법으로 범위를 지정할 수 있습니다.  
  
-   프로시저 내에 존재 하는 상수를 만들려면 해당 절차 내에서 선언 합니다.  
  
-   클래스 내의 모든 프로시저에 속하지만 해당 모듈 외부 코드에 사용할 수 있는 상수를 만들려면 클래스의 선언 섹션에서 선언 합니다.  
  
-   어셈블리의 클라이언트 외부 아니라 어셈블리의 모든 구성원에 사용할 수 있는 상수를 만들려면 사용 하 여 선언는 `Friend` 클래스의 선언 섹션에는 키워드입니다.  
  
-   응용 프로그램에 걸쳐 사용할 수 있는 상수를 만들려면 사용 하 여 선언 된 `Public` 선언에서 키워드 섹션 클래스입니다.  
  
 자세한 내용은 참조 [하는 방법: A 상수 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)합니다.  
  
### <a name="avoiding-circular-references"></a>순환 참조를 방지합니다.  
 다른 상수 상수 정의 될 수 있습니다, 이므로에 실수로 만들 수는 *주기*, 또는 두 개 이상의 상수 간의 순환 참조. 다음 예제와 같이 서로 의해 정의 되는 각각 두 개 이상의 공용 상수 경우 순환이 발생:  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 주기가 발생 하는 경우 Visual Basic 컴파일러 오류를 생성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Const 문](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [상수 및 리터럴 데이터 형식](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [상수 및 열거형](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [열거형 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [상수 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
