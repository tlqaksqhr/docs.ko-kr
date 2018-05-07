---
title: If 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 192309a7ca728feb300e867bf2340e669e9da16c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="if-operator-visual-basic"></a>If 연산자(Visual Basic)
사용 조건에 따라 두 값 중 하나를 반환할 (short-circuit). `If` 는 세 개의 인수 또는 인수 두 개 연산자를 호출할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a>연산자는 세 개의 인수를 호출 하는 경우  
 때 `If` 라고 세 개의 인수를 사용 하 여 첫 번째 인수가로 캐스팅 될 수 있는 값으로 계산 되어야 합니다는 `Boolean`합니다. `Boolean` 나머지 두 인수 중 평가 되 고 반환 값은 결정 합니다. 다음과 같은 경우에만 적용 되는 `If` 세 개의 인수를 사용 하 여 연산자 라고 합니다.  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`argument1`|필수. `Boolean`. 이외의 인수는 평가 하 고 반환을 결정 합니다.|  
|`argument2`|필수. `Object`. 계산 되 고 반환 if `argument1` 계산 `True`합니다.|  
|`argument3`|필수. `Object`. 계산 되 고 반환 하는 경우 `argument1` 계산 `False` 경우 `argument1` 는 [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` 계산 되는 변수 [Nothing](../../../visual-basic/language-reference/nothing.md)합니다.|  
  
 `If` 처럼 작동 하는 세 개의 인수 없이 호출 되는 연산자는 `IIf` 함수를 사용 한다는 점을 제외 하 고 단락 (short-circuit) 계산 합니다. `IIf` 함수는 항상 세 가지 인수를 계산 하지만 `If` 세 개의 인수가 있는 연산자 중 두 개만 계산 합니다. 첫 번째 `If` 인수가 계산 되 고 결과로 캐스팅 되는 `Boolean` 값 `True` 또는 `False`합니다. 값이 `True`, `argument2` 가 계산 되 고 해당 값이 반환 되지만 `argument3` 평가 되지 않습니다. 하는 경우의 값은 `Boolean` 식은 `False`, `argument3` 은 평가 되 고 해당 값이 반환 되지만 `argument2` 평가 되지 않습니다. 다음 예에서는 사용법을 보여 줍니다. `If` 세 개의 인수가 사용 되는 경우:  
  
 [!code-vb[VbVbalrOperators#100](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_1.vb)]  
  
 다음 예제에서는 값의 단락 (short-circuit) 계산 합니다. 예제에서는 변수를 분할 2 회 시도 `number` 변수로 `divisor` 경우는 제외 `divisor` 은 0입니다. 이 경우 0을 반환 하 고 없는 시도해 야 나누기를 수행 하는 런타임 오류를 초래 하기 때문에 합니다. 때문에 `If` 사용 되는 식 (short-circuit), 두 번째 또는 첫 번째 인수의 값에 따라 세 번째 인수를 계산 합니다. 첫 번째 인수가 true 이면 제 수 0이 아니면 및 두 번째 인수를 평가 하 고 나누기를 수행 해도 안전 합니다. 첫 번째 인수가 false 이면 세 번째 인수에만 계산 되 고 0이 반환 됩니다. 따라서 제 수 0 이면 하려고 시도 하지는 나누기를 수행 하는 오류가 발생 하지 않습니다. 그러나 때문에 `IIf` 사용 하지 않습니다 (short-circuit), 첫 번째 인수가 false 인 경우에 두 번째 인수를 평가 합니다. 런타임에 0으로 나누기 오류가 발생 합니다.  
  
 [!code-vb[VbVbalrOperators#101](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_2.vb)]  
  
## <a name="if-operator-called-with-two-arguments"></a>연산자는 두 개의 인수를 사용 하 여 호출 하는 경우  
 첫 번째 인수 `If` 생략할 수 있습니다. 그러면 연산자를 두 개의 인수를 사용 하 여 호출할 수 있습니다. 다음과 같은 경우에만 적용 되는 `If` 연산자는 두 개의 인수로 호출 됩니다.  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`argument2`|필수. `Object`. 참조 또는 nullable 형식 이어야 합니다. 계산 되 고 아닌 다른 값으로 계산 될 때 반환 `Nothing`합니다.|  
|`argument3`|필수. `Object`. 계산 되 고 반환 if `argument2` 계산 `Nothing`합니다.|  
  
 경우는 `Boolean` 인수를 생략 하면, 첫 번째 인수는 참조 또는 nullable 형식 이어야 합니다. 첫 번째 인수를 평가 하는 경우 `Nothing`, 두 번째 인수의 값이 반환 됩니다. 다른 모든 경우에 첫 번째 인수의 값이 반환 됩니다. 다음 예제에서는이 계산의 작동 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#102](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.IIf%2A>  
 [Nullable 값 형식](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
