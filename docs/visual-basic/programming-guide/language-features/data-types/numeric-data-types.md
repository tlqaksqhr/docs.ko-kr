---
title: "Numeric Data Types (Visual Basic) | Microsoft Docs"
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
  - "integral types, Visual Basic"
  - "Short data type, numeric data types"
  - "Double data type, numeric data types"
  - "Long data type, Visual Basic numeric data types"
  - "numbers, whole"
  - "fractions"
  - "numbers"
  - "whole numbers"
  - "integer numbers"
  - "numbers, integer"
  - "fractional data types"
  - "mantissas, of fractional numbers"
  - "mantissas"
  - "data types [Visual Basic], numeric"
  - "Integer data type, numeric data types"
  - "exponent, of fractional numbers"
  - "integers"
  - "numeric data types, Visual Basic"
  - "Single data type, numeric types"
  - "Decimal data type, numeric data types"
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# Numeric Data Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 다양한 표현으로 숫자를 처리할 수 있도록 여러 *숫자 데이터 형식*을 제공합니다.  *정수 계열* 형식은 정수\(양수, 음수 및 0\)만 나타내고 *비정수 계열* 형식은 정수 부분과 소수점 아래 부분이 모두 있는 숫자를 나타냅니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 데이터 형식을 비교한 표를 보려면 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)을 참조하십시오.  
  
## 정수 계열 숫자 형식  
 *정수 계열 데이터 형식*은 소수점 아래 부분이 없는 정수만 나타내는 데이터 형식입니다.  
  
 *부호 있는* 정수 계열 데이터 형식은 [SByte Data Type](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)\(8비트\), [Short Data Type](../../../../visual-basic/language-reference/data-types/short-data-type.md)\(16비트\), [Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md)\(32비트\) 및 [Long Data Type](../../../../visual-basic/language-reference/data-types/long-data-type.md)\(64비트\)입니다.  변수가 소수점 아래 부분이 있는 숫자 대신 항상 정수만 포함하는 경우 변수를 이 형식 중 하나로 선언합니다.  
  
 *부호 없는* 정수 계열 형식은 [Byte Data Type](../../../../visual-basic/language-reference/data-types/byte-data-type.md)\(8비트\), [UShort Data Type](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)\(16비트\), [UInteger Data Type](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)\(32비트\) 및 [ULong Data Type](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)\(64비트\)입니다.  변수가 이진 데이터나 특성을 알 수 없는 데이터를 포함하는 경우 변수를 이 형식 중 하나로 선언합니다.  
  
### 성능  
 산술 연산에는 정수 계열 형식을 사용하는 것이 다른 데이터 형식을 사용하는 것보다 빠릅니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]의 `Integer` 및 `UInteger` 형식을 사용하면 산술 연산을 가장 빠르게 수행할 수 있습니다.  
  
### 큰 정수  
 `Integer` 데이터 형식에 포함될 수 있는 것보다 더 큰 정수를 포함해야 하는 경우 `Long` 데이터 형식을 대신 사용할 수 있습니다.  `Long` 변수에는 \-9,223,372,036,854,775,808부터 9,223,372,036,854,775,807까지의 숫자가 포함될 수 있습니다.  `Long`을 사용하는 연산 작업은 `Integer`를 사용하는 연산 작업보다 속도가 다소 느립니다.  
  
 이보다 훨씬 더 큰 값이 필요한 경우 [Decimal Data Type](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)을 사용할 수 있습니다.  `Decimal`에는 \-79,228,162,514,264,337,593,543,950,335부터 79,228,162,514,264,337,593,543,950,335까지의 숫자\(소수 자릿수를 사용하지 않은 경우\)가 포함될 수 있습니다.  그러나 `Decimal` 숫자를 사용하는 연산 작업은 다른 숫자 데이터 형식을 사용하는 연산 작업보다 속도가 상당히 느립니다.  
  
### 작은 정수  
 모든 범위의 `Integer` 데이터 형식이 필요한 경우가 아니라면 \-32,768부터 32,767까지의 정수를 포함할 수 있는 `Short` 데이터 형식을 사용할 수 있습니다.  가장 작은 정수 범위를 사용하려면 \-128부터 127까지의 정수를 포함하는 `SByte` 데이터 형식을 사용합니다.  작은 정수를 포함하는 변수가 매우 많은 경우 공용 언어 런타임에서 `Short` 및 `SByte` 변수를 저장하는 것이 더 효율적이며 메모리 사용량도 줄일 수 있습니다.  그러나 `Short` 및 `SByte`를 사용하는 연산 작업은 `Integer`를 사용하는 연산 작업보다 속도가 조금 느립니다.  
  
