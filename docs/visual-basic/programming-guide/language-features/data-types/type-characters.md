---
title: 형식 문자(Visual Basic)
ms.date: 01/31/2018
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9262c57c5773b947f18fd9e8cf9087bb8e02de7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="type-characters-visual-basic"></a>입력 문자 (Visual Basic)

를 선언문의 데이터 형식을 지정 하는 것 외에도 데이터 형식을 사용 하 여 몇 가지 프로그래밍 요소의 강제로 실행할 수는 *형식 문자*합니다. 형식 문자 어떤 종류의 중간 문자가 없는 요소를 다음에 나와야 합니다.

형식 문자 요소 이름의 일부가 아닙니다. 형식 문자 없이 형식 문자를 정의 된 요소를 참조할 수 있습니다.

## <a name="identifier-type-characters"></a>식별자 형식 문자

집합을 제공 하는 Visual Basic *식별자 형식 문자* 데이터 형식의 변수 또는 상수를 지정 하는 선언에서 사용할 수 있습니다. 다음 표에서 사용 예제를 사용할 수 있는 식별자 형식 문자를 보여 줍니다.
  
|식별자 형식 문자|데이터 형식|예제|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 식별자 형식 문자가 없습니다는 `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, 또는 `UShort` 데이터 형식 또는 배열 또는 구조체와 같은 복합 데이터 형식입니다.

일부 경우에 추가할 수는 `$` Visual Basic 함수 예를 들어 문자 `Left$` 대신 `Left`형식의 반환된 값을 얻기 위해 `String`합니다.

모든 경우에 식별자 형식 문자 바로 뒤에 붙여야 식별자 이름입니다.

## <a name="literal-type-characters"></a>리터럴 형식 문자

A *리터럴* 데이터 형식의 특정 값의 텍스트 표현입니다.  

### <a name="default-literal-types"></a>기본 리터럴 형식

리터럴 형태가 일반적으로 코드에 표시 된 대로 해당 데이터 형식을 결정 합니다. 다음 표에서 이러한 기본 유형을 보여 줍니다.  
  
|리터럴 텍스트 형식|기본 데이터 형식|예제|  
|-----------------------------|-----------------------|-------------|  
|숫자, 더 소수 부분|`Integer`|`2147483647`|  
|너무 커서 숫자, 더 소수 부분 `Integer`|`Long`|`2147483648`|  
|숫자, 소수 부분|`Double`|`1.2`|  
|큰따옴표로 묶인|`String`|`"A"`|  
|숫자 기호 사이 포함 된|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a>강제 리터럴 형식

집합을 제공 하는 Visual Basic *리터럴 형식 문자*, 리터럴을 이외의 데이터 형식을 형태로 취하도록을 강제 적용 하는 데 사용할 수를 나타냅니다. 리터럴의 끝에 문자를 추가 하 여이 작업을 수행 합니다. 다음 표에서 사용 예제를 사용할 수 있는 리터럴 형식 문자를 보여 줍니다.
  
|리터럴 형식 문자|데이터 형식|예제|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

리터럴 형식 문자가 없습니다는 `Boolean`, `Byte`, `Date`, `Object`, `SByte`, 또는 `String` 데이터 형식 또는 배열 또는 구조체와 같은 복합 데이터 형식에 대 한 합니다.

리터럴 식별자 형식 문자를 사용할 수도 있습니다 (`%`, `&`, `@`, `!`, `#`, `$`), 변수, 상수, 및 식 처럼 합니다. 그러나 리터럴 형식 문자 (`S`, `I`, `L`, `D`, `F`, `R`, `C`) 리터럴 에서만 사용할 수 있습니다.

모든 경우에 리터럴 형식 문자 바로 뒤에 붙여야 리터럴 값입니다.

## <a name="hexadecimal-binary-and-octal-literals"></a>16 진수, 이진 및 8 진수 리터럴

컴파일러는 일반적으로 10 진수 (밑수 10) 번호 시스템에는 정수 리터럴로 해석 합니다. 과 함께 16 진수 (밑수 16) 숫자로 정수 리터럴을 정의할 수도 있습니다는 `&H` 접두사를 포함 하 여 이진 (밑 2) 숫자로 `&B` 접두사는 8 진수 8으로 번호를 `&O` 접두사 합니다. 접두사 뒤의 숫자는 체계에 적합 해야 합니다. 다음 표에서이 보여 줍니다.  
  
|기 수|접두사|유효한 숫자 값|예제|
|-----------------|------------|------------------------|-------------|
|16진수|`&H`|0-9 및 A-F|`&HFFFF`|
|이진 (밑 2)|`&B`|0-1|`&B01111100`|
|8진수|`&O`|0-7|`&O77`|

Visual Basic 2017 년부터 밑줄만 사용할 수 있습니다 (`_`) 정수 계열 리터럴의 가독성 향상을 위해 그룹 구분 기호로 합니다. 사용 하 여 다음 예제는 `_` 문자 리터럴 이진 8 비트 그룹으로 그룹화입니다.

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

접두사가 붙은 리터럴 형식 문자 리터럴을 따를 수 있습니다. 다음 예제에서는이 보여 줍니다.

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

이전 예에서 `counter` -32768 10 진수 값 및 `flags` 에 10 진수 값 + 32768을 갖습니다.

Visual Basic 15.5 부터는 사용할 수도 있습니다는 밑줄 문자 (`_`)는 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 합니다. 예를 들어:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a>참고 항목

 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
