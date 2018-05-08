---
title: 부울 식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: ff5843c815658468ac69fe5d62a9ea4cac2be830
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="boolean-expressions-visual-basic"></a>부울 식(Visual Basic)
A *부울 식* 식의 값으로 계산 되는 [Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` 또는 `False`합니다. `Boolean` 식에는 여러 가지 형식을 취할 수 있습니다. 가장 간단한는 값의 직접 비교는 `Boolean` 변수를 한 `Boolean` 리터럴, 다음 예제와 같이 합니다.  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## <a name="two-meanings-of-the--operator"></a>두 가지 의미는 = 연산자  
 다음에 유의 대입문 `newCustomer = True` 앞의 예제에서 식과 동일 하 게 표시 하지만 다른 함수를 수행 하 고 다르게 사용 됩니다. 위의 예제에서는 식에서에서 `newCustomer = True` 부울 값을 나타내는 및 `=` 기호는 비교 연산자로 해석 됩니다. 독립 실행형 문에 `=` 기호는 할당 연산자 해석 되 고 왼쪽에 있는 변수에 오른쪽에 있는 값을 할당 합니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 자세한 내용은 참조 하십시오. [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) 및 [문을](../../../../visual-basic/language-reference/statements/index.md)합니다.  
  
## <a name="comparison-operators"></a>비교 연산자  
 비교 연산자와 같은 `=`, `<`, `>`, `<>`, `<=`, 및 `>=` 오른쪽에 있는 식에 연산자의 왼쪽에 식을 비교 하 여 부울 식을 생성 연산자와로 결과 평가할 `True` 또는 `False`합니다. 다음은 이에 대한 예입니다.  
  
 `42 < 81`  
  
 앞의 예제에 나오는 부울 식으로 계산 42는 보다 작은 81 `True`합니다. 이러한 종류의 식에 대 한 자세한 내용은 참조 하십시오. [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)합니다.  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>논리 연산자와 조합해 서 비교 연산자  
 비교 식 논리 연산자를 사용 하 여 보다 복잡 한 부울 식을 생성 하기 위해 조합할 수 있습니다. 다음 예제에서는 논리 연산자와 함께에서 비교 연산자의 사용을 보여 줍니다.  
  
 `x > y And x < 1000`  
  
 앞의 예제에서 전체 식의 값의 양쪽에 있는 식의 값에 종속 된 `And` 연산자입니다. 두 식이 모두 `True`, 전체 식은 다음 `True`합니다. 식 중 하나가 `False`, 전체 식은 다음 `False`합니다.  
  
## <a name="short-circuiting-operators"></a>단락 연산자  
 논리 연산자 `AndAlso` 및 `OrElse` 라고 하는 동작을 나타낼 *단락 (short-circuiting)* 합니다. 단락 연산자는 왼쪽된 피연산자를 먼저 평가합니다. 경우 전체 식의 값을 결정 하는 왼쪽된 피연산자, 오른쪽 식의 계산 하지 않고 프로그램 실행이 계속 됩니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 앞의 예제는 연산자는 왼쪽된에 있는 식 계산 `45 < 12`합니다. 왼쪽된에 있는 식이로 계산 되므로 `False`, 전체 논리 식으로 계산 해야 `False`합니다. 프로그램 실행 내에서 코드 실행을 건너뜁니다 따라서는 `If` 오른쪽에 있는 식을 계산 하지 않고 블록 `testFunction(3)`합니다. 이 예제에서는 호출 하지 않습니다 `testFunction()` 왼쪽된 식에는 전체 식을 falsifies 때문에 있습니다.  
  
 마찬가지로, 경우에 사용 하 여 논리 식 왼쪽된에 있는 식이 `OrElse` 로 계산 `True`, 실행 코드의 다음 줄을 계산 하지 않고 계속 오른쪽 식의 왼쪽된 식의 전체 유효성 검사가 이미 있으므로 식입니다.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>짧은 단락 Circuit 연산자와 비교  
 논리 연산자의 양쪽 모두 평가 되는 반면 때 논리 연산자 `And` 및 `Or` 사용 됩니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 위의 예제에서는 `testFunction()` 왼쪽된 식이 계산 되는 경우에 `False`합니다.  
  
## <a name="parenthetical-expressions"></a>괄호 식  
 부울 식의 평가 순서를 제어 하려면 괄호를 사용할 수 있습니다. 괄호로 묶은 식을 먼저 평가 합니다. 다중 중첩 수준에 대 한 우선 순위가 가장 깊이 중첩 된 식에 부여 됩니다. 괄호 안에 연산자 선행 규칙에 따라 확인이 됩니다. 자세한 내용은 참조 [Visual Basic의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 논리 및 비트 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [문](../../../../visual-basic/programming-guide/language-features/statements.md)  
 [비교 연산자](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [연산자의 효율적 결합](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
