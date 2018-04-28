---
title: 인라인 함수(F#)
description: 'F # 인라인 함수를 호출 하는 코드에 직접 통합을 사용 하는 방법에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: cb0addd1456af1ab97e249b9c5ece4d9f0818fa3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="inline-functions"></a><span data-ttu-id="bd7aa-103">인라인 함수</span><span class="sxs-lookup"><span data-stu-id="bd7aa-103">Inline Functions</span></span>

<span data-ttu-id="bd7aa-104">*인라인 함수* 는 호출 코드에 직접 통합 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>


## <a name="using-inline-functions"></a><span data-ttu-id="bd7aa-105">인라인 함수를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="bd7aa-105">Using Inline Functions</span></span>
<span data-ttu-id="bd7aa-106">정적 형식 매개 변수를 사용 하면 형식 매개 변수를 통해 매개 변수화 하는 모든 기능은 인라인 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="bd7aa-107">이렇게 하면 컴파일러 이러한 형식 매개 변수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="bd7aa-108">일반적인 제네릭 형식 매개 변수를 사용 하는 경우에 이러한 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="bd7aa-109">멤버 제약 조건 사용을 설정, 이외의 인라인 함수 코드를 최적화 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="bd7aa-110">그러나 인라인 함수 남용 되지 않도록 어려울 수 컴파일러 최적화 하 고 라이브러리 함수 구현의 변화에 따라 코드를 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="bd7aa-111">이러한 이유로 모든 다른 최적화 기술을 시도한 하지 않는 한 최적화에 대 한 인라인 함수를 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="bd7aa-112">함수 또는 메서드 인라인 만들기 성능이 향상 될 수 있습니다 사용할 수 있지만 항상 대/소문자입니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="bd7aa-113">따라서 특정된 함수를 인라인으로 만드는 영향을 주었는지 권한이 실제로 있는지 확인 하려면 성능 측정값을도 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="bd7aa-114">`inline` 최상위 수준에, 모듈 수준 또는 클래스에서 메서드 수준에서 함수에 한정자를 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="bd7aa-115">다음 코드 예제에서는 최상위 수준, 인라인 인스턴스 메서드인 및 인라인 정적 메서드는 인라인 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="bd7aa-116">인라인 함수 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="bd7aa-116">Inline Functions and Type Inference</span></span>
<span data-ttu-id="bd7aa-117">존재 여부 `inline` 형식 유추 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="bd7aa-118">비인라인 함수 수 없는 반면 인라인 함수 수 있는 정적으로 확인 된 형식 매개 변수 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="bd7aa-119">다음 코드 예제는 경우를 보여 줍니다. 여기서 `inline` 정적으로 확인 된 형식 매개 변수를 가진 함수를 사용 하는 때문에 유용는 `float` 변환 연산자.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="bd7aa-120">없이 `inline` 한정자,이 경우 특정 형식을 사용 하도록 함수를 사용 형식 유추 하면 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="bd7aa-121">하지만 `inline` 한정자가 있으면 함수가 유추에 정적으로 확인 된 형식 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="bd7aa-122">와 `inline` 다음 한정자를 형식 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="bd7aa-123">함수를 변환할 수 있는 모든 형식을 허용 하는 것이 즉 **float**합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7aa-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>


## <a name="see-also"></a><span data-ttu-id="bd7aa-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd7aa-124">See Also</span></span>
[<span data-ttu-id="bd7aa-125">함수</span><span class="sxs-lookup"><span data-stu-id="bd7aa-125">Functions</span></span>](index.md)

[<span data-ttu-id="bd7aa-126">제약 조건</span><span class="sxs-lookup"><span data-stu-id="bd7aa-126">Constraints</span></span>](../generics/constraints.md)

[<span data-ttu-id="bd7aa-127">정적으로 확인된 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd7aa-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
