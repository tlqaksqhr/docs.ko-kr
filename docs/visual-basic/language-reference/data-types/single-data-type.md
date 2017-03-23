---
title: "Single Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Single"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Single data type"
  - "F literal type character"
  - "trailing zeros"
  - "real numbers"
  - "literal type characters, F"
  - "trailing 0 characters"
  - "identifier type characters, !"
  - "single-precision numbers"
  - "! identifier type character"
  - "0 characters, trailing"
  - "data types [Visual Basic], assigning"
  - "floating-point numbers, Single data type"
  - "numbers, real"
  - "zeros, trailing"
  - "numbers, floating point"
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Single Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

값의 범위가 \-3.4028235E\+38에서 \-1.401298E\-45까지\(음수\) 또는 1.401298E\-45에서 3.4028235E\+38까지\(양수\)인 IEEE 32비트\(4바이트\) 단정밀도 부동 소수점 숫자를 저장합니다.  단정밀도 숫자는 실수의 근사값을 저장합니다.  
  
## 설명  
 `Single` 데이터 형식을 사용하면 `Double`의 전체 데이터 너비가 필요하지 않은 부동 소수점 값을 포함할 수 있습니다.  공용 언어 런타임에서 `Single` 변수를 조밀하게 압축하여 메모리 사용량을 줄일 수 있는 경우도 가끔 있습니다.  
  
 `Single`의 기본값은 0입니다.  
  
## 프로그래밍 팁  
  
-   **정밀도.** 부동 소수점 숫자로 작업할 때에는 메모리에 정밀한 표현이 항상 제공되지는 않는다는 것을 염두에 두고 있어야 합니다.  따라서 값 비교, `Mod` 연산자 등과 같은 특정 연산에서 예기치 않은 결과가 나타날 수 있습니다.  자세한 내용은 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)를 참조하십시오.  
  
-   **확대 변환.** `Single` 데이터 형식은 `Double`로 확대 변환됩니다.  즉, <xref:System.OverflowException?displayProperty=fullName> 오류의 발생 없이 `Single`을 `Double`로 변환할 수 있습니다.  
  
-   **뒤에 오는 0.** 부동 소수점 데이터 형식에는 후행 0 문자에 대한 내부 표현이 없습니다.  예를 들어, 4.2000과 4.2를 구분하지 않습니다.  따라서 부동 소수점 값을 표시하거나 인쇄할 때 후행 0 문자는 나타나지 않습니다.  
  
-   **형식 문자.** 리터럴 형식 문자 `F`를 리터럴에 추가하면 `Single` 데이터 형식이 됩니다.  식별자 형식 문자 `!`을 식별자에 추가하면 `Single`가 됩니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Single?displayProperty=fullName> 구조체입니다.  
  
## 참고 항목  
 <xref:System.Single?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Decimal Data Type](../../../visual-basic/language-reference/data-types/decimal-data-type.md)   
 [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)