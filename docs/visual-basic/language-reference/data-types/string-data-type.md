---
title: "String 데이터 형식 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.String
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings, string data type
- literals, string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals
- data types [Visual Basic], assigning
- String literals
- identifier type characters, $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9221a89a1fb46609b4b8550968e3a2bbe874772c
ms.lasthandoff: 03/13/2017

---
# <a name="string-data-type-visual-basic"></a>String 데이터 형식(Visual Basic)
0에서 65535 사이의 값에 부호 없는 16 비트 (2 바이트) 코드 포인트의 시퀀스를 범위에 저장 합니다. 각 *코드 포인트*, 또는 문자 코드를 단일 유니코드 문자를 나타냅니다. 문자열로 약 2 십억 0에서 사용할 수 있습니다 (2 ^31) 유니코드 문자입니다.  
  
## <a name="remarks"></a>주의  
 사용 하는 `String` 배열 관리 오버 헤드 없이 여러 문자를 저장할 데이터 형식을 `Char()`, 배열을 `Char` 요소입니다.  
  
 기본값 `String` 는 `Nothing` (null 참조). 이 하지 빈 문자열과 같은 (값 `""`).  
  
## <a name="unicode-characters"></a>유니코드 문자  
 유니코드의 처음 128 개 코드 포인트 (0-127) 문자와 기호 미국 표준 키보드에에 해당합니다. 이러한 128 개 코드 포인트는 ASCII 문자 집합에 정의 된 것과 동일 합니다. 두 번째 128 개 코드 포인트 (128-255)는 라틴 문자 기반의 영문자, 악센트, 통화 기호 및 소수 등의 특수 문자를 나타냅니다. 유니코드는 다양 한 기호에 대 한 나머지 코드 포인트 (256-65535)를 사용합니다. 전 세계의 텍스트 문자, 분음 부호, 및 수학 및 공학 기호 포함 됩니다.  
  
 와 같은 메서드를 사용할 수 <xref:System.Char.IsDigit%2A>및 <xref:System.Char.IsPunctuation%2A>의 개별 문자에는 `String` 유니코드 분류를 확인 하는 변수.</xref:System.Char.IsPunctuation%2A> </xref:System.Char.IsDigit%2A>  
  
## <a name="format-requirements"></a>형식 요구 사항  
 묶어야는 `String` 리터럴은 따옴표 (`" "`). 두 개의 연속 된 따옴표를 사용 하는 인용 부호 문자열의 문자 중 하나로 포함 해야 합니다 (`""`). 다음은 이에 대한 예입니다.  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 문자열에 인용 부호를 나타내는 연속 따옴표는 독립적으로 시작 및 종료 되는 따옴표는 `String` 리터럴.  
  
## <a name="string-manipulations"></a>문자열 조작  
 에 대 한 문자열을 할당 하면는 `String` 변수를 해당 문자열은 *변경할 수 없는*, 길이 또는 내용을 변경할 수 없습니다 것입니다. 어떤 방식으로 문자열을 변경 하는 경우 Visual Basic 새 문자열을 만들고 이전을 중단 합니다. `String` 변수는 다음 새 문자열을 가리킵니다.  
  
 내용을 조작할 수는 `String` 다양 한 문자열 함수를 사용 하 여 변수입니다. 다음 예제에서는 <xref:Microsoft.VisualBasic.Strings.Left%2A>함수</xref:Microsoft.VisualBasic.Strings.Left%2A> 를 보여 줍니다.  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 다른 구성 요소에서 만든 문자열 선행 또는 후행 공백을 채워질 수 있습니다. 이러한 문자열을 받은 경우 사용할 수 있습니다는 <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, 및 <xref:Microsoft.VisualBasic.Strings.RTrim%2A>이러한 공백을 제거 하는 함수입니다.</xref:Microsoft.VisualBasic.Strings.RTrim%2A> </xref:Microsoft.VisualBasic.Strings.LTrim%2A> </xref:Microsoft.VisualBasic.Strings.Trim%2A>  
  
 문자열 조작에 대 한 자세한 내용은 참조 [문자열](../../../visual-basic/programming-guide/language-features/strings/index.md)합니다.  
  
## <a name="programming-tips"></a>프로그래밍 팁  
  
-   **음수입니다.** 보유 하는 문자 기억 `String` 서명 되지 않은 및 음수 값을 나타낼 수 없습니다. 어떤 경우 든 사용해 서는 안 `String` 숫자 값을 저장 합니다.  
  
-   **Interop 고려 사항입니다.** .NET Framework에 대해 작성 되지 않은 구성 요소와 상호 작용 하는 경우 예제 Automation 또는 COM 개체에 대 한 있다는 점을 기억해 문자열 문자 서로 다른 데이터 너비 (8 비트)를 다른 환경에서. 이러한 구성 요소에는 8 비트 문자는 문자열 인수를 전달 하는 경우로 선언 `Byte()`, 배열을 `Byte` 요소 대신 `String` 새 Visual Basic 코드에서.  
  
-   **형식 문자입니다.** 식별자 형식 문자 추가 `$` 를 식별자에 리터럴에 `String` 데이터 형식입니다. `String`에 리터럴 형식 문자가 없습니다. 컴파일러는 따옴표로 묶인 리터럴을 처리 하는 반면 (`" "`)으로 `String`합니다.  
  
-   **Framework 형식입니다.** .NET Framework에 있는 해당 형식이 <xref:System.String?displayProperty=fullName>클래스가 있습니다.</xref:System.String?displayProperty=fullName>  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.String?displayProperty=fullName></xref:System.String?displayProperty=fullName>   
 [데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Char 데이터 형식](../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [방법: 부호 없는 형식을 사용 하는 Windows 함수 호출](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

