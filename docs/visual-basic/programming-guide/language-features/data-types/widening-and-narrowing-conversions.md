---
title: 확대 변환과 축소 변환(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- widening conversions [Visual Basic]
- narrowing conversions [Visual Basic]
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions [Visual Basic], exceptions during conversion
- type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], data type
- conversions [Visual Basic], narrowing
- type conversion [Visual Basic], narrowing
- data type conversion [Visual Basic], widening
- data type conversion [Visual Basic], narrowing
- changing data types [Visual Basic]
- type conversion [Visual Basic], widening
- data type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 960b4e4c7184309b6a84247d86fb94ccb2faf877
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>확대 변환과 축소 변환(Visual Basic)
형식 변환에 중요 한 고려 사항은 변환 결과 대상 데이터 형식의 범위 이내 인지 여부입니다.  
  
 A *확대 변환* 원래 데이터의 모든 가능한 값에 대해 허용할 수 있는 데이터 형식으로 값을 변경 합니다.  확대 변환 소스 값을 유지 하지만 표현 변경할 수 있습니다. 정수 계열 형식에서 변환 하는 경우이 경고가 발생 `Decimal`, 또는 `Char` 를 `String`합니다.  
  
 *축소 변환* 은 가능한 값의 일부를 저장하지 못할 수도 있는 데이터 형식으로 값을 변경합니다. 정수 계열 형식 및 숫자 형식으로 변환 되 고 변환 될 때 소수 자릿수 값은 반올림 하는 예를 들어 `Boolean` 로 `True` 또는 `False`합니다.  
  
## <a name="widening-conversions"></a>확대 변환  
 다음 표에서 표준 확대 변환을 보여 줍니다.  
  
|데이터 형식|데이터 형식 확장 <sup>1</sup>|  
|---|---|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|모든 열거형 형식 ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))|내부 정수 계열 형식 및 모든 형식을 내부 형식 확대 변환 합니다.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|`Char` 배열|`Char` 배열에 `String`|  
|모든 형식|[개체](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|모든 파생된 형식|파생 된 형식의 기본 <sup>3</sup>합니다.|  
|모든 형식|모든 인터페이스를 구현 합니다.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|모든 데이터 형식이 나 개체 유형입니다.|  
  
 <sup>1</sup> 정의 따라 모든 데이터 형식에 자신에 게 확대 하는 변환입니다.  
  
 <sup>2</sup> 변환할 때 `Integer`, `UInteger`, `Long`, `ULong`, 또는 `Decimal` 를 `Single` 또는 `Double` 정밀도 손실에는 있지만 더 손실 되지에 발생할 수 있습니다. 이런이 의미에서 정보 손실이 발생 하지 않습니다.  
  
 <sup>3</sup> 파생된 된 형식 기본 형식 중 하나로 변환은 확대 처럼 보일 수 있습니다. 양쪽 맞춤을 파생된 형식이 기본 형식의 인스턴스로 한정 되므로 기본 형식의 모든 멤버를 포함 합니다. 반대 방향으로의 기본 형식에 파생된 형식에서 정의 된 모든 새 멤버  
  
 확대 변환 실행 시 항상 성공 하 고 데이터가 손실 되지 마십시오. 암시적으로 항상 수행할 수 있는지 여부,는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 형식 검사 스위치를 설정 하는 `On` 또는 `Off`합니다.  
  
## <a name="narrowing-conversions"></a>축소 변환  
 표준 축소 변환에는 다음과 같습니다.  
  
-   앞의 확대 변환이의 역방향 테이블 (제외 하 고 자신에 게 모든 형식이 확장 되는지를)  
  
-   사이 변환 [부울](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 모든 숫자 형식  
  
-   열거 형식에 임의의 숫자 형식에서 변환 (`Enum`)  
  
-   사이 변환 [문자열](../../../../visual-basic/language-reference/data-types/string-data-type.md) 모든 숫자 형식 `Boolean`, 또는 [날짜](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
-   파생 된 형식으로 입력 데이터 형식이 나 개체에서 변환  
  
 축소 변환 않는 항상 실행 시 성공 및 실패 하거나 하 데이터 손실이 발생할 합니다. 오류가 대상 데이터 형식 변환 되는 값을 받을 수 없는 경우 발생 합니다. 예를 들어 숫자 변환 하면 오버플로가 발생할 수 있습니다. 컴파일러 허용 하지 않는 한 축소 변환을 암시적으로 수행 하지 않습니다는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 형식 검사 스위치를 설정 하는 `Off`합니다.  
  
> [!NOTE]
>  요소에서 변환에 축소 변환 오류가 기록 됩니다는 `For Each…Next` 루프 제어 변수 컬렉션입니다. 자세한 내용과 예제는 "축소 변환" 섹션을 참조 [각각에 대해... 다음 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.  
  
### <a name="when-to-use-narrowing-conversions"></a>축소 변환을 사용 하는 경우  
 오류 또는 데이터 손실 없이 대상 데이터 형식으로 변환할 수 소스 값을 알고 있는 경우에 축소 변환을 사용 합니다. 예를 들어 한 `String` 를 "True" 또는 "False"를 포함 하는 것이 알아야를 사용할 수 있습니다는 `CBool` 변환할 키워드 `Boolean`합니다.  
  
## <a name="exceptions-during-conversion"></a>변환 중 예외  
 확대 변환은 항상 때문에 성공 하 고 예외를 throw 하지 않습니다. 실패할 경우에 축소 변환이 가장 일반적으로 다음과 같은 예외를 throw 합니다.  
  
-   <xref:System.InvalidCastException> -두 형식 간의 정의 된 변환이 없는 경우  
  
-   <xref:System.OverflowException> -(정수 계열 형식만) 변환 된 값이 너무 커서 대상 유형에 적합 하지  
  
 클래스 또는 구조체 정의 하는 경우는 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 변환 연산자 또는 해당 클래스 또는 구조체에서 역할을 하는 `CType` 적절 하다 고 판단 되는 모든 예외를 throw 할 수 있습니다. 또한 하 `CType` Visual Basic 함수를 호출할 수 있습니다 또는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 는 다양 한 예외를 throw 할 수 있는 메서드입니다.  
  
## <a name="changes-during-reference-type-conversions"></a>참조 형식 변환 하는 동안 변경 내용  
 변환은 *유형을 참조* 포인터만 값으로 복사 합니다. 값 자체 복사 아니고 어떤 식으로든에서 변경 합니다. 변경할 수 있는 유일한 항목에는 포인터를가지고 있는 변수의 데이터 형식입니다. 다음 예제에서는 데이터 형식은 해당 기본 클래스나 파생된 클래스에서 변환 됩니다 있지만 두 변수가 가리키는 개체는 변경 되지 않습니다.  
  
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
 [문자열과 다른 형식 사이의 변환](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [방법: Visual Basic에서 다른 형식으로 변환](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [배열 규칙](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
