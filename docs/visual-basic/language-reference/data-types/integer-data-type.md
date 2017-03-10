---
title: "Integer Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Integer"
  - "Integer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "numbers, whole"
  - "enumerated values"
  - "whole numbers"
  - "integral data types"
  - "integer numbers"
  - "numbers, integer"
  - "integers, data types"
  - "literal type characters, I"
  - "integers, types"
  - "data types [Visual Basic], integral"
  - "% identifier type character"
  - "data types [Visual Basic], assigning"
  - "identifier type characters, %"
  - "I literal type character"
  - "Integer data type"
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Integer Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

\-2,147,483,648에서 2,147,483,647까지의 값 범위에 속하는 부호 있는 32비트\(4바이트\) 정수를 저장합니다.  
  
## 설명  
 `Integer` 데이터 형식은 32비트 프로세서에서 최적의 성능을 제공합니다.  다른 정수 계열 형식은 메모리에서 로드하고 저장하는 속도가 더 느려집니다.  
  
 `Integer`의 기본값은 0입니다.  
  
## 프로그래밍 팁  
  
-   **Interop 고려 사항.** Automation 또는 COM 개체와 같이 .NET Framework용으로 작성되지 않은 구성 요소와 상호 작용하는 경우 다른 환경에서는 `Integer`의 데이터 너비\(16비트\)가 다르다는 점에 유의해야 합니다.  이러한 구성 요소에 16비트 인수를 전달하는 경우 새 Visual Basic 코드에서 이 인수를 `Integer` 대신 `Short`로 선언하십시오.  
  
-   **확대.** `Integer` 데이터 형식은 `Long`, `Decimal`, `Single` 또는 `Double`로 확대 변환됩니다.  이는 <xref:System.OverflowException?displayProperty=fullName> 오류 발생 없이 `Integer`를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.  
  
-   **형식 문자.** 리터럴 형식 문자 `I`를 리터럴에 추가하면 `Integer` 데이터 형식이 됩니다.  식별자 형식 문자 `%`를 식별자에 추가하면 `Integer`가 됩니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Int32?displayProperty=fullName> 구조체입니다.  
  
## 범위  
 정수 계열 형식의 변수를 이 형식의 범위에서 벗어난 숫자로 설정하려고 하면 오류가 발생합니다.  분수로 설정하려고 하면 숫자는 가장 근사한 정수값으로 반올림되거나 반내림됩니다.  숫자가 두 정수 값에 가까우면 값은 가장 근사한 짝수 정수로 반올림됩니다.  이 동작은 중간값을 한 방향으로 계속해서 반올림할 때 발생하는 반올림 오류가 최소화됩니다.  다음 코드는 반올림의 예제를 보여 줍니다.  
  
```  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```  
  
## 참고 항목  
 <xref:System.Int32?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md)   
 [Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)