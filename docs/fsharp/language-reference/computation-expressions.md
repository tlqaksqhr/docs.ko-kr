---
title: 계산 식(F#)
description: '제어 흐름 구문 및 바인딩을 사용 하 여 결합 하 고 시퀀스를 지정할 수 있는 F #에서 계산을 작성 하기 위한 편리한 구문을 만드는 방법에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: a4ddb3fde284452bc901c5270551611e43742c1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="computation-expressions"></a>계산 식

F #에서 계산 식 시퀀스를 지정할 수 있으며 제어 흐름 구문 바인딩을 사용 하 여 결합 된 계산을 작성 하기 위한 편리한 구문을 제공 합니다. 에 대 한 편리한 구문 하 게 사용할 수 *monads*, 데이터, 제어 및 기능 프로그램에서 부작용을 관리 하는 데 사용할 수 있는 함수형 프로그래밍 기능입니다.


## <a name="built-in-workflows"></a>기본 제공 워크플로
시퀀스 식은 비동기 워크플로 및 쿼리 식 이므로 계산 식의 예입니다. 자세한 내용은 참조 [시퀀스](sequences.md), [비동기 워크플로](asynchronous-workflows.md), 및 [쿼리 식](query-expressions.md)합니다.

특정 시퀀스 식 및 비동기 워크플로 모두에 공통 된 기능과 계산 식에 대 한 기본 구문을 보여 줍니다.

```fsharp
builder-name { expression }
```

위 구문 지정된 된 식에서 지정 된 형식의 계산 식 임을 지정 *작성기 이름을*합니다. 계산 식 기본 제공 워크플로 같은 수 `seq` 또는 `async`, 정의 워크플로가 될 수 있습니다. *작성기 이름을* 라고 하는 특별 한 유형의 인스턴스에 대 한 식별자는 *작성기 형식을*합니다. 작성기 형식은 식이 실행 되는 방식을 제어 하는 방법은 계산 식의 조각을 결합 되어, 즉, 코드를 제어 하는 특수 메서드를 정의 하는 클래스 형식이입니다. 작성기 클래스를 설명 하는 다른 방법은 사용할 수 있는 것의 루프나 바인딩 등과 같은 많은 F # 구문, 작업을 사용자 지정할 수 있습니다 하입니다.

계산 식의 두 가지 형태는 몇 가지 일반적인 언어 구문에 대해 사용할 수 있습니다. 특정 키워드를 사용 하 여 수 있습니다는! (느낌표)와 같은 특정 키워드에 접미사 `let!`, `do!`등입니다. 이러한 특수 형식을 사용 하면 이러한 작업의 기본 제공 일반 동작을 바꿀 수 작성기 클래스에 정의 된 특정 기능입니다. 이러한 폼 유사는 `yield!` 형태의 `yield` 시퀀스 식에 사용 되는 키워드입니다. 자세한 내용은 참조 [시퀀스](sequences.md)합니다.


## <a name="creating-a-new-type-of-computation-expression"></a>계산 식의 새 형식 만들기
작성기 클래스를 만들고 클래스에 한 특수 메서드를 정의 하 여 사용자 고유의 계산 식의 특징을 정의할 수 있습니다. 필요에 따라 작성기 클래스는 다음 표에 나열 된 메서드를 정의할 수 있습니다.

다음 표에서 워크플로 작성기 클래스에 사용할 수 있는 메서드를 설명 합니다.


|**메서드**|**형식 시그니처**|**설명**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|에 대 한 호출 `let!` 및 `do!` 계산 식에 있습니다.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|계산 식 함수를 래핑합니다.|
|`Return`|`'T -> M<'T>`|에 대 한 호출 `return` 계산 식에 있습니다.|
|`ReturnFrom`|`M<'T> -> M<'T>`|에 대 한 호출 `return!` 계산 식에 있습니다.|
|`Run`|`M<'T> -> M<'T>` 또는<br /><br />`M<'T> -> 'T`|계산 식을 실행합니다.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` 또는<br /><br />`M<unit> * M<'T> -> M<'T>`|계산 식에는 시퀀스에 대 한 호출 됩니다.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` 또는<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|에 대 한 호출 `for...do` 계산 식에는 식입니다.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|에 대 한 호출 `try...finally` 계산 식에는 식입니다.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|에 대 한 호출 `try...with` 계산 식에는 식입니다.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|에 대 한 호출 `use` 계산 식의 바인딩.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|에 대 한 호출 `while...do` 계산 식에는 식입니다.|
|`Yield`|`'T -> M<'T>`|에 대 한 호출 `yield` 계산 식에는 식입니다.|
|`YieldFrom`|`M<'T> -> M<'T>`|에 대 한 호출 `yield!` 계산 식에는 식입니다.|
|`Zero`|`unit -> M<'T>`|비어 있는 대해 호출 `else` 의 분기 `if...then` 계산 식에는 식입니다.|
사용 및 반환 작성기 클래스의 메서드는 다양 한 `M<'T>` 구문을 일반적으로 예를 들어 조합 하는 계산의 종류를 지정 하는 별도로 정의 된 형식, `Async<'T>` 비동기 워크플로와 및 `Seq<'T>` 에 대 한 시퀀스 워크플로입니다. 이러한 메서드의 시그니처 마다 하나의 구성에서 반환 되는 워크플로 개체를 전달할 수 있도록 결합 하 고 서로 중첩할 수 있도록 합니다. 계산 식 구문 분석할 때 컴파일러는 일련의 중첩 된 함수 호출 식 앞의 표에 메서드 및 계산 식의 코드를 사용 하 여 변환 합니다.

중첩 된 식은 다음과 같은 형식입니다.

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

위의 코드에 대 한 호출에서 `Run` 및 `Delay` 계산 식 작성기 클래스에 정의 되지 않은 경우 생략 됩니다. 여기로 표시 된 계산 식의 본문 `{| cexpr |}`, 다음 표에 설명 된 번역에서 작성기 클래스의 메서드를 포함 하는 호출으로 변환 됩니다. 계산 식 `{| cexpr |}` 가 이러한 변환에 따라 정의 된 재귀적으로 여기서 `expr` 은 F # 식 및 `cexpr` 계산 식입니다.



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
앞의 표에 `other-expr` 그렇지 않은 경우 테이블에 나열 되어 있지 않은 식에 설명 합니다. 작성기 클래스의 모든 메서드를 구현 하 고 앞의 표에 나열 된 번역의 일부를 지원 하려면 필요는 없습니다. 구현 되지 않은 이러한 구문과 해당 유형의 계산 식에 사용할 수 있습니다. 예를 들어, 지원 하지 않을 경우는 `use` 계산 식에서 키워드의 정의 생략할 수 있습니다 `Use` 작성기 클래스에 있습니다.

다음 코드 예제에는 일련의 일 수 있는 단계를 한 번에 한 번 계산한 계산을 캡슐화 하는 계산 식을 보여 줍니다. 공용 구조체 형식 구별 된 `OkOrException`, 지금까지 계산 되는 식의 오류 상태를 인코딩합니다. 이 코드에서는 작성기 메서드 중 일부의 상용구 구현과 같은, 계산 식에서 사용할 수 있는 몇 가지 일반적인 패턴을 보여 줍니다.

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

계산 식에 식에서 반환 하는 내부 형식이 있습니다. 계산 된 결과 또는 지연 된 계산을 수행할 수 있는 내부 형식을 나타낼 수 있습니다 또는 특정 유형의 컬렉션을 반복 하는 방법을 제공할 수 있습니다. 이전 예에서는 기본 형식이 이었습니다 **결국**합니다. 시퀀스 식에 대 한 내부 형식이 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>합니다. 쿼리 식에 대 한 내부 형식이 <xref:System.Linq.IQueryable?displayProperty=nameWithType>합니다. 비동기 워크플로에 대 한 내부 형식이 [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)합니다. `Async` 개체는 결과 계산 하기 위해 수행 하는 작업을 나타냅니다. 호출 하는 예를 들어 [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) 계산을 실행 하 고 결과 반환 합니다.

## <a name="custom-operations"></a>사용자 지정 작업
계산 식에서 사용자 지정 작업을 정의 하 고 계산 식의 연산자와 사용자 지정 작업을 사용 하 여 수 있습니다. 예를 들어 쿼리 식에는 쿼리 연산자를 포함할 수 있습니다. 결과 정의 해야 합니다는 사용자 지정 작업을 정의할 때 및 계산 식의 메서드에 대 한 합니다. 사용자 지정 작업을 정의 하려면 계산 식에 대 한 작성기 클래스에 배치 하 고 다음 적용 하는 [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)합니다. 이 특성은이 사용자 지정 작업에 사용할 이름을 인수로 문자열입니다. 이 이름은 계산 식의 여는 중괄호의 시작 부분에 범위에 제공 됩니다. 따라서이 블록의 사용자 지정 작업으로 동일한 이름을 가진 식별자가 사용 하지 않아야 합니다. 예를 들어 같은 식별자의 사용을 방지 `all` 또는 `last` 쿼리 식에 있습니다.

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[비동기 워크플로](asynchronous-workflows.md)

[시퀀스](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[쿼리 식](query-expressions.md)
