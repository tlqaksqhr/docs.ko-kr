---
title: "인라인 함수(F#)"
description: "F # 인라인 함수를 호출 하는 코드에 직접 통합을 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3fa31178-08f8-463d-9d41-d29220a90027
ms.openlocfilehash: 0489d411e2754eaab6a10ff0feb4405491b3b511
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2017
---
# <a name="inline-functions"></a><span data-ttu-id="e3a17-104">인라인 함수</span><span class="sxs-lookup"><span data-stu-id="e3a17-104">Inline Functions</span></span>

<span data-ttu-id="e3a17-105">*인라인 함수* 는 호출 코드에 직접 통합 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-105">*Inline functions* are functions that are integrated directly into the calling code.</span></span>


## <a name="using-inline-functions"></a><span data-ttu-id="e3a17-106">인라인 함수를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="e3a17-106">Using Inline Functions</span></span>
<span data-ttu-id="e3a17-107">정적 형식 매개 변수를 사용 하면 형식 매개 변수를 통해 매개 변수화 하는 모든 기능은 인라인 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-107">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="e3a17-108">이렇게 하면 컴파일러 이러한 형식 매개 변수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-108">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="e3a17-109">일반적인 제네릭 형식 매개 변수를 사용 하는 경우에 이러한 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-109">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="e3a17-110">멤버 제약 조건 사용을 설정, 이외의 인라인 함수 코드를 최적화 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-110">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="e3a17-111">그러나 인라인 함수 남용 되지 않도록 어려울 수 컴파일러 최적화 하 고 라이브러리 함수 구현의 변화에 따라 코드를 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-111">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="e3a17-112">이러한 이유로 모든 다른 최적화 기술을 시도한 하지 않는 한 최적화에 대 한 인라인 함수를 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-112">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="e3a17-113">함수 또는 메서드 인라인 만들기 성능이 향상 될 수 있습니다 사용할 수 있지만 항상 대/소문자입니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-113">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="e3a17-114">따라서 특정된 함수를 인라인으로 만드는 영향을 주었는지 권한이 실제로 있는지 확인 하려면 성능 측정값을도 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-114">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="e3a17-115">`inline` 최상위 수준에, 모듈 수준 또는 클래스에서 메서드 수준에서 함수에 한정자를 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-115">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="e3a17-116">다음 코드 예제에서는 최상위 수준, 인라인 인스턴스 메서드인 및 인라인 정적 메서드는 인라인 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-116">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="e3a17-117">인라인 함수 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="e3a17-117">Inline Functions and Type Inference</span></span>
<span data-ttu-id="e3a17-118">존재 여부 `inline` 형식 유추 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-118">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="e3a17-119">비인라인 함수 수 없는 반면 인라인 함수 수 있는 정적으로 확인 된 형식 매개 변수 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-119">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="e3a17-120">다음 코드 예제는 경우를 보여 줍니다. 여기서 `inline` 정적으로 확인 된 형식 매개 변수를 가진 함수를 사용 하는 때문에 유용는 `float` 변환 연산자.</span><span class="sxs-lookup"><span data-stu-id="e3a17-120">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="e3a17-121">없이 `inline` 한정자,이 경우 특정 형식을 사용 하도록 함수를 사용 형식 유추 하면 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-121">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="e3a17-122">하지만 `inline` 한정자가 있으면 함수가 유추에 정적으로 확인 된 형식 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-122">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="e3a17-123">와 `inline` 다음 한정자를 형식 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-123">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="e3a17-124">함수를 변환할 수 있는 모든 형식을 허용 하는 것이 즉 **float**합니다.</span><span class="sxs-lookup"><span data-stu-id="e3a17-124">This means that the function accepts any type that supports a conversion to **float**.</span></span>


## <a name="see-also"></a><span data-ttu-id="e3a17-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3a17-125">See Also</span></span>
[<span data-ttu-id="e3a17-126">함수</span><span class="sxs-lookup"><span data-stu-id="e3a17-126">Functions</span></span>](index.md)

[<span data-ttu-id="e3a17-127">제약 조건</span><span class="sxs-lookup"><span data-stu-id="e3a17-127">Constraints</span></span>](../generics/constraints.md)

[<span data-ttu-id="e3a17-128">정적으로 확인된 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3a17-128">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
