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
# <a name="computation-expressions"></a><span data-ttu-id="d85aa-103">계산 식</span><span class="sxs-lookup"><span data-stu-id="d85aa-103">Computation Expressions</span></span>

<span data-ttu-id="d85aa-104">F # 계산 식을 제어 흐름 구문 및 바인딩을 사용 하 여 결합 및 시퀀싱 할 수 있는 계산을 작성 하는 것에 대 한 간편한 구문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="d85aa-105">계산 식의 종류에 따라 이러한 생각할 수 있습니다 monads, monoids, monad 변환기 및 applicative 함수를 표현 하는 방법으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="d85aa-106">그러나 다른 언어와 달리 (같은 *do 표기법* Haskell에서), 단일 추상화를 얽매여 있지 않는 하며 매크로 또는 다른 형태의에 의존 하지 마십시오 편리 하 고 상황에 맞는 구문을 위해 메타 프로그래밍 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="d85aa-107">개요</span><span class="sxs-lookup"><span data-stu-id="d85aa-107">Overview</span></span>

<span data-ttu-id="d85aa-108">계산이 많은 형식을 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-108">Computations can take many forms.</span></span> <span data-ttu-id="d85aa-109">계산의 가장 일반적인 형식은 쉽게 이해 하 고 수정할 수 있는 단일 스레드 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="d85aa-110">그러나 일부 형태의 계산은 단일 스레드 실행으로 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="d85aa-111">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-111">Some examples include:</span></span>

* <span data-ttu-id="d85aa-112">명확 하지 않은 계산</span><span class="sxs-lookup"><span data-stu-id="d85aa-112">Non-deterministic computations</span></span>
* <span data-ttu-id="d85aa-113">비동기 계산</span><span class="sxs-lookup"><span data-stu-id="d85aa-113">Asynchronous computations</span></span>
* <span data-ttu-id="d85aa-114">Effectful 계산</span><span class="sxs-lookup"><span data-stu-id="d85aa-114">Effectful computations</span></span>
* <span data-ttu-id="d85aa-115">인기 계산</span><span class="sxs-lookup"><span data-stu-id="d85aa-115">Generative computations</span></span>

<span data-ttu-id="d85aa-116">일반적으로 더 *상황에 맞는* 응용 프로그램의 특정 부분에서 수행 해야 하는 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="d85aa-117">상황에 맞는 코드를 작성이 이므로 이렇게 않도록 하는 추상화 하지 않고 지정된 된 컨텍스트 외부에서 "누수" 계산 하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="d85aa-118">이러한 추상화는 F #에 수행 하는 일반화 된 방법은 소위 이유는 직접 쓸 까다로운 것은 종종 **계산 식**합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="d85aa-119">계산 식 상황에 맞는 계산 인코딩에 대 한 구문 및 추상화 한 균일 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="d85aa-120">모든 계산 식에서 지원 되는 *작성기* 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="d85aa-121">작성기 형식을 계산 식에 사용할 수 있는 작업을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="d85aa-122">참조 [계산 식의 새 형식 만들기](computation-expressions.md#creating-a-new-type-of-computation-expression), 사용자 지정 계산 식을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="d85aa-123">구문 개요</span><span class="sxs-lookup"><span data-stu-id="d85aa-123">Syntax overview</span></span>

<span data-ttu-id="d85aa-124">다음 형식 이어야 하는 모든 계산 식:</span><span class="sxs-lookup"><span data-stu-id="d85aa-124">All computation expressions have the following form:</span></span>

```
builder-expr { cexper }
```

