---
title: SByte 데이터 형식(Visual Basic)
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20a5a9182da50345f97331e6f01e0e3665a2a61c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591423"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte 데이터 형식 (Visual Basic)

부호 있는 8 비트 (1 바이트) 정수 값 범위에 있는-128에서 127 까지의 저장 합니다.  
  
## <a name="remarks"></a>설명

사용 하 여는 `SByte` 의 데이터를 전체 너비가 필요 하지 않은 정수 값을 포함 하는 데이터 형식을 `Integer` 의 절반 데이터 너비 또는 `Short`합니다. 경우에 따라 공용 언어 런타임 압축할 수 있습니다 프로그램 `SByte` 변수 긴밀 한 협력을 및 메모리 소비를 저장 합니다.

`SByte`의 기본값은 0입니다.

## <a name="literal-assignments"></a>리터럴 할당
  
선언 하 고 초기화는 `SByte` 10 진 리터럴, 16 진수 리터럴을 8 진수 리터럴을 할당 (부터는 Visual Basic 2017) 이진 리터럴 또는 변수입니다.

다음 예제에서는 정수 같지-102 10 진수, 16 진수로 표현 되는 및에 할당 된 이진 리터럴 `SByte` 값입니다. 이 예제에서는 사용 하 여 컴파일하는 `/removeintchecks` 컴파일러 스위치입니다.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> 접두사를 사용 `&h` 또는 `&H` 를 나타내는 16 진수 리터럴을, 접두사 `&b` 또는 `&B` 이진 리터럴와 접두사를 나타내기 위해 `&o` 또는 `&O` 8 진수 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017 부터는 사용할 수도 있습니다는 밑줄 문자 `_`, 가독성을 향상 시키기 위해 숫자 구분 기호,으로 다음 예제와 같이 보여 줍니다.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

Visual Basic 15.5 부터는 사용할 수도 있습니다는 밑줄 문자 (`_`)는 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 합니다. 예를 들어:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

정수 리터럴이 `SByte` 범위를 벗어나는 경우(즉 <xref:System.SByte.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.SByte.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다. 정수 리터럴 접미사가 없는 [정수](integer-data-type.md) 유추 됩니다. 정수 리터럴이의 범위를 벗어나는 경우는 `Integer` 종류는 [긴](long-data-type.md) 유추 됩니다. 즉, 이전 예제에서는 숫자 리터럴 `0x9A` 및 `0b10011010` 초과 하는 값의 156, 32 비트 부호 있는 정수로 해석 <xref:System.SByte.MaxValue?displayProperty=nameWithType>합니다. 성공적으로 10 진수가 아닌 정수를 할당 하는 다음과 같은 코드를 컴파일하려면는 `SByte`, 다음 중 하나를 수행할 수 있습니다.

- 사용 하 여 컴파일하면 정수 범위 검사를 사용 하지 않도록 설정 된 `/removeintchecks` 컴파일러 스위치입니다.

- 사용 하 여 한 [형식 문자](../../programming-guide\language-features\data-types/type-characters.md) 을 할당할 리터럴 값을 명시적으로 정의 하는 `SByte`합니다. 다음 예제에서는 할당 음수 리터럴 `Short` 값을 `SByte`합니다. 유의 음수에 대 한, 숫자 리터럴 상위 단어의 상위 비트를 설정 해야 합니다. 이 예제의 경우이 비트 리터럴 15 `Short` 값입니다.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>프로그래밍 팁
  
-   **CLS 규격입니다.** `SByte` 데이터 형식이 아니므로의 일부가 [공용 언어 사양](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), 지므로 CLS 규격 코드를 사용 하는 구성 요소를 사용할 수 없습니다.

-   **확대 합니다.** `SByte` 데이터 형식으로 확대 되 `Short`, `Integer`, `Long`, `Decimal`, `Single`, 및 `Double`합니다. 즉, 변환할 수 `SByte` 발생 없이 이러한 유형 중 하나로 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.
  
-   **형식 문자입니다.** `SByte` 에 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.SByte?displayProperty=nameWithType> 구조체입니다.
  
## <a name="see-also"></a>참고자료

 <xref:System.SByte?displayProperty=nameWithType>  
 [데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Short 데이터 형식](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [Integer 데이터 형식](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Long 데이터 형식](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
