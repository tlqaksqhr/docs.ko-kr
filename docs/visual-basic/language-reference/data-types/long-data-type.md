---
title: "Long Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Long"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "identifier type characters, &"
  - "numbers, whole"
  - "whole numbers"
  - "integral data types"
  - "& identifier type character"
  - "integer numbers"
  - "literal type characters, L"
  - "numbers, integer"
  - "integers, data types"
  - "L literal type character"
  - "integers, types"
  - "Long keyword"
  - "data types [Visual Basic], integral"
  - "data types [Visual Basic], assigning"
  - "Long data type"
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Long Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

\-9,223,372,036,854,775,808에서 9,223,372,036,854,775,807\(9.2...E\+18\)까지 범위의 부호 있는 64비트\(8바이트\) 정수 값을 저장합니다.  
  
## 설명  
 너무 커서 `Integer` 데이터 형식으로 저장할 수 없는 정수에는 `Long` 데이터 형식을 사용합니다.  
  
 `Long`의 기본값은 0입니다.  
  
## 프로그래밍 팁  
  
-   **Interop 고려 사항.** Automation 또는 COM 개체와 같이 .NET Framework용으로 작성되지 않은 구성 요소를 사용하는 경우 다른 환경에서는 `Long`의 데이터 너비\(32비트\)가 다르다는 것을 염두에 두고 있어야 합니다.  그러한 구성 요소에 32비트 인수를 전달하는 경우 새 Visual Basic 코드에서 이 인수를 `Long` 대신 `Integer`로 선언하십시오.  
  
     또한 자동화는 Windows 95, Windows 98, Windows ME 또는 Windows 2000에서 64비트 정수를 지원하지 않습니다.  이러한 운영 체제에서 자동화 구성 요소에 Visual Basic `Long` 인수를 전달할 수 없습니다.  
  
-   **확대 변환.** `Long` 데이터 형식은 `Decimal`, `Single` 또는 `Double`로 확대 변환됩니다.  이것은 <xref:System.OverflowException?displayProperty=fullName> 오류의 발생 없이 `Long`을 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.  
  
-   **형식 문자.** 리터럴 형식 문자 `L`를 리터럴에 추가하면 `Long` 데이터 형식이 됩니다.  식별자 형식 문자 `&`을 식별자에 추가하면 `Long`가 됩니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Int64?displayProperty=fullName> 구조체입니다.  
  
## 참고 항목  
 <xref:System.Int64>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)