---
title: ^= 연산자(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fa9d87d2f090a8c18aaab742e73878c7b80f55c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>^= 연산자(Visual Basic)
변수 또는 식의 제곱으로 속성의 값 및 변수 또는 속성에 다시 결과 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 필수 요소. 숫자 변수 또는 속성입니다.  
  
 `expression`  
 필수 요소. 임의의 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 왼쪽에 요소는 `^=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 될 수 있습니다. 변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.  
  
 `^=` 연산자 (연산자의 오른쪽)에 식의 값의 거듭제곱으로 변수 또는 연산자의 왼쪽) (에 속성의 값을 먼저 발생 합니다. 연산자는 다음 다시 변수 또는 속성에 해당 작업의 결과 할당 합니다.  
  
 Visual Basic의 지 수를 항상 수행는 [Double 데이터 형식의](../../../visual-basic/language-reference/data-types/double-data-type.md)합니다. 다른 형식의 피연산자 변환할 `Double`, 결과 항상 `Double`합니다.  
  
 값 `expression` 소수인 수 음수, 또는 둘 다 합니다.  
  
## <a name="overloading"></a>오버로딩  
 [^ 연산자](../../../visual-basic/language-reference/operators/exponentiation-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 오버 로드는 `^` 연산자의 동작에 영향을 줍니다는 `^=` 연산자입니다. 코드에서 `^=` 클래스 또는 구조체에 오버 로드에서 `^`, 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `^=` 연산자를 하나의 값 `Integer` 변수의 두 번째 변수 및 결과 첫 번째 변수에 할당 합니다.  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [^ 연산자](../../../visual-basic/language-reference/operators/exponentiation-operator.md)  
 [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [문](../../../visual-basic/programming-guide/language-features/statements.md)