<span data-ttu-id="d85aa-125">여기서 `builder-expr` 계산 식을 정의 하는 작성기 형식 이름인 및 `cexper` 계산 식의 식 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="d85aa-126">예를 들어 `async` 계산 식 코드가 있습니다.이 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="d85aa-127">구문은 특수 한 추가 계산 식에서 사용할 수 있는 이전 예제에 표시 된 대로입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="d85aa-128">다음과 같은 식을 계산 식을 사용 하 여 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="d85aa-129">각 이러한 키워드 및 다른 표준 F # 키워드는 지원 작성기 형식에서 정의한 경우에 계산 식에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="d85aa-130">이 유일한 예외는 `match!`에 자체를 사용 하기 위한 syntactic sugar `let!` 패턴 일치 결과에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="d85aa-131">작성기 유형이 계산 식 조각의; 결합 하는 방법을 제어 하는 특수 메서드를 정의 하는 개체 즉, 해당 메서드 계산 식의 동작 방식을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="d85aa-132">다른 작성기 클래스를 설명 방법은 사용할 수 있는 것의 루프 및 바인딩 같은 많은 F # 구문, 작업을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="d85aa-133">`let!` 키워드 이름에 다른 계산 식에 대 한 호출의 결과 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="d85aa-134">사용 하 여 계산 식에 대 한 호출을 바인딩할 경우 `let`, 계산 식의 결과 가져오지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="d85aa-135">대신는 바인딩한의 값을 *표시 되지 않은* 해당 계산 식으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="d85aa-136">사용 하 여 `let!` 결과에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="d85aa-137">`let!` 정의한는 `Bind(x, f)` 작성기 형식 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="d85aa-138">합니다 `do!` 키워드는 반환 하는 계산 식 호출에 대 한는 `unit`-형식 처럼 (정의한는 `Zero` 작성기의 멤버):</span><span class="sxs-lookup"><span data-stu-id="d85aa-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! sumbitData data url
        ...
    }
```

<span data-ttu-id="d85aa-139">에 대 한 합니다 [비동기 워크플로](asynchronous-workflows.md),이 형식은 `Async<unit>`합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="d85aa-140">기타 계산 식 형식은 짧을 수 `CExpType<unit>`입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="d85aa-141">`do!` 정의한를 `Bind(x, f)` 작성기 형식에서 멤버 위치 `f` 생성을 `unit`입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="d85aa-142">합니다 `yield` 키워드를 사용할 수 있도록 계산 식에서 값을 반환 하는 데는 <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="d85aa-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="d85aa-143">와 마찬가지로 합니다 [yield 키워드에서 C#](../../csharp/language-reference/keywords/yield.md), 반복 될 때마다 계산 식의 각 요소가 생성 될 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-143">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="d85aa-144">`yield` 정의한를 `Yield(x)` 작성기 형식에서 멤버 위치 `x` 항목을 다시 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-144">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="d85aa-145">`yield!` 키워드는 계산 식에서 값의 컬렉션을 평면화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-145">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

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

<span data-ttu-id="d85aa-146">계산 식에서 호출을 평가할 때 `yield!` 는 해당 항목 생성 백--하나씩 결과 평면화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-146">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="d85aa-147">`yield!` 정의한 합니다 `YieldFrom(x)` 작성기 형식에서 멤버 위치 `x` 값의 컬렉션인 경우.</span><span class="sxs-lookup"><span data-stu-id="d85aa-147">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

### `return`

<span data-ttu-id="d85aa-148">`return` 키워드 계산 식에 해당 하는 형식의 값을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-148">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="d85aa-149">사용 하 여 계산 식 외에도 `yield`, 계산 식 "완료"로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-149">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="d85aa-150">`return` 정의한 합니다 `Return(x)` 작성기 형식에서 멤버 위치 `x` 래핑할 항목이 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-150">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="d85aa-151">`return!` 키워드 계산 식의 값을 인식 하 고 계산 식에 해당 하는 형식에 해당 결과 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-151">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="d85aa-152">`return!` 정의한를 `ReturnFrom(x)` 작성기 형식에서 멤버 위치 `x` 다른 계산 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-152">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="d85aa-153">F # 4.5부터는 `match!` 키워드를 사용 하면 인라인 해당 결과에 다른 계산 식 및 패턴 일치에 대 한 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-153">Starting with F# 4.5, the `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="d85aa-154">포함 하는 계산 식을 호출할 때 `match!`와 같은 호출의 결과 실현 됩니다 `let!`합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-154">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="d85aa-155">이 대개 여기서 결과 계산 식을 호출 하는 경우는 [선택적](options.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-155">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="d85aa-156">기본 제공 계산 식</span><span class="sxs-lookup"><span data-stu-id="d85aa-156">Built-in computation expressions</span></span>

