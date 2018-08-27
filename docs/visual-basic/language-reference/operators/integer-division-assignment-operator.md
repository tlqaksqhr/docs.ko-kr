---
title: '\= 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: bcfc59efda0627f83713fe9ada24cedc20d823e3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934515"
---
# <a name="-operator"></a>\\= 연산자
식의 값으로 변수 또는 속성의 값을 나누고 정수 결과 변수 또는 속성에 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 필수. 숫자 변수 또는 속성입니다.  
  
 `expression`  
 필수. 임의의 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 왼쪽된에 있는 요소는 `\=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 수입니다. 변수 또는 속성 일 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.  
  
 `\=` 연산자는 오른쪽에 값으로 변수 또는 왼쪽에는 속성의 값으로 나누고 정수 결과 변수 또는 왼쪽의 속성에 할당  
  
 정수 나누기에 대 한 자세한 내용은 참조 [\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)합니다.  
  
## <a name="overloading"></a>오버로딩  
 합니다 `\` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 오버 로드 된 `\` 연산자의 동작에 영향을 줍니다는 `\=` 연산자입니다. 코드를 사용 하는 경우 `\=` 클래스나 구조체에 오버 로드에서 `\`, 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 합니다 `\=` 연산자를 하나 `Integer` 정수 결과 첫 번째 변수 할당을 두 번째 변수입니다.  
  
 [!code-vb[VbVbalrOperators#19](codesnippet/VisualBasic/integer-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [/ = 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [문](../../../visual-basic/programming-guide/language-features/statements.md)
