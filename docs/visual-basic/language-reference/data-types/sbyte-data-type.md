---
title: "SByte Data Type (Visual Basic) | Microsoft Docs"
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
  - "vb.sbyte"
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
  - "SByte data type"
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# SByte Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

\-128에서 127까지의 값 범위에 있는 부호 있는 8비트\(1바이트\) 정수를 저장합니다.  
  
## 설명  
 `Integer`의 전체 데이터 너비가 필요하지 않거나 `Short`의 데이터 너비가 반 만큼도 필요하지 않은 정수 값을 포함하려면 `SByte` 데이터 형식을 사용합니다.  공용 언어 런타임에서 `SByte` 변수를 조밀하게 압축하여 메모리 사용량을 줄일 수 있는 경우도 가끔 있습니다.  
  
 `SByte`의 기본값은 0입니다.  
  
## 프로그래밍 팁  
  
-   **CLS 규격.** `SByte` 데이터 형식은 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\)에 포함되어 있지 않으므로 CLS 규격 코드에서는 이 데이터 형식을 사용하는 구성 요소를 사용할 수 없습니다.  
  
-   **확대 변환.** `SByte` 데이터 형식은 `Short`, `Integer`, `Long`, `Decimal`, `Single` 및 `Double`로 확대 변환됩니다.  이것은 <xref:System.OverflowException?displayProperty=fullName> 오류의 발생 없이 `SByte`를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.  
  
-   **형식 문자.** `SByte`에는 리터럴 형식 문자나 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.SByte?displayProperty=fullName> 구조체입니다.  
  
## 참고 항목  
 <xref:System.SByte?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)   
 [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)