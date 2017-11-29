---
title: "ULong 데이터 형식(Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afc52bfd16541feed599d5445adad7aba04f8e9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ulong-data-type-visual-basic"></a>ULong 데이터 형식 (Visual Basic)

값은 0에서 18446744073709551615 까지의 부호 없는 64 비트 (8 바이트) 정수를 포함 (1.84 이상 10 ^19).  
  
## <a name="remarks"></a>설명

사용 하 여는 `ULong` 데이터 형식에 대해 너무 큰 이진 데이터를 포함 하도록 `UInteger`, 가장 큰 부호 없는 정수 값 또는 합니다.  
  
`ULong`의 기본값은 0입니다.

## <a name="literal-assignments"></a>리터럴 할당

선언 하 고 초기화는 `ULong` 10 진 리터럴, 16 진수 리터럴을 8 진수 리터럴을 할당 (부터는 Visual Basic 2017) 이진 리터럴 또는 변수입니다. 정수 리터럴이 `ULong` 범위를 벗어나는 경우(즉 <xref:System.UInt64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.

다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 7,934,076,125와 같은 정수가 `ULong` 값에 할당됩니다.
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> 접두사를 사용 `&h` 또는 `&H` 를 나타내는 16 진수 리터럴을, 접두사 `&b` 또는 `&B` 이진 리터럴와 접두사를 나타내기 위해 `&o` 또는 `&O` 8 진수 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017 부터는 사용할 수도 있습니다는 밑줄 문자 `_`, 가독성을 향상 시키기 위해 숫자 구분 기호,으로 다음 예제와 같이 보여 줍니다.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

숫자 리터럴을 포함할 수는 `UL` 또는 `ul` [형식 문자](../../programming-guide\language-features\data-types/type-characters.md) 를 표시 하는 `ULong` 다음 예제와 같이 데이터 형식입니다.

```vb
Dim number = &H00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>프로그래밍 팁
  
-   **음수입니다.** 때문에 `ULong` 부호 없는 정수 형식이 면 음수를 나타낼 수 없습니다. 단항 빼기를 사용 하는 경우 (`-`) 형식으로 계산 되는 식에 연산자 `ULong`, Visual Basic 식을 변환 `Decimal` 첫 번째입니다.  
  
-   **CLS 규격입니다.** `ULong` 데이터 형식이 아니므로의 일부가 [공용 언어 사양](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), 지므로 CLS 규격 코드를 사용 하는 구성 요소를 사용할 수 없습니다.  
  
-   **Interop 고려 사항입니다.** Automation 또는 COM 개체를 위한.NET Framework에 대해 작성 되지 않은 구성 요소와 상호 작용 하는 경우 유의 같은 형식은 `ulong` 다른 환경에서 다른 데이터 너비 (32 비트)를 가질 수 있습니다. 이러한 구성 요소를 32 비트 인수를 전달 하는 경우로 선언 `UInteger` 대신 `ULong` 관리 되는 Visual Basic 코드에서.  
  
     또한 자동화는 Windows 95, Windows 98, Windows ME 또는 Windows 2000에서 64 비트 정수를 지원 하지 않습니다. Visual Basic을 전달할 수 없으며 `ULong` 이러한 플랫폼에서 자동화 구성 요소에 대 한 인수입니다.  
  
-   **확대 합니다.** `ULong` 데이터 형식으로 확대 되 `Decimal`, `Single`, 및 `Double`합니다. 즉, 변환할 수 `ULong` 발생 없이 이러한 유형 중 하나로 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.  
  
-   **형식 문자입니다.** 리터럴 형식 문자를 추가 `UL` 리터럴에 리터럴에 `ULong` 데이터 형식입니다. `ULong`에 식별자 형식 문자가 없습니다.
  
-   **Framework 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.UInt64?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="see-also"></a>참고 항목

 <xref:System.UInt64>  
 [데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [방법: 부호 없는 형식을 사용하는 Windows 함수 호출](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
