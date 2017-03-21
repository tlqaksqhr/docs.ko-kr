---
title: "데이터 형식 (Visual Basic) 문제 해결 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Char data type, converting
- Decimal data type, conversions
- data types [Visual Basic], troubleshooting
- literals, default types
- type characters, literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types
- floating-point numbers, precision
- Boolean data type, converting
- literal types
- literal type characters
- floating-point numbers, imprecision
- String data type, converting
- floating-point numbers, comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
caps.latest.revision: 29
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cfb8fc77d3e0d85ef795a94fc95ab61a8f68ff39
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-data-types-visual-basic"></a>데이터 형식 문제 해결(Visual Basic)
이 페이지는 내장 데이터 형식에 대 한 작업을 수행할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열 합니다.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>부동 소수점 식 동일한 것으로 비교 하지 않습니다.  
 부동 소수점 숫자를 작업 하는 경우 ([단일 데이터 형식](../../../../visual-basic/language-reference/data-types/single-data-type.md) 및 [Double 데이터 형식](../../../../visual-basic/language-reference/data-types/double-data-type.md)), 이진 소수로 저장 해야 합니다. 즉, 이진 소수 없는 수량 정확 하 게 나타내지는 저장할 수 없습니다 (형식 k / (2 ^ n) k 및 n은 정수). 예를 들어 0.5 (= 1/2)와 0.3125 (= 5/16) 이지만 (= 1/5) 0.2 및 0.3 (3/10 =) 정확한 값으로 유지 수 있습니다.  
  
 이 때문에 부정확성으로 사용할 수 없게 정확한 결과를 부동 소수점 값에 작동 하는 경우. 특히, 이론적으로 동일한 두 값에는 약간 다르게 표시 될 수 있습니다.  
  
