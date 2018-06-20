---
title: 문자열(F#)
description: "F # 'string' 유형의 변경할 수 없는 텍스트의 유니코드 문자 시퀀스로 나타내는 하는 방법에 대해 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 80c08f5b768dd826745e07b8c5726093050ab730
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207107"
---
# <a name="strings"></a>문자열

> [!NOTE]
이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

`string` 형식은 변경할 수 없는 텍스트를 일련의 유니코드 문자로 나타냅니다. `string`은 .NET Framework에서 `System.String`의 별칭입니다.

## <a name="remarks"></a>설명
문자열 리터럴은 따옴표 (") 문자로 구분 됩니다. 백슬래시 문자 ( \\ ) 특수 문자를 인코딩하는 데 사용 됩니다. 백슬래시와 함께 다음 문자 라고는 *이스케이프 시퀀스*합니다. 이스케이프 시퀀스가 지원 F # 문자열 리터럴은 다음 표에 나와 있습니다.

|문자|이스케이프 시퀀스|
|---------|---------------|
|백스페이스|\b|
|줄 바꿈|\n|
|캐리지 리턴|\r|
|탭|\t|
|백슬래시|\\|
|따옴표|\"|
|아포스트로피|\'|
|유니코드 문자|\u*XXXX* 또는 \U*XXXXXXXX* (여기서 *X* 16 진수 숫자 나타냅니다)|

앞에 @ 기호를 리터럴 축 자 문자열 (가) 있습니다. 즉, 모든 이스케이프 시퀀스는 무시 제외 하 고 두 인용 부호 문자는 하나의 따옴표 문자로 해석 됩니다.

또한 문자열 삼중 따옴표로 묶을 수 있습니다. 이 경우 모든 이스케이프 시퀀스는 무시 큰따옴표 문자를 포함 하 합니다. 포함 된 따옴표 붙은 문자열 포함 하는 문자열을 지정 하려면 축 자 문자열 또는 삼중 따옴표가 붙은 문자열 사용할 수 있습니다. 축 자 문자열을 사용 하면 단일 따옴표 문자를 나타내기 위해 두 개의 따옴표 문자를 지정 해야 합니다. 삼중 따옴표가 붙은 문자열을 사용 하면 문자열의 끝으로 구문 분석 중인 없이도 단일 따옴표 문자를 사용할 수 있습니다. XML 또는 포함 된 따옴표를 포함 하는 다른 구조를 사용 하 여 작업할 때이 방법이 유용할 수 있습니다.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

코드에서 줄 바꿈이 포함 문자열이 허용 되는 고 줄 바꿈으로 해석 됩니다 문자 그대로 줄 바꿈 백슬래시 문자는 줄 바꿈 앞 마지막 문자가 하지 않는 한 합니다. 백슬래시 문자를 사용할 때 다음 줄에서 선행 공백 무시 됩니다. 다음 코드에서는 문자열 `str1` 에 값을 갖는 `"abc\n     def"` 및 문자열 `str2` 에 값을 갖는 `"abcdef"`합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

다음과 같이 배열 유사 구문을 사용 하 여 문자열의 문자들을 액세스할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

출력은 `b`입니다.

또는 다음 코드와 같이 배열 조각 구문을 사용 하 여 부분 문자열을 추출할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

출력은 다음과 같습니다.

```
abc
def
```

유형, 부호 없는 바이트의 배열에서 ASCII 문자열을 표현할 수 `byte[]`합니다. 접미사를 추가 `B` 문자열 리터럴로 ASCII 문자열 임을 나타냅니다. 바이트 배열에서 사용 된 ASCII 문자열 리터럴은 유니코드 이스케이프 시퀀스를 제외한 유니코드 문자열로 같은 이스케이프 시퀀스를 지원 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]
    
## <a name="string-operators"></a>문자열 연산자
문자열을 연결 하는 방법은 두 가지가:를 사용 하 여는 `+` 연산자를 사용 하 여 또는 `^` 연산자입니다. `+` 연산자 기능을 처리 하는.NET Framework 문자열과 호환성이 유지 됩니다.

다음 예제에서는 문자열을 연결 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]
    
## <a name="string-class"></a>String 클래스
F #에서 문자열 형식이.NET Framework 실제로 `System.String` 모든 입력은 `System.String` 멤버는 사용할 수 있습니다. 여기에는 `+` 연산자를 사용 되는 문자열을 연결 하는 `Length` 속성 및 `Chars` 유니코드 문자 배열 문자열을 반환 하는 속성입니다. 문자열에 대 한 자세한 내용은 참조 `System.String`합니다.

사용 하 여는 `Chars` 속성 `System.String`, 다음 코드 에서처럼는 인덱스를 지정 하 여 문자열의 개별 문자를 액세스할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]
    
## <a name="string-module"></a>String 모듈
문자열 처리에 대 한 추가 기능에 포함 되어는 `String` 모듈에는 `FSharp.Core` 네임 스페이스입니다. 자세한 내용은 참조 [Core.String 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)합니다.

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)
