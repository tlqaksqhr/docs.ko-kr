---
title: Char 데이터 형식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: e672402535215ca30d19cc480e39b42b0364f137
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590818"
---
# <a name="char-data-type-visual-basic"></a>Char 데이터 형식(Visual Basic)
값은 0에서 65535 까지의 부호 없는 16 비트 (2 바이트) 코드 포인트를 저장 합니다. 각 *코드 포인트*, 또는 문자 코드 단일 유니코드 문자를 나타냅니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여는 `Char` 하나만 포함 해야 하는 경우 데이터 형식 및 오버 헤드가 필요 하지 않는 문자 `String`합니다. 일부 경우에 사용할 수 있습니다 `Char()`, 배열을 `Char` 여러 문자를 저장할 요소입니다.  
  
 기본값 `Char` 0의 코드 포인트와 문자입니다.  
  
## <a name="unicode-characters"></a>유니코드 문자  
 유니코드는 첫 번째 128 개 코드 포인트 (0-127) 문자와 기호 미국 표준 키보드에 매핑됩니다. 이러한 128 개 코드 포인트는 ASCII 문자 집합에 정의 된 것과 동일 합니다. 두 번째 128 개 코드 포인트 (128-255) 라틴어 기반 알파벳 글자, 악센트, 통화 기호 및 조각 등의 특수 문자를 나타냅니다. 유니코드에 대 한 기호를 전 세계의 텍스트 문자, 분음 기호, 수학 및 기술 기호 등의 다양 한 나머지 코드 포인트 (256-65535)를 사용 합니다.  
  
 와 같은 메서드를 사용할 수 있습니다 <xref:System.Char.IsDigit%2A> 및 <xref:System.Char.IsPunctuation%2A> 에 `Char` 변수를 유니코드 분류를 결정 합니다.  
  
## <a name="type-conversions"></a>형식 변환  
 Visual Basic 사이 직접 변환 되지 않습니다. `Char` 및 숫자 형식입니다. 사용할 수는 <xref:Microsoft.VisualBasic.Strings.Asc%2A> 또는 <xref:Microsoft.VisualBasic.Strings.AscW%2A> 변환 하는 함수는 `Char` 값을 `Integer` 해당 코드 포인트를 나타내는입니다. 사용할 수 있습니다는 <xref:Microsoft.VisualBasic.Strings.Chr%2A> 또는 <xref:Microsoft.VisualBasic.Strings.ChrW%2A> 변환 하는 함수는 `Integer` 값을 `Char` 있는 코드 포인트입니다.  
  
 형식 검사 스위치 하는 경우 ([Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md))를로 식별 하기 리터럴 단일 문자 문자열 리터럴 형식 문자를 추가 해야이 설정의 `Char` 데이터 형식입니다. 다음은 이에 대한 예입니다.  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a>프로그래밍 팁  
  
-   **음수입니다.** `Char` 부호 없는 형식 및 음수 값을 나타낼 수 없습니다. 사용 하지 않아야 어떤 경우 든, `Char` 숫자 값을 저장 합니다.  
  
-   **Interop 고려 사항입니다.** .NET Framework에 대해 작성 되지 않은 구성 요소와 인터페이스 하는 경우 예제 Automation 또는 COM 개체에 대 한 기억 문자 형식을 다른 데이터 너비 (8 비트) 한지 다른 환경에서 합니다. 이러한 구성 요소에는 8 비트 인수를 전달 하는 경우로 선언 `Byte` 대신 `Char` 새 Visual Basic 코드에서.  
  
-   **확대 합니다.** `Char` 데이터 형식으로 확대 되 `String`합니다. 즉, 변환할 수 `Char` 를 `String` 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.  
  
-   **형식 문자입니다.** 리터럴 형식 문자 추가 `C` 를 단일 문자 문자열 리터럴에 `Char` 데이터 형식입니다. `Char` 에 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.Char?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Char?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [String 데이터 형식](../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [방법: 부호 없는 형식을 사용하는 Windows 함수 호출](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
