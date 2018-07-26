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
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245676"
---
# <a name="troubleshooting-data-types-visual-basic"></a>데이터 형식 문제 해결(Visual Basic)
이 페이지는 기본 데이터 형식에 대 한 작업을 수행할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열 합니다.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>부동 소수점 식 동일한 것으로 비교 하지 않습니다.  
 부동 소수점 숫자를 사용 하 여 작업할 때 ([단일 데이터 형식](../../../../visual-basic/language-reference/data-types/single-data-type.md) 하 고 [Double 데이터 형식](../../../../visual-basic/language-reference/data-types/double-data-type.md)), 이진 소수로 저장 하는 것을 기억 합니다. 즉, 이러한 이진 소수 없는 수량을 정확히 표시를 포함할 수 없습니다 (k 형식의 / (2 ^ n) 및 n은 정수). 예를 들어 0.5 (1/2 =)와 (5 월 16 =) 0.3125 반면 (1 월 5 =) 0.2 및 0.3 (3/10 =) 정확한 값으로 유지 수 있습니다.  
  
 이 때문에 부정확성으로 사용할 수 없게 정확한 결과를 부동 소수점 값에 작동 합니다. 특히 이론적으로 동일한 두 개의 값 약간 다르게 표시 될 수 있습니다.  
  
| 부동 소수점 수량을 비교 하려면 | 
|---| 
|1.  사용 하 여 해당 차이의 절대값을 계산할를 <xref:System.Math.Abs%2A> 메서드를 <xref:System.Math> 클래스는 <xref:System> 네임 스페이스입니다.<br />2.  같아야 실무 차이가 크지 않은 경우 두 개의 수량을 고려할 수 있도록 허용 가능한 최대 차이 결정 합니다.<br />3.  차이 허용 오차의 절대 값을 비교 합니다.|  
  
 다음 예제에서는 두 개의 잘못 된 및 올바른 비교 `Double` 값입니다.  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 앞의 예제에서는 <xref:System.Double.ToString%2A> 메서드를 <xref:System.Double> 인스턴스보다 정확도 향상을 지정할 수 있도록 구조체는 `CStr` 키워드 사용 합니다. 기본값은 15 자리까지 하지만 "G17" 형식으로 17 자리를 확장 합니다.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Mod 연산자 정확한 결과 반환 하지 않습니다.  
 부동 소수점 저장소의 부정확성으로 인해 합니다 [Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md) 피연산자 중 하나 이상에 부동 소수점 때 예기치 않은 결과 반환할 수 있습니다.  
  
 합니다 [Decimal 데이터 형식](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) 부동 소수점 표현을 사용 하지 않습니다. 에서는 정확 하지 않은 많은 숫자 `Single` 하 고 `Double` 에서는 정확 하 `Decimal` (예: 0.2 및 0.3). 산술에서 느립니다 `Decimal` 보다 부동 소수점 수 것이 성능 저하를 감내할 것이 좋습니다.  
  
|부동 소수점 수량 정수 나머지를 구하려는|  
|---|  
|1.  변수 선언 `Decimal`합니다.<br />2.  리터럴 형식 문자를 사용 하 여 `D` 리터럴을 적용할 `Decimal`경우 해당 값은 너무 커서는 `Long` 데이터 형식.|  
  
 다음 예제에서는 부동 소수점 피연산자의 잠재적 부정확성을 보여 줍니다.  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 앞의 예제에서는 <xref:System.Double.ToString%2A> 메서드를 <xref:System.Double> 인스턴스보다 정확도 향상을 지정할 수 있도록 구조체는 `CStr` 키워드 사용 합니다. 기본값은 15 자리까지 하지만 "G17" 형식으로 17 자리를 확장 합니다.  
  
 때문에 `zeroPointTwo` 는 `Double`, 0.2에 대 한 해당 값이 저장 된 값이 0.20000000000000001 인 무한 반복 이진 되 소수입니다. 2.0이이 수량으로 나눈 9.9999999999999995 0.19999999999999991 나머지를 사용 하 여 생성 됩니다.  
  
 식에서 `decimalRemainder`, 리터럴 형식 문자 `D` 대 한 두 피연산자를 강제로 `Decimal`, 0.2에 정확한 표현이 고 합니다. 따라서는 `Mod` 연산자 예상된 0.0 나머지를 구합니다.  
  
 선언 하는 데 충분 하지는 `decimalRemainder` 으로 `Decimal`입니다. 리터럴을 해야 할 `Decimal`, 또는 사용 하 여 `Double` 기본적으로 및 `decimalRemainder` 와 같은 부정확 한 값을 받는 `doubleRemainder`합니다.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>부울 형식 숫자 형식으로 정확 하 게 변환 되지 않습니다.  
 [Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값은 숫자로 저장 되지 않으며 저장 된 값은 숫자에 해당 되지 않아야 합니다. 이전 버전과 호환성을 위해 Visual Basic 변환 키워드를 제공 ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)를 `CBool`, `CInt`등) 간에 변환할 `Boolean` 및 숫자 형식입니다. 그러나 기타 언어 경우에 따라 이러한 변환을 수행 마찬가지로 다르게는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 메서드.  
  
 에 해당 하는 숫자 값을 사용 하는 코드를 작성 하지 말아야 `True` 고 `False`입니다. 사용을 제한 해야 가능 하면 `Boolean` 변수는 설계 하는 논리 값입니다. 혼합 해야 하는 경우 `Boolean` 숫자 값을 선택 하는 변환 메서드를 알고 있는지 확인 합니다.  
  
