---
title: 정적으로 확인된 형식 매개 변수(F#)
description: 'F #을 사용 하는 방법을 알아봅니다 런타임이 아닌 컴파일 타임에 실제 형식으로 대체 되는 정적으로 확인 된 형식 매개 변수입니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 12c2af4d9df7ae1e5e77efc9413eb8777459a83c
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34233784"
---
# <a name="statically-resolved-type-parameters"></a>정적으로 확인된 형식 매개 변수

A *정적으로 확인 된 형식 매개 변수* 런타임이 아닌 컴파일 타임에 실제 형식으로 대체 되는 형식 매개 변수입니다. 캐럿 (^) 기호로 앞입니다.


## <a name="syntax"></a>구문

```
ˆtype-parameter
```

## <a name="remarks"></a>설명
F # 언어에서 두 가지 종류의 형식 매개 변수가 있습니다. 첫 번째 표준 제네릭 형식 매개 변수입니다. 와 같이 아포스트로피 (')로 표시는 이러한 `'T` 및 `'U`합니다. 다른.NET Framework 언어의 제네릭 형식 매개 변수와 동일 합니다. 와 같이 캐럿 기호를 표시 된 정적으로 확인 된 다른 종류 이며 `^T` 및 `^U`합니다.

정적으로 확인 된 형식 매개 변수는 제약 조건이 있어야 하도록 지정 하는 형식 인수가 특정 멤버 또는 멤버 사용할 수 있도록 하는 멤버 제약 조건과 함께에서 주로 유용 합니다. 일반 제네릭 형식 매개 변수를 사용 하 여 이러한 종류의 제약 조건 만드는 방법이 없습니다.

다음 표에서 유사성과 형식 매개 변수 중 두 가지 차이점이 요약 되어 있습니다.

|기능|제네릭|정적으로 확인 된|
|-------|-------|-------------------|
|구문|`'T`, `'U`|`^T`, `^U`|
|해결 시간|런타임|컴파일 시간|
|멤버 제약 조건|멤버 제약 조건과 함께 사용할 수 없습니다.|멤버 제약 조건과 함께 사용할 수 있습니다.|
|코드 생성|표준 제네릭 형식 매개 변수가 있는 형식 (또는 메서드) 단일 제네릭 형식 또는 메서드의 생성 됩니다.|여러 인스턴스는 형식 및 메서드 생성, 형식 마다 필요 합니다.|
|형식과 함께 사용|형식에 사용할 수 있습니다.|형식에 사용할 수 없습니다.|
|인라인 함수와 함께 사용|아니요. 표준 제네릭 형식 매개 변수는 인라인 함수를 매개 변수화 할 수 없습니다.|예. 정적으로 확인 된 형식 매개 변수는 함수나 인라인이 아닌 메서드를 사용할 수 없습니다.|

많은 F # 핵심 라이브러리 함수, 특히 연산자는 형식 매개 변수 정적으로 확인 된 있어야 합니다. 이러한 함수 및 연산자에는 인라인 및 숫자 계산에 대 한 효율적인 코드 생성 합니다.

인라인 메서드 및 연산자를 사용 하거나 형식 매개 변수를 정적으로 해결 된 다른 기능을 사용 하는 함수 자체 정적으로 확인 된 형식 매개 변수에 사용할 수도 있습니다. 종종 형식 유추와 같은 인라인 함수를 정적으로 확인 된 형식 매개 변수를 유추 합니다. 다음 예제는 정적으로 확인 된 형식 매개 변수가으로 유추 되는 연산자 정의입니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

형식이 확인된 `(+@)` 둘 다의 사용에 따라 `(+)` 및 `(*)`, 둘 다의 정적으로 확인 된 형식 매개 변수에 대 다 형식 유추 될 있습니다. 확인 된 형식, F # 인터프리터에 표시 된 대로 다음과 같습니다.

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

출력은 다음과 같습니다.

```
2
1.500000
```

F # 4.1 부터는에 정적으로 확인 된 형식 매개 변수 서명과 구체적인 형식 이름의도 지정할 수 있습니다.  언어의 이전 버전에서는 형식 이름 컴파일러에서 유추할 수 실제로 하지만 실제로 지정할 수 없습니다 서명에 합니다.  4.1 F #을 기준으로 정적으로 확인 된 형식 매개 변수 시그니처에 구체적인 형식 이름을 지정할 수도 있습니다. 예를 들면 다음과 같습니다.

```fsharp
let inline konst x _ = x

type CFunctor() = 
    static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
    static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

    // default implementation of replace
    static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

    // call overridden replace if present
    static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
        ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a>참고 항목
[제네릭](index.md)

[형식 유추](../type-inference.md)

[자동 일반화](automatic-generalization.md)

[제약 조건](constraints.md)

[인라인 함수](../functions/inline-functions.md)
