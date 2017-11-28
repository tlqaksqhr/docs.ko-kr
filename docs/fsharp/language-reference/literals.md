---
title: "리터럴(F#)"
description: "F # 프로그래밍 언어의 리터럴 형식에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4b1d6e9d-f933-4cd4-966d-d643152c27e4
ms.openlocfilehash: 6bb1f233b6846e226c4e73aee00b8cf77735fe2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="literals"></a>리터럴

> [!NOTE]
이 문서에서 API 참조 링크 이동 합니다 msdn (당분간).

이 항목에서는 F # 리터럴 형식을 지정 하는 방법을 보여 주는 표를 제공 합니다.

## <a name="literal-types"></a>리터럴 형식
다음 표에서 F #에서 리터럴 형식을 보여 줍니다. 16 진수 표기법으로 숫자를 나타내는 문자는 대/소문자 구분; 됩니다. 문자 형식을 식별 하는 대/소문자를 구분 하지 않습니다.

|형식|설명|접두사 또는 접미사|예제|
|----|-----------|----------------|--------|
|sbyte|부호 있는 8 비트 정수입니다.|y|`86y`<br /><br />`0b00000101y`|
|byte|부호 없는 8 비트 자연 수|uy|`86uy`<br /><br />`0b00000101uy`|
|int16|부호 있는 16 비트 정수입니다.|s|`86s`|
|uint16|부호 없는 16 비트 자연 수|us|`86us`|
|int<br /><br />int32|부호 있는 32 비트 정수입니다.|l 또는 없음|`86`<br /><br />`86l`|
|uint<br /><br />uint32|부호 없는 32 비트 자연 수|u 또는 u l|`86u`<br /><br />`86ul`|
|unativeint|부호 없는 자연 숫자로 네이티브 포인터입니다.|취소|`0x00002D3Fun`|
|int64|부호 있는 64 비트 정수입니다.|L|`86L`|
|uint64|부호 없는 64 비트 자연 수|UL|`86UL`|
|단일, float32|32 비트 부동 소수점 숫자|F 또는 f|`4.14F` 또는 `4.14f`|
|||lf|`0x00000000lf`|
|float이 고 double|64 비트 부동 소수점 숫자|없음|`4.14`, `2.3E+32` 또는 `2.3e+32`|
|||LF|`0x0000000000000000LF`|
|bigint|64 비트 표현에 제한 되지 않는 정수|I|`9999999999999999999999999999I`|
|decimal|고정된 소수점 또는 유리수도 표현 되는 소수|M 또는 m|`0.7833M` 또는 `0.7833m`|
|Char|유니코드 문자|없음|`'a'`|
|문자열|유니코드 문자열|없음|`"text\n"`<br /><br />또는<br /><br />`@"c:\filename"`<br /><br />또는<br /><br />`"""<book title="Paradise Lost">"""`<br /><br />또는<br /><br />`"string1" + "string2"`<br /><br />참고 항목 [문자열](Strings.md)합니다.|
|byte|ASCII 문자|B|`'a'B`|
|byte[]|ASCII 문자열|B|`"text"B`|
|String 또는 byte]|축 자 문자열|@ 접두사|`@"\\server\share"`(유니코드)<br /><br />`@"\\server\share"B`(ASCII)|

## <a name="remarks"></a>설명
유니코드 문자열에 명시적 인코딩을 사용 하 여 지정할 수 있는 포함 될 수 있습니다 `\u` 뒤에 16 비트 16 진수 코드 또는 utf-32 인코딩을 사용 하 여 지정할 수 있는 `\U` 뒤에 유니코드를 나타내는 32 비트 16 진수 코드 서로게이트 쌍입니다.

F # 3.1을 기준으로 사용할 수 있습니다는 `+` 문자열 리터럴을 결합 하 여 로그인 합니다. 비트 사용할 수 또는 (`|||`) 열거형 플래그를 결합 하는 연산자입니다. 예를 들어 다음 코드는 올바른 F # 3.1에서:

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

다른 비트 연산자의 사용이 허용 되지 않습니다.


## <a name="named-literals"></a>명명 된 리터럴
로 상수 있어야 하는 값을 표시할 수 있습니다는 [리터럴](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) 특성입니다. 이 특성을 상수로 컴파일할 사용 하면 값의 효과 가집니다.

패턴 일치 식에서 소문자로 시작 하는 식별자는 항상 변수를 바인딩할 수으로 처리 하지 않고 리터럴로 하므로 일반적으로 사용 해야 문자가 대문자 리터럴을 정의할 때.

## <a name="integers-in-other-bases"></a>다른 밑에 있는 정수

사용 하 여 16 진수, 8 진수 또는 이진에서 부호 있는 32 비트 정수로 지정 될 수도 있습니다는 `0x`, `0o` 또는 `0b` 각각 접두사입니다.

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>숫자 리터럴에 밑줄이

F # 4.1 부터는 구분할 수 있습니다 자리는 밑줄 문자 (`_`).

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a>참고 항목

[Core.LiteralAttribute 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
