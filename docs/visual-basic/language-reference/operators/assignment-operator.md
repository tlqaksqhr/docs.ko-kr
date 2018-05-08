---
title: = 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 55b3a8201940a6fec351327aaa88e4ac1ee9246a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-visual-basic"></a>= 연산자(Visual Basic)
변수 또는 속성에 값을 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 모든 쓰기 가능한 변수 또는 모든 속성입니다.  
  
 `value`  
 모든 리터럴, 상수 또는 식입니다.  
  
## <a name="remarks"></a>설명  
 등호 기호 왼쪽에 요소 (`=`)는 단순 스칼라 변수, 속성 또는 배열의 요소 수 있습니다. 변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다. `=` 연산자의 왼쪽에는 속성 또는 변수는 오른쪽에 값 할당 합니다.  
  
> [!NOTE]
>  `=` 연산자는도 비교 연산자로 사용 됩니다. 자세한 내용은 참조 [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md)합니다.  
  
## <a name="overloading"></a>오버로딩  
 `=` 할당 연산자가 아닌 관계 비교 연산자로 연산자를 오버 로드 될 수 있습니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 할당 연산자를 보여 줍니다. 오른쪽에 있는 값을 왼쪽에 있는 변수에 할당 됩니다.  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [&= 연산자](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [*= 연산자](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [+= 연산자](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [-= 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [/ = 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [\\= 연산자](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [^= 연산자](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [문](../../../visual-basic/programming-guide/language-features/statements.md)  
 [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
