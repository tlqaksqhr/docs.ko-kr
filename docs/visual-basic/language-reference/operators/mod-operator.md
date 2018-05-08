---
title: Mod 연산자(Visual Basic)
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5120823f4e001fc3aff71f267176311e2465597a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mod-operator-visual-basic"></a>Mod 연산자 (Visual Basic)
두 숫자를 나누고 나머지만 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a>요소  
 `number1`  
 필수. 임의의 숫자 식입니다.  
  
 `number2`  
 필수. 임의의 숫자 식입니다.  
  
## <a name="supported-types"></a>지원 되는 형식  
 모든 숫자 형식입니다. 여기에 서명 되지 않은 부동 소수점 형식과 및 `Decimal`합니다.  
  
## <a name="result"></a>결과

결과 나머지 `number1` 나눈 `number2`합니다. 예를 들어 식 `14 Mod 4` 계산 결과 2입니다.  

> [!NOTE]
> 간의 차이가 *나머지* 및 *모듈러스* 수학 여 음수에 대 한 다양 한 결과입니다. `Mod` Visual Basic의 경우.NET Framework에서는 연산자 `op_Modulus` 연산자 및 기본 [rem]<xref:System.Reflection.Emit.OpCodes.Rem> IL 명령의 모든 나머지 작업을 수행 합니다.

결과 `Mod` 는 피제수의 부호를 유지 하는 작업 `number1`, 등과 양수 또는 음수가 될 수 있습니다. 결과 항상 범위에서 (-`number2`, `number2`)을 제외 합니다. 예를 들어:

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a>설명  
 어느 경우 `number1` 또는 `number2` 는 부동 소수점 값, 부동 소수점 나누기의 나머지가 반환 됩니다. 결과의 데이터 형식이 데이터 형식으로 나눈 결과인 가능한 모든 값을 보유할 수 있는 가장 작은 데이터 형식 `number1` 및 `number2`합니다.  
  
 경우 `number1` 또는 `number2` 계산 [Nothing](../../../visual-basic/language-reference/nothing.md), 0으로 간주 됩니다.  
  
 관련 된 연산자는 다음과 같습니다.  
  
-   [\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) 나누기의 몫을 반환 합니다. 예를 들어 식 `14 \ 4` 3으로 계산 합니다.  
  
-   [/ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) 부동 소수점 숫자로 나머지를 포함 하 여 전체 몫을 반환 합니다. 예를 들어 식 `14 / 4` 3.5로 계산 합니다.  
  
## <a name="attempted-division-by-zero"></a>0으로 나누기  
 경우 `number2` 의 동작을 0으로 계산 되는 `Mod` 연산자는 피연산자의 데이터 형식에 따라 달라 집니다. 이 정수 나누기를 throw 한 <xref:System.DivideByZeroException> 예외입니다. 부동 소수점 나누기 반환 <xref:System.Double.NaN>합니다.  
  
## <a name="equivalent-formula"></a>해당 하는 수식  
 식 `a Mod b` 다음 수식을 중 하나에 해당 합니다.  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a>부동 소수점 연산이  
 부동 소수점 숫자를 작업할 때는 항상 없는 정확한 10 진수 표현을 메모리에서 기억 합니다. 값 비교 같은 특정 작업에서 예기치 않은 결과가 발생할 수 있습니다 및 `Mod` 연산자입니다. 자세한 내용은 참조 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.  
  
## <a name="overloading"></a>오버로딩  
 `Mod` 연산자 *오버 로드 된*, 클래스 또는 구조체의 동작 할 수 있습니다. 코드에 적용 되는 경우 `Mod` 클래스 또는 이러한 오버 로드를 포함 하는 구조체의 인스턴스로 사용할 다시 정의 된 동작을 알고 있어야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Mod` 연산자를 두 개의 숫자를 나누고 나머지만 반환 합니다. 중 하나가 숫자가 부동 소수점 숫자 이면의 결과 나머지를 나타내는 부동 소수점 숫자입니다.  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 부동 소수점 피연산자의 잠재적 부정확성 보여 줍니다. 피연산자는 첫 번째 문에서 `Double`, 0.2는 저장 된 값이 0.20000000000000001 인 무한 반복 이진 소수 및 합니다. 두 번째 문을 리터럴 형식 문자 `D` 두 피연산자 모두 강제로 `Decimal`, 0.2에 정확한 표시 합니다.  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a>참고자료  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
