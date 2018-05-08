---
title: '방법: 숫자 값 계산(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: cf24d7259ac04f6901497c81558a4d59b340eec7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>방법: 숫자 값 계산(Visual Basic)
숫자 식 사용 하 여 숫자 값을 계산할 수 있습니다. A *숫자 식* 리터럴, 상수 및 숫자 값을 나타내는 변수를 포함 하는 식을 이며 해당 값에 대해 작동 하는 연산자입니다.  
  
## <a name="calculating-numeric-values"></a>숫자 값 계산  
  
#### <a name="to-calculate-a-numeric-value"></a>숫자 값을 계산 하려면  
  
-   숫자 리터럴, 상수, 변수 및 하나 이상의 숫자를 식 결합 합니다. 다음 예제에는 유효한 숫자 식을 보여 줍니다.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     처음 세 줄은 리터럴, 상수 및 변수를 보여 줍니다. 각각 자체적으로 유효한 숫자 식을 형성합니다. 마지막 줄에서는 두 개의 리터럴 사용 하 여 변수의 조합을 보여 줍니다.  
  
     참고는 숫자 식 단독으로 전체 Visual Basic 문을 형성 하지 않습니다. 전체 문의 일부로 식을 사용 해야 합니다.  
  
#### <a name="to-store-a-numeric-value"></a>숫자 값을 저장 하려면  
  
-   다음 예제에서 보여 주듯이 변수에 숫자 식으로 표현 되는 값을 할당 하는 할당 문을 사용할 수 있습니다.  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     위의 예제에서는 같음 연산자의 우변에 있는 식의 값 (`=`) 변수에 할당 `j` 연산자의 왼쪽에 있으므로 `j` 276으로 계산 합니다.  
  
     자세한 내용은 [문](../../../../visual-basic/language-reference/statements/index.md)을 참조하세요.  
  
## <a name="multiple-operators"></a>여러 명의 연산자  
 숫자 식에 하나 이상의 연산자, 평가 되는 순서는 연산자 우선 순위 규칙에 의해 결정 됩니다. 식을 위 예와 괄호로 묶습니다 있습니다 연산자 우선 순위 규칙을 재정의 하려면 괄호 안의 식이 먼저 계산 됩니다.  
  
#### <a name="to-override-normal-operator-precedence"></a>일반 연산자 우선 순위를 재정의 하려면  
  
-   먼저 수행 하려는 작업을 묶는 괄호를 사용 합니다. 다음 예제에서는 동일한 연산자와 피연산자와 두 개의 서로 다른 결과 보여 줍니다.  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     앞의 예제에 대 한 계산에서 `j` 수행 더하기 연산자 (`+`) 첫 번째 때문에 주위에 괄호 `(67 + i)` 일반 우선 순위 및에 할당 된 값을 재정의 `j` 은 276 (4 회 69). 에 대 한 계산 `k` 에서 일반 우선 순위는 연산자를 수행 하므로 (`*` 하기 전에 `+`), 및에 할당 된 값 `k` 은 270 (268 + 2).  
  
     자세한 내용은 참조 [Visual Basic의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연산자 및 식](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [값 비교](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [문](../../../../visual-basic/language-reference/statements/index.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [산술 연산자](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [연산자의 효율적 결합](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