| 부동 소수점 수량을 비교 하려면 | 
|---| 
|1.  사용 하 여 해당 차이의 절대값을 계산할는 <xref:System.Math.Abs%2A>의 메서드는 <xref:System.Math>클래스에 <xref:System>네임 스페이스.</xref:System> </xref:System.Math> </xref:System.Math.Abs%2A><br />2.  같아야 실무 점 간의 차이 크지 않은 경우 두 개의 수량을 고려할 수 있도록 허용 가능한 최대 차이 결정 합니다.<br />3.  허용 오차에 대 한 차이의 절대값을 비교 합니다.|  
  
 다음 예제에서는 두 개의 잘못 된 방법과 올바른 비교 `Double` 값입니다.  
  
 [!code-vb[VbVbalrDataTypes #&10;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 앞의 예제에서는 <xref:System.Double.ToString%2A>의 메서드는 <xref:System.Double>보다 더 정확한을 지정할 수 있도록 구조는 `CStr` 키워드를 사용 합니다.</xref:System.Double> </xref:System.Double.ToString%2A> 기본값은 15 자리인 하지만 "G17" 형식 17 자리를 확장 합니다.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Mod 연산자 정확한 결과 반환 하지 않습니다.  
 부동 소수점 저장의 부정확성으로 인해는 [Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md) 피연산자 중 하나는 부동 소수점 예기치 않은 결과 반환할 수 있습니다.  
  
 [Decimal 데이터 형식](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) 부동 소수점 표시를 사용 하지 않습니다. 에서는 정확 하지 않은 숫자 `Single` 및 `Double` 에서는 정확 하 `Decimal` (예: 0.2 및 0.3). 산술에서 느린 `Decimal` 보다 부동 소수점 수도 성능 저하를 감내할 가치가 있습니다.  
  
|부동 소수점 수량의 정수 나머지를 찾을 수|  
|---|  
|1.  변수를 선언 `Decimal`합니다.<br />2.  리터럴 형식 문자를 사용 하 여 `D` 에 리터럴을 적용 `Decimal`해당 값이에 비해 너무 큰 경우에 `Long` 데이터 형식입니다.|  
  
 다음 예제에서는 부동 소수점 피연산자의 잠재적 부정확성을 보여 줍니다.  
  
 [!code-vb[VbVbalrDataTypes #&11;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 앞의 예제에서는 <xref:System.Double.ToString%2A>의 메서드는 <xref:System.Double>보다 더 정확한을 지정할 수 있도록 구조는 `CStr` 키워드를 사용 합니다.</xref:System.Double> </xref:System.Double.ToString%2A> 기본값은 15 자리인 하지만 "G17" 형식 17 자리를 확장 합니다.  
  
 때문에 `zeroPointTwo` 는 `Double`, 0.2에 대 한 값이 저장 된 값이 0.20000000000000001 인 무한 반복 되는 이진 소수입니다. 이 수량 2.0 나누어 9.9999999999999995 0.19999999999999991의 나머지를 구합니다.  
  
 에 대 한 식에서 `decimalRemainder`, 리터럴 형식 문자 `D` 두 피연산자 모두 강제로 `Decimal`, 0.2에 정확한 표시 합니다. 따라서는 `Mod` 연산자 0.0 예상된 나머지를 구합니다.  
  
 선언 하는 데 충분 하지는 `decimalRemainder` 으로 `Decimal`합니다. 리터럴의 강제로 해야 `Decimal`, 사용 하 여 `Double` 기본적으로 및 `decimalRemainder` 같은 부정확 한 값을 받는 `doubleRemainder`합니다.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>부울 형식 숫자 형식으로 정확 하 게 변환 되지 않습니다.  
 [Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값은 숫자로 저장 되지 않으며 저장 된 값은 숫자에 해당 되지 않습니다. 이전 버전과 호환성에 대 한 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 변환 키워드를 제공 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`등) 사이 변환할 `Boolean` 및 숫자 형식입니다. 그러나 다른 언어 때로는 이러한 변환을 수행할 마찬가지로 다르게는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 메서드.  
  
 해당 하는 숫자 값을 사용 하는 코드를 작성 하지 마십시오 `True` 및 `False`합니다. 사용을 제한 해야 가능 하다 면 `Boolean` 하도록 디자인 된 논리 값으로 변수입니다. 혼합 해야 하는 경우 `Boolean` 숫자 값을 선택 하는 변환 메서드를 알고 있는지 확인 합니다.  
  
### <a name="conversion-in-visual-basic"></a>Visual Basic의 변환  
 사용 하는 경우는 `CType` 또는 `CBool` 변환 키워드를 숫자 데이터 형식을 변환 하려면 `Boolean`, 0은 `False` 고 다른 모든 값은 `True`합니다. 변환 하는 경우 `Boolean` 값을 변환 키워드를 사용 하 여 숫자 형식 `False` 0이 되 고 `True` 는-1입니다.  
  
### <a name="conversion-in-the-framework"></a>Framework의 변환  
 <xref:System.Convert.ToInt32%2A>의 메서드는 <xref:System.Convert>클래스에 <xref:System>네임 스페이스 변환 `True` 를 +&1;.</xref:System> </xref:System.Convert> </xref:System.Convert.ToInt32%2A>  
  
 변환 해야 하는 경우는 `Boolean` 숫자 데이터 형식으로 값을 주의 해야 변환 메서드를 사용 합니다.  
  
## <a name="character-literal-generates-compiler-error"></a>컴파일러 오류를 생성 하는 문자 리터럴  
 형식 문자가 없을 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 에서는 기본 리터럴에 대 한 데이터 형식을 사용 합니다. 리터럴 문자에 대 한 기본 형식-따옴표로 묶인 (`" "`)-은 `String`합니다.  
  
 `String` 데이터 형식에 확대 변환 되지 않으면는 [Char 데이터 형식을](../../../../visual-basic/language-reference/data-types/char-data-type.md)합니다. 즉 리터럴을 할당 하려는 경우는 `Char` 변수인 축소 변환을 하거나 리터럴을에 `Char` 유형입니다.  

|Char 변수 또는 상수에 할당 하려면 리터럴 만들려면|
|---|  
|1.  변수 또는으로 상수 선언 `Char`합니다.<br />2.  문자 값을 따옴표로 묶습니다 (`" "`).<br />3.  닫는 큰따옴표와 리터럴 형식 문자에 따라 `C` 에 리터럴을 강제로 `Char`합니다. 이 경우 형식 검사 스위치 필요 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))은 `On`는 것이 좋습니다 어떤 경우 든 합니다.|  
  
 다음 예제에서는 리터럴을 실패 하 여 성공적으로 할당 한 `Char` 변수입니다.  
  
 [!code-vb[VbVbalrDataTypes #&12;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 항상 위험을 사용 하는 축소 변환을 런타임에 실패할 수 있기 때문입니다. 예를 들어 변환 `String` 를 `Char` 경우 실패할 수 있습니다는 `String` 개 이상의 문자를 포함 하는 값입니다. 따라서 사용 하 여 더 프로그래밍이 `C` 문자를 입력 합니다.  
  
## <a name="string-conversion-fails-at-run-time"></a>런타임에 문자열 변환 실패  
 [문자열 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md) 거의 확대 변환에 참여 합니다. `String`자체에 확장 및 `Object`만 `Char` 및 `Char()` (한 `Char` 배열)로 확대 변환 `String`합니다. 즉, `String` 변수 및 상수에 다른 데이터 형식을 포함할 수 없는 값을 포함할 수 있습니다.  
  
 형식 검사 스위치 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))은 `On`, 컴파일러가 모든 암시적 축소 변환을 허용 하지 않습니다. 여기에 포함 됩니다 관련 `String`합니다. 코드 변환 키워드와 같은 사용할 여전히 수 `CStr` 및 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)를 지시할은 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 변환 하려고 합니다.  
  
> [!NOTE]
>  축소 변환 오류에 있는 요소에서 변환에 대해 무시 됩니다는 `For Each…Next` 루프 제어 변수 컬렉션입니다. 자세한 내용과 예제는 "축소 변환" 섹션을 참조 [각각에 대해... 다음 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.  
  
### <a name="narrowing-conversion-protection"></a>축소 변환 보호  
 축소 변환의 단점은 런타임에 실패할 수 있습니다. 예를 들어 하는 경우는 `String` 변수에 포함 된 모든 항목 "True" 또는 "False"로 변환할 수 없는 이외의 `Boolean`합니다. 문장 부호 문자를 포함 하는 경우 모든 숫자 형식 변환이 실패 합니다. 알 수 없다면 사용자 `String` 변수는 항상 대상 유형에 사용할 수 있는 값을 가집니다, 변환을 시도 하지 마십시오.  
  
 변환 해야 하는 경우 `String` 가장 안전한 절차는 다른 데이터 형식에서 시도 된 변환은 묶으면는 [시도 중... Catch... Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다. 이 런타임 오류를 다룰 수 있습니다.  
  
### <a name="character-arrays"></a>문자 배열  
 단일 `Char` 배열 및 `Char` 요소 둘 다로 확대 변환 `String`합니다. 그러나 `String` 를 확대 변환 되지 않으면 `Char()`합니다. 변환 하는 `String` 값을 한 `Char` 배열에는 <xref:System.String.ToCharArray%2A> <xref:System.String?displayProperty=fullName>클래스</xref:System.String?displayProperty=fullName> 의 메서드</xref:System.String.ToCharArray%2A> 를 사용할 수 있습니다  
  
### <a name="meaningless-values"></a>의미 없는 값  
 일반적으로 `String` 값이 다른 데이터 형식에서는 의미가 및 변환이 매우 부적절 하며 위험 합니다. 사용을 제한 해야 가능 하다 면 `String` 변수 하도록 디자인 된 문자 시퀀스를 합니다. 다른 형식에 해당 하는 값을 사용 하는 코드를 작성 하지 마십시오.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [데이터 형식의 효율적 사용](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
