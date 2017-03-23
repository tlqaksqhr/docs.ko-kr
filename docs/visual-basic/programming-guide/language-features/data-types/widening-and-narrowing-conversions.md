---
title: "확대 변환과 축소 변환 (Visual Basic) | Microsoft 문서"
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
- widening conversions
- narrowing conversions
- conversions, type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions, exceptions during conversion
- type conversion, exceptions during conversion
- conversions, data type
- conversions, narrowing
- type conversion, narrowing
- data type conversion, widening
- data type conversion, narrowing
- changing data types
- type conversion, widening
- data type conversion, exceptions during conversion
- conversions, widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
caps.latest.revision: 27
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
ms.openlocfilehash: 88c5db6e7e82a88ae8015b581e5a795ec389d003
ms.lasthandoff: 03/13/2017

---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>확대 변환과 축소 변환(Visual Basic)
고려해 야 할 형식 변환 대상 데이터 형식의 범위 내에서 변환의 결과 인지 됩니다.  
  
 A *확대 변환* 원래 데이터의 모든 가능한 값에 대해 허용할 수 있는 데이터 형식으로 값을 변경 합니다.  확대 변환 소스 값을 유지 하지만 표현 변경할 수 있습니다. 정수 계열 형식에서 변환 하는 경우이 경고가 발생 `Decimal`, 또는 `Char` 를 `String`합니다.  
  
 *축소 변환* 은 가능한 값의 일부를 저장하지 못할 수도 있는 데이터 형식으로 값을 변경합니다. 숫자 형식으로 변환 되 고 정수 계열 형식으로 변환할 때 소수 자릿수 값은 반올림 하는 예를 들어 `Boolean` 로 `True` 또는 `False`합니다.  
  
## <a name="widening-conversions"></a>확대 변환  
 다음 표에서 표준 확대 변환을 보여 줍니다.  
  
|데이터 형식|데이터 형식 확장 <sup>1</sup>|  
|---|---|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[짧은](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[정수](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[긴](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|모든 열거형 형식 ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))|내부 정수 계열 형식 및 기본 형식 확대 변환 형식입니다.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|`Char` 배열|`Char`배열,`String`|  
|모든 형식|[개체](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|모든 파생된 형식|파생 된 형식의 기본 <sup>3</sup>합니다.|  
|모든 형식|모든 인터페이스를 구현 합니다.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|모든 데이터 형식이 나 개체 유형입니다.|  
  
 <sup>1</sup> 정의 따라 모든 데이터 형식에 자신에 게 확대 하는 변환입니다.  
  
 <sup>2</sup> 변환할 때 `Integer`, `UInteger`, `Long`, `ULong`, 또는 `Decimal` 를 `Single` 또는 `Double` 정밀도 손실에는 있지만 더 손실 되지에 발생할 수 있습니다. 이런이 의미에서 정보 손실이 발생 하지 않습니다.  
  
 <sup>3</sup> 파생된 형식 해당 형식의 기본 형식 중 하나로 변환 확대는 놀랍게 느껴질 수 있습니다. 양쪽 맞춤을 파생된 된 유형의 기본 형식의 인스턴스를 정규화 하도록 기본 형식의 모든 멤버를 포함 합니다. 반대 방향으로 기본 형식이 파생된 형식에서 정의 된 모든 새 멤버를 포함 되지 않습니다.  
  
 확대 변환을 수행 하면 런타임 시 항상 실패 하 고 데이터가 손실 되지 마십시오. 암시적으로 항상 수행할 수 있는지 여부,는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 형식 검사 스위치를 설정 하는 `On` 또는 `Off`합니다.  
  
## <a name="narrowing-conversions"></a>축소 변환  
 표준 축소 변환에는 다음과 같습니다.  
  
-   앞에 확대 변환의 역방향 테이블 (한다는 점을 제외 하면 모든 형식은 자체로 확대 변환)  
  
-   사이 변환 [부울](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 및 숫자 형식  
  
-   열거 형식에 임의의 숫자 형식에서 변환 (`Enum`)  
  
-   사이 변환 [문자열](../../../../visual-basic/language-reference/data-types/string-data-type.md) 및 숫자 형식, `Boolean`, 또는 [날짜](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
-   파생 된 형식으로 입력 데이터 형식이 나 개체에서 변환  
  
 축소 변환을 항상 실행 시 성공 하 고 수 실패 하거나 데이터가 손실 될. 오류는 대상 데이터 형식 변환 되는 값을 받을 수 없는 경우에 발생 합니다. 예를 들어 숫자 변환 하면 오버플로가 발생할 수 있습니다. 컴파일러 없도록 하지 않으면 암시적으로 축소 변환을 수행 하는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 형식 검사 스위치를 설정 하는 `Off`합니다.  
  
> [!NOTE]
>  축소 변환 오류에 있는 요소에서 변환에 대해 무시 됩니다는 `For Each…Next` 루프 제어 변수 컬렉션입니다. 자세한 내용과 예제는 "축소 변환" 섹션을 참조 [각각에 대해... 다음 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.  
  
### <a name="when-to-use-narrowing-conversions"></a>축소 변환을 사용 하는 경우  
 오류 또는 데이터 손실 없이 대상 데이터 형식으로 변환할 수 소스 값을 알고 있는 경우에 축소 변환을 사용 합니다. 예를 들어 한 `String` 가진다는 사실을 알고 "True" 또는 "False"를 사용할 수 있습니다는 `CBool` 변환할 키워드 `Boolean`합니다.  
  
## <a name="exceptions-during-conversion"></a>변환 중 예외  
 확대 변환은 항상 때문에 성공 하 고 예외를 throw 하지 않습니다. 가장 일반적으로 축소 변환을 실패할 경우 다음 예외를 throw 합니다.  
  
-   <xref:System.InvalidCastException>-두 형식 간의 정의 된 변환이 없는 경우</xref:System.InvalidCastException>  
  
-   <xref:System.OverflowException>-(정수 계열 형식만) 변환 된 값이 너무 커서 대상 유형에 적합 한 경우</xref:System.OverflowException>  
  
 클래스 또는 구조체 정의 하는 경우는 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 변환 연산자 또는 해당 클래스 또는 구조체를 제공 하는 `CType` 적절 하다 고 판단 되는 모든 예외를 throw 할 수 있습니다. 또한는 `CType` 호출할 수 있는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 함수 또는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 다양 한 예외 throw 할 수 있는 메서드.  
  
## <a name="changes-during-reference-type-conversions"></a>참조 형식 변환 하는 동안 변경 내용  
 변환은 *참조 형식* 포인터만 값에 복사 합니다. 값 자체는 복사 되거나 어떤 식으로든에서 변경 합니다. 변경할 수 있는 유일한 항목에 포인터를가지고 있는 변수의 데이터 형식입니다. 다음 예제에서는 해당 기본 클래스를 파생된 클래스에서 데이터 형식을 변환 됩니다 되지만 두 변수가 가리키는 개체는 변경 되지 않습니다.  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [문자열과 다른 형식 간의 변환](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [방법: Visual Basic에서 다른 형식으로 변환](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [배열 변환](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
