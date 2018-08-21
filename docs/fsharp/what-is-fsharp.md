---
title: 'F # 이란'
description: '어떤 F # 프로그래밍 언어는 및와 같은 새로운 F # 프로그래밍에 알아봅니다. 다양 한 데이터 형식, 함수 및 서로 연결 되는 방법에 대해 알아봅니다.'
ms.date: 08/03/2018
ms.openlocfilehash: 193747f380c61a387ed79ecca6abbcd90ee74376
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2018
ms.locfileid: "40240646"
---
# <a name="what-is-f"></a>F # 이란 #

F #은 쉽게 올바른 및 유지 관리 가능한 코드를 작성할 수 있도록 하는 함수형 프로그래밍 언어입니다.

F # 프로그래밍은 주로 형식 및 형식 유추 되어 자동으로 일반화 된 함수를 정의 해야 합니다. 이렇게 하면 포커스 문제 도메인 및 프로그래밍의 세부 정보를 사용 하지 않고 해당 데이터를 조작에 유지 합니다.

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

F # 등의 여러 기능을에 있습니다.

* 간단한 구문
* 기본적으로 변경할 수 없는
* 형식 유추 및 자동 일반화
* 첫 번째 클래스 함수
* 강력한 데이터 형식
* 패턴 일치
* 비동기 프로그래밍

기능의 전체 집합에 설명 되어는 [F # 언어 참조](language-reference/index.md)합니다.

## <a name="rich-data-types"></a>다양 한 데이터 형식

데이터 형식 [레코드](language-reference/records.md) 하 고 [구별 된 공용 구조체](language-reference/discriminated-unions.md) 복잡 한 데이터 및 도메인을 나타낼 수 있습니다.

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

F # 레코드 및 구분 된 공용 구조체는 null이 아닌, 변경할 수 없는 및 매우 쉽게 사용할 수 있도록 기본적으로 비교할 수 있습니다.

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>함수 및 패턴 일치를 사용 하 여 적용된 정확성

F # 함수를 쉽게 선언할 수는 실제로 강력한입니다. 함께 사용 하면 [패턴 일치](language-reference/pattern-matching.md), 인 정확성 컴파일러에 의해 적용 되는 동작을 정의할 수 있습니다.

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

F # 함수는 첫 번째 클래스를 매개 변수로 전달 되 고 다른 함수에서 반환 된 수를 의미 합니다. 또한입니다.

## <a name="functions-to-define-operations-on-objects"></a>개체에 대 한 작업을 정의 하는 함수

F #은 데이터 및 기능을 혼합 하는 경우 유용한 데이터 형식인 개체의 전체를 지원 합니다. F # 함수는 개체를 조작 하는 데 사용 됩니다.

```fsharp
type Set<[<EqualityConditionOn>] ‘T when ‘T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

개체 지향, F #에 코드를 작성 하는 대신 자주 코드를 작성 합니다 처리 개체와 다른 데이터 형식을 함수에 대 한 조작 하는 합니다. 같은 기능 [제네릭 인터페이스](language-reference/interfaces.md), [개체 식](language-reference/object-expressions.md)를 적절히 사용 하 고 [멤버](language-reference/members/index.md) 큰 F # 프로그램에서 일반적입니다.

## <a name="next-steps"></a>다음 단계

F # 기능을 더 큰 집합에 대 한 자세한 내용은 체크 아웃 합니다 [F # 둘러보기](tour.md)합니다.