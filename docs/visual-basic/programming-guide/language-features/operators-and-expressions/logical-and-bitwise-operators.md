---
title: Visual Basic의 논리 및 비트 연산자
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: 371d28629b39fb2808ca018ea69da3306a31f50c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656154"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Visual Basic의 논리 및 비트 연산자
논리 연산자 비교 `Boolean` 식 및 반환 된 `Boolean` 결과입니다. `And`, `Or`, `AndAlso`, `OrElse`, 및 `Xor` 연산자는 *이진* 동안 두 개의 피연산자를 고려 하기 때문에 `Not` 연산자는 *단항* 단일 피연산자를 사용 하기 때문에 있습니다. 정수 계열 값의 비트 논리 연산을 수행할 수도 이러한 연산자 중 일부입니다.  
  
## <a name="unary-logical-operator"></a>단항 논리 연산자  
 [Not 연산자](../../../../visual-basic/language-reference/operators/not-operator.md) 논리 수행 *부정* 에 `Boolean` 식입니다. 피연산자의 논리적 반대를 생성합니다. 식이 계산 되는 경우 `True`, 다음 `Not` 반환 `False`식이 계산 되는 경우; `False`, 다음 `Not` 반환 `True`합니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#77](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_1.vb)]  
  
## <a name="binary-logical-operators"></a>이진 논리 연산자  
 [및 연산자](../../../../visual-basic/language-reference/operators/and-operator.md) 논리 수행 *함께* 두 `Boolean` 식입니다. 두 식이 모두 `True`, 다음 `And` 반환 `True`합니다. 식 중 하나 이상 계산 되 면 `False`, 다음 `And` 반환 `False`합니다.  
  
 [또는 연산자](../../../../visual-basic/language-reference/operators/or-operator.md) 논리 수행 *분리* 또는 *포함* 두 `Boolean` 식입니다. 두 식 중 하나가 경우 `True`, 이거나 두 식이 `True`, 다음 `Or` 반환 `True`합니다. 두 식이 모두 경우 `True`, `Or` 반환 `False`합니다.  
  
 [Xor 연산자](../../../../visual-basic/language-reference/operators/xor-operator.md) 논리 수행 *제외* 두 `Boolean` 식입니다. 정확히 하나의 식이 `True`, 두만 `Xor` 반환 `True`합니다. 두 식이 모두 `True` 이거나 두 식이 `False`, `Xor` 반환 `False`합니다.  
  
 다음 예제는 `And`, `Or`, 및 `Xor` 연산자입니다.  
  
 [!code-vb[VbVbalrOperators#78](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_2.vb)]  
  
## <a name="short-circuiting-logical-operations"></a>논리 연산자를 단락 (short-circuiting)  
 [AndAlso 연산자](../../../../visual-basic/language-reference/operators/andalso-operator.md) 매우 비슷합니다는 `And` 연산자를 두 개에서 한 논리 결합을 수행 한다는 점에서 `Boolean` 식입니다. 둘 사이의 주요 차이점은 `AndAlso` 유효 *단락 (short-circuiting)* 동작 합니다. 경우에 첫 번째 식은 `AndAlso` 식이 `False`, 최종 결과 변경할 수 있기 때문에 두 번째 식은 평가 되지 됩니다 및 `AndAlso` 반환 `False`합니다.  
  
 마찬가지로,는 [OrElse 연산자](../../../../visual-basic/language-reference/operators/orelse-operator.md) 두에 논리 분리를 단락 수행 `Boolean` 식입니다. 경우에 첫 번째 식은 `OrElse` 식이 `True`, 최종 결과 변경할 수 있기 때문에 두 번째 식은 평가 되지 됩니다 및 `OrElse` 반환 `True`합니다.  
  
### <a name="short-circuiting-trade-offs"></a>상충 관계를 단락 (short-circuiting)  
 단락 (short-circuiting) 하지 논리 작업의 결과 변경할 수 없는 식을 평가 하 여 성능을 향상 시킬 수 있습니다. 그러나 해당 식을 추가 작업을 수행 하는 경우 이러한 작업을 건너뜁니다 단락 (short-circuiting). 예를 들어, 식에 대 한 호출을 포함 하는 경우는 `Function` 프로시저, 식은 short-circuited, 및에 추가 코드가 포함 된 경우 프로시저가 호출 되지 않습니다는 `Function` 실행 되지 않습니다. 따라서 함수 가끔씩만 실행할 수 있으며 올바르게 테스트 될 수 있습니다. 프로그램 논리의 코드에 따라 달라질 수 있습니다는 `Function`합니다.  
  
 다음 예제에서는 차이점을 보여 줍니다. `And`, `Or`, 및 단락 대응 합니다.  
  
 [!code-vb[VbVbalrOperators#81](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_3.vb)]  
  
 [!code-vb[VbVbalrOperators#80](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_4.vb)]  
  
 [!code-vb[VbVbalrOperators#79](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_5.vb)]  
  
 앞의 예제에서 몇 가지 중요 한 코드 내 `checkIfValid()` 호출이 short-circuited 될 때 실행 되지 않습니다. 첫 번째 `If` 문 호출 `checkIfValid()` 있지만 `12 > 45` 반환 `False`때문에, `And` 단락 하지 않습니다. 두 번째 `If` 호출 하지 않습니다 `checkIfValid()`때문에 때 `12 > 45` 반환 `False`, `AndAlso` short-circuits 두 번째 식입니다. 세 번째 `If` 문 호출 `checkIfValid()` 있지만 `12 < 45` 반환 `True`때문에, `Or` 단락 하지 않습니다. 네 번째 `If` 호출 하지 않습니다 `checkIfValid()`때문에 때 `12 < 45` 반환 `True`, `OrElse` short-circuits 두 번째 식입니다.  
  
## <a name="bitwise-operations"></a>비트 연산  
 비트 연산 (밑 2) 이진 형식으로 두 정수 계열 값을 평가합니다. 해당 위치의 비트를 비교 하 고 비교를 기반으로 값을 할당 합니다. 다음 예제는 `And` 연산자입니다.  
  
 [!code-vb[VbVbalrConcepts#2](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/logical-and-bitwise-operators_6.vb)]  
  
 값을 설정 하는 앞의 예제 `x` 1입니다. 이 다음과 같은 상황이 발생합니다.  
  
-   값은 이진으로 처리 됩니다.  
  
     이진 형식으로 3 011 =  
  
     이진 형식으로 5 = 101  
  
-   `And` 연산자는 한 번에 하나의 이진 위치 (비트)에서 이진 표현을 비교 합니다. 지정된 된 위치에서 두 비트가 모두 1 이면 1 결과의 해당 위치에 배치 됩니다. 두 비트 중 하나가 0 이면 0은 결과에서 해당 위치에 배치 됩니다. 앞의 예에서이 다음과 같습니다.  
  
     011 (이진 형식으로 3)  
  
     101 (5의 이진 형식)  
  
     001 (이진 형식으로 결과)  
  
-   결과 10 진수로 처리 됩니다. 001 값은 1의 이진 표현 이므로 `x` = 1입니다.  
  
 비트 `Or` 연산도 비슷합니다 제외 하 고 비교 비트 중 하나 또는 모두 1 이면 결과 비트는 1이 할당 됩니다. `Xor` 1 (멤버나) 비교 비트 중 정확히 하나의 이면 결과 비트에 1을 할당 합니다. `Not` 단일 피연산자를 사용 하 고 부호 비트를 포함 하 여 모든 비트를을 반전 하 고 결과에 해당 값을 할당 합니다. 즉, 부호 있는 양수, `Not` 항상 음수 값을 반환 하 고 음수 값에 대 한 `Not` 항상 양수 또는 0 값을 반환 합니다.  
  
 `AndAlso` 및 `OrElse` 연산자는 비트 연산을 지원 하지 않습니다.  
  
> [!NOTE]
>  비트 연산에서 정수 계열 형식 에서만 수행할 수 있습니다. 부동 소수점 값은 비트 연산을 수행 하려면 먼저 정수 계열 형식으로 변환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [논리/비트 연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [부울 식](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [Visual Basic의 산술 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Visual Basic의 연결 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [연산자의 효율적 결합](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
