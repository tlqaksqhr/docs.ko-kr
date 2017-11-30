---
title: "Byte 데이터 형식(Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6475ff3ed905abb022a9ef60204c04b45130ae22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="byte-data-type-visual-basic"></a>Byte 데이터 형식 (Visual Basic)
값 범위에 있는 0에서 255 까지의 부호 없는 8 비트 (1 바이트) 정수를 보유 합니다.

## <a name="remarks"></a>설명

사용 하 여는 `Byte` 이진 데이터를 포함 하도록 데이터 형식입니다.  
  
`Byte`의 기본값은 0입니다.

## <a name="literal-assignments"></a>리터럴 할당

선언 하 고 초기화는 `Byte` 10 진 리터럴, 16 진수 리터럴을 8 진수 리터럴을 할당 (부터는 Visual Basic 2017) 이진 리터럴 또는 변수입니다. 정수 리터럴은의 범위를 벗어나는 경우는 `Byte` (경우 즉, 보다 작은 <xref:System.Byte.MinValue?displayProperty=nameWithType> 보다 큰 <xref:System.Byte.MaxValue?displayProperty=nameWithType>), 컴파일 오류가 발생 합니다.

다음 예제에서는 정수 같지 10 진수, 16 진수로 표현 되는 201 및 이진 리터럴에서 암시적으로 변환 된 [정수](integer-data-type.md) 를 `byte` 값입니다.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> 접두사를 사용 `&h` 또는 `&H` 를 나타내는 16 진수 리터럴을, 접두사 `&b` 또는 `&B` 이진 리터럴와 접두사를 나타내기 위해 `&o` 또는 `&O` 8 진수 리터럴을 나타냅니다. 10진수 리터럴에는 접두사가 없습니다.

Visual Basic 2017 부터는 사용할 수도 있습니다는 밑줄 문자 `_`, 가독성을 향상 시키기 위해 숫자 구분 기호,으로 다음 예제와 같이 보여 줍니다.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

## <a name="programming-tips"></a>프로그래밍 팁

-   **음수입니다.** 때문에 `Byte` 부호 없는 정수 형식이 면 음수를 나타낼 수 없습니다. 단항 빼기를 사용 하는 경우 (`-`) 형식으로 계산 되는 식에 연산자 `Byte`, Visual Basic 식을 변환 `Short` 첫 번째입니다.
  
-   **형식 변환 합니다.** Visual Basic을 읽거나 파일을 작성 하는 경우 또는 Dll, 메서드 및 속성을 호출할 때 자동 데이터 형식 간에 변환할 수 있습니다. 에 저장 된 이진 데이터 `Byte` 변수 및 배열 그러한 형식 변환이 이루어지는 동안 보존 됩니다. 사용 하지 않아야는 `String` ANSI 및 유니코드 변환 시의 내용이 손상 될 수 때문에 이진 데이터에 대 한 변수입니다.

-   **확대 합니다.** `Byte` 데이터 형식으로 확대 되 `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, 또는 `Double`합니다. 즉, 변환할 수 `Byte` 발생 없이 이러한 유형 중 하나로 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.
  
-   **형식 문자입니다.** `Byte`에 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.

-   **Framework 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.Byte?displayProperty=nameWithType> 구조체입니다.

## <a name="example"></a>예제

 다음 예에서 `b` 는 `Byte` 변수입니다. 문을 변수의 범위와 비트 시프트 연산자의 응용 프로그램을 보여 줍니다.

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a>참고 항목

 <xref:System.Byte?displayProperty=nameWithType>  
 [데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
