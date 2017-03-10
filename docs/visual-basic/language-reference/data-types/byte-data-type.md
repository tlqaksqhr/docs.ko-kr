---
title: "Byte Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Byte"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Byte data type"
  - "data types [Visual Basic], assigning"
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Byte Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

0에서 255까지의 값 범위에 있는 부호 없는 8비트\(1바이트\) 정수를 저장합니다.  
  
## 설명  
 이진 데이터를 저장하려면 `Byte` 데이터 형식을 사용합니다.  
  
 `Byte`의 기본값은 0입니다.  
  
## 프로그래밍 팁  
  
-   **음수.** `Byte`는 부호 없는 형식이므로 음수를 나타낼 수 없습니다.  `Byte` 형식으로 계산되는 식에서 단항 마이너스\(`-`\) 연산자를 사용하면 Visual Basic은 먼저 식을 `Short`로 변환합니다.  
  
-   **형식 변환.** Visual Basic에서 파일을 읽거나 쓰는 경우 또는 DLL, 메서드 및 속성을 호출하는 경우 데이터 형식 간 변환이 자동으로 이루어질 수 있습니다.  `Byte` 변수와 배열에 저장된 이진 데이터는 그러한 형식 변환이 이루어지는 동안 보존됩니다.  ANSI와 유니코드 형식 사이에서 변환하는 동안 이진 데이터의 내용이 손상될 수도 있기 때문에 이진 데이터에 `String` 변수를 사용해서는 안 됩니다.  
  
-   **확대 변환.** `Byte` 데이터 형식은 `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single` 또는 `Double`로 확대 변환됩니다.  이것은 <xref:System.OverflowException?displayProperty=fullName> 오류의 발생 없이 `Byte`를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.  
  
-   **형식 문자.** `Byte`에는 리터럴 형식 문자나 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Byte?displayProperty=fullName> 구조체입니다.  
  
## 예제  
 다음 예제에서 `b`는 `Byte` 변수입니다.  예제의 문에서는 이 변수의 범위와 비트 시프트 연산자가 적용되는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/visualbasic/byte-data-type_1.vb)]  
  
## 참고 항목  
 <xref:System.Byte?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)