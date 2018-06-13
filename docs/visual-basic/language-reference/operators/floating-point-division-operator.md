---
title: / 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: 17eb3eddfae3cf7c818514a2fee20f646876a6ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604525"
---
# <a name="-operator-visual-basic"></a>/ 연산자(Visual Basic)
두 숫자를 나누고 부동 소수점 결과 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a>요소  
 `expression1`  
 필수. 임의의 숫자 식입니다.  
  
 `expression2`  
 필수. 임의의 숫자 식입니다.  
  
## <a name="supported-types"></a>지원 형식  
 부호 없는 및 부동 소수점 형식을 포함 한 모든 숫자 형식 및 `Decimal`합니다.  
  
## <a name="result"></a>결과  
 결과 전체 몫 `expression1` 나눈 `expression2`, 나머지 포함 합니다.  
  
 [\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) 나머지 부분을 삭제 하는 정수 몫을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 데이터 형식의 결과 피연산자의 형식에 따라 달라 집니다. 다음 표에서 결과의 데이터 형식을 결정 하는 방법 보여 줍니다.  
  
|피연산자 데이터 형식|결과 데이터 형식|  
|------------------------|----------------------|  
|두 식이 모두 정수 계열 데이터 형식 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [바이트](../../../visual-basic/language-reference/data-types/byte-data-type.md), [짧은](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [정수](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [긴](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|하나의 식이 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) 데이터 형식과 다른 않습니다는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|하나의 식이 [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md) 데이터 형식과 다른 않습니다는 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) 또는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|두 식 중 하나가 한 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) 데이터 형식|`Double`|  
  
 정수 계열 숫자 식이 모두는 확장 나누기를 수행 하기 전에 `Double`합니다. Visual Basic에서 결과 변환 하려고 정수 데이터 형식으로 결과 할당 하는 경우 `Double` 해당 형식으로. 이 결과 해당 형식에 맞지 않는 경우 예외가 throw 합니다. 특히이 도움말 페이지에 "0으로 나누기"을 참조 하십시오.  
  
 경우 `expression1` 또는 `expression2` 계산 [Nothing](../../../visual-basic/language-reference/nothing.md), 0으로 간주 됩니다.  
  
## <a name="attempted-division-by-zero"></a>0으로 나누기  
 경우 `expression2` 가 0 이면는 `/` 연산자는 피연산자를 다른 데이터 형식에 따라 다르게 동작 합니다. 다음 표에서 가능한 동작을 보여 줍니다.  
  
|피연산자 데이터 형식|동작 하는 경우 `expression2` 0|  
|------------------------|---------------------------------------|  
|부동 소수점 (`Single` 또는 `Double`)|무한대를 반환 (<xref:System.Double.PositiveInfinity> 또는 <xref:System.Double.NegativeInfinity>), 또는 <xref:System.Double.NaN> (숫자가 아님) 하는 경우 `expression1` 0입니다|  
|`Decimal`|Throw <xref:System.DivideByZeroException>|  
|정수 계열 (정수 또는 부호 없는)|정수 계열 형식 throw로 다시 변환 하려고 <xref:System.OverflowException> 정수 계열 형식 받아들일 수 있기 때문에 <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, 또는 <xref:System.Double.NaN>|  
  
> [!NOTE]
>  `/` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `/` 부동 소수점 나누기를 수행 하는 연산자입니다. 결과 두 피연산자의 몫입니다.  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]  
  
 앞의 예제에서 식에는 2.5 및 3.333333 값을 반환 합니다. 결과 항상 부동 소수점 (`Double`) 두 피연산자는 정수 상수는 경우에 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [/ = 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)  
 [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
