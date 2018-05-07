---
title: 형식 확장명(F#)
description: '이전에 정의 된 개체 형식에 새 멤버를 추가할 F # 형식 확장을 사용 하는 방법에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 2181745ea75894fbfe35d5522c130baaf1876455
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="type-extensions"></a>형식 확장명

형식 확장을 사용 하면 이전에 정의 된 개체 형식에 새 멤버를 추가할 수 있습니다.

## <a name="syntax"></a>구문

```fsharp
// Intrinsic extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]

// Optional extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]
```

## <a name="remarks"></a>설명
두 가지 형태의 형식 확장에 약간 다른 구문 및 동작이 있습니다. *기본 확장* 되는 확장 유형으로는 동일한 네임 스페이스 또는 모듈에, 동일한 소스 파일 및 동일한 어셈블리 (DLL 또는 실행 파일)에 표시 되는 확장 합니다. *선택적 확장* 는 원래 모듈, 네임 스페이스 또는 확장 되는 형식의 어셈블리 외부에 표시 하는 확장 합니다. 기본 확장 유형 리플렉션을 통해 검사 되지만 선택적 확장 되지 않습니다 때 형식에 나타납니다. 확장 모듈 이어야 하며 확장을 포함 하는 모듈 열릴 때에 범위에는 선택 사항입니다.

위 구문에서 *typename* 확장 하 고 하는 형식을 나타냅니다. 액세스할 수 있는 모든 형식이 확장 될 수 있습니다, 하지만 형식 이름은 실제 형식 이름, 형식 약어가 아니라 이어야 합니다. 형식 확장에서 여러 멤버를 정의할 수 있습니다. *자체 식별자* 일반 멤버와 마찬가지로 호출 되는 개체의 인스턴스를 나타냅니다.

`end` 키워드는 간단한 구문에서 선택 사항입니다.

클래스 형식에 다른 멤버와 마찬가지로 형식 확장에 정의 된 멤버를 사용할 수 있습니다. 다른 멤버와 마찬가지로 정적 또는 인스턴스 멤버 수 있습니다. 이러한 메서드는 라고도 *확장 메서드*; 속성 이라고 *확장 속성*등입니다. 선택적 확장 멤버를 개체 인스턴스 암시적으로 매개 변수로 전달 되는 첫 번째 정적 멤버에 컴파일됩니다. 그러나 큐브인 것 처럼 인스턴스 멤버나 정적 멤버는 선언 된 방식에 따라 작동 합니다. 암시적 확장 멤버 종류의 구성원으로 포함 되어 있으며 제한 없이 사용할 수 있습니다.

확장 메서드는 가상 또는 추상 메서드 일 수 없습니다. 이름이 같은 다른 메서드를 오버 로드할 수 있지만 비 확장 메서드 호출이 모호에 우선 순위를 지정 하면 컴파일러가 사용 합니다.

한 형식에 대 한 여러 기본 형식 확장이 있는, 모든 멤버 고유 해야 합니다. 동일한 형식으로 서로 다른 형식 확장의 멤버는 선택적 형식 확장에 대 한 이름이 동일한 있을 수 있습니다. 모호성으로 인해 오류가 클라이언트 코드는 동일한 멤버 이름을 정의 하는 두 개의 서로 다른 범위를가 하는 경우에 발생 합니다.

다음 예제에서는 모듈의 형식은 확장명이 내장 형식입니다. 모듈 외부 클라이언트 코드에 형식 확장 형식과 모든 측면에서의 일반 멤버로 나타납니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3701.fs)]

섹션으로 형식 정의 구분 하려면 내장 형식 확장을 사용할 수 있습니다. 이 별도 컴파일러에서 생성 된 코드와 작성 된 코드를 유지 하거나 다른 사람에 의해 생성 되거나 다른 기능와 관련 된 코드를 그룹화 하 여 큰 형식 정의 관리에 유용한 수 있습니다.

다음 예에서는 선택적 형식 확장 확장는 `System.Int32` 확장 메서드에 형식 `FromString` 정적 멤버를 호출 하는 `Parse`합니다. `testFromString` 메서드 새 멤버의 모든 인스턴스 멤버와 마찬가지로 호출 되도록 하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3702.fs)]

새 인스턴스 멤버의 다른 모든 메서드처럼 표시 됩니다는 `Int32` intellisense에서 하지만에 있을 때만 확장을 포함 하는 모듈 열려 있거나 기타 범위 유형입니다.

## <a name="generic-extension-methods"></a>제네릭 확장 메서드
F # 컴파일러 F # 3.1의 경우, 하기 전에 C#의 사용을 지원 하지 않았습니다-확장 메서드는 제네릭 형식 변수, 배열 형식, 튜플 형식 또는 "this" 매개이 변수는 F # 함수 형식과 스타일 지정 합니다. F # 3.1 이러한 확장 멤버의 사용을 지원 합니다.

예를 들어 F # 3.1 코드에서 C#에서 다음 구문과 유사 하는 서명이 있는 확장 메서드를 사용할 수 있습니다.

```csharp
static member Method<T>(this T input, T other)
```

이 방법은 제네릭 형식 매개 변수가 제한 되는 경우에 특히 유용 합니다. 또한 이제 F # 코드에서 다음과 같은 확장 멤버를 선언 고 추가 이며 의미상 풍부한 일련의 확장 메서드를 정의할 수 있습니다. F #에서 일반적으로 다음 예제와 같이 확장 멤버를 정의합니다.

```fsharp
open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq { for x in xs do for i in 1 .. n do yield x }
```

그러나 제네릭 형식에 대 한 유형 변수에 하지 제한 될 수 있습니다. 선언할 수 있습니다는 C#-이 제한을 해결 하려면 F #에서 스타일 확장 멤버입니다. F #의 인라인와 함께 이러한 종류의 선언 결합 하는 경우에 확장 멤버로 일반 알고리즘을 제공할 수 있습니다.

다음 선언을 생각해 보세요.

```fsharp
[<Extension>]
type ExtraCSharpStyleExtensionMethodsInFSharp () =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

이 선언은 사용 하 여 다음 예제와 유사한 코드를 작성할 수 있습니다.

```fsharp
let listOfIntegers = [ 1 .. 100 ]
let listOfBigIntegers = [ 1I to 100I ]
let sum1 = listOfIntegers.Sum()
let sum2 = listOfBigIntegers.Sum()
```

이 코드에서는 단일 확장 멤버를 정의 하 여 오버 로드 하지 않고 동일한 일반 산술 코드는 두 형식의 목록을에 적용 됩니다.


## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[멤버](members/index.md)
