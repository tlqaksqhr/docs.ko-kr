---
title: '&lt;&lt;= 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: 559624f7097f90d374ee83e3c0a9ac97d9f93444
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ltlt-operator-visual-basic"></a>&lt;&lt;= 연산자 (Visual Basic)
변수 또는 속성의 값에 산술 왼쪽된 시프트를 수행 하 고 변수 또는 속성에 다시 결과 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 필수. 변수 또는 정수 계열 형식의 속성 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, 또는 `ULong`).  
  
 `amount`  
 필수. 숫자 식으로 확대 되는 데이터 형식의 `Integer`합니다.  
  
## <a name="remarks"></a>설명  
 왼쪽에 요소는 `<<=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 될 수 있습니다. 변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.  
  
 `<<=` 연산자 먼저 변수 또는 속성의 값에 산술 왼쪽된 시프트를 수행 합니다. 연산자는 다음 다시 해당 변수 또는 속성에 해당 작업의 결과 할당 합니다.  
  
 이동 하는 산술 형식 이므로 하지 순환, 결과의 한쪽 끝에서 이동 하는 비트는 다른 쪽 끝에서 다시 도입 되지 않습니다. 산술 왼쪽 시프트 연산 결과 데이터 형식의 범위를 넘어 이동 하는 비트는 무시 되 고 오른쪽에 비워진 비트 위치 0으로 설정 됩니다.  
  
## <a name="overloading"></a>오버로딩  
 [<< 연산자](../../../visual-basic/language-reference/operators/left-shift-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 오버 로드는 `<<` 연산자의 동작에 영향을 줍니다는 `<<=` 연산자입니다. 코드에서 `<<=` 클래스 또는 구조체에 오버 로드에서 `<<`, 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `<<=` 연산자의 비트 패턴을 이동할는 `Integer` 변수에 변수 만큼 왼쪽으로 지정 된 크기 및 결과 할당 합니다.  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [<< 연산자](../../../visual-basic/language-reference/operators/left-shift-operator.md)  
 [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [비트 시프트 연산자](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [문](../../../visual-basic/programming-guide/language-features/statements.md)
