---
title: 연산자의 효율적 결합(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: 8ced464cb0cc8e1bec3c3449dccb827575599905
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="efficient-combination-of-operators-visual-basic"></a>연산자의 효율적 결합(Visual Basic)
복잡 한 식은 여러 다른 연산자를 포함할 수 있습니다. 다음은 이에 대한 예입니다.  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 앞의 예제에 대 한 것과 같은 복잡 한 식 작성 연산자 우선 순위 규칙을 파악을 해야 합니다. 자세한 내용은 참조 [Visual Basic의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)합니다.  
  
## <a name="parenthetical-expressions"></a>괄호 식  
 연산자 우선 순위에 의해 결정 된 것과 다른 순서로 연산을 할 경우가 있습니다. 다음 예제를 살펴보십시오.  
  
 `x = z * y + 4`  
  
 앞의 예제를 곱합니다 `z` 여 `y`, 그런 다음 결과를 `4`합니다. 추가 하려는 경우 `y` 및 `4` 기준으로 결과 곱하기 전에 `z`, 괄호를 사용 하 여 일반 연산자 우선 순위를 재정의할 수 있습니다. 식을 괄호로 묶어, 묶으면 연산자 우선 순위에 관계 없이, 먼저 계산 됩니다. 먼저 추가 작업을 수행 하는 앞의 예제를 강제로 표시 하려면 다음 예제와 같이 다시를 작성할 수 있습니다.  
  
 `x = z * (y + 4)`  
  
 위의 예제에서는 `y` 및 `4`를 더한 값에 곱합니다 `z`합니다.  
  
### <a name="nested-parenthetical-expressions"></a>중첩 된 괄호 식  
 식에 여러 수준의 우선 순위를 더욱 해소를 무시 하려면 괄호를 중첩할 수 있습니다. 가장 깊게 중첩 등을 가장 깊이 중첩 된 마지막 괄호 외부의 식이 다음으로 가장 깊이 중첩 된 괄호 안에 식은 먼저 평가 됩니다. 다음은 이에 대한 예입니다.  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 앞의 예제에서 `z + 2` 가장 먼저 평가 된 다음 다른 괄호 식이 됩니다. 지 수 연산자, 더하기 나 빼기 보다 높은 우선 순위에 일반적으로, 다른 식을 괄호로 묶여 있기 때문에이 예에서 마지막 평가 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 산술 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Visual Basic의 논리 및 비트 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [논리/비트 연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [부울 식](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [방법: 숫자 값 계산](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)
