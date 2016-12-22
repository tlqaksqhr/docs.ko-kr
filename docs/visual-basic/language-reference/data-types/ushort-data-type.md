---
title: "UShort Data Type (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ushort"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "numbers, whole"
  - "literal type characters, US"
  - "whole numbers"
  - "integral data types"
  - "integer numbers"
  - "numbers, integer"
  - "integers, data types"
  - "integers, types"
  - "data types [Visual Basic], integral"
  - "UShort data type"
  - "US literal type characters"
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# UShort Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

값의 범위가 0에서 65,535까지인 부호 없는 16비트\(2바이트\) 정수를 저장합니다.  
  
## 설명  
 `UShort` 데이터 형식을 사용하면 `Byte`에 비해 너무 큰 이진 데이터를 포함할 수 있습니다.  
  
 `UShort`의 기본값은 0입니다.  
  
## 프로그래밍 팁  
  
-   **음수.** `UShort`는 부호 없는 형식이므로 음수를 나타낼 수 없습니다.  `UShort` 형식으로 계산되는 식에서 단항 마이너스\(`-`\) 연산자를 사용하면 Visual Basic은 먼저 식을 `Integer`로 변환합니다.  
  
-   **CLS 규격.** `UShort` 데이터 형식은 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\)에 포함되어 있지 않으므로 CLS 규격 코드에서는 이 데이터 형식을 사용하는 구성 요소를 사용할 수 없습니다.  
  
-   **확대 변환.** `UShort` 데이터 형식은 `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`로 확대 변환됩니다.  이것은 <xref:System.OverflowException?displayProperty=fullName> 오류의 발생 없이 `UShort`를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.  
  
-   **형식 문자.** 리터럴 형식 문자 `US`를 리터럴에 추가하면 `UShort` 데이터 형식이 됩니다.  `UShort`에는 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.UInt16?displayProperty=fullName> 구조체입니다.  
  
## 참고 항목  
 <xref:System.UInt16>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)