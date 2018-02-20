---
title: "계산 식(F#)"
description: "제어 흐름 구문 및 바인딩을 사용 하 여 결합 하 고 시퀀스를 지정할 수 있는 F #에서 계산을 작성 하기 위한 편리한 구문을 만드는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: acabbf5d-fbb8-479f-894c-7251bf16c8c3
ms.openlocfilehash: c4ff998c65f3a5c458f36312f6887d869569d814
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2018
---
# <a name="computation-expressions"></a><span data-ttu-id="e9cd9-104">계산 식</span><span class="sxs-lookup"><span data-stu-id="e9cd9-104">Computation Expressions</span></span>

<span data-ttu-id="e9cd9-105">F #에서 계산 식 시퀀스를 지정할 수 있으며 제어 흐름 구문 바인딩을 사용 하 여 결합 된 계산을 작성 하기 위한 편리한 구문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-105">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="e9cd9-106">에 대 한 편리한 구문 하 게 사용할 수 *monads*, 데이터, 제어 및 기능 프로그램에서 부작용을 관리 하는 데 사용할 수 있는 함수형 프로그래밍 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-106">They can be used to provide a convenient syntax for *monads*, a functional programming feature that can be used to manage data, control, and side effects in functional programs.</span></span>


## <a name="built-in-workflows"></a><span data-ttu-id="e9cd9-107">기본 제공 워크플로</span><span class="sxs-lookup"><span data-stu-id="e9cd9-107">Built-in Workflows</span></span>
<span data-ttu-id="e9cd9-108">시퀀스 식은 비동기 워크플로 및 쿼리 식 이므로 계산 식의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-108">Sequence expressions are an example of a computation expression, as are asynchronous workflows and query expressions.</span></span> <span data-ttu-id="e9cd9-109">자세한 내용은 참조 [시퀀스](sequences.md), [비동기 워크플로](asynchronous-workflows.md), 및 [쿼리 식](query-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-109">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

<span data-ttu-id="e9cd9-110">특정 시퀀스 식 및 비동기 워크플로 모두에 공통 된 기능과 계산 식에 대 한 기본 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-110">Certain features are common to both sequence expressions and asynchronous workflows and illustrate the basic syntax for a computation expression:</span></span>

```fsharp
builder-name { expression }
```

<span data-ttu-id="e9cd9-111">위 구문 지정된 된 식에서 지정 된 형식의 계산 식 임을 지정 *작성기 이름을*합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-111">The previous syntax specifies that the given expression is a computation expression of a type specified by *builder-name*.</span></span> <span data-ttu-id="e9cd9-112">계산 식 기본 제공 워크플로 같은 수 `seq` 또는 `async`, 정의 워크플로가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-112">The computation expression can be a built-in workflow, such as `seq` or `async`, or it can be something you define.</span></span> <span data-ttu-id="e9cd9-113">*작성기 이름을* 라고 하는 특별 한 유형의 인스턴스에 대 한 식별자는 *작성기 형식을*합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-113">The *builder-name* is the identifier for an instance of a special type known as the *builder type*.</span></span> <span data-ttu-id="e9cd9-114">작성기 형식은 식이 실행 되는 방식을 제어 하는 방법은 계산 식의 조각을 결합 되어, 즉, 코드를 제어 하는 특수 메서드를 정의 하는 클래스 형식이입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-114">The builder type is a class type that defines special methods that govern the way the fragments of the computation expression are combined, that is, code that controls how the expression executes.</span></span> <span data-ttu-id="e9cd9-115">작성기 클래스를 설명 하는 다른 방법은 사용할 수 있는 것의 루프나 바인딩 등과 같은 많은 F # 구문, 작업을 사용자 지정할 수 있습니다 하입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-115">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