### 부호 없는 정수  
 변수가 음수를 포함할 필요가 없는 경우 *부호 없는 형식*인 `Byte`, `UShort`, `UInteger` 및 `ULong`을 사용할 수 있습니다.  이러한 데이터 형식은 각각 대응되는 부호 있는 형식\(`SByte`, `Short`, `Integer` 및 `Long`\)에서 포함할 수 있는 양의 두 배에 해당하는 정수를 포함할 수 있습니다.  성능 면에서는 부호 없는 형식과 대응되는 부호 있는 형식의 효율성이 정확히 동일합니다.  특히 `UInteger`와 `Integer`는 모든 기본 숫자 데이터 형식 중에서 가장 효율적입니다.  
  
## 비정수 계열 숫자 형식  
 *비정수 데이터 형식*은 정수와 소수 부분을 모두 가진 숫자를 나타냅니다.  
  
 비정수 계열 숫자 데이터 형식은 `Decimal`\(128비트 고정 소수점\), [Single Data Type](../../../../visual-basic/language-reference/data-types/single-data-type.md)\(32비트 부동 소수점\) 및 [Double Data Type](../../../../visual-basic/language-reference/data-types/double-data-type.md)\(64비트 부동 소수점\)입니다.  이 데이터 형식은 모두 부호 있는 형식입니다.  변수가 소수를 포함할 수 있으면 변수를 이 형식 중 하나로 선언합니다.  
  
 `Decimal`은 부동 소수점 데이터 형식이 아닙니다.  `Decimal` 숫자는 이진 정수 값과 소수점 아래에 해당하는 값 부분을 지정하는 소수 자릿수 요소를 갖습니다.  
  
 사용할 수 있는 `Decimal` 변수에 금액 값을 합니다.  값의 정밀도 있습니다.  `Double` 데이터 형식은 속도가 빠르고 메모리를 적게 사용하지만 반올림 오류가 발생하기 쉽습니다.  `Decimal` 데이터 형식이 10 진수를 정확성을 유지 합니다.  
  
 부동 소수점\(`Single` 및 `Double`\) 숫자는 `Decimal` 숫자보다 더 큰 범위를 나타낼 수 있지만 반올림 오류가 발생할 수 있습니다.  부동 소수점 형식은 `Decimal`보다 적은 유효 자릿수를 지원하지만 더 큰 값을 나타낼 수 있습니다.  
  
 비정수 계열 숫자 값은 mmmEeee로 나타낼 수 있습니다. 여기서 mmm은 *가수*\(유효 자릿수\)이며 eee는 *지수*\(10의 거듭제곱\)입니다.  비정수 계열 형식에서 가장 큰 양수 값은 `Decimal`의 경우 7.9228162514264337593543950335E\+28이고, `Single`의 경우 3.4028235E\+38이고, `Double`의 경우 1.79769313486231570E\+308입니다.  
  
### 성능  
 현재 플랫폼의 프로세서는 배정밀도의 부동 소수점 연산을 수행하므로 `Double`이 소수 데이터 형식 중 가장 효율적인 형식입니다.  그러나 `Double`을 사용하는 연산 작업은 `Integer` 등의 정수 계열 형식을 사용하는 연산보다 속도가 느립니다.  
  
### 작은 크기  
 크기가 가능한 한 가장 작은 숫자\(0에 가장 가까운 숫자\)를 사용해야 하는 경우 `Double` 변수를 사용하면 음수 값의 경우 \-4.94065645841246544E\-324, 양수 값의 경우 4.94065645841246544E\-324에 해당하는 작은 크기의 숫자를 포함할 수 있습니다.  
  
### 작은 소수  
 `Double` 데이터 형식의 범위가 모두 필요하지는 않은 경우 `Single` 데이터 형식을 사용할 수 있습니다. 이 형식에는 \-3.4028235E\+38부터 3.4028235E\+38까지의 부동 소수점 숫자가 포함될 수 있습니다.  `Single` 변수에 사용할 수 있는 가장 작은 크기의 값은 음수의 경우 \-1.401298E\-45이고 양수의 경우 1.401298E\-45입니다.  작은 부동 소수점 숫자를 포함하는 변수가 매우 많은 경우 일반 언어 런타임에서 `Single` 변수를 저장하는 것이 더 효율적이며 메모리 사용량도 줄일 수 있습니다.  
  
## 참고 항목  
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Character Data Types](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [Miscellaneous Data Types](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [How to: Call a Windows Function that Takes Unsigned Types](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)