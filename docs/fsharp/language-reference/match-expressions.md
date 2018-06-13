---
title: '일치 식 (F #)'
description: 'F # 일치 식 패턴의 집합 식의 비교를 기반으로 하는 분기를 제어를 제공 하는 방법에 대해 알아봅니다.'
ms.date: 04/19/2018
ms.openlocfilehash: 22cc4b7a87a60d8a5dcbe05ac5abec5560a37516
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565180"
---
# <a name="match-expressions"></a><span data-ttu-id="b9aa4-103">일치 식</span><span class="sxs-lookup"><span data-stu-id="b9aa4-103">Match expressions</span></span>

<span data-ttu-id="b9aa4-104">`match` 식은 일련의 패턴으로 식의 비교를 기반으로 하는 분기를 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="b9aa4-105">구문</span><span class="sxs-lookup"><span data-stu-id="b9aa4-105">Syntax</span></span>

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a><span data-ttu-id="b9aa4-106">설명</span><span class="sxs-lookup"><span data-stu-id="b9aa4-106">Remarks</span></span>

<span data-ttu-id="b9aa4-107">일련의 패턴으로 테스트 식의 비교를 기반으로 복잡 한 분기에 대 한 패턴 일치 하는 식을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="b9aa4-108">에 `match` 식은 *테스트 식* 차례로 일치 하는 항목이 발견 되 면 해당 각 패턴와 비교 됩니다 *결과 식* 평가 결과 값이 고 일치 식의 값으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="b9aa4-109">패턴 일치 위 구문에서 표시 된 함수에는 패턴 일치는 즉시 인수에 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="b9aa4-110">패턴 일치 위 구문에서 표시 된 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="b9aa4-111">람다 식에 대 한 자세한 내용은 참조 [람다 식:는 `fun` 키워드](functions/lambda-expressions-the-fun-keyword.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="b9aa4-112">패턴의 전체 집합 입력 변수의 가능한 모든 일치 항목을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="b9aa4-113">와일드 카드 패턴을 사용 하는 자주 (`_`) 이전에 일치 하지 않는 입력된 값에 맞게 마지막 패턴으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="b9aa4-114">다음 코드에서는 있는 방법 중 일부는 `match` 식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="b9aa4-115">대 한 참조 및 사용할 수 있는 모든 패턴의 예제를 참조 하세요. [패턴 일치](pattern-matching.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="b9aa4-116">패턴 가드</span><span class="sxs-lookup"><span data-stu-id="b9aa4-116">Guards on patterns</span></span>

<span data-ttu-id="b9aa4-117">사용할 수 있습니다는 `when` 절 변수 패턴과 일치 하도록 만족 해야 하는 추가 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="b9aa4-118">이러한 절의 라고는 *가드*합니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="b9aa4-119">식은 다음의 `when` 해당 가드와 관련 된 패턴에 일치 하는 항목이 있어야만 키워드는 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="b9aa4-120">다음 예제에서는 변수 패턴에 대 한 숫자 범위를 지정 하는 가드의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="b9aa4-121">참고 여러 조건은 부울 연산자를 사용 하 여 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="b9aa4-122">패턴의 리터럴 이외의 값을 사용할 수 없으므로, 있습니다를 사용 해야는 `when` 절 값에 대해 입력의 일부 비교 해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="b9aa4-123">이 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="b9aa4-124">공용 구조체 패턴을 가드에서 검사 하는 가드를 적용 **모든** 의 마지막 하나 뿐 아니라 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="b9aa4-125">예를 들어 다음 코드에서는 가드 `when a > 12` 모두에 적용 되지만 `A a` 및 `B a`:</span><span class="sxs-lookup"><span data-stu-id="b9aa4-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a><span data-ttu-id="b9aa4-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="b9aa4-126">See also</span></span>

[<span data-ttu-id="b9aa4-127">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="b9aa4-127">F# Language Reference</span></span>](index.md)  
[<span data-ttu-id="b9aa4-128">활성 패턴</span><span class="sxs-lookup"><span data-stu-id="b9aa4-128">Active Patterns</span></span>](active-patterns.md)  
[<span data-ttu-id="b9aa4-129">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="b9aa4-129">Pattern Matching</span></span>](pattern-matching.md)  
