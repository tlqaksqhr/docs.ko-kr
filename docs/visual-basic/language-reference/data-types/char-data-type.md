---
title: "Char Data Type (Visual Basic) | Microsoft Docs"
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
  - "vb.Char"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "literal type characters, C"
  - "Char data type"
  - "C literal type character"
  - "data types [Visual Basic], assigning"
  - "Char data type, character literals"
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Char Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

0에서 255까지의 값 범위에 있는 부호 없는 16비트\(2바이트\) 코드 포인트를 저장합니다.  각 *코드 포인트* 또는 문자 코드는 단일 유니코드 문자를 나타냅니다.  
  
## 설명  
 단일 문자만 저장해야 할 경우에는 `Char` 데이터 형식을 사용하십시오. `String`의 오버헤드가 필요 없습니다.  경우에 따라 `Char` 요소의 배열인 `Char()`를 사용하여 여러 문자를 저장할 수도 있습니다.  
  
 `Char`의 기본값은 코드 포인트가 0인 문자입니다.  
  
## 유니코드 문자  
 유니코드의 처음 128개 코드 포인트\(0–127\)는 미국 표준 키보드의 문자와 기호에 해당합니다.  키보드.  이러한 128개 코드 포인트는 ASCII 문자 집합에 정의된 것과 동일합니다.  그 다음 128개 코드 포인트\(128–255\)는 특수 문자\(예: 라틴 계열의 영문자, 악센트, 통화 기호, 분수 등\)를 나타냅니다.  나머지 코드 포인트\(256\-65535\)들은 전 세계의 텍스트 문자, 분음 부호, 수학 기호, 기술 기호 등과 같은 다양한 기호를 나타내는 데 사용됩니다.  
  
 `Char` 변수의 <xref:System.Char.IsDigit%2A> 및 <xref:System.Char.IsPunctuation%2A> 같은 메서드를 사용하여 유니코드 분류를 확인할 수 있습니다.  
  
## 형식 변환  
 Visual Basic에서는 `Char` 형식과 숫자 형식을 직접 변환할 수 없습니다.  <xref:Microsoft.VisualBasic.Strings.Asc%2A> 또는 <xref:Microsoft.VisualBasic.Strings.AscW%2A> 함수를 사용하여 `Char` 값을 해당 코드 포인트를 나타내는 `Integer`로 변환할 수 있습니다.  <xref:Microsoft.VisualBasic.Strings.Chr%2A> 또는 <xref:Microsoft.VisualBasic.Strings.ChrW%2A> 함수를 사용하면 `Integer` 값을 해당 코드 포인트를 갖는 `Char`로 변환할 수 있습니다.  
  
 형식 검사 스위치\([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)\)가 설정되어 있으면 리터럴 형식 문자를 단일 문자 문자열 리터럴에 추가하여 `Char` 데이터 형식으로 나타내야 합니다.  다음은 이에 대한 예입니다.  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## 프로그래밍 팁  
  
-   **음수.** `Char`는 부호 없는 형식이므로 음수 값을 나타낼 수 없습니다.  어떤 경우이든 `Char`에 숫자 값을 지정할 수는 없습니다.  
  
-   **Interop 고려 사항.** Automation 또는 COM 개체와 같이 .NET Framework용으로 작성되지 않은 구성 요소를 사용하는 경우 다른 환경에서는 문자 형식의 데이터 너비\(8비트\)가 다르다는 것을 염두에 두고 있어야 합니다.  그러한 구성 요소에 8비트 인수를 전달하는 경우 새 Visual Basic 코드에서 이 인수를 `Char` 대신 `Byte`로 선언하십시오.  
  
-   **확대 변환.** `Char` 데이터 형식은 `String`로 확대 변환됩니다.  이것은 <xref:System.OverflowException?displayProperty=fullName> 오류의 발생 없이 `Char`를 `String`으로 변환할 수 있음을 의미합니다.  
  
-   **형식 문자.** 리터럴 형식 문자 `C`를 단일 문자 문자열 리터럴에 추가하면 `Char` 데이터 형식이 됩니다.  `Char`에는 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.Char?displayProperty=fullName> 구조체입니다.  
  
## 참고 항목  
 <xref:System.Char?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)