---
title: '&gt;&gt; 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: 9bb8e82b3f5451417fe1867d08b7601ee1acb036
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="gtgt-operator-visual-basic"></a>&gt;&gt; 연산자 (Visual Basic)
비트 패턴에 산술 오른쪽 시프트를 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수. 정수 계열 숫자 값입니다. 변화 하는 비트 패턴의 결과입니다. 데이터 형식이 같습니다 `pattern`합니다.  
  
 `pattern`  
 필수. 정수 계열 숫자 식입니다. 이동할 비트 패턴입니다. 데이터 형식은 정수 계열 형식 이어야 합니다 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, 또는 `ULong`).  
  
 `amount`  
 필수. 숫자 식입니다. 비트 패턴을 이동할 비트 수를 지정 합니다. 데이터 형식이 있어야 `Integer` 으로 확장 또는 `Integer`합니다.  
  
## <a name="remarks"></a>설명  
 이동 하는 산술 형식 이므로 하지 순환, 결과의 한쪽 끝에서 이동 하는 비트는 다른 쪽 끝에서 다시 도입 되지 않습니다. 산술 오른쪽 시프트 연산 가장 오른쪽 위치를 넘어 이동 하는 비트는 무시 되 고 맨 왼쪽 (기호) 비트는 비워진 왼쪽 비트 위치로 전파 됩니다. 즉 `pattern` 음수 값을 가진 비워진된 위치 1로 설정 됩니다; 그렇지 않으면 0으로 설정 됩니다.  
  
 데이터 형식 `Byte`, `UShort`, `UInteger`, 및 `ULong` 전파할 수 없는 부호 비트 이므로 서명 되지 않은 합니다. 경우 `pattern` 의 부호 없는 형식이, 빈된 위치는 항상 0으로 설정 됩니다.  
  
 Visual Basic로 결과 표시할 수 있는 양보다 더 많은 비트 시프트를 방지 하려면의 값을 마스크 `amount` 의 데이터 형식에 해당 하는 크기 마스크로 `pattern`합니다. 이러한 값의 이진 AND 시프트 횟수에 대 한 사용 됩니다. 마스크 크기는 다음과 같습니다.  
  
|데이터 형식 `pattern`|크기 마스크 (10 진수)|마스크 크기 (16 진수)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&AMP; H00000007|  
|`Short`, `UShort`|15|&AMP; H0000000F|  
|`Integer`, `UInteger`|31|&AMP; H0000001F|  
|`Long`, `ULong`|63|&AMP; H0000003F|  
  
 경우 `amount` 0의 값이 `result` 의 값과 일치 `pattern`합니다. 경우 `amount` 가 음수 이면 해당 부호 없는 값으로 취급 되며 적절 한 크기 마스크를 사용 합니다.  
  
 이동 하는 산술 오버플로 예외를 생성 하지 않습니다.  
  
## <a name="overloading"></a>오버로딩  
 `>>` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `>>` 정수 값에 산술 오른쪽 시프트 연산을 수행 하는 연산자입니다. 결과는 항상 동일한 데이터 이동 되는 식과 같은 형식을 갖습니다.  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 위 예의 결과 다음과 같습니다.  
  
-   `result1` 2560 (0000 1010 0000 0000)입니다.  
  
-   `result2` 160 (0000 0000 1010 0000)입니다.  
  
-   `result3` 2 (0000 0000 0000 0010)입니다.  
  
-   `result4` 640 (0010 1000 0000 0000)입니다.  
  
-   `result5` 0 (오른쪽으로 15 자리 이동된)입니다.  
  
 에 대 한 시프트 횟수가 `result4` 18로 계산 됩니다가 2 및 15입니다.  
  
 다음 예제에서는 음수 값을 산술 시프트 합니다.  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 위 예의 결과 다음과 같습니다.  
  
-   `negresult1` -512 (1111 1110 0000 0000)입니다.  
  
-   `negresult2` -1 (부호 비트 전파 됨 입니다).  
  
## <a name="see-also"></a>참고 항목  
 [비트 시프트 연산자](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [>>= 연산자](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