### <a name="conversion-in-visual-basic"></a>Visual Basic의 변환  
 사용 하는 경우는 `CType` 또는 `CBool` 숫자 데이터 형식을 변환할 변환 키워드 `Boolean`, 0 됩니다 `False` 고 다른 모든 값은 `True`합니다. 변환 하는 경우 `Boolean` 값을 변환 키워드를 사용 하 여 숫자 형식 `False` 는 0이 되 고 `True` 는-1입니다.  
  
### <a name="conversion-in-the-framework"></a>Framework의 변환  
 <xref:System.Convert.ToInt32%2A> 메서드를 <xref:System.Convert> 클래스는 <xref:System> 네임 스페이스 변환 `True` 를 + 1입니다.  
  
 변환 해야 하는 경우는 `Boolean` 숫자 데이터 형식으로 값을 주의 사용 하는 변환 메서드.  
  
## <a name="character-literal-generates-compiler-error"></a>컴파일러 오류를 생성 하는 문자 리터럴  
 형식 문자가 없는 경우, Visual Basic 리터럴에 대 한 데이터 형식을 기본을 가정합니다. 문자 리터럴에 대 한 기본 형식-따옴표로 묶인 (`" "`)-는 `String`합니다.  
  
 합니다 `String` 데이터 형식으로 확대 되지 않습니다 합니다 [데이터 형식 Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)합니다. 즉, 리터럴을 할당 하려는 경우는 `Char` 변수인 축소 변환을 하거나에 리터럴을 `Char` 형식입니다.  

|Char 변수 또는 상수를 할당 하려면 리터럴 만들려면|
|---|  
|1.  변수 또는 상수를 선언 `Char`합니다.<br />2.  문자 값을 따옴표로 묶습니다 (`" "`).<br />3.  닫는 큰따옴표와 리터럴 형식 문자에 따라 `C` 강제로 리터럴을 `Char`합니다. 이 속성이 필요 형식 검사 스위치 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))는 `On`, 어떤 경우 든 바람직한 것.|  
  
 다음 예제에서는 리터럴을 성공 및 실패 한 할당을 `Char` 변수입니다.  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 에 항상 위험 축소 변환을 사용 하 여 런타임에 실패할 수 있습니다. 예를 들어 변환 `String` 를 `Char` 실패할 수 있습니다를 `String` 값 두 개 이상의 문자를 포함 합니다. 따라서 사용을 더 잘 프로그래밍은 `C` 문자를 입력 합니다.  
  
## <a name="string-conversion-fails-at-run-time"></a>런타임 시 문자열 변환이 실패  
 합니다 [문자열 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md) 거의 확대 변환에 참여 합니다. `String` 자체에 확대 및 `Object`, 및 전용 `Char` 및 `Char()` (을 `Char` 배열)으로 확장 `String`합니다. 왜냐하면 `String` 변수 및 상수 다른 데이터 형식을 포함할 수 없는 값을 포함할 수 있습니다.  
  
 형식 검사 스위치 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))은 `On`, 컴파일러가 모든 암시적 축소 변환을 허용 하지 않습니다. 여기에 관련 된 이러한 `String`합니다. 코드 변환 키워드와 같은 사용할 여전히 수 `CStr` 및 [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)에 직접은 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 변환 하려고 합니다.  
  
> [!NOTE]
>  축소 변환 오류 요소에서 변환에 대 한 표시 되지 않는지를 `For Each…Next` 루프 제어 변수 컬렉션입니다. 자세한 내용 및 예제에 "Narrowing Conversions" 섹션을 참조 [각각에 대 한 중... 다음 문을](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.  
  
### <a name="narrowing-conversion-protection"></a>축소 변환 보호  
 축소 변환의 단점은 런타임에 실패할 수 있습니다. 예를 들어 경우는 `String` 로 변환할 수 없습니다 "True" 또는 "False" 이외의 항목이 변수 들어 `Boolean`합니다. 문장 부호 문자를 포함 하는 경우 모든 숫자 형식 변환이 실패 합니다. 알 수 없다면 사용자 `String` 항상 변수에 대상 유형을 허용할 수 있는 값을 변환 하지 않아야 합니다.  
  
 변환 해야 하는 경우 `String` 다른 데이터 형식으로 가장 안전한 절차 포함 하는 것에서 시도 된 변환은 [시도 하는 중... Catch 하는 중... Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다. 이렇게 하면 런타임 오류로 처리할 수 있습니다.  
  
### <a name="character-arrays"></a>문자 배열  
 단일 `Char` 배열과 `Char` 변환할 모두 요소 `String`합니다. 그러나 `String` 으로 확대 되지 않는 `Char()`합니다. 변환할를 `String` 값을 `Char` 배열에 사용할 수는 <xref:System.String.ToCharArray%2A> 메서드의 <xref:System.String?displayProperty=nameWithType> 클래스.  
  
### <a name="meaningless-values"></a>의미 없는 값  
 일반적으로 `String` 값 다른 데이터 형식에서는 의미가 없으며 변환이 매우 인위적인 하며 위험 합니다. 사용을 제한 해야 가능 하면 `String` 하도록 디자인 된 문자 시퀀스에는 변수입니다. 다른 형식에 해당 하는 값을 사용 하는 코드를 작성 하지 말아야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [데이터 형식의 효율적 사용](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
