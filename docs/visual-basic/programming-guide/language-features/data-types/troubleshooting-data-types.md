---
title: 데이터 형식 문제 해결(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Char data type [Visual Basic], converting
- Decimal data type [Visual Basic], conversions
- data types [Visual Basic], troubleshooting
- literals [Visual Basic], default types
- type characters [Visual Basic], literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types [Visual Basic]
- floating-point numbers [Visual Basic], precision
- Boolean data type [Visual Basic], converting
- literal types [Visual Basic]
- literal type characters [Visual Basic]
- floating-point numbers [Visual Basic], imprecision
- String data type [Visual Basic], converting
- floating-point numbers [Visual Basic], comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
ms.openlocfilehash: c5ff9d097c0660956a9751a23511d8273766227c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655787"
---
# <a name="troubleshooting-data-types-visual-basic"></a>데이터 형식 문제 해결(Visual Basic)
이 페이지는 내장 데이터 형식에 대 한 작업을 수행할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열 합니다.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>부동 소수점 식을 동일한 것으로 비교 하지 않습니다.  
 부동 소수점 숫자를 작업할 때 ([단일 데이터 형식](../../../../visual-basic/language-reference/data-types/single-data-type.md) 및 [Double 데이터 형식의](../../../../visual-basic/language-reference/data-types/double-data-type.md)), 이진 소수로 저장 되도록 해야 합니다. 즉, 이진 소수 되지 않은 수량 정확한 숫자를 포함할 수 없습니다 (형식 k / (2 ^ n) k 및 n은 정수). 예를 들어 0.5 (1/2 =) 및 (= 5/16) 0.3125 반면 0.2 (1/5 =) 및 (3/10 =) 0.3 정확한 값으로 보유할 수 있습니다.  
  
 이 때문에 부정확성으로 사용할 수 없게 정확한 결과를 부동 소수점 값에 작동 하는 경우. 특히, 이론적으로 동일한 두 개의 값 약간 다르게 표시 될 수 있습니다.  
  
| 부동 소수점 수량을 비교 하려면 | 
|---| 
|1.  사용 하 여 해당 차이의 절대값을 계산할는 <xref:System.Math.Abs%2A> 의 메서드는 <xref:System.Math> 클래스에 <xref:System> 네임 스페이스입니다.<br />2.  차이가 크지 해당 하는 경우 실제로 동일한 것으로 두 개의 수량을 고려할 수 있도록 허용 가능한 최대 차이 결정 합니다.<br />3.  차이 허용 오차를 절대 값을 비교 합니다.|  
  
 다음 예제에서는 두 개의 잘못 된 방법과 올바른 비교 `Double` 값입니다.  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 사용 하 여 이전 예제는 <xref:System.Double.ToString%2A> 의 메서드는 <xref:System.Double> 보다 더 정확한을 지정할 수 있도록 구조는 `CStr` 키워드를 사용 합니다. 기본값은 15 자리 하지만 "G17" 형식 17 자리를 확장 합니다.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Mod 연산자 정확한 결과 반환 하지 않습니다.  
 부동 소수점 저장소 부정확성으로 인해는 [Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md) 피연산자 중 하나 이상에 부동 소수점 경우 예기치 않은 결과 반환할 수 있습니다.  
  
 [Decimal 데이터 형식](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) 부동 소수점 표시를 사용 하지 않습니다. 정확 하지 않은 많은 숫자 `Single` 및 `Double` 에서는 정확 하 `Decimal` (예: 0.2 및 0.3). 산술에 느린 `Decimal` 보다에 부동 소수점, 두면 유용할 수 성능 저하를 감내할 합니다.  
  
|부동 소수점 수량이의 정수 나머지를 구하려는 수|  
|---|  
|1.  변수를 선언 `Decimal`합니다.<br />2.  리터럴 형식 문자를 사용 하 여 `D` 에 리터럴을 적용 `Decimal`리터럴 값이 너무 커서에 대 한 경우, 고 `Long` 데이터 형식입니다.|  
  
 다음 예제에서는 부동 소수점 피연산자의 잠재적 부정확성 보여 줍니다.  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 사용 하 여 이전 예제는 <xref:System.Double.ToString%2A> 의 메서드는 <xref:System.Double> 보다 더 정확한을 지정할 수 있도록 구조는 `CStr` 키워드를 사용 합니다. 기본값은 15 자리 하지만 "G17" 형식 17 자리를 확장 합니다.  
  
 때문에 `zeroPointTwo` 은 `Double`, 0.2에 대 한 해당 값이 저장 된 값이 0.20000000000000001 인 무한 반복 되는 이진 소수입니다. 2.0이이 수량으로 나누는 9.9999999999999995 0.19999999999999991의 나머지를 구합니다.  
  
 에 대 한 식에서 `decimalRemainder`, 리터럴 형식 문자 `D` 두 피연산자 모두 강제로 `Decimal`, 0.2에 정확한 표시 합니다. 따라서는 `Mod` 연산자 0.0 예상된 나머지를 구합니다.  
  
 선언 하는 데 충분 하지 않습니다 `decimalRemainder` 으로 `Decimal`합니다. 리터럴을 강제 해야 `Decimal`를 사용 하 여 `Double` 기본적으로 및 `decimalRemainder` 같은 부정확 한 값을 받는 `doubleRemainder`합니다.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Boolean 형식의 숫자 형식으로 정확 하 게 변환 되지 않습니다.  
 [Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 숫자로 값은 저장 되지 않으며 숫자에 해당 되는 저장 된 값은 하지 않습니다. 이전 버전과 호환성에 대 한 Visual Basic에서는 변환 키워드 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`등) 사이 변환할 `Boolean` 및 숫자 형식입니다. 하지만 다른 언어 때로는 이러한 변환을 수행 같이 다르게는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 메서드.  
  
 해당 하는 숫자 값을 사용 하는 코드를 작성 하지 마십시오 `True` 및 `False`합니다. 용도 제한 해야 가능 하면 항상 `Boolean` 변수도 설계 된 논리 값입니다. 혼합 해야 `Boolean` 숫자 값을 선택 하는 변환 메서드를 알고 있는지 확인 합니다.  
  
### <a name="conversion-in-visual-basic"></a>Visual Basic의 변환  
 사용 하는 경우는 `CType` 또는 `CBool` 변환 키워드를 숫자 데이터 형식을 변환 하려면 `Boolean`, 0은 `False` 고 다른 모든 값은 `True`합니다. 변환 하는 경우 `Boolean` 값을 변환 키워드를 사용 하 여 숫자 형식 `False` 0이 되 고 `True` 는-1입니다.  
  
### <a name="conversion-in-the-framework"></a>Framework의 변환  
 <xref:System.Convert.ToInt32%2A> 의 메서드는 <xref:System.Convert> 클래스에 <xref:System> 네임 스페이스 변환 `True` 에서 + 1입니다.  
  
 변환 해야 하는 경우는 `Boolean` 숫자 데이터 형식으로 값을 주의 변환 메서드를 사용 합니다.  
  
## <a name="character-literal-generates-compiler-error"></a>문자 리터럴은 컴파일러 오류를 생성합니다.  
 형식 문자가 없는 경우, Visual Basic 리터럴에 대 한 데이터 형식을 기본을 가정합니다. 리터럴 문자에 대 한 기본 형식-따옴표로 묶인 (`" "`)-은 `String`합니다.  
  
 `String` 데이터 형식으로 확대 되지 않습니다는 [Char 데이터 형식을](../../../../visual-basic/language-reference/data-types/char-data-type.md)합니다. 즉 리터럴을 할당 하려는 경우는 `Char` 변수인 축소 변환을 하거나에 리터럴을 `Char` 유형입니다.  

|변수 또는 상수에 할당할 리터럴 Char를 만들려면|
|---|  
|1.  변수 또는으로 상수 선언 `Char`합니다.<br />2.  문자 값을 따옴표로 묶습니다 (`" "`).<br />3.  닫는 큰따옴표와 리터럴 형식 문자에 따라 `C` 에 리터럴을 강제로 `Char`합니다. 이 형식 검사 스위치 경우 필요 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))은 `On`, 것이 바람직합니다 어떤 경우에 한 합니다.|  
  
 다음 예제에서는 리터럴을 실패 및 성공한 할당 한 `Char` 변수입니다.  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 항상 위험이 있습니다 축소 변환을 사용 하 여 런타임 시 실패할 수 있기 때문입니다. 변환 예를 들어 `String` 를 `Char` 에 실패할 수 있습니다는 `String` 값 둘 이상의 문자가 포함 되어 있습니다. 사용 하 여 더 잘 프로그래밍 따라서는 `C` 문자를 입력 합니다.  
  
## <a name="string-conversion-fails-at-run-time"></a>런타임 시 문자열 변환이 실패  
 [문자열 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md) 매우 적은 확대 변환에 참여 합니다. `String` 자체에 확장 및 `Object`만 `Char` 및 `Char()` (한 `Char` 배열)으로 확장 `String`합니다. 즉, `String` 변수 및 상수를 포함할 수 없는 다른 데이터 형식 값을 포함할 수 있습니다.  
  
 형식 검사 스위치 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))은 `On`, 컴파일러에 모든 암시적 축소 변환을 허용 하지 않습니다. 여기에 관련 된 `String`합니다. 코드 여전히 צ ְ ײ 변환 키워드와 같은 `CStr` 및 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)를 지시할은 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 변환 하려고 합니다.  
  
> [!NOTE]
>  요소에서 변환에 축소 변환 오류가 기록 됩니다는 `For Each…Next` 루프 제어 변수 컬렉션입니다. 자세한 내용과 예제는 "축소 변환" 섹션을 참조 [각각에 대해... 다음 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.  
  
### <a name="narrowing-conversion-protection"></a>축소 변환 보호  
 축소 변환의 단점은 런타임 시 실패할 수 있습니다. 예를 들어 경우는 `String` 변수 항목이 들어 있는 "True" 또는 "False"로 변환할 수 없는 것과 다른 `Boolean`합니다. 문장 부호 문자를 포함 하는 경우는 숫자 형식으로 변환에 실패 합니다. 알 수 없다면 프로그램 `String` 항상 변수에 대상 유형에 사용할 수 있는 값, 변환을 시도 하지 마십시오.  
  
 변환 해야 하는 경우 `String` 가장 안전한 절차는 다른 데이터 형식에서 시도 된 변환은 묶습니다 하는 [시도 중... Catch 하는 중... Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다. 이렇게 하면 런타임에 오류와 함께 처리할 수 있습니다.  
  
### <a name="character-arrays"></a>문자 배열  
 단일 `Char` 배열을 `Char` 요소 둘 다로 확대 변환 `String`합니다. 그러나 `String` 으로 확대 되지 않는 `Char()`합니다. 변환 하는 `String` 값을 한 `Char` 사용할 수 있습니다 배열에는 <xref:System.String.ToCharArray%2A> 의 메서드는 <xref:System.String?displayProperty=nameWithType> 클래스.  
  
### <a name="meaningless-values"></a>의미 없는 값  
 일반적으로 `String` 값이 다른 데이터 형식에서는 의미가 및 변환이 매우 부적절 하며 위험 합니다. 용도 제한 해야 가능 하면 항상 `String` 변수도 설계 된 문자 시퀀스를 합니다. 다른 형식에 해당 하는 값을 사용 하는 코드를 작성 하지 마십시오.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [데이터 형식의 효율적 사용](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
