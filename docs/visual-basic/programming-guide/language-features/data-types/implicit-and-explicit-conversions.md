---
title: "Implicit and Explicit Conversions (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conversions, type"
  - "variables [Visual Basic], changing data type"
  - "casting"
  - "conversions, data type"
  - "type conversion, implicit conversions"
  - "CType function, conversions"
  - "casting, data types"
  - "data type conversion, explicit"
  - "type conversion, explicit conversions"
  - "data types [Visual Basic], casting"
  - "conversions, implicit"
  - "explicit data type conversions"
  - "conversions"
  - "changing data types"
  - "conversions, explicit"
  - "data type conversion, implicit"
  - "implicit data type conversions"
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
caps.latest.revision: 25
caps.handback.revision: 25
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Implicit and Explicit Conversions (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*암시적 변환*에서는 소스 코드에 특별한 구문이 필요하지 않습니다.  다음 예제의 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 `k` 값을 `q`에 할당하기 전에 암시적으로 단정밀도 부동 소수점 값으로 변환합니다.  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 *명시적 변환*에서는 형식 변환 키워드를 사용합니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 괄호 안의 식을 원하는 데이터 형식으로 강제 변환하는 여러 가지 형식 변환 키워드를 제공합니다.  이런 키워드는 함수처럼 동작하지만 컴파일러가 인라인으로 코드를 생성하므로 함수 호출보다 약간 빠르게 실행됩니다.  
  
 위 예제를 확장한 아래 코드에서는 `CInt` 키워드가 `q` 값을 `k`에 할당하기 전에 다시 정수로 변환합니다.  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## 변환 키워드  
 다음 표에서는 사용할 수 있는 변환 키워드를 보여 줍니다.  
  
||||  
|-|-|-|  
|형식 변환 키워드|식을 다음 데이터 형식으로 변환|변환할 식에 허용되는 데이터 형식|  
|`CBool`|[Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|임의의 숫자 형식\(`Byte`, `SByte` 및 열거 형식 포함\), `String`, `Object`|  
|`CByte`|[Byte Data Type](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|임의의 숫자 형식\(`SByte` 및 열거 형식 포함\), `Boolean`, `String`, `Object`|  
|`CChar`|[Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|  
|`CDate`|[Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|  
|`CDbl`|[Double Data Type](../../../../visual-basic/language-reference/data-types/double-data-type.md)|임의의 숫자 형식\(`Byte`, `SByte` 및 열거 형식 포함\), `Boolean`, `String`, `Object`|  
|`CDec`|[Decimal Data Type](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|임의의 숫자 형식\(`Byte`, `SByte` 및 열거 형식 포함\), `Boolean`, `String`, `Object`|  
|`CInt`|[Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|임의의 숫자 형식\(`Byte`, `SByte` 및 열거 형식 포함\), `Boolean`, `String`, `Object`|  
|`CLng`|[Long Data Type](../../../../visual-basic/language-reference/data-types/long-data-type.md)|임의의 숫자 형식\(`Byte`, `SByte` 및 열거 형식 포함\), `Boolean`, `String`, `Object`|  
|`CObj`|[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)|모든 형식|  
|`CSByte`|[SByte Data Type](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|임의의 숫자 형식\(`Byte` 및 열거 형식 포함\), `Boolean`, `String`, `Object`|  
|`CShort`|[Short Data Type](../../../../visual-basic/language-reference/data-types/short-data-type.md)|임의의 숫자 형식\(`Byte`, `SByte` 및 열거 형식 포함\), `Boolean`, `String`, `Object`|  
|`CSng`|[Single Data Type](../../../../visual-basic/language-reference/data-types/single-data-type.md)|임의의 숫자 형식\(`Byte`, `SByte` 및 열거 형식 포함\), `Boolean`, `String`, `Object`|  
|`CStr`|[String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md)|임의의 숫자 형식\(`Byte`, `SByte` 및 열거 형식 포함\), `Boolean`, `Char`, `Char` 배열, `Date`, `Object`|  
|`CType`|쉼표\(`,`\) 다음에 지정된 형식|*기본 데이터 형식*\(기본 형식의 배열 포함\)으로 변환하는 경우, 해당하는 변환 키워드에 허용되는 것과 동일한 형식<br /><br /> *복합 데이터 형식*으로 변환하는 경우, 해당 형식이 구현하는 인터페이스 및 해당 형식이 상속하는 클래스<br /><br /> `CType`을 오버로드한 클래스 또는 구조체로 변환하는 경우, 해당 클래스 또는 구조체|  
|`CUInt`|[UInteger Data Type](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|임의의 숫자 형식\(`Byte`, `SByte` 및 열거 형식 포함\), `Boolean`, `String`, `Object`|  
|`CULng`|[ULong Data Type](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|임의의 숫자 형식\(`Byte`, `SByte` 및 열거 형식 포함\), `Boolean`, `String`, `Object`|  
|`CUShort`|[UShort Data Type](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|임의의 숫자 형식\(`Byte`, `SByte` 및 열거 형식 포함\), `Boolean`, `String`, `Object`|  
  
## CType 함수  
 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md)는 두 개의 인수로 연산을 수행합니다.  첫 번째는 변환할 식이고 두 번째는 대상 데이터 형식이나 개체 클래스입니다.  첫 번째 인수는 형식이 아니라 식이어야 합니다.  
  
 `CType`은 *인라인 함수*입니다. 즉, 컴파일된 코드에서 변환을 수행하며 대개 함수 호출은 생성되지 않습니다.  이렇게 하면 성능이 향상됩니다.  
  
 `CType`과 다른 형식 변환 키워드를 비교하려면 [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) 및 [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md)를 참조하십시오.  
  
### 기본 형식  
 다음 예제는 `CType`의 사용을 보여 줍니다.  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### 복합 형식  
 `CType`을 사용하여 값을 기본 형식은 물론 복합 데이터 형식으로도 변환할 수 있습니다.  또한 이 함수를 사용하여 다음 예제처럼 개체 클래스를 해당 인터페이스 중 하나의 형식으로 강제 변환할 수도 있습니다.  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### 배열 형식  
 또한 `CType`은 다음 예제처럼 배열 데이터 형식을 변환할 수도 있습니다.  
  
```  
Dim v() As classV  
Dim obArray() As Object  
' Assume some object array has been assigned to obArray.  
' Check for run-time type compatibility.  
If TypeOf obArray Is classV()  
    ' obArray can be converted to classV.  
    v = CType(obArray, classV())  
End If  
```  
  
 자세한 내용과 예제는 [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)을 참조하십시오.  
  
### CType을 정의하는 형식  
 사용자가 정의한 클래스 또는 구조체에 `CType`을 정의할 수 있습니다.  이렇게 하면 사용자가 정의한 클래스 또는 구조체의 형식과 값 간의 변환이 가능해집니다.  자세한 내용과 예제는 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)를 참조하십시오.  
  
> [!NOTE]
>  변환 키워드와 함께 사용되는 값은 대상 데이터 형식에 대해 유효해야 하며 그렇지 않으면 오류가 발생합니다.  예를 들어, `Long`을 `Integer`로 변환하는 경우 `Long`의 값이 `Integer` 데이터 형식에 맞는 유효한 범위 안에 있어야 합니다.  
  
> [!CAUTION]
>  `CType`을 지정하여 한 클래스 형식에서 다른 클래스 형식으로 변환할 경우 소스 형식이 대상 형식에서 파생되지 않았으면 런타임에 오류가 발생합니다.  이러한 오류가 발생하면 <xref:System.InvalidCastException> 예외가 throw됩니다.  
  
 그러나 형식 중 하나가 사용자가 정의한 구조체나 클래스이고 해당 구조체 또는 클래스에 `CType`을 정의한 경우에는 `CType`의 요구 사항이 충족되면 변환이 성공적으로 수행됩니다.  [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)를 참조하십시오.  
  
 명시적 변환을 수행하는 것을 특정 데이터 형식이나 개체 클래스로 식을 *캐스팅*한다고도 합니다.  
  
## 참고 항목  
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Conversions Between Strings and Other Types](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)