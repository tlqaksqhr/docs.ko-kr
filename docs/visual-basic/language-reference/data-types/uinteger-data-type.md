---
title: "UInteger Data Type | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.uinteger"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "numbers, whole"
  - "UInteger data type"
  - "literal type characters, UI"
  - "whole numbers"
  - "integral data types"
  - "integer numbers"
  - "numbers, integer"
  - "integers, data types"
  - "integers, types"
  - "UI literal type characters"
  - "data types [Visual Basic], integral"
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# UInteger Data Type
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

0에서 4,294,967,295까지의 부호 없는 32비트\(4바이트\) 정수를 저장합니다.  
  
## 설명  
 `UInteger` 데이터 형식은 부호 없는 가장 큰 값을 가장 효율적인 데이터 너비로 제공합니다.  
  
 `UInteger`의 기본값은 0입니다.  
  
## 프로그래밍 팁  
 더 작은 정수 형식\(`UShort`, `Short`, `Byte` 및 `SByte`\)의 경우 사용하는 비트 수는 적어도 로드, 저장 및 페치하는 시간이 오래 걸리기 때문에 32비트 프로세서에는 `UInteger`와 `Integer` 데이터 형식이 최적의 성능을 발휘합니다.  
  
-   **음수.** `UInteger`는 부호 없는 형식이므로 음수를 나타낼 수 없습니다.  `UInteger` 형식으로 계산되는 식에서 단항 마이너스\(`-`\) 연산자를 사용하면 Visual Basic은 먼저 식을 `Long`로 변환합니다.  
  
-   **CLS 규격.** `UInteger` 데이터 형식은 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\)에 포함되어 있지 않으므로 CLS 규격 코드에서는 이 데이터 형식을 사용하는 구성 요소를 사용할 수 없습니다.  
  
-   **Interop 고려 사항.** Automation 또는 COM 개체와 같이 .NET Framework용으로 작성되지 않은 구성 요소를 사용하는 경우 다른 환경에서는 `uint`과 같은 형식이 다른 데이터 너비\(16비트\)를 가질 수 있다는 것을 염두에 두고 있어야 합니다.  이러한 구성 요소에 16비트 인수를 전달하는 경우 Visual Basic 관리 코드에서 이 인수를 `UInteger` 대신 `UShort`로 선언하십시오.  
  
-   **확대 변환.** `UInteger` 데이터 형식은 `Long`, `ULong`, `Decimal`, `Single` 및 `Double`로 확대 변환됩니다.  이것은 <xref:System.OverflowException?displayProperty=fullName> 오류의 발생 없이 `UInteger`를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.  
  
-   **형식 문자.** 리터럴 형식 문자 `UI`를 리터럴에 추가하면 `UInteger` 데이터 형식이 됩니다.  `UInteger`에는 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.UInt32?displayProperty=fullName> 구조체입니다.  
  
## 참고 항목  
 <xref:System.UInt32>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)