<span data-ttu-id="d85aa-157">F # 핵심 라이브러리는 세 개의 기본 제공 계산 식을 정의 합니다. [시퀀스 식](sequences.md), [비동기 워크플로](asynchronous-workflows.md), 및 [쿼리 식](query-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-157">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="d85aa-158">계산 식의 새 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="d85aa-158">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="d85aa-159">작성기 클래스를 만들고 클래스에 대 한 특수 메서드를 정의 하 여 사용자 고유의 계산 식의 특징을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-159">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="d85aa-160">필요에 따라 작성기 클래스는 다음 표에 나열 된 대로 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-160">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="d85aa-161">다음 표에서 워크플로 작성기 클래스에서 사용할 수 있는 메서드를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-161">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="d85aa-162">**메서드**</span><span class="sxs-lookup"><span data-stu-id="d85aa-162">**Method**</span></span>|<span data-ttu-id="d85aa-163">**형식 시그니처**</span><span class="sxs-lookup"><span data-stu-id="d85aa-163">**Typical signature(s)**</span></span>|<span data-ttu-id="d85aa-164">**설명**</span><span class="sxs-lookup"><span data-stu-id="d85aa-164">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="d85aa-165">에 대 한 호출 `let!` 고 `do!` 계산 식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-165">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="d85aa-166">계산 식을 함수로 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-166">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="d85aa-167">에 대 한 호출 `return` 계산 식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-167">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="d85aa-168">에 대 한 호출 `return!` 계산 식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-168">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="d85aa-169">`M<'T> -> M<'T>` 또는</span><span class="sxs-lookup"><span data-stu-id="d85aa-169">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="d85aa-170">계산 식을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-170">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="d85aa-171">`M<'T> * M<'T> -> M<'T>` 또는</span><span class="sxs-lookup"><span data-stu-id="d85aa-171">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="d85aa-172">계산 식의 시퀀싱에 대 한 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-172">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="d85aa-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` 또는</span><span class="sxs-lookup"><span data-stu-id="d85aa-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="d85aa-174">에 대 한 호출 `for...do` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-174">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="d85aa-175">에 대 한 호출 `try...finally` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-175">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="d85aa-176">에 대 한 호출 `try...with` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-176">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="d85aa-177">에 대 한 호출 `use` 계산 식의 바인딩.</span><span class="sxs-lookup"><span data-stu-id="d85aa-177">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="d85aa-178">에 대 한 호출 `while...do` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-178">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="d85aa-179">에 대 한 호출 `yield` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-179">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="d85aa-180">에 대 한 호출 `yield!` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-180">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="d85aa-181">빈 호출 `else` 의 분기 `if...then` 계산 식에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-181">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|

<span data-ttu-id="d85aa-182">대부분의 작성기 클래스에서 메서드를 사용 및 반환을 `M<'T>` 는 일반적으로 예를 들어 조합 하는 계산의 종류를 지정 하는 별도로 정의 된 형식, 구문 `Async<'T>` 비동기 워크플로와 및 `Seq<'T>` 시퀀스 워크플로에 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-182">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="d85aa-183">다음 하나의 구문에서 반환 되는 워크플로 개체를 전달할 수 있도록 이러한 메서드의 시그니처는 결합 하 고 서로 중첩 될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-183">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="d85aa-184">계산 식 구문 분석할 때 컴파일러는 앞의 표에 메서드 및 계산 식의 코드를 사용 하 여 일련의 중첩 된 함수 호출에 식을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-184">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="d85aa-185">중첩 된 식은 다음과 같습니다. 다음 형식의</span><span class="sxs-lookup"><span data-stu-id="d85aa-185">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="d85aa-186">위의 코드에 대 한 호출에서 `Run` 고 `Delay` 계산 식 작성기 클래스에 정의 되지 않은 경우 생략 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-186">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="d85aa-187">여기로 표시, 계산 식의 본문이 `{| cexpr |}`, 다음 표에 설명 된 번역으로 작성기 클래스의 메서드를 포함 하는 호출으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-187">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="d85aa-188">계산 식 `{| cexpr |}` 가 이러한 변환에 따라 정의 된 재귀적으로 위치 `expr` F # 식 및 `cexpr` 계산 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-188">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>



