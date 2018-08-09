---
title: 계산 식(F#)
description: '시퀀싱 할 수 있으며 제어 흐름 구문 및 바인딩을 사용 하 여 결합 하는 F # 계산을 작성 하는 편리한 구문을 만드는 방법에 알아봅니다.'
ms.date: 07/27/2018
ms.openlocfilehash: 4995efc757d99a575ee9fad3abf0465a32398c44
ms.sourcegitcommit: 78bcb629abdbdbde0e295b4e81f350a477864aba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "36207435"
---
# <a name="computation-expressions"></a>계산 식

F # 계산 식을 제어 흐름 구문 및 바인딩을 사용 하 여 결합 및 시퀀싱 할 수 있는 계산을 작성 하는 것에 대 한 간편한 구문을 제공 합니다. 계산 식의 종류에 따라 이러한 생각할 수 있습니다 monads, monoids, monad 변환기 및 applicative 함수를 표현 하는 방법으로 합니다. 그러나 다른 언어와 달리 (같은 *do 표기법* Haskell에서), 단일 추상화를 얽매여 있지 않는 하며 매크로 또는 다른 형태의에 의존 하지 마십시오 편리 하 고 상황에 맞는 구문을 위해 메타 프로그래밍 합니다.

## <a name="overview"></a>개요

계산이 많은 형식을 취할 수 있습니다. 계산의 가장 일반적인 형식은 쉽게 이해 하 고 수정할 수 있는 단일 스레드 실행 합니다. 그러나 일부 형태의 계산은 단일 스레드 실행으로 간단 합니다. 예를 들면 다음과 같습니다.

* 명확 하지 않은 계산
* 비동기 계산
* Effectful 계산
* 인기 계산

일반적으로 더 *상황에 맞는* 응용 프로그램의 특정 부분에서 수행 해야 하는 계산 합니다. 상황에 맞는 코드를 작성이 이므로 이렇게 않도록 하는 추상화 하지 않고 지정된 된 컨텍스트 외부에서 "누수" 계산 하기가 어려울 수 있습니다. 이러한 추상화는 F #에 수행 하는 일반화 된 방법은 소위 이유는 직접 쓸 까다로운 것은 종종 **계산 식**합니다.

계산 식 상황에 맞는 계산 인코딩에 대 한 구문 및 추상화 한 균일 모델을 제공 합니다.

모든 계산 식에서 지원 되는 *작성기* 형식입니다. 작성기 형식을 계산 식에 사용할 수 있는 작업을 정의 합니다. 참조 [계산 식의 새 형식 만들기](computation-expressions.md#creating-a-new-type-of-computation-expression), 사용자 지정 계산 식을 만드는 방법을 보여 줍니다.

### <a name="syntax-overview"></a>구문 개요

다음 형식 이어야 하는 모든 계산 식:

```
builder-expr { cexper }
```

여기서 `builder-expr` 계산 식을 정의 하는 작성기 형식 이름인 및 `cexper` 계산 식의 식 본문입니다. 예를 들어 `async` 계산 식 코드가 있습니다.이 다음과 같을 수 있습니다.

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

구문은 특수 한 추가 계산 식에서 사용할 수 있는 이전 예제에 표시 된 대로입니다. 다음과 같은 식을 계산 식을 사용 하 여 나타날 수 있습니다.

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

각 이러한 키워드 및 다른 표준 F # 키워드는 지원 작성기 형식에서 정의한 경우에 계산 식에서 사용할 수 있습니다. 이 유일한 예외는 `match!`에 자체를 사용 하기 위한 syntactic sugar `let!` 패턴 일치 결과에 옵니다.

작성기 유형이 계산 식 조각의; 결합 하는 방법을 제어 하는 특수 메서드를 정의 하는 개체 즉, 해당 메서드 계산 식의 동작 방식을 제어 합니다. 다른 작성기 클래스를 설명 방법은 사용할 수 있는 것의 루프 및 바인딩 같은 많은 F # 구문, 작업을 사용자 지정할 수 있습니다.

### `let!`

`let!` 키워드 이름에 다른 계산 식에 대 한 호출의 결과 바인딩합니다.

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

사용 하 여 계산 식에 대 한 호출을 바인딩할 경우 `let`, 계산 식의 결과 가져오지 것입니다. 대신는 바인딩한의 값을 *표시 되지 않은* 해당 계산 식으로 호출 합니다. 사용 하 여 `let!` 결과에 바인딩합니다.

`let!` 정의한는 `Bind(x, f)` 작성기 형식 멤버입니다.

### `do!`

합니다 `do!` 키워드는 반환 하는 계산 식 호출에 대 한는 `unit`-형식 처럼 (정의한는 `Zero` 작성기의 멤버):

```fsharp
let doThingsAsync data url =
    async {
        do! sumbitData data url
        ...
    }
```

에 대 한 합니다 [비동기 워크플로](asynchronous-workflows.md),이 형식은 `Async<unit>`합니다. 기타 계산 식 형식은 짧을 수 `CExpType<unit>`입니다.

`do!` 정의한를 `Bind(x, f)` 작성기 형식에서 멤버 위치 `f` 생성을 `unit`입니다.

### `yield`

합니다 `yield` 키워드를 사용할 수 있도록 계산 식에서 값을 반환 하는 데는 <xref:System.Collections.Generic.IEnumerable%601>:

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

와 마찬가지로 합니다 [yield 키워드에서 C#](../../csharp/language-reference/keywords/yield.md), 반복 될 때마다 계산 식의 각 요소가 생성 될 합니다.

`yield` 정의한를 `Yield(x)` 작성기 형식에서 멤버 위치 `x` 항목을 다시 생성 됩니다.

### `yield!`

`yield!` 키워드는 계산 식에서 값의 컬렉션을 평면화 합니다.

```fsharp
let squares =
    seq {
        for i in 1..3 -> i * i
    }

let cubes =
    seq {
        for i in 1..3 -> i * i * i
    }

let squaresAndCubes =
    seq {
        yield! squares
        yield! cubes
    }

printfn "%A" squaresAndCubes // Prints - 1; 4; 9; 1; 8; 27
```

계산 식에서 호출을 평가할 때 `yield!` 는 해당 항목 생성 백--하나씩 결과 평면화 합니다.

`yield!` 정의한 합니다 `YieldFrom(x)` 작성기 형식에서 멤버 위치 `x` 값의 컬렉션인 경우.

### `return`

`return` 키워드 계산 식에 해당 하는 형식의 값을 래핑합니다. 사용 하 여 계산 식 외에도 `yield`, 계산 식 "완료"로 사용 됩니다.

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return` 정의한 합니다 `Return(x)` 작성기 형식에서 멤버 위치 `x` 래핑할 항목이 합니다.

### `return!`

`return!` 키워드 계산 식의 값을 인식 하 고 계산 식에 해당 하는 형식에 해당 결과 래핑합니다.

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!` 정의한를 `ReturnFrom(x)` 작성기 형식에서 멤버 위치 `x` 다른 계산 식입니다.

### `match!`

F # 4.5부터는 `match!` 키워드를 사용 하면 인라인 해당 결과에 다른 계산 식 및 패턴 일치에 대 한 호출 합니다.

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

포함 하는 계산 식을 호출할 때 `match!`와 같은 호출의 결과 실현 됩니다 `let!`합니다. 이 대개 여기서 결과 계산 식을 호출 하는 경우는 [선택적](options.md)합니다.

## <a name="built-in-computation-expressions"></a>기본 제공 계산 식

F # 핵심 라이브러리는 세 개의 기본 제공 계산 식을 정의 합니다. [시퀀스 식](sequences.md), [비동기 워크플로](asynchronous-workflows.md), 및 [쿼리 식](query-expressions.md)합니다.

## <a name="creating-a-new-type-of-computation-expression"></a>계산 식의 새 형식 만들기

작성기 클래스를 만들고 클래스에 대 한 특수 메서드를 정의 하 여 사용자 고유의 계산 식의 특징을 정의할 수 있습니다. 필요에 따라 작성기 클래스는 다음 표에 나열 된 대로 메서드를 정의할 수 있습니다.

다음 표에서 워크플로 작성기 클래스에서 사용할 수 있는 메서드를 설명 합니다.

|**메서드**|**형식 시그니처**|**설명**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|에 대 한 호출 `let!` 고 `do!` 계산 식에 있습니다.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|계산 식을 함수로 래핑합니다.|
|`Return`|`'T -> M<'T>`|에 대 한 호출 `return` 계산 식에 있습니다.|
|`ReturnFrom`|`M<'T> -> M<'T>`|에 대 한 호출 `return!` 계산 식에 있습니다.|
|`Run`|`M<'T> -> M<'T>` 또는<br /><br />`M<'T> -> 'T`|계산 식을 실행합니다.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` 또는<br /><br />`M<unit> * M<'T> -> M<'T>`|계산 식의 시퀀싱에 대 한 호출 됩니다.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` 또는<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|에 대 한 호출 `for...do` 계산 식에는 식입니다.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|에 대 한 호출 `try...finally` 계산 식에는 식입니다.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|에 대 한 호출 `try...with` 계산 식에는 식입니다.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|에 대 한 호출 `use` 계산 식의 바인딩.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|에 대 한 호출 `while...do` 계산 식에는 식입니다.|
|`Yield`|`'T -> M<'T>`|에 대 한 호출 `yield` 계산 식에는 식입니다.|
|`YieldFrom`|`M<'T> -> M<'T>`|에 대 한 호출 `yield!` 계산 식에는 식입니다.|
|`Zero`|`unit -> M<'T>`|빈 호출 `else` 의 분기 `if...then` 계산 식에는 식입니다.|

대부분의 작성기 클래스에서 메서드를 사용 및 반환을 `M<'T>` 는 일반적으로 예를 들어 조합 하는 계산의 종류를 지정 하는 별도로 정의 된 형식, 구문 `Async<'T>` 비동기 워크플로와 및 `Seq<'T>` 시퀀스 워크플로에 합니다. 다음 하나의 구문에서 반환 되는 워크플로 개체를 전달할 수 있도록 이러한 메서드의 시그니처는 결합 하 고 서로 중첩 될 수 있도록 합니다. 계산 식 구문 분석할 때 컴파일러는 앞의 표에 메서드 및 계산 식의 코드를 사용 하 여 일련의 중첩 된 함수 호출에 식을 변환 합니다.

중첩 된 식은 다음과 같습니다. 다음 형식의

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

위의 코드에 대 한 호출에서 `Run` 고 `Delay` 계산 식 작성기 클래스에 정의 되지 않은 경우 생략 됩니다. 여기로 표시, 계산 식의 본문이 `{| cexpr |}`, 다음 표에 설명 된 번역으로 작성기 클래스의 메서드를 포함 하는 호출으로 변환 됩니다. 계산 식 `{| cexpr |}` 가 이러한 변환에 따라 정의 된 재귀적으로 위치 `expr` F # 식 및 `cexpr` 계산 식입니다.



|식|변환|
|----------|-----------|
|<code>{&#124; let binding in cexpr &#124;}</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{&#124; let! pattern = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; do! expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; yield expr &#124;}</code>|`builder.Yield(expr)`|
|<code>{&#124; yield! expr &#124;}</code>|`builder.YieldFrom(expr)`|
|<code>{&#124; return expr &#124;}</code>|`builder.Return(expr)`|
|<code>{&#124; return! expr &#124;}</code>|`builder.ReturnFrom(expr)`|
|<code>{&#124; use pattern = expr in cexpr &#124;}</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; use! value = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> {&#124; cexpr &#124;}))))</code>|
|<code>{&#124; if expr then cexpr0 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else binder.Zero()</code>|
|<code>{&#124; if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else {&#124; cexpr1 &#124;}</code>|
|<code>{&#124; match expr with &#124; pattern_i -> cexpr_i &#124;}</code>|<code>match expr with &#124; pattern_i -> {&#124; cexpr_i &#124;}</code>|
|<code>{&#124; for pattern in expr do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; for identifier = expr1 to expr2 do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun identifier -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; while expr do cexpr &#124;}</code>|<code>builder.While(fun () -> expr), builder.Delay({&#124;cexpr &#124;})</code>|
|<code>{&#124; try cexpr with &#124; pattern_i -> expr_i &#124;}</code>|<code>builder.TryWith(builder.Delay({&#124; cexpr &#124;}), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{&#124; try cexpr finally expr &#124;}</code>|<code>builder.TryFinally(builder.Delay( {&#124; cexpr &#124;}), (fun () -> expr))</code>|
|<code>{&#124; cexpr1; cexpr2 &#124;}</code>|<code>builder.Combine({&#124;cexpr1 &#124;}, {&#124; cexpr2 &#124;})</code>|
|<code>{&#124; other-expr; cexpr &#124;}</code>|<code>expr; {&#124; cexpr &#124;}</code>|
|<code>{&#124; other-expr &#124;}</code>|`expr; builder.Zero()`|
이전 표에 `other-expr` 그렇지 않은 경우 테이블에 나열 되지 않은 식에 설명 합니다. 작성기 클래스는 모든 메서드를 구현 하 고 이전 표에 나열 된 번역의 모든 지원 필요가 없습니다. 구현 되지 않은 이러한 구문 형식의 계산 식에서 사용할 수 없는 경우 예를 들어, 지원 하지 않을 경우 합니다 `use` 계산 식에서 키워드의 정의 생략할 수 있습니다 `Use` 작성기 클래스에 있습니다.

다음 코드 예제에는 일련의 단계는 한 번에 한 번 계산한 계산을 캡슐화 하는 계산 식을 보여 줍니다. 공용 구조체 형식 구별 된 `OkOrException`, 지금까지 계산한 식의 오류 상태를 인코딩합니다. 이 코드를 상용구 구현의 일부 작성기 메서드 같은 계산 식에서 사용할 수 있는 몇 가지 일반적인 패턴을 보여 줍니다.

```fsharp
// Computations that can be run step by step
type Eventually<'T> =
    | Done of 'T
    | NotYetDone of (unit -> Eventually<'T>)

module Eventually =
    // The bind for the computations. Append 'func' to the
    // computation.
    let rec bind func expr =
        match expr with
        | Done value -> NotYetDone (fun () -> func value)
        | NotYetDone work -> NotYetDone (fun () -> bind func (work()))

    // Return the final value wrapped in the Eventually type.
    let result value = Done value

    type OkOrException<'T> =
        | Ok of 'T
        | Exception of System.Exception

    // The catch for the computations. Stitch try/with throughout
    // the computation, and return the overall result as an OkOrException.
    let rec catch expr =
        match expr with
        | Done value -> result (Ok value)
        | NotYetDone work ->
            NotYetDone (fun () ->
                let res = try Ok(work()) with | exn -> Exception exn
                match res with
                | Ok cont -> catch cont // note, a tailcall
                | Exception exn -> result (Exception exn))

    // The delay operator.
    let delay func = NotYetDone (fun () -> func())

    // The stepping action for the computations.
    let step expr =
        match expr with
        | Done _ -> expr
        | NotYetDone func -> func ()

    // The rest of the operations are boilerplate.
    // The tryFinally operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryFinally expr compensation =
        catch (expr)
        |> bind (fun res -> 
            compensation();
            match res with
            | Ok value -> result value
            | Exception exn -> raise exn)

    // The tryWith operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryWith exn handler =
        catch exn
        |> bind (function Ok value -> result value | Exception exn -> handler exn)

    // The whileLoop operator.
    // This is boilerplate in terms of "result" and "bind".
    let rec whileLoop pred body =
        if pred() then body |> bind (fun _ -> whileLoop pred body)
        else result ()

    // The sequential composition operator.
    // This is boilerplate in terms of "result" and "bind".
    let combine expr1 expr2 =
        expr1 |> bind (fun () -> expr2)

    // The using operator.
    let using (resource: #System.IDisposable) func =
        tryFinally (func resource) (fun () -> resource.Dispose())

    // The forLoop operator.
    // This is boilerplate in terms of "catch", "result", and "bind".
    let forLoop (collection:seq<_>) func =
        let ie = collection.GetEnumerator()
        tryFinally 
            (whileLoop 
                (fun () -> ie.MoveNext()) 
                (delay (fun () -> let value = ie.Current in func value)))
            (fun () -> ie.Dispose())

// The builder class.
type EventuallyBuilder() =
    member x.Bind(comp, func) = Eventually.bind func comp
    member x.Return(value) = Eventually.result value
    member x.ReturnFrom(value) = value
    member x.Combine(expr1, expr2) = Eventually.combine expr1 expr2
    member x.Delay(func) = Eventually.delay func
    member x.Zero() = Eventually.result ()
    member x.TryWith(expr, handler) = Eventually.tryWith expr handler
    member x.TryFinally(expr, compensation) = Eventually.tryFinally expr compensation
    member x.For(coll:seq<_>, func) = Eventually.forLoop coll func
    member x.Using(resource, expr) = Eventually.using resource expr

let eventually = new EventuallyBuilder()

let comp = eventually {
    for x in 1..2 do
        printfn " x = %d" x
    return 3 + 4 }

// Try the remaining lines in F# interactive to see how this 
// computation expression works in practice.
let step x = Eventually.step x

// returns "NotYetDone <closure>"
comp |> step

// prints "x = 1"
// returns "NotYetDone <closure>"
comp |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "NotYetDone <closure>"
comp |> step |> step |> step |> step |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step |> step |> step |> step |> step
```

계산 식에는 식을 반환 하는 내부 형식을 있습니다. 계산된 결과 또는 지연 된 계산을 수행할 수 있는 기본 형식을 나타낼 수 또는 일종의 컬렉션을 반복 하는 방법을 제공할 수 있습니다. 이전 예제에서는 기본 형식이 되었습니다 **결국**합니다. 시퀀스 식에 대 한 기본 형식은 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>합니다. 쿼리 식에 대 한 기본 형식은 <xref:System.Linq.IQueryable?displayProperty=nameWithType>합니다. 비동기 워크플로에 대 한 기본 형식은 [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)합니다. `Async` 개체 결과 계산 하기 위해 수행 해야 하는 작업을 나타냅니다. 호출 하는 예를 들어 [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) 계산을 실행 하 고 결과 반환 합니다.

## <a name="custom-operations"></a>사용자 지정 작업
계산 식에서 사용자 지정 작업을 정의 하 고 계산 식의 연산자와 사용자 지정 작업을 사용할 수 있습니다. 예를 들어, 쿼리 식에는 쿼리 연산자를 포함할 수 있습니다. 사용자 지정 작업을 정의할 때 결과 정의 해야 하 고 계산 식에서 메서드에 대 한 합니다. 사용자 지정 작업을 정의 하려면 계산 식 작성기 클래스에 배치 하 고 적용 합니다는 [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)합니다. 이 특성은이 사용자 지정 작업에 사용할 이름을 인수로 문자열입니다. 이 이름은 여는 중괄호 계산 식의 시작 범위에 제공 됩니다. 따라서이 블록의 사용자 지정 작업으로 동일한 이름을 가진 식별자 사용할 수 없습니다. 예를 들어, 같은 식별자를 사용 하지 않도록 `all` 또는 `last` 쿼리 식에 있습니다.

### <a name="extending-existing-builders-with-new-custom-operations"></a>새 사용자 지정 작업을 사용 하 여 기존 작성기 확장
작성기 클래스에 이미 있는 경우이 작성기 클래스 외부에서 사용자 지정 작업을 확장할 수 있습니다. 확장 모듈에서 선언 되어야 합니다. 네임 스페이스는 제외 하 고 동일한 파일에는 형식이 정의 되어 있는 동일한 네임 스페이스 선언 그룹 확장 멤버를 포함할 수 없습니다.

다음 예제에서는 기존 확장 `Microsoft.FSharp.Linq.QueryBuilder` 클래스입니다.

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[비동기 워크플로](asynchronous-workflows.md)

[시퀀스](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[쿼리 식](query-expressions.md)
