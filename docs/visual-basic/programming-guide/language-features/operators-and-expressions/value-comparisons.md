---
title: 값 비교(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: 6e1eda09784814d139ef94b6720b538aef30e5e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649609"
---
# <a name="value-comparisons-visual-basic"></a>값 비교(Visual Basic)
숫자 변수 값을 비교 하는 식을 구성할 비교 연산자를 사용할 수 있습니다. 이러한 식은 반환는 `Boolean` 비교가 true 인지에 따라 값 false입니다. 식의 예는 다음과 같습니다.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 첫 번째 식이 `True`45가 26 보다 크므로, 합니다. 두 번째 예에서는 `False`26 45 보다 크지 않아 합니다.  
  
 이 방식으로 식을 숫자를 비교할 수 있습니다. 비교 식 수 다음 예제와 같이 복잡 한 식입니다.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 이전 복잡 한 식에서 리터럴, 변수 및 함수 호출이 포함 됩니다. 비교 연산자의 양쪽 모두에 식이 평가 되는 결과 값을 다음 비교를 사용 하 여 `>=` 비교 연산자. 왼쪽에 있는 식의 값 보다 크면 또는 오른쪽에 있는 식의 값과 같은 전체 식을 계산 하는 경우 `True`, 그렇지 않으면가 `False`합니다.  
  
 값을 비교 하는 식에서 가장 흔히 사용은 `If...Then` 다음 예제와 같이 생성 합니다.  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 `=` 기호가으로 비교 연산자는 대입 연산자입니다. 비교 연산자로 사용 하는 다음 예제와 같이 왼쪽의 값이 오른쪽의 값과 같은 여부를 평가 합니다.  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 비교 식 어디 사용할 수도 수는 `Boolean` 에서 같이 등 필요한 값은는 `If`, `While`, `Loop`, 또는 `ElseIf` 문, 할당 하거나 값을 전달 하는 경우 또는 `Boolean` 변수입니다. 다음 예제에서는 비교 식에서 반환 된 값에 할당 되는 `Boolean` 변수입니다.  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [부울 식](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [연산자 및 식](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [방법: 숫자 값 계산](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)
