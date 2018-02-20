---
title: "정적으로 확인된 형식 매개 변수(F#)"
description: "F #을 사용 하는 방법을 알아봅니다 런타임이 아닌 컴파일 타임에 실제 형식으로 대체 되는 정적으로 확인 된 형식 매개 변수입니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b3797415-3e49-4f8a-a8ee-fa614c5721aa
ms.openlocfilehash: 14c629d6223584113af47636495be61decca02ad
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2018
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="4553e-104">정적으로 확인된 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="4553e-104">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="4553e-105">A *정적으로 확인 된 형식 매개 변수* 런타임이 아닌 컴파일 타임에 실제 형식으로 대체 되는 형식 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-105">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="4553e-106">캐럿 (^) 기호로 앞입니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-106">They are preceded by a caret (^) symbol.</span></span>


## <a name="syntax"></a><span data-ttu-id="4553e-107">구문</span><span class="sxs-lookup"><span data-stu-id="4553e-107">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="4553e-108">설명</span><span class="sxs-lookup"><span data-stu-id="4553e-108">Remarks</span></span>
<span data-ttu-id="4553e-109">F # 언어에서 두 가지 종류의 형식 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-109">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="4553e-110">첫 번째 표준 제네릭 형식 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-110">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="4553e-111">와 같이 아포스트로피 (')로 표시는 이러한 `'T` 및 `'U`합니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-111">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="4553e-112">다른.NET Framework 언어의 제네릭 형식 매개 변수와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-112">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="4553e-113">와 같이 캐럿 기호를 표시 된 정적으로 확인 된 다른 종류 이며 `^T` 및 `^U`합니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-113">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="4553e-114">정적으로 확인 된 형식 매개 변수는 제약 조건이 있어야 하도록 지정 하는 형식 인수가 특정 멤버 또는 멤버 사용할 수 있도록 하는 멤버 제약 조건과 함께에서 주로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-114">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="4553e-115">일반 제네릭 형식 매개 변수를 사용 하 여 이러한 종류의 제약 조건 만드는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-115">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="4553e-116">다음 표에서 유사성과 형식 매개 변수 중 두 가지 차이점이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-116">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="4553e-117">기능</span><span class="sxs-lookup"><span data-stu-id="4553e-117">Feature</span></span>|<span data-ttu-id="4553e-118">제네릭</span><span class="sxs-lookup"><span data-stu-id="4553e-118">Generic</span></span>|<span data-ttu-id="4553e-119">정적으로 확인 된</span><span class="sxs-lookup"><span data-stu-id="4553e-119">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="4553e-120">구문</span><span class="sxs-lookup"><span data-stu-id="4553e-120">Syntax</span></span>|<span data-ttu-id="4553e-121">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="4553e-121">`'T`, `'U`</span></span>|<span data-ttu-id="4553e-122">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="4553e-122">`^T`, `^U`</span></span>|
|<span data-ttu-id="4553e-123">해결 시간</span><span class="sxs-lookup"><span data-stu-id="4553e-123">Resolution time</span></span>|<span data-ttu-id="4553e-124">런타임</span><span class="sxs-lookup"><span data-stu-id="4553e-124">Run time</span></span>|<span data-ttu-id="4553e-125">컴파일 시간</span><span class="sxs-lookup"><span data-stu-id="4553e-125">Compile time</span></span>|
|<span data-ttu-id="4553e-126">멤버 제약 조건</span><span class="sxs-lookup"><span data-stu-id="4553e-126">Member constraints</span></span>|<span data-ttu-id="4553e-127">멤버 제약 조건과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-127">Cannot be used with member constraints.</span></span>|<span data-ttu-id="4553e-128">멤버 제약 조건과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-128">Can be used with member constraints.</span></span>|
|<span data-ttu-id="4553e-129">코드 생성</span><span class="sxs-lookup"><span data-stu-id="4553e-129">Code generation</span></span>|<span data-ttu-id="4553e-130">표준 제네릭 형식 매개 변수가 있는 형식 (또는 메서드) 단일 제네릭 형식 또는 메서드의 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-130">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="4553e-131">여러 인스턴스는 형식 및 메서드 생성, 형식 마다 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-131">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="4553e-132">형식과 함께 사용</span><span class="sxs-lookup"><span data-stu-id="4553e-132">Use with types</span></span>|<span data-ttu-id="4553e-133">형식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-133">Can be used on types.</span></span>|<span data-ttu-id="4553e-134">형식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-134">Cannot be used on types.</span></span>|
|<span data-ttu-id="4553e-135">인라인 함수와 함께 사용</span><span class="sxs-lookup"><span data-stu-id="4553e-135">Use with inline functions</span></span>|<span data-ttu-id="4553e-136">아니요.</span><span class="sxs-lookup"><span data-stu-id="4553e-136">No.</span></span> <span data-ttu-id="4553e-137">표준 제네릭 형식 매개 변수는 인라인 함수를 매개 변수화 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-137">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="4553e-138">예.</span><span class="sxs-lookup"><span data-stu-id="4553e-138">Yes.</span></span> <span data-ttu-id="4553e-139">정적으로 확인 된 형식 매개 변수는 함수나 인라인이 아닌 메서드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-139">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="4553e-140">많은 F # 핵심 라이브러리 함수, 특히 연산자는 형식 매개 변수 정적으로 확인 된 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-140">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="4553e-141">이러한 함수 및 연산자에는 인라인 및 숫자 계산에 대 한 효율적인 코드 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-141">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="4553e-142">인라인 메서드 및 연산자를 사용 하거나 형식 매개 변수를 정적으로 해결 된 다른 기능을 사용 하는 함수 자체 정적으로 확인 된 형식 매개 변수에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-142">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="4553e-143">종종 형식 유추와 같은 인라인 함수를 정적으로 확인 된 형식 매개 변수를 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-143">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="4553e-144">다음 예제는 정적으로 확인 된 형식 매개 변수가으로 유추 되는 연산자 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-144">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="4553e-145">형식이 확인된 `(+@)` 둘 다의 사용에 따라 `(+)` 및 `(*)`, 둘 다의 정적으로 확인 된 형식 매개 변수에 대 다 형식 유추 될 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-145">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="4553e-146">확인 된 형식, F # 인터프리터에 표시 된 대로 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-146">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="4553e-147">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-147">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="4553e-148">F # 4.1 부터는에 정적으로 확인 된 형식 매개 변수 서명과 구체적인 형식 이름의도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-148">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="4553e-149">언어의 이전 버전에서는 형식 이름 컴파일러에서 유추할 수 실제로 하지만 실제로 지정할 수 없습니다 서명에 합니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-149">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="4553e-150">4.1 F #을 기준으로 정적으로 확인 된 형식 매개 변수 시그니처에 구체적인 형식 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-150">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="4553e-151">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4553e-151">Here's an example:</span></span>

```fsharp
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

## <a name="see-also"></a><span data-ttu-id="4553e-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4553e-152">See Also</span></span>
[<span data-ttu-id="4553e-153">제네릭</span><span class="sxs-lookup"><span data-stu-id="4553e-153">Generics</span></span>](index.md)

[<span data-ttu-id="4553e-154">형식 유추</span><span class="sxs-lookup"><span data-stu-id="4553e-154">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="4553e-155">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="4553e-155">Automatic Generalization</span></span>](automatic-generalization.md)

[<span data-ttu-id="4553e-156">제약 조건</span><span class="sxs-lookup"><span data-stu-id="4553e-156">Constraints</span></span>](constraints.md)

[<span data-ttu-id="4553e-157">인라인 함수</span><span class="sxs-lookup"><span data-stu-id="4553e-157">Inline Functions</span></span>](../functions/inline-functions.md)
