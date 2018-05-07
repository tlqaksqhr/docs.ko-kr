---
title: '방법: 프로시저 인수의 값 변경(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: 118dd3389804794801d39e7d67b68ab195bbad3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>방법: 프로시저 인수의 값 변경(Visual Basic)
프로시저를 호출할 때 각 인수를 제공 하는 프로시저에 정의 된 매개 변수 중 하나에 해당 합니다. 경우에 따라 프로시저 코드에서 호출 코드의 기반이 되는 값을 변경할 수 있습니다. 다른 경우에 프로시저 자체 로컬 복사본 인수를 변경할 수 있습니다.  
  
 Visual Basic 전달 되는 모든 인수의 로컬 복사본을 만듭니다는 프로시저를 호출할 때 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다. 각 인수에 대해 전달 된 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic 프로시저 코드에 호출 코드의 기반이 되는 프로그래밍 요소에 대 한 직접 참조를 제공 합니다.  
  
 호출 코드에서 해당 요소는 수정할 수 있고 인수가 전달 될 경우 `ByRef`, 프로시저 코드 호출 코드에서 요소의 값을 변경 하려면 직접 참조를 사용할 수 있습니다.  
  
## <a name="changing-the-underlying-value"></a>내부 값을 변경합니다.  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>프로시저 인수를 호출 하는 코드에 기본 값을 변경 하려면  
  
1.  프로시저 선언에서 지정 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 인수에 해당 하는 매개 변수에 대 한 합니다.  
  
2.  호출 코드에서 수정할 수 있는 프로그래밍 요소를 인수로 전달 합니다.  
  
3.  호출 코드에서 인수를 인수 목록에 괄호로 묶지 마십시오.  
  
4.  프로시저 코드에서 매개 변수 이름을 사용 하 여 호출 코드에서 해당 요소에 값을 할당 합니다.  
  
 예제를 참조 하십시오 데모를 추가 합니다.  
  
## <a name="changing-local-copies"></a>로컬 복사본을 변경합니다.  
 호출 코드에서 기본 요소는 수정할 수 없는 요소 또는 인수가 전달 될 경우 `ByVal`, 프로시저가 호출 코드에서 해당 값을 변경할 수 없습니다. 그러나 프로시저 이러한 인수의 자체 로컬 복사본을 변경할 수 있습니다.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>프로시저 코드의 프로시저 인수의 복사본을 변경 하려면  
  
1.  프로시저 선언에서 지정 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 인수에 해당 하는 매개 변수에 대 한 합니다.  
  
     -또는-  
  
     호출 코드에서 인수 목록의 괄호 안에 인수를 묶습니다. 이렇게 하면 Visual Basic 값으로 인수를 전달 하 여 해당 매개 변수를 지정 하는 경우에 `ByRef`합니다.  
  
2.  프로시저 코드에서 매개 변수 이름을 사용 하 여 인수의 로컬 복사본에 값을 할당 합니다. 호출 코드에서 기본 값이 변경 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 요소를 사용 하는 배열 변수를 받아 두 개의 프로시저를 보여 줍니다. `increase` 프로시저 단순히 각 요소에 1을 추가 합니다. `replace` 프로시저 매개 변수는 새 배열을 할당 `a()` 다음 각 요소에 1을 추가 합니다.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 첫 번째 `MsgBox` 표시 호출 "increase(n) 후: 11, 21, 31, 41"입니다. 때문에 배열 `n` 참조 형식인 `replace` 전달 메커니즘이 해당 멤버를 변경할 수 있습니다 `ByVal`합니다.  
  
 두 번째 `MsgBox` 표시 호출 "replace(n) 후: 101, 201, 301"입니다. 때문에 `n` 전달 `ByRef`, `replace` 변수를 수정할 수 `n` 에 새 배열 할당할 고 호출 코드에서. 때문에 `n` 참조 형식인 `replace` 해당 멤버를 변경할 수도 있습니다.  
  
 프로시저가 호출 코드에서 변수 자체를 수정할 수 없도록 방지할 수 있습니다. 참조 [하는 방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 참조 하 여 변수를 전달할 때 사용 해야는 `ByRef` 키워드가이 메커니즘을 지정 합니다.  
  
 Visual Basic의 기본값인 값으로 인수 전달 합니다. 그러나 것이 바람직한 프로그래밍 습관 하나를 포함 하는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드 모든 선언 된 매개 변수를 사용 합니다. 이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 호출 코드의 기반이 되는 값을 변경 하는 절차를 허용할 경우 잠재적인 위험이 항상 있습니다. 변경 되 고 사용 하기 전에 유효성을 검사할 수 있도록 준비 하려면이 값을 예상 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)  
 [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)  
 [수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [인수를 값으로 전달할 때와 참조로 전달할 때의 차이점](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [방법: 인수가 값으로 전달되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)  
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
