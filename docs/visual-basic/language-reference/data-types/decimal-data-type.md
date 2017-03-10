---
title: "Decimal Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Decimal"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "literal type characters, D"
  - "trailing zeros"
  - "real numbers"
  - "trailing 0 characters"
  - "Decimal data type"
  - "D literal type character"
  - "decimals, Decimal data type"
  - "0 characters, trailing"
  - "data types [Visual Basic], assigning"
  - "decimal keyword"
  - "numbers, real"
  - "variable-precision numbers"
  - "zeros, trailing"
  - "@ identifier type character"
  - "identifier type characters, @"
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Decimal Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

10의 거듭제곱으로 환산된 96비트\(12바이트\)를 나타내는 128비트\(16바이트\) 값을 저장합니다.  배율 인수는 소수점 오른쪽의 자릿수를 지정하며 범위는 0 ~ 28입니다.  배율이 0\(소수 자릿수 없음\)일 때 가능한 가장 큰 값은 \+\/\-79,228,162,514,264,337,593,543,950,335 \(\+\/\-7.9228162514264337593543950335E\+28\)입니다.  소수 자릿수가 28인 경우 가능한 값은 \+\/\-7.9228162514264337593543950335 사이의 값이며, 0이 아닌 값 중에서 최소값은 \+\/\-0.0000000000000000000000000001\(\+\/\-E\-28\)입니다.  
  
## 설명  
 `Decimal` 데이터 형식은 숫자에 대한 최대 유효 자릿수를 제공합니다.  이 데이터 형식은 최대 29개의 유효 자릿수를 지원하고 7.9228 x 10^28을 초과하는 값을 나타낼 수 있습니다.  이 형식은 특히 금융 분야처럼 많은 자릿수가 필요하지만 반올림 오류가 발생해서는 안 되는 계산에 적합합니다.  
  
 `Decimal`의 기본값은 0입니다.  
  
## 프로그래밍 팁  
  
-   **정밀도.** `Decimal`은 부동 소수점 데이터 형식이 아닙니다.  `Decimal` 구조체는 이진 정수 값을 부호 비트 및 소수점 아래에 해당하는 값 부분을 지정하는 소수 자릿수 요소와 함께 사용합니다.  따라서 `Decimal` 숫자는 부동 소수점 형식\(`Single` 및 `Double`\)보다 메모리에서 더 정밀한 표현을 제공합니다.  
  
-   **성능.** `Decimal` 데이터 형식은 모든 숫자 형식 중 가장 느린 형식입니다.  데이터 형식을 선택하기 전에 정밀도와 성능 중 무엇이 더 중요한지를 충분히 검토해야 합니다.  
  
-   **확대 변환.** `Decimal` 데이터 형식은 `Single` 또는 `Double`로 확대 변환됩니다.  이것은 <xref:System.OverflowException?displayProperty=fullName> 오류의 발생 없이 `Decimal`을 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.  
  
-   **뒤에 오는 0.** Visual Basic에서는 후행 0 문자를 `Decimal` 리터럴에 저장하지 않습니다.  그러나 `Decimal` 변수는 계산을 통해 얻은 후행 0 문자를 유지합니다.  다음은 이에 대한 예입니다.  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     이전 예제의 `MsgBox` 출력은 다음과 같습니다.  
  
     d1 \= 2.375, d2 \= 1.625, d3 \= 4.000, d4 \= 4  
  
-   **형식 문자.** 리터럴 형식 문자 `D`를 리터럴에 추가하면 `Decimal` 데이터 형식이 됩니다.  식별자 형식 문자 `@`을 식별자에 추가하면 `Decimal`가 됩니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Decimal?displayProperty=fullName> 구조체입니다.  
  
## 범위  
 `Decimal` 변수 또는 상수에 큰 값을 할당하려면 `D` 형식 문자를 사용해야 할 수 있습니다.  컴파일러는 리터럴 문자로 해석 하기 때문에이 요구 사항입니다 `Long` 리터럴 형식 문자 리터럴, 다음 예제와 같이 뒤에 오는 경우를 제외 합니다.  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 에 대 한 선언을 `bigDec1` 에 할당 되는 값 범위를 벗어나므로 오버플로 생성 하지 않습니다 `Long`.  `Long` 값에 할당 하는 `Decimal` 변수입니다.  
  
 에 대 한 선언을 `bigDec2` 에 할당 되는 값에 대 한 너무 크기 때문에 오버플로 오류가 생성 됩니다. `Long`.  숫자 리터럴은으로 먼저 해석 될 수 있기 때문에 `Long`를 할당할 수 없습니다의 `Decimal` 변수.  
  
 에 대 한 `bigDec3`, 리터럴 형식 문자 `D` 는 리터럴로 해석 하도록 컴파일러를 강제 적용 하 여 문제가 해결 되었습니다.는 `Decimal` 대신으로 `Long`.  
  
## 참고 항목  
 <xref:System.Decimal?displayProperty=fullName>   
 <xref:System.Decimal.%23ctor%2A?displayProperty=fullName>   
 <xref:System.Math.Round%2A?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Single Data Type](../../../visual-basic/language-reference/data-types/single-data-type.md)   
 [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)