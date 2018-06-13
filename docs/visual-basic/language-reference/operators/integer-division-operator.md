---
title: '\ 연산자(Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: ef3946e871e1dc248b54932e16f6cae6026da08e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604239"
---
# <a name="-operator-visual-basic"></a>\ 연산자(Visual Basic)
두 숫자를 나누고 정수 결과 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a>요소  
 `expression1`  
 필수. 임의의 숫자 식입니다.  
  
 `expression2`  
 필수. 임의의 숫자 식입니다.  
  
## <a name="supported-types"></a>지원 형식  
 부호 없는 및 부동 소수점 형식을 포함 한 모든 숫자 형식 및 `Decimal`합니다.  
  
## <a name="result"></a>결과  
 결과의 정수 몫은 `expression1` 나눈 `expression2`, 나머지는 버리고 정수 부분만 유지 합니다. 로 알려져 *잘림*합니다.  
  
 결과 데이터 형식이 데이터 형식에 대 한 적합 한 숫자 형식 `expression1` 및 `expression2`합니다. "정수 연산" 표를 참조 하십시오. [연산자 결과의 데이터 형식을](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.  
  
 [/ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) 소수 부분에 있는 나머지를 유지 하면서 전체 몫을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 나누기를 수행 하기 전에 Visual Basic에 임의의 부동 소수점 숫자 식으로 변환 하려고 `Long`합니다. 경우 `Option Strict` 은 `On`, 컴파일러 오류가 발생 합니다. 경우 `Option Strict` 은 `Off`, <xref:System.OverflowException> 값의 범위를 벗어납니다.이 경우에 [Long 데이터 형식](../../../visual-basic/language-reference/data-types/long-data-type.md)합니다. 변환할 `Long` 를 일으키는 이기도 *banker rounding*합니다. 자세한 내용은의 "소수 부분이" 참조 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)합니다.  
  
 경우 `expression1` 또는 `expression2` 계산 [Nothing](../../../visual-basic/language-reference/nothing.md), 0으로 간주 됩니다.  
  
## <a name="attempted-division-by-zero"></a>0으로 나누기  
 경우 `expression2` 가 0 이면는 `\` 연산자를 throw 한 <xref:System.DivideByZeroException> 예외입니다. 이 피연산자의 모든 숫자 데이터 형식에 적용 됩니다.  
  
> [!NOTE]
>  `\` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `\` 정수 나누기를 수행 하는 연산자입니다. 결과 나머지 삭제는 두 피연산자의 몫을 나타내는 정수입니다.  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 앞의 예제에 있는 식은 각각 2, 3, 33,-22의 값을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\\= 연산자](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [/ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
