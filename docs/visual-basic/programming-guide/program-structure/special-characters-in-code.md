---
title: 코드의 특수 문자(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b724c48320f74045d7192be6d6e269c00511ffc9
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="special-characters-in-code-visual-basic"></a>코드의 특수 문자(Visual Basic)
경우에 따라 영문자 또는 숫자 하지 않은 문자가 즉, 사용자 코드에 특수 문자를 사용 해야 할 수도 있습니다. 문장 부호 및 Visual Basic 문자 집합의 특수 문자는 프로그램 텍스트에서 컴파일러 또는 컴파일된 프로그램이 수행 하는 작업 정의에 이르기까지 다양 한 용도로 사용 합니다. 이러한 특수 문자는 수행할 작업을 지정하지 않습니다.  
  
## <a name="parentheses"></a>괄호  
 와 같은 프로시저를 정의 하는 경우 괄호를 사용 하 여 한 `Sub` 또는 `Function`합니다. 모든 프로시저 인수 목록을 괄호로 묶어야 합니다. 또한 사용 하면 괄호를 논리 그룹으로 변수나 인수에 대 한 특히 다시 정의할 복잡 한 식에서 연산자 우선 순위의 기본 순서입니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 값을 이전 코드의 실행 `d` 8.225의 값은 `e` 3입니다. 에 대 한 계산 `d` 는 기본 우선 순위를 사용 하 여 `/` 통해 `+` 와 같습니다 `d = b + (c / a)`합니다. 에 대 한 계산에 괄호 `e` 기본 우선 순위를 무시 합니다.  
  
## <a name="separators"></a>Separators  
 구분 기호는 이름 기준의 제안지 않습니다: 여러 코드 섹션입니다. Visual Basic의 경우 구분 기호 문자는 콜론 (`:`). 별도 줄이 아니라 한 줄에 여러 개의 문을 포함할 구분 기호를 사용 합니다. 이 공간을 절약 하 고 코드의 가독성을 향상 됩니다. 다음 예제에는 콜론으로 구분 된 세 가지 문을 보여 줍니다.  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 자세한 내용은 참조 [하는 방법: 해제 및 코드에서 문 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)합니다.  
  
 콜론 (`:`) 문자는 또한 문 레이블을 식별 하는 데 사용 됩니다. 자세한 내용은 참조 [하는 방법: Label 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)합니다.  
  
## <a name="concatenation"></a>연결 연산  
 사용 하 여는 `&` 에 대 한 연산자 *연결*, 또는 문자열을 함께 연결 합니다. 혼동 하지 마십시오는 `+` 숫자 값을 함께 추가 하는 연산자입니다. 사용 하는 경우는 `+` 연산자를 숫자 값으로 작업할 때 잘못 된 결과 얻을 수 있습니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 값을 이전 코드의 실행 `resultA` 21.01의 값은 `resultB` "10.0111로 실행" 됩니다.  
  
## <a name="member-access-operators"></a>멤버 액세스 연산자  
 점 형식의 멤버에 액세스 하려면 사용 (`.`) 또는 느낌표 (`!`) 연산자 형식 이름과 멤버 이름 사이입니다.  
  
### <a name="dot--operator"></a>점 (입니다.) 연산자  
 사용 하 여는 `.` 연산자를 클래스, 구조체, 인터페이스 또는 열거형의 멤버 액세스 연산자입니다. 필드, 속성, 이벤트 또는 메서드 멤버 수 있습니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a>느낌표 (!) 연산자  
 사용 된 `!` 사전 액세스 연산자와 클래스 또는 인터페이스에 대해서만 연산자입니다. 클래스 또는 인터페이스에는 단일 허용 하는 기본 속성이 있어야 `String` 인수입니다. 바로 뒤에 식별자는 `!` 연산자에 기본 속성을 문자열로 전달 된 인수 값이 됩니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 3 개의 출력의 줄 `MsgBox` 모든 값을 표시할 `32856`합니다. 첫 번째 줄은 속성에 대 한 일반적인 액세스를 사용 하 여 `index`, 두 번째에서는 팩트를 활용 하는 `index` 클래스의 기본 속성은 `hasDefault`, 세 번째 사전 클래스에 대 한 액세스를 사용 하 여 합니다.  
  
 두 번째 피연산자는 `!` 연산자 큰따옴표로 묶지 유효한 Visual Basic 식별자 여야 합니다 (`" "`). 즉, 문자열 리터럴 또는 문자열 변수를 사용할 수 없습니다. 다음과 같이 변경 하면 마지막 줄에서 `MsgBox` 호출 하면 오류가 발생 하기 때문에 `"X"` 은 괄호로 묶은 문자열 리터럴.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  기본 컬렉션에 대 한 참조를 명시적 이어야 합니다. 특히, 사용할 수 없습니다는 `!` 런타임에 바인딩된 변수에 연산자입니다.  
  
 `!` 문자는로 사용은 `Single` 문자를 입력 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