<span data-ttu-id="e9cd9-116">계산 식의 두 가지 형태는 몇 가지 일반적인 언어 구문에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-116">In computation expressions, two forms are available for some common language constructs.</span></span> <span data-ttu-id="e9cd9-117">특정 키워드를 사용 하 여 수 있습니다는!</span><span class="sxs-lookup"><span data-stu-id="e9cd9-117">You can invoke the variant constructs by using a !</span></span> <span data-ttu-id="e9cd9-118">(느낌표)와 같은 특정 키워드에 접미사 `let!`, `do!`등입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-118">(bang) suffix on certain keywords, such as `let!`, `do!`, and so on.</span></span> <span data-ttu-id="e9cd9-119">이러한 특수 형식을 사용 하면 이러한 작업의 기본 제공 일반 동작을 바꿀 수 작성기 클래스에 정의 된 특정 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-119">These special forms cause certain functions defined in the builder class to replace the ordinary built-in behavior of these operations.</span></span> <span data-ttu-id="e9cd9-120">이러한 폼 유사는 `yield!` 형태의 `yield` 시퀀스 식에 사용 되는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-120">These forms resemble the `yield!` form of the `yield` keyword that is used in sequence expressions.</span></span> <span data-ttu-id="e9cd9-121">자세한 내용은 참조 [시퀀스](sequences.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-121">For more information, see [Sequences](sequences.md).</span></span>


## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="e9cd9-122">계산 식의 새 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="e9cd9-122">Creating a New Type of Computation Expression</span></span>
<span data-ttu-id="e9cd9-123">작성기 클래스를 만들고 클래스에 한 특수 메서드를 정의 하 여 사용자 고유의 계산 식의 특징을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-123">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="e9cd9-124">필요에 따라 작성기 클래스는 다음 표에 나열 된 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-124">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="e9cd9-125">다음 표에서 워크플로 작성기 클래스에 사용할 수 있는 메서드를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-125">The following table describes methods that can be used in a workflow builder class.</span></span>


|<span data-ttu-id="e9cd9-126">**메서드**</span><span class="sxs-lookup"><span data-stu-id="e9cd9-126">**Method**</span></span>|<span data-ttu-id="e9cd9-127">**형식 시그니처**</span><span class="sxs-lookup"><span data-stu-id="e9cd9-127">**Typical signature(s)**</span></span>|<span data-ttu-id="e9cd9-128">**설명**</span><span class="sxs-lookup"><span data-stu-id="e9cd9-128">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="e9cd9-129">에 대 한 호출 `let!` 및 `do!` 계산 식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-129">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="e9cd9-130">계산 식 함수를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-130">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="e9cd9-131">에 대 한 호출 `return` 계산 식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-131">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="e9cd9-132">에 대 한 호출 `return!` 계산 식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-132">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="e9cd9-133">`M<'T> -> M<'T>` 또는</span><span class="sxs-lookup"><span data-stu-id="e9cd9-133">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="e9cd9-134">계산 식을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-134">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="e9cd9-135">`M<'T> * M<'T> -> M<'T>` 또는</span><span class="sxs-lookup"><span data-stu-id="e9cd9-135">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="e9cd9-136">계산 식에는 시퀀스에 대 한 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-136">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="e9cd9-137">`seq<'T> * ('T -> M<'U>) -> M<'U>` 또는</span><span class="sxs-lookup"><span data-stu-id="e9cd9-137">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="e9cd9-138">에 대 한 호출 `for...do` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-138">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="e9cd9-139">에 대 한 호출 `try...finally` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-139">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="e9cd9-140">에 대 한 호출 `try...with` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-140">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="e9cd9-141">에 대 한 호출 `use` 계산 식의 바인딩.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-141">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="e9cd9-142">에 대 한 호출 `while...do` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-142">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="e9cd9-143">에 대 한 호출 `yield` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-143">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="e9cd9-144">에 대 한 호출 `yield!` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-144">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="e9cd9-145">비어 있는 대해 호출 `else` 의 분기 `if...then` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-145">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
<span data-ttu-id="e9cd9-146">사용 및 반환 작성기 클래스의 메서드는 다양 한 `M<'T>` 구문을 일반적으로 예를 들어 조합 하는 계산의 종류를 지정 하는 별도로 정의 된 형식, `Async<'T>` 비동기 워크플로와 및 `Seq<'T>` 에 대 한 시퀀스 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-146">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="e9cd9-147">이러한 메서드의 시그니처 마다 하나의 구성에서 반환 되는 워크플로 개체를 전달할 수 있도록 결합 하 고 서로 중첩할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-147">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="e9cd9-148">계산 식 구문 분석할 때 컴파일러는 일련의 중첩 된 함수 호출 식 앞의 표에 메서드 및 계산 식의 코드를 사용 하 여 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-148">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="e9cd9-149">중첩 된 식은 다음과 같은 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-149">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="e9cd9-150">위의 코드에 대 한 호출에서 `Run` 및 `Delay` 계산 식 작성기 클래스에 정의 되지 않은 경우 생략 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-150">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="e9cd9-151">여기로 표시 된 계산 식의 본문 `{| cexpr |}`, 다음 표에 설명 된 번역에서 작성기 클래스의 메서드를 포함 하는 호출으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-151">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="e9cd9-152">계산 식 `{| cexpr |}` 가 이러한 변환에 따라 정의 된 재귀적으로 여기서 `expr` 은 F # 식 및 `cexpr` 계산 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-152">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>



|<span data-ttu-id="e9cd9-153">식</span><span class="sxs-lookup"><span data-stu-id="e9cd9-153">Expression</span></span>|<span data-ttu-id="e9cd9-154">변환</span><span class="sxs-lookup"><span data-stu-id="e9cd9-154">Translation</span></span>|
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
<span data-ttu-id="e9cd9-155">앞의 표에 `other-expr` 그렇지 않은 경우 테이블에 나열 되어 있지 않은 식에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-155">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="e9cd9-156">작성기 클래스의 모든 메서드를 구현 하 고 앞의 표에 나열 된 번역의 일부를 지원 하려면 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-156">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="e9cd9-157">구현 되지 않은 이러한 구문과 해당 유형의 계산 식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-157">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="e9cd9-158">예를 들어, 지원 하지 않을 경우는 `use` 계산 식에서 키워드의 정의 생략할 수 있습니다 `Use` 작성기 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-158">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="e9cd9-159">다음 코드 예제에는 일련의 일 수 있는 단계를 한 번에 한 번 계산한 계산을 캡슐화 하는 계산 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-159">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="e9cd9-160">공용 구조체 형식 구별 된 `OkOrException`, 지금까지 계산 되는 식의 오류 상태를 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-160">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="e9cd9-161">이 코드에서는 작성기 메서드 중 일부의 상용구 구현과 같은, 계산 식에서 사용할 수 있는 몇 가지 일반적인 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-161">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="e9cd9-162">계산 식에 식에서 반환 하는 내부 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-162">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="e9cd9-163">계산 된 결과 또는 지연 된 계산을 수행할 수 있는 내부 형식을 나타낼 수 있습니다 또는 특정 유형의 컬렉션을 반복 하는 방법을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-163">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="e9cd9-164">이전 예에서는 기본 형식이 이었습니다 **결국**합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-164">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="e9cd9-165">시퀀스 식에 대 한 내부 형식이 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-165">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e9cd9-166">쿼리 식에 대 한 내부 형식이 <xref:System.Linq.IQueryable?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-166">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e9cd9-167">비동기 워크플로에 대 한 내부 형식이 [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-167">For an asychronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="e9cd9-168">`Async` 개체는 결과 계산 하기 위해 수행 하는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-168">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="e9cd9-169">호출 하는 예를 들어 [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) 계산을 실행 하 고 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-169">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="e9cd9-170">사용자 지정 작업</span><span class="sxs-lookup"><span data-stu-id="e9cd9-170">Custom Operations</span></span>
<span data-ttu-id="e9cd9-171">계산 식에서 사용자 지정 작업을 정의 하 고 계산 식의 연산자와 사용자 지정 작업을 사용 하 여 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-171">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="e9cd9-172">예를 들어 쿼리 식에는 쿼리 연산자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-172">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="e9cd9-173">결과 정의 해야 합니다는 사용자 지정 작업을 정의할 때 및 계산 식의 메서드에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-173">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="e9cd9-174">사용자 지정 작업을 정의 하려면 계산 식에 대 한 작성기 클래스에 배치 하 고 다음 적용 하는 [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-174">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="e9cd9-175">이 특성은이 사용자 지정 작업에 사용할 이름을 인수로 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-175">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="e9cd9-176">이 이름은 계산 식의 여는 중괄호의 시작 부분에 범위에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-176">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="e9cd9-177">따라서이 블록의 사용자 지정 작업으로 동일한 이름을 가진 식별자가 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-177">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="e9cd9-178">예를 들어 같은 식별자의 사용을 방지 `all` 또는 `last` 쿼리 식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9cd9-178">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9cd9-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9cd9-179">See Also</span></span>
[<span data-ttu-id="e9cd9-180">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="e9cd9-180">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="e9cd9-181">비동기 워크플로</span><span class="sxs-lookup"><span data-stu-id="e9cd9-181">Asynchronous Workflows</span></span>](asynchronous-workflows.md)

[<span data-ttu-id="e9cd9-182">시퀀스</span><span class="sxs-lookup"><span data-stu-id="e9cd9-182">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[<span data-ttu-id="e9cd9-183">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="e9cd9-183">Query Expressions</span></span>](query-expressions.md)
