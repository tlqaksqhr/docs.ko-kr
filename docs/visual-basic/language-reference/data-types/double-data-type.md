---
title: "Double Data Type (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Double"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "identifier type characters, #"
  - "trailing zeros"
  - "real numbers"
  - "trailing 0 characters"
  - "0 characters, trailing"
  - "literal type characters, R"
  - "data types [Visual Basic], assigning"
  - "Double data type [Visual Basic]"
  - "# identifier type character"
  - "double-precision numbers"
  - "floating-point numbers, Double data type"
  - "R literal type character"
  - "zeros, trailing"
  - "Double data type"
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
caps.latest.revision: 25
caps.handback.revision: 25
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Double Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

값의 범위가 \-1.79769313486231570E\+308에서 \-4.94065645841246544E\-324까지\(음수\) 또는 4.94065645841246544E\-324에서 1.79769313486231570E\+308까지\(양수\)인 부호 있는 IEEE 64비트\(8바이트\) 배정밀도 부동 소수점 숫자를 저장합니다.  배정밀도 숫자는 실수의 근사값을 저장합니다.  
  
## 설명  
 `Double` 데이터 형식은 크기가 가장 큰 숫자와 가장 작은 숫자를 제공합니다.  
  
 `Double`의 기본값은 0입니다.  
  
## 프로그래밍 팁  
  
-   **정밀도.** 부동 소수점 숫자에 대한 작업을 수행하는 경우 해당 숫자가 메모리에서 항상 정확하게 표현되지 않는다는 점에 주의합니다.  따라서 값 비교, `Mod` 연산자 등과 같은 특정 연산에서 예기치 않은 결과가 나타날 수 있습니다.  자세한 내용은 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)를 참조하십시오.  
  
-   **뒤에 오는 0.** 부동 소수점 데이터 형식에는 후행 0 문자에 대한 내부 표현이 없습니다.  예를 들어, 4.2000과 4.2를 구분하지 않습니다.  따라서 부동 소수점 값을 표시하거나 인쇄할 때 후행 0 문자는 나타나지 않습니다.  
  
-   **형식 문자.** 리터럴 형식 문자 `R`를 리터럴에 추가하면 `Double` 데이터 형식이 됩니다.  예를 들어 정수 값 뒤에 `R`이 있으면 이 값은 `Double`로 바뀝니다.  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     식별자 형식 문자 `#`을 식별자에 추가하면 `Double`가 됩니다.  다음 예제에서 변수 `num`은 `Double`로 형식이 지정됩니다.  
  
    ```  
    Dim num# = 3  
    ```  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Double?displayProperty=fullName> 구조체입니다.  
  
## 참고 항목  
 <xref:System.Double?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Decimal Data Type](../../../visual-basic/language-reference/data-types/decimal-data-type.md)   
 [Single Data Type](../../../visual-basic/language-reference/data-types/single-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)