|<span data-ttu-id="d85aa-189">식</span><span class="sxs-lookup"><span data-stu-id="d85aa-189">Expression</span></span>|<span data-ttu-id="d85aa-190">변환</span><span class="sxs-lookup"><span data-stu-id="d85aa-190">Translation</span></span>|
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
<span data-ttu-id="d85aa-191">이전 표에 `other-expr` 그렇지 않은 경우 테이블에 나열 되지 않은 식에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-191">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="d85aa-192">작성기 클래스는 모든 메서드를 구현 하 고 이전 표에 나열 된 번역의 모든 지원 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-192">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="d85aa-193">구현 되지 않은 이러한 구문 형식의 계산 식에서 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="d85aa-193">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="d85aa-194">예를 들어, 지원 하지 않을 경우 합니다 `use` 계산 식에서 키워드의 정의 생략할 수 있습니다 `Use` 작성기 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-194">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="d85aa-195">다음 코드 예제에는 일련의 단계는 한 번에 한 번 계산한 계산을 캡슐화 하는 계산 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-195">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="d85aa-196">공용 구조체 형식 구별 된 `OkOrException`, 지금까지 계산한 식의 오류 상태를 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-196">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="d85aa-197">이 코드를 상용구 구현의 일부 작성기 메서드 같은 계산 식에서 사용할 수 있는 몇 가지 일반적인 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-197">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="d85aa-198">계산 식에는 식을 반환 하는 내부 형식을 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-198">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="d85aa-199">계산된 결과 또는 지연 된 계산을 수행할 수 있는 기본 형식을 나타낼 수 또는 일종의 컬렉션을 반복 하는 방법을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-199">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="d85aa-200">이전 예제에서는 기본 형식이 되었습니다 **결국**합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-200">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="d85aa-201">시퀀스 식에 대 한 기본 형식은 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-201">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d85aa-202">쿼리 식에 대 한 기본 형식은 <xref:System.Linq.IQueryable?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-202">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d85aa-203">비동기 워크플로에 대 한 기본 형식은 [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-203">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="d85aa-204">`Async` 개체 결과 계산 하기 위해 수행 해야 하는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-204">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="d85aa-205">호출 하는 예를 들어 [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) 계산을 실행 하 고 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-205">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="d85aa-206">사용자 지정 작업</span><span class="sxs-lookup"><span data-stu-id="d85aa-206">Custom Operations</span></span>
<span data-ttu-id="d85aa-207">계산 식에서 사용자 지정 작업을 정의 하 고 계산 식의 연산자와 사용자 지정 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-207">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="d85aa-208">예를 들어, 쿼리 식에는 쿼리 연산자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-208">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="d85aa-209">사용자 지정 작업을 정의할 때 결과 정의 해야 하 고 계산 식에서 메서드에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-209">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="d85aa-210">사용자 지정 작업을 정의 하려면 계산 식 작성기 클래스에 배치 하 고 적용 합니다는 [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-210">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="d85aa-211">이 특성은이 사용자 지정 작업에 사용할 이름을 인수로 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-211">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="d85aa-212">이 이름은 여는 중괄호 계산 식의 시작 범위에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-212">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="d85aa-213">따라서이 블록의 사용자 지정 작업으로 동일한 이름을 가진 식별자 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-213">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="d85aa-214">예를 들어, 같은 식별자를 사용 하지 않도록 `all` 또는 `last` 쿼리 식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-214">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="d85aa-215">새 사용자 지정 작업을 사용 하 여 기존 작성기 확장</span><span class="sxs-lookup"><span data-stu-id="d85aa-215">Extending existing Builders with new Custom Operations</span></span>
<span data-ttu-id="d85aa-216">작성기 클래스에 이미 있는 경우이 작성기 클래스 외부에서 사용자 지정 작업을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-216">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="d85aa-217">확장 모듈에서 선언 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-217">Extensions must be declared in modules.</span></span> <span data-ttu-id="d85aa-218">네임 스페이스는 제외 하 고 동일한 파일에는 형식이 정의 되어 있는 동일한 네임 스페이스 선언 그룹 확장 멤버를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-218">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="d85aa-219">다음 예제에서는 기존 확장 `Microsoft.FSharp.Linq.QueryBuilder` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d85aa-219">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="d85aa-220">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d85aa-220">See Also</span></span>
[<span data-ttu-id="d85aa-221">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="d85aa-221">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="d85aa-222">비동기 워크플로</span><span class="sxs-lookup"><span data-stu-id="d85aa-222">Asynchronous Workflows</span></span>](asynchronous-workflows.md)

[<span data-ttu-id="d85aa-223">시퀀스</span><span class="sxs-lookup"><span data-stu-id="d85aa-223">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[<span data-ttu-id="d85aa-224">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="d85aa-224">Query Expressions</span></span>](query-expressions.md)
