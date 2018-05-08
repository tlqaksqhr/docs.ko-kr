---
title: ^ 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: 426c3e9913dadda1091f4ba53c66c6b65e40e768
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-visual-basic"></a>^ 연산자(Visual Basic)
숫자를를 다른 숫자의 거듭제곱을 발생 시킵니다.  
  
## <a name="syntax"></a>구문  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a>요소  
 `number`  
 필수. 임의의 숫자 식입니다.  
  
 `exponent`  
 필수. 임의의 숫자 식입니다.  
  
## <a name="result"></a>결과  
 결과 `number` 의 거듭제곱을 `exponent`, 항상로 `Double` 값입니다.  
  
## <a name="supported-types"></a>지원 형식  
 `Double`. 다른 형식의 피연산자 변환할 `Double`합니다.  
  
## <a name="remarks"></a>설명  
 Visual Basic의 지 수를 항상 수행는 [Double 데이터 형식의](../../../visual-basic/language-reference/data-types/double-data-type.md)합니다.  
  
 값 `exponent` 소수인 수 음수, 또는 둘 다 합니다.  
  
 단일 식에서 둘 이상의 지 수 연산을 수행 되는 `^` 연산자는 왼쪽에서 오른쪽으로 계산 됩니다.  
  
> [!NOTE]
>  `^` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `^` 연산자를 지 수의 숫자입니다. 결과 두 번째 거듭제곱을 첫 번째 피연산자입니다.  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 앞의 예제 결과 다음과 같습니다.  
  
 `exp1` 4 (2의 제곱)로 설정 됩니다.  
  
 `exp2` 19683 (3, 3 제곱 값을 제곱)로 설정 됩니다.  
  
 `exp3` (3 제곱-5)-125로 설정 됩니다.  
  
 `exp4` 625 (4 제곱-5)로 설정 됩니다.  
  
 `exp5` 2 (64.64의 8)로 설정 됩니다.  
  
 `exp6` (1.0 8의 세 제곱근으로 나눈) 0.5로 설정 됩니다.  
  
 앞의 예제 식에서는 괄호의 중요성을 note 합니다. 때문에 *연산자 우선 순위*, Visual Basic을 정상적으로 수행 된 `^` 단항 포함 하 여 다른 대체 이전에, 연산자 `–` 연산자입니다. 경우 `exp4` 및 `exp6` 계산 괄호 없이 다음과 같은 결과가 생성:  
  
 `exp4 = -5 ^ 4` – (4 제곱 5)로 계산 될 것-625를 초래 합니다.  
  
 `exp6 = 8 ^ -1.0 / 3.0` (-1 제곱, 즉 0.125 8)로 계산 될 것 3.0 0.041666666666666666666666666666667로 나눈 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [^= 연산자](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
