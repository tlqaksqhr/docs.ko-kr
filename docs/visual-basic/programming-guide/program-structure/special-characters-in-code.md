---
title: "(Visual Basic) 코드의 특수 문자 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
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
dev_langs:
- VB
helpviewer_keywords:
- special characters, in code
- parentheses, using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator
- concatenation operators, special characters in code
- concatenation operators, vs. addition operator
- '! operator'
- separators, using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator
- addition operator
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
ms.openlocfilehash: 6d4b6e74ef3dfab3a7174da07cff7100fa4b2a2f
ms.lasthandoff: 03/13/2017

---
# <a name="special-characters-in-code-visual-basic"></a>코드의 특수 문자(Visual Basic)
숫자 하지 않은 문자를, 사용자 코드에서 특수 문자를 사용 해야 하는 경우가 있습니다. 문장 부호와 특수 문자는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자 집합은 컴파일러 또는 컴파일된 프로그램이 수행 하는 작업 정의에 프로그램 텍스트의 구성에서 다양 한 용도로 사용 합니다. 이러한 특수 문자는 수행할 작업을 지정하지 않습니다.  
  
## <a name="parentheses"></a>괄호  
 와 같은 프로시저를 정의 하는 경우 괄호를 사용 하 여 한 `Sub` 또는 `Function`합니다. 모든 프로시저 인수 목록은 괄호로 묶어야 합니다. 또한 괄호를 사용 하면 변수 또는 인수를 논리 그룹으로 배치 하는 데 특히 복잡 한 식에서 연산자 우선 순위의 기본 순서를 무시 하 게 합니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions #&11;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 앞의 코드에서 값을 실행 하 고 `d` 은 8.225 값 `e` 은 3입니다. 에 대 한 계산 `d` 는 기본 우선 순위를 사용 하 여 `/` 통해 `+` 와 같습니다 `d = b + (c / a)`합니다. 에 대 한 계산에 괄호 `e` 기본 우선 순위를 무시 합니다.  
  
## <a name="separators"></a>Separators  
 구분 기호 그 이름이 의미 하는 기능을 수행 합니다: 여러 코드 섹션입니다. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 구분 기호 문자는 콜론 (`:`). 별도 줄이 아니라 한 줄에 여러 개의 문을 포함 하려면 구분 기호를 사용 합니다. 이 공간을 절약 하 고 코드의 가독성을 향상 시킵니다. 다음 예제에는 콜론으로 구분 된 세 개의 문을 보여 줍니다.  
  
 [!code-vb[VbVbcnConventions #&12;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 자세한 내용은 참조 [하는 방법: 중단 되 고 코드에서 문 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)합니다.  
  
 콜론 (`:`) 문자는 또한 문 레이블을 식별 하는 데 사용 됩니다. 자세한 내용은 참조 [하는 방법: Label 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)합니다.  
  
## <a name="concatenation"></a>연결 연산  
 사용 하는 `&` 에 대 한 연산자 *연결*, 또는 문자열을 함께 연결 합니다. 혼동 하지 마십시오는 `+` 함께 숫자 값을 추가 하는 연산자입니다. 사용 하는 경우는 `+` 연산자를 숫자 값으로 작업할 때 잘못 된 결과 얻을 수 있습니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions #&13;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 앞의 코드에서 값을 실행 하 고 `resultA` 21.01의 값은 `resultB` "10.0111로 실행" 됩니다.  
  
## <a name="member-access-operators"></a>멤버 액세스 연산자  
 점 연산자를 사용 하면 형식 멤버에 액세스 하려면 (`.`) 또는 느낌표 (`!`) 형식 이름과 멤버 이름 사이 연산자입니다.  
  
### <a name="dot--operator"></a>점 (입니다.) 연산자  
 사용 된 `.` 클래스, 구조체, 인터페이스 또는 열거형의 멤버 액세스 연산자와 연산자입니다. 필드, 속성, 이벤트 또는 메서드 멤버 수 있습니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions #&14;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a>느낌표 (!) 연산자  
 사용 된 `!` 사전 액세스 연산자와 클래스 또는 인터페이스에 대해서만 연산자입니다. 클래스 또는 인터페이스에는 단일 허용 하는 기본 속성 있어야 `String` 인수입니다. 바로 다음에 오는 식별자는 `!` 연산자를 문자열로 기본 속성에 전달 된 인수 값이 됩니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions #&15;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 3 개의 출력 줄의 `MsgBox` 모두 표시 값 `32856`합니다. 속성에 대 한 일반적인 액세스를 사용 하는 첫 번째 줄 `index`, 두 번째 사실을 활용 하는 `index` 클래스의 기본 속성은 `hasDefault`, 세 번째 클래스에 대 한 사전 액세스를 사용 합니다.  
  
 두 번째 피연산자는 `!` 연산자는 큰따옴표로 묶지는 유효한 Visual Basic 식별자 여야 합니다 (`" "`). 즉, 문자열 리터럴 또는 문자열 변수를 사용할 수 없습니다. 다음과 같이 변경 하면 마지막 줄은 `MsgBox` 호출 하면 오류가 발생 하기 때문에 `"X"` 은 괄호로 묶인된 문자열 리터럴.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  기본 컬렉션에 대 한 참조를 명시적 이어야 합니다. 특히, 사용할 수 없습니다는 `!` 연산자의 런타임에 바인딩된 변수입니다.  
  
 `!` 문자는로 사용은 `Single` 문자를 입력 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
