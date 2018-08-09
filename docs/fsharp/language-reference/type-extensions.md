---
title: 형식 확장명(F#)
description: '이전에 정의 된 개체 형식에 새 멤버를 추가 하면 F # 형식 확장을 허용 하는 방법에 대해 알아봅니다.'
ms.date: 07/20/2018
ms.openlocfilehash: 2181745ea75894fbfe35d5522c130baaf1876455
ms.sourcegitcommit: 78bcb629abdbdbde0e295b4e81f350a477864aba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "33566888"
---
# <a name="type-extensions"></a>형식 확장명

형식 확장명 (라고도 _확대_)은 이전에 정의 된 개체 형식에 새 멤버를 추가할 수 있는 기능입니다. 세 가지 기능은 다음과 같습니다.

* 기본 형식 확장
* 선택적 형식 확장
* 확장 메서드

각 다양 한 시나리오에서 사용할 수 있고 다른 절충 합니다.

## <a name="syntax"></a>구문

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a>기본 형식 확장

내장 형식 확장은 사용자 정의 형식을 확장 하는 형식 확장.

기본 형식 확장이 동일한 파일에 정의 되어야 합니다 **및** 동일한 네임 스페이스 또는 확장 되는 해당 형식으로는 모듈입니다. 다른 정의 해도 되 [선택적 형식 확장의](type-extensions.md#optional-type-extensions)합니다.

내장 형식 확장은 경우에 따라 형식 선언에서 기능을 분리 하는 깔끔한 방법입니다. 다음 예제에서는 내장 형식 확장을 정의 하는 방법을 보여 줍니다.

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

형식 확장을 사용 하 여 다음의 각 수 있습니다.

* 선언의 한 `Variant` 형식
* 인쇄 하는 기능을 `Variant` "모양"에 따라 클래스
* 개체 스타일을 사용 하 여 인쇄 기능에 액세스 하는 방법을 `.`-표기법

이의 모든 멤버를 정의 하는 대신 `Variant`합니다. 하지 않으면 기본적으로 더 나은 접근 방식을 상황에 따라 기능의 클리너 표현 될 수 있습니다.

기본 형식 확장을 보강 하며 리플렉션을 통해 형식을 검사할 때 형식에 나타나는 형식의 멤버로 컴파일됩니다.

## <a name="optional-type-extensions"></a>선택적 형식 확장

선택적 형식 확장에는 원래 모듈, 네임 스페이스 또는 확장 되는 형식의 어셈블리 외부에 표시 되는 확장이입니다.

선택적 형식 확장의 직접 정의 하지 않은 형식을 확장 하는 데 유용 합니다. 예를 들어:

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

이제 액세스할 수 있습니다 `RepeatElements` 의 멤버인 것 처럼 <xref:System.Collections.Generic.IEnumerable%601> 으로 `Extensions` 모듈에서 작업 하는 범위에서 열립니다.

선택적 확장 리플렉션을 통해 검사 하는 경우 확장된 형식에 표시 되지 않습니다. 확장 모듈 이어야 하며 있을 때만 범위 확장을 포함 하는 모듈 열려 또는 그렇지 않은 경우 범위는 경우에 선택 사항입니다.

선택적 확장 멤버는 정적 멤버는 개체 인스턴스를 암시적으로 매개 변수로 전달 되는 첫 번째 컴파일됩니다. 그러나 인스턴스 멤버 또는 선언 하는 방법에 따라 정적 멤버인 것 처럼 작동 합니다.

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a>기본 및 선택적 형식 확장의 일반 제한 사항

형식 변수가 제한 되는 제네릭 형식에 형식 확장을 선언 하는 것이 가능 합니다. 요구 사항 확장 선언의 제약 조건이 선언 된 형식의 제약 조건과 일치 하는 합니다.

그러나 제약 조건이 선언된 된 형식 사이의 형식 확장을 일치 하는 경우에 있기 제약 조건의 형식 매개 변수에 선언 된 형식 보다 다양 한 요구 사항을 적용 하는 확장된 멤버의 본문에서 유추할 수 있습니다. 예를 들어:

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

이 코드는 선택적 형식 확장을 사용 하는 방법이 있습니다.

* 그대로 합니다 `Sum` 멤버 다양 한 제약 조건을 갖기 `'T` (`static member get_Zero` 및 `static member (+)`) 형식 확장을 정의 하는 보다.
* 형식 확장으로 동일한 제약 조건이 수정 `Sum` 더 이상 일치 하지 정의 된 제약 조건에서 `IEnumerable<'T>`합니다.
* 멤버를 변경 하기 `member inline Sum` 형식 제약 조건이 일치 하지 않으면 오류가 표시 됩니다

경우 원하는 정적 메서드는 "공간에서 부동" 및 형식을 확장 하는 것 처럼 표시 될 수 있습니다. 확장 메서드 필요할입니다.

## <a name="extension-methods"></a>확장 메서드

마지막으로, 확장 메서드 ("C# 스타일 확장 구성원"이 라고도 함)에 선언할 수 있습니다 F #의 정적 멤버 메서드로 클래스.

확장 메서드는 제네릭 형식 변수를 제한 하는 형식에 확장을 정의 하려는 경우 유용 합니다. 예를 들어:

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

를 사용 하면이 코드는 표시 되도록 처럼 `Sum` 에 정의 된 <xref:System.Collections.Generic.IEnumerable%601>. 단, `Extensions` 열린 또는 범위입니다.

## <a name="other-remarks"></a>다른 설명

형식 확장명 다음 특성도 있습니다.

* 액세스할 수 있는 모든 형식을 확장할 수 있습니다.
* 기본 및 선택적 형식 확장을 정의할 수 있습니다 _모든_ 멤버 유형, 뿐 아니라 메서드. 확장 속성은 예를 들어도 가능 합니다.
* `self-identifier` 토큰을 [구문](type-extensions.md#syntax) 일반 멤버와 마찬가지로 호출 되는 형식의 인스턴스를 나타냅니다.
* 확장 된 멤버 인스턴스 멤버 또는 정적 수 있습니다.
* 형식 확장의 형식이 변수 선언 된 형식의 제약 조건 일치 해야 합니다.

형식 확장에 대 한 다음과 같은 제한 사항이 존재 합니다.

* 형식 확장에서 가상 또는 추상 메서드를 지원 하지 않습니다.
* 형식 확장명 확대도 재정의 메서드를 지원 하지 않습니다.
* 형식 확장을 지원 하지 않습니다 [정적으로 확인 한 형식 매개](generics/statically-resolved-type-parameters.md)합니다.
* 선택적 형식 확장 확대도 생성자를 지원 하지 않습니다.
* 에 형식 확장을 정의할 수 없습니다 [형식 약어](type-abbreviations.md)합니다.
* 형식 확장에 대해 올바르지 않습니다. `byref<'T>` (경우에 선언 될 수 있습니다).
* (경우에 선언 될 수 있습니다) 형식 확장 특성에 대해 올바르지 않습니다.
* 동일한 이름의 다른 메서드 오버 로드 하는 확장을 정의할 수 있지만 모호한 호출이 발생할 경우 F # 컴파일러에서 확장 되지 않은 메서드에 우선권을 부여 합니다.

마지막으로, 한 형식에 대 한 여러 기본 형식 확장이 존재 하는 경우 모든 구성원은 고유 해야 합니다. 동일한 형식으로 서로 다른 형식 확장의 멤버는 선택적 형식 확장에 대 한 이름과 있을 수 있습니다. 모호성 오류가 클라이언트 코드는 동일한 멤버 이름을 정의 하는 두 개의 서로 다른 범위를가 하는 경우에 발생 합니다.

## <a name="see-also"></a>참고자료

[F# 언어 참조](index.md)

[멤버](members/index.md)
