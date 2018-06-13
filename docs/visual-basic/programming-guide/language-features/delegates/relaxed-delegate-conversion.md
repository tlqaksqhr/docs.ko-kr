---
title: 완화된 대리자 변환(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: c4a41bf74716a6ea7d3c1139651834acccf27657
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650831"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>완화된 대리자 변환(Visual Basic)
완화 된 대리자 변환에는 해당 서명이 동일 하지 않은 경우에 처리기에 sub 및 함수를 할당할 수 있습니다. 따라서 대리자에는 바인딩이 이미 메서드 호출에 대해 허용 된 바인딩과 일치 됩니다.  
  
## <a name="parameters-and-return-type"></a>매개 변수 및 반환 형식  
 서명이 완전히 일치 하는 대신 완화 된 변환 필요 합니다. 다음 조건이 충족 될 때 `Option Strict` 로 설정 된 `On`:  
  
-   할당 된 함수는 해당 매개 변수의 데이터 형식으로 각 대리자 매개 변수의 데이터 형식에서 확대 변환이 있어야 또는 `Sub`합니다. 다음 예제에서는 대리자 `Del1` 하나의 매개 변수가 있는 `Integer`합니다. 매개 변수 `m` 할당된 된 람다 식에서의 확대 변환이 없는 데이터 형식이 있어야 `Integer`와 같은 `Long` 또는 `Double`합니다.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     축소 변환은 경우에만 허용 됩니다 `Option Strict` 로 설정 된 `Off`합니다.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   할당 된 함수 반환 형식에서 반대 방향으로 확대 변환이 있어야 합니다. 또는 `Sub` 대리자의 반환 형식입니다. 다음 예제에서 각 할당 된 람다 식의 본문으로 확대 되는 데이터 형식으로 계산 되어야 `Integer` 의 반환 형식인 `del1` 은 `Integer`합니다.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 경우 `Option Strict` 로 설정 된 `Off`, 두 방향에서 제한 확대가 제거 되었습니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a>매개 변수 사양 생략  
 또한 완화 된 대리자를 통해 할당 된 메서드의 매개 변수 사양 완전히 생략할 수 있습니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 참고 일부 매개 변수를 지정 되 고 다른 사용자를 생략할 수 없습니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 매개 변수를 생략 하는 기능 복잡 한 여러 매개 변수 관련 된 이벤트 처리기를 정의 하는 경우에 유용 합니다. 일부 이벤트 처리기에 대 한 인수는 사용 되지 않습니다. 대신, 처리기 이벤트를 등록 및 인수를 무시 하는 컨트롤의 상태를 직접 액세스 합니다. 완화 된 대리자를 통해 모호성이 없는 선언에서 인수를 생략할 수 있습니다. 다음 예제에서는 완전 하 게 지정 된 메서드 `OnClick` 로 다시 작성 `RelaxedOnClick`합니다.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>AddressOf 예제  
 람다 식은 형식 관계를 쉽게 확인할 수 있도록 이전 예제에서 사용 됩니다. 동일한 relaxations 사용 하는 대리자 할당에 허용 되는 반면 `AddressOf`, `Handles`, 또는 `AddHandler`합니다.  
  
 다음 예제에서는 작동 `f1`, `f2`, `f3`, 및 `f4` 모두에 할당할 수 있습니다 `Del1`합니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 다음 예제는 경우에만 유효 `Option Strict` 로 설정 된 `Off`합니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a>함수 반환 값 삭제  
 완화 된 대리자 변환을 사용 하면 함수를 할당할 수는 `Sub` 대리자를 효과적으로 함수의 반환 값을 무시 합니다. 그러나, 할당할 수 없습니다는 `Sub` 함수 대리자입니다. 다음 예제에서는 함수의 주소로 `doubler` 에 할당 된 `Sub` 위임 `Del3`합니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [방법: Visual Basic에서 프로시저에 다른 프로시저 전달](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
