---
title: "Widening and Narrowing Conversions (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "widening conversions"
  - "narrowing conversions"
  - "conversions, type"
  - "data types [Visual Basic], changing"
  - "variables [Visual Basic], changing data type"
  - "conversions, exceptions during conversion"
  - "type conversion, exceptions during conversion"
  - "conversions, data type"
  - "conversions, narrowing"
  - "type conversion, narrowing"
  - "data type conversion, widening"
  - "data type conversion, narrowing"
  - "changing data types"
  - "type conversion, widening"
  - "data type conversion, exceptions during conversion"
  - "conversions, widening"
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Widening and Narrowing Conversions (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

형식 변환 시 고려해야 하는 중요한 사항은 변환의 결과가 대상 데이터 형식의 범위 안에 있는지의 여부입니다.  
  
 A  *확대 변환* 은 원본 데이터의 모든 가능한 값을 허용할 수 있는 데이터 형식으로 변경 합니다.  확대 변환을 수행하면 소스 값은 유지되지만 표현이 변경될 수 있습니다.  정수 계열 형식으로 변환 하는 경우이 문제가 발생 `Decimal`, 또는 `Char` 에 `String`.  
  
 *축소 변환*은 일부 가능한 값을 가질 수 없는 데이터 형식으로 값을 변경합니다.  숫자 형식으로 변환 하 고 정수 계열 형식으로 변환 하면 소수 값 반올림 예를 들어, `Boolean` 로 감소 `True` 또는 `False`.  
  
## 확대 변환  
 다음 표에서는 표준 확대 변환을 보여 줍니다.  
  
|||  
|-|-|  
|데이터 형식|확대 데이터 형식 <sup>1</sup>|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double` <sup>2</sup>|  
|[Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double` <sup>2</sup>|  
|[ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double` <sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single`, `Double` <sup>2</sup>|  
|[Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|모든 열거 형식\([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)\)|내부 정수 계열 형식 및 하는 내부 형식의 모든 확대 형식입니다.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|`Char` 배열|`Char` 배열, `String`|  
|모든 형식|[개체](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|모든 파생된 형식|된 형식이 파생 된 기본  <sup>3</sup>.|  
|모든 형식|구현한 모든 인터페이스입니다.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|모든 데이터 형식이 나 개체 형식입니다.|  
  
 <sup>1</sup> 정의에 따라 모든 데이터 형식의 확대 형식에는 해당 형식이 포함됩니다.  
  
 <sup>2</sup> `Integer`, `UInteger`, `Long`, `ULong` 또는 `Decimal`을 `Single` 또는 `Double`로 변환하면 정밀도는 낮아지지만 크기는 손실되지 않습니다.  따라서 정보 손실이 발생하지 않습니다.  
  
 <sup>3</sup> 파생된 형식을 기본 형식 중 하나로 변환하는 것은 확대 변환에 포함됩니다.  실제로 파생된 형식은 기본 형식의 모든 멤버를 가지고 있기 때문에 기본 형식의 인스턴스로 사용됩니다.  반대로 기본 형식은 파생된 형식에 의해 정의된 새 멤버를 가지고 있지 않습니다.  
  
 확대 변환은 런타임에 항상 성공하며 데이터 손실이 없습니다.  확대 변환은 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)에서 형식 검사 스위치를 `On`으로 설정하든 `Off`로 설정하든 관계없이 항상 암시적으로 수행할 수 있습니다.  
  
## 축소 변환  
 표준 축소 변환에는 다음과 같은 변환이 포함됩니다.  
  
-   위의 표에 설명된 확대 변환의 역방향 변환\(모든 형식이 자체 형식으로 확대되는 것은 제외\)  
  
-   [Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)과 임의의 숫자 형식 사이의 변환  
  
-   임의의 숫자 형식에서 임의의 열거 형식\(`Enum`\)으로 변환  
  
-   [String](../../../../visual-basic/language-reference/data-types/string-data-type.md)과 임의의 숫자 형식, `Boolean` 또는 [Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) 사이의 변환  
  
-   데이터 형식이나 개체 형식을 여기에서 파생된 형식으로 변환  
  
 축소 변환은 런타임에 항상 성공하는 것은 아니며 실패하거나 데이터가 손실될 수 있습니다.  대상 데이터 형식이 변환되는 값을 수신할 수 없으면 오류가 발생합니다.  예를 들어, 숫자 변환은 오버플로가 발생할 수 있습니다.  컴파일러에서는 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)에서 형식 검사 스위치를 `Off`로 설정하지 않았으면 축소 변환이 암시적으로 수행되는 것을 허용하지 않습니다.  
  
> [!NOTE]
>  `For Each…Next` 컬렉션의 요소에서 루프 제어 변수로의 변환에 대한 축소 변환 오류는 표시되지 않습니다.  자세한 내용 및 예제는 [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)의 "축소 변환" 단원을 참조하십시오.  
  
### 축소 변환 사용 시기  
 소스 값이 오류 또는 데이터 손실 없이 대상 데이터 형식으로 변환될 수 있다는 사실을 알고 있는 경우에 축소 변환을 사용합니다.  예를 들어, 사용자는 `String` 수 있습니다을 "True" 또는 "False"를 포함 알고의 `CBool` 키워드를 변환 하려면 `Boolean`.  
  
## 변환 중 발생하는 예외  
 확대 변환은 항상 성공하므로 예외를 throw하지 않습니다.  축소 변환이 실패할 경우에는 대부분 다음과 같은 예외를 throw합니다.  
  
-   <xref:System.InvalidCastException> — 두 형식 간에 정의된 변환이 없는 경우  
  
-   <xref:System.OverflowException> — 변환된 값이 대상 형식에 비해 너무 큰 경우\(정수 계열 형식만 해당\)  
  
 클래스나 구조체에서 해당 클래스나 구조체에 대한 변환 연산자 역할을 하도록 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)를 정의한 경우, 해당 `CType`은 적절한 예외를 throw할 수 있습니다.  또한 해당 `CType`은 다양한 예외를 throw할 수 있는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 함수나 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] 메서드를 호출할 수 있습니다.  
  
## 참조 형식 변환 도중 변경  
 *참조 형식*을 변환할 때는 값에 대한 포인터만 복사됩니다.  값 자체는 어떤 방식으로도 복사되거나 변경되지 않습니다.  포인터를 가지고 있는 변수의 데이터 형식만 변경할 수 있습니다.  다음 예제에서는 파생된 클래스에서 기본 클래스로 데이터 형식이 변경되지만 두 변수가 가리키는 개체는 변경되지 않습니다.  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## 참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Conversions Between Strings and Other Types](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)