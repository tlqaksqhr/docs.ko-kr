---
title: "String Data Type (Visual Basic) | Microsoft Docs"
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
  - "vb.String"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "strings [Visual Basic], character"
  - "strings [Visual Basic], fixed-length"
  - "string keyword [Visual Basic]"
  - "fixed-length strings, string data type"
  - "literals, string"
  - "text [Visual Basic], String data type"
  - "$ identifier type character"
  - "String data type"
  - "fixed-length strings"
  - "string literals"
  - "data types [Visual Basic], assigning"
  - "" String literals"
  - "identifier type characters, $"
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# String Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

0에서 255까지의 값 범위에 있는 부호 없는 16비트\(2바이트\) 코드 포인트의 시퀀스를 저장합니다.  각 *코드 포인트* 또는 문자 코드는 단일 유니코드 문자를 나타냅니다.  String의 길이는 유니코드 문자로 0개에서 약 20억\(2^31\)개까지 가능합니다.  
  
## 설명  
 `String` 데이터 형식을 사용하면 `Char` 요소의 배열인 `Char()`의 배열 관리 오버헤드 없이 여러 문자를 저장할 수 있습니다.  
  
 `String`의 기본값은 `Nothing`\(null 참조\)입니다.  이 값은 빈 문자열\(값 `""`\)과 다릅니다.  
  
## 유니코드 문자  
 유니코드의 처음 128개 코드 포인트\(0–127\)는 미국 표준 키보드의 문자와 기호에 해당합니다.  키보드.  이러한 128개 코드 포인트는 ASCII 문자 집합에 정의된 것과 동일합니다.  그 다음 128개 코드 포인트\(128–255\)는 특수 문자\(예: 라틴 계열의 영문자, 악센트, 통화 기호, 분수 등\)를 나타냅니다.  유니코드에서는 다양한 기호에 대해 나머지 코드 포인트\(256\-65535\)를 사용합니다.  여기에는 전 세계의 텍스트 문자, 분음 부호 및 수학\/기술 기호가 포함됩니다.  
  
 `String` 변수의 개별 문자에서 <xref:System.Char.IsDigit%2A> 및 <xref:System.Char.IsPunctuation%2A>과 같은 메서드를 사용하여 유니코드 분류를 확인할 수 있습니다.  
  
## 형식 요구 사항  
 `String` 리터럴은 따옴표\(`" "`\)로 묶어야 합니다.  따옴표를 문자열의 문자 중 하나로 사용하려면 두 개의 따옴표를 연속해서 사용해야 합니다\(`""`\).  다음은 이에 대한 예입니다.  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 문자열의 따옴표를 나타내는 연속하는 따옴표는 `String` 리터럴을 시작하고 끝내는 따옴표와 별개입니다.  
  
## 문자열 조작  
 `String` 변수에 문자열을 할당하면 해당 문자열은 *변경할 수 없으므로* 길이 또는 내용을 변경할 수 없습니다.  어떤 방법으로든 문자열을 변경하면 Visual Basic에 새 문자열이 만들어지고 이전 문자열은 사용되지 않습니다.  `String` 변수는 새 문자열을 가리킵니다.  
  
 다양한 문자열 함수를 사용하여 `String` 변수의 내용을 조작할 수 있습니다.  다음 예제에서는 <xref:Microsoft.VisualBasic.Strings.Left%2A> 함수를 보여 줍니다.  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 다른 구성 요소에서 만든 문자열에 선행 공백 또는 후행 공백이 채워질 수 있습니다.  그런 문자열이 표시되면 <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A> 및 <xref:Microsoft.VisualBasic.Strings.RTrim%2A> 함수를 사용하여 해당 공백을 제거할 수 있습니다.  
  
 문자열 조작에 대한 자세한 내용은 [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md)을 참조하십시오.  
  
## 프로그래밍 팁  
  
-   **음수.** `String`의 문자는 부호 없는 문자이므로 음의 값을 나타낼 수 없습니다.  어떤 경우이든 `String`에 숫자 값을 지정할 수는 없습니다.  
  
-   **Interop 고려 사항.** Automation 또는 COM 개체와 같이 .NET Framework용으로 작성되지 않은 구성 요소를 사용하는 경우 다른 환경에서는 문자열의 데이터 너비\(8비트\)가 다르다는 것을 염두에 두고 있어야 합니다.  이러한 구성 요소에 8비트 문자의 문자열 인수를 전달하는 경우 새 Visual Basic 코드에서 이 인수를 `String` 대신 `Byte` 요소의 배열인 `Byte()`로 선언하십시오.  
  
-   **형식 문자.** 식별자 형식 문자 `$`을 식별자에 추가하면 `String` 데이터 형식이 됩니다.  `String`에는 리터럴 형식 문자가 없습니다.  그러나 컴파일러는 큰따옴표\(`" "`\)로 묶인 리터럴을 `String`으로 간주합니다.  
  
-   **Framework 형식.** .NET Framework에서 해당하는 형식은 <xref:System.String?displayProperty=fullName> 클래스입니다.  
  
## 참고 항목  
 <xref:System.String?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Char Data Type](../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)