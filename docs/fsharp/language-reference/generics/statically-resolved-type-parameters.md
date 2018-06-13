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
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="f2590-103">정적으로 확인된 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="f2590-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="f2590-104">A *정적으로 확인 된 형식 매개 변수* 런타임이 아닌 컴파일 타임에 실제 형식으로 대체 되는 형식 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="f2590-105">캐럿 (^) 기호로 앞입니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-105">They are preceded by a caret (^) symbol.</span></span>


## <a name="syntax"></a><span data-ttu-id="f2590-106">구문</span><span class="sxs-lookup"><span data-stu-id="f2590-106">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="f2590-107">설명</span><span class="sxs-lookup"><span data-stu-id="f2590-107">Remarks</span></span>
<span data-ttu-id="f2590-108">F # 언어에서 두 가지 종류의 형식 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="f2590-109">첫 번째 표준 제네릭 형식 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="f2590-110">와 같이 아포스트로피 (')로 표시는 이러한 `'T` 및 `'U`합니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="f2590-111">다른.NET Framework 언어의 제네릭 형식 매개 변수와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="f2590-112">와 같이 캐럿 기호를 표시 된 정적으로 확인 된 다른 종류 이며 `^T` 및 `^U`합니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="f2590-113">정적으로 확인 된 형식 매개 변수는 제약 조건이 있어야 하도록 지정 하는 형식 인수가 특정 멤버 또는 멤버 사용할 수 있도록 하는 멤버 제약 조건과 함께에서 주로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="f2590-114">일반 제네릭 형식 매개 변수를 사용 하 여 이러한 종류의 제약 조건 만드는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="f2590-115">다음 표에서 유사성과 형식 매개 변수 중 두 가지 차이점이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="f2590-116">기능</span><span class="sxs-lookup"><span data-stu-id="f2590-116">Feature</span></span>|<span data-ttu-id="f2590-117">제네릭</span><span class="sxs-lookup"><span data-stu-id="f2590-117">Generic</span></span>|<span data-ttu-id="f2590-118">정적으로 확인 된</span><span class="sxs-lookup"><span data-stu-id="f2590-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="f2590-119">구문</span><span class="sxs-lookup"><span data-stu-id="f2590-119">Syntax</span></span>|<span data-ttu-id="f2590-120">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="f2590-120">`'T`, `'U`</span></span>|<span data-ttu-id="f2590-121">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="f2590-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="f2590-122">해결 시간</span><span class="sxs-lookup"><span data-stu-id="f2590-122">Resolution time</span></span>|<span data-ttu-id="f2590-123">런타임</span><span class="sxs-lookup"><span data-stu-id="f2590-123">Run time</span></span>|<span data-ttu-id="f2590-124">컴파일 시간</span><span class="sxs-lookup"><span data-stu-id="f2590-124">Compile time</span></span>|
|<span data-ttu-id="f2590-125">멤버 제약 조건</span><span class="sxs-lookup"><span data-stu-id="f2590-125">Member constraints</span></span>|<span data-ttu-id="f2590-126">멤버 제약 조건과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="f2590-127">멤버 제약 조건과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="f2590-128">코드 생성</span><span class="sxs-lookup"><span data-stu-id="f2590-128">Code generation</span></span>|<span data-ttu-id="f2590-129">표준 제네릭 형식 매개 변수가 있는 형식 (또는 메서드) 단일 제네릭 형식 또는 메서드의 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="f2590-130">여러 인스턴스는 형식 및 메서드 생성, 형식 마다 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="f2590-131">형식과 함께 사용</span><span class="sxs-lookup"><span data-stu-id="f2590-131">Use with types</span></span>|<span data-ttu-id="f2590-132">형식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-132">Can be used on types.</span></span>|<span data-ttu-id="f2590-133">형식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="f2590-134">인라인 함수와 함께 사용</span><span class="sxs-lookup"><span data-stu-id="f2590-134">Use with inline functions</span></span>|<span data-ttu-id="f2590-135">아니요.</span><span class="sxs-lookup"><span data-stu-id="f2590-135">No.</span></span> <span data-ttu-id="f2590-136">표준 제네릭 형식 매개 변수는 인라인 함수를 매개 변수화 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="f2590-137">예.</span><span class="sxs-lookup"><span data-stu-id="f2590-137">Yes.</span></span> <span data-ttu-id="f2590-138">정적으로 확인 된 형식 매개 변수는 함수나 인라인이 아닌 메서드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="f2590-139">많은 F # 핵심 라이브러리 함수, 특히 연산자는 형식 매개 변수 정적으로 확인 된 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="f2590-140">이러한 함수 및 연산자에는 인라인 및 숫자 계산에 대 한 효율적인 코드 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="f2590-141">인라인 메서드 및 연산자를 사용 하거나 형식 매개 변수를 정적으로 해결 된 다른 기능을 사용 하는 함수 자체 정적으로 확인 된 형식 매개 변수에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="f2590-142">종종 형식 유추와 같은 인라인 함수를 정적으로 확인 된 형식 매개 변수를 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="f2590-143">다음 예제는 정적으로 확인 된 형식 매개 변수가으로 유추 되는 연산자 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="f2590-144">형식이 확인된 `(+@)` 둘 다의 사용에 따라 `(+)` 및 `(*)`, 둘 다의 정적으로 확인 된 형식 매개 변수에 대 다 형식 유추 될 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="f2590-145">확인 된 형식, F # 인터프리터에 표시 된 대로 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="f2590-146">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-146">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="f2590-147">F # 4.1 부터는에 정적으로 확인 된 형식 매개 변수 서명과 구체적인 형식 이름의도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="f2590-148">언어의 이전 버전에서는 형식 이름 컴파일러에서 유추할 수 실제로 하지만 실제로 지정할 수 없습니다 서명에 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="f2590-149">4.1 F #을 기준으로 정적으로 확인 된 형식 매개 변수 시그니처에 구체적인 형식 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="f2590-150">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f2590-150">Here's an example:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f2590-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2590-151">See Also</span></span>
[<span data-ttu-id="f2590-152">제네릭</span><span class="sxs-lookup"><span data-stu-id="f2590-152">Generics</span></span>](index.md)

[<span data-ttu-id="f2590-153">형식 유추</span><span class="sxs-lookup"><span data-stu-id="f2590-153">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="f2590-154">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="f2590-154">Automatic Generalization</span></span>](automatic-generalization.md)

[<span data-ttu-id="f2590-155">제약 조건</span><span class="sxs-lookup"><span data-stu-id="f2590-155">Constraints</span></span>](constraints.md)

[<span data-ttu-id="f2590-156">인라인 함수</span><span class="sxs-lookup"><span data-stu-id="f2590-156">Inline Functions</span></span>](../functions/inline-functions.md)
