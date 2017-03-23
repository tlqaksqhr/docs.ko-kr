---
title: "Short Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Short"
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
  - "S literal type character"
  - "Short data type"
  - "literal type characters, S"
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Short Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

\-32,768에서 32,767까지의 값 범위에 있는 부호 있는 16비트\(2바이트\) 정수를 저장합니다.  
  
## 설명  
 `Integer`의 전체 데이터 너비가 필요하지 않은 정수 값을 포함하려는 경우에 `Short` 데이터 형식을 사용합니다.  공용 언어 런타임에서 `Short` 변수를 조밀하게 압축하여 메모리 사용량을 줄일 수 있는 경우도 가끔 있습니다.  
  
 `Short`의 기본값은 0입니다.  
  
## 프로그래밍 팁  
  
-   **확대 변환.** `Short` 데이터 형식은 `Integer`, `Long`, `Decimal`, `Single` 또는 `Double`로 확대 변환됩니다.  이것은 <xref:System.OverflowException?displayProperty=fullName> 오류의 발생 없이 `Short`를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.  
  
-   **형식 문자.** 리터럴 형식 문자 `S`를 리터럴에 추가하면 `Short` 데이터 형식이 됩니다.  `Short`에는 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Int16?displayProperty=fullName> 구조체입니다.  
  
## 참고 항목  
 <xref:System.Int16?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)