---
title: "ULong Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ulong"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "numbers, whole"
  - "whole numbers"
  - "integral data types"
  - "integer numbers"
  - "numbers, integer"
  - "integers, data types"
  - "integers, types"
  - "data types [Visual Basic], integral"
  - "literal type characters, UL"
  - "ULong data type"
  - "UL literal type characters"
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# ULong Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

값의 범위가 0에서 18,446,744,073,709,551,615\(1.84 x 10 ^ 19 이상\)까지인 부호 없는 64비트\(8바이트\) 정수를 저장합니다.  
  
## 설명  
 `ULong` 데이터 형식을 사용하면 `UInteger`에 비해 너무 큰 이진 데이터나 가장 큰 부호 없는 정수 값을 포함할 수 있습니다.  
  
 `ULong`의 기본값은 0입니다.  
  
## 프로그래밍 팁  
  
-   **음수.** `ULong`는 부호 없는 형식이므로 음수를 나타낼 수 없습니다.  `ULong` 형식으로 계산되는 식에서 단항 마이너스\(`-`\) 연산자를 사용하면 Visual Basic은 먼저 식을 `Decimal`로 변환합니다.  
  
-   **CLS 규격.** `ULong` 데이터 형식은 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\)에 포함되어 있지 않으므로 CLS 규격 코드에서는 이 데이터 형식을 사용하는 구성 요소를 사용할 수 없습니다.  
  
-   **Interop 고려 사항.** Automation 또는 COM 개체와 같이 .NET Framework용으로 작성되지 않은 구성 요소를 사용하는 경우 다른 환경에서는 `ulong`과 같은 형식이 다른 데이터 너비\(32비트\)를 가질 수 있다는 것을 염두에 두고 있어야 합니다.  이러한 구성 요소에 32비트 인수를 전달하는 경우 Visual Basic 관리 코드에서 이 인수를 `ULong` 대신 `UInteger`로 선언하십시오.  
  
     또한 자동화는 Windows 95, Windows 98, Windows ME 또는 Windows 2000에서 64비트 정수를 지원하지 않습니다.  이러한 플랫폼에서 자동화 구성 요소에 Visual Basic `ULong` 인수를 전달할 수 없습니다.  
  
-   **확대 변환.** `ULong` 데이터 형식은 `Decimal`, `Single` 및 `Double`로 확대 변환됩니다.  이것은 <xref:System.OverflowException?displayProperty=fullName> 오류의 발생 없이 `ULong`를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.  
  
-   **형식 문자.** 리터럴 형식 문자 `UL`를 리터럴에 추가하면 `ULong` 데이터 형식이 됩니다.  `ULong`에는 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.UInt64?displayProperty=fullName> 구조체입니다.  
  
## 참고 항목  
 <xref:System.UInt64>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)