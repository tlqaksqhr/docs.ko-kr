---
title: "일치 식(F#)"
description: "F # 일치 식 패턴의 집합 식의 비교를 기반으로 하는 분기를 제어를 제공 하는 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8854b713-255a-408d-942a-e80ab52fd2a4
ms.openlocfilehash: c8b9be744cfa7bc76f0d663b12abd66f8757fc56
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="match-expressions"></a><span data-ttu-id="5a760-104">일치 식</span><span class="sxs-lookup"><span data-stu-id="5a760-104">Match Expressions</span></span>

<span data-ttu-id="5a760-105">`match` 식은 일련의 패턴으로 식의 비교를 기반으로 하는 분기를 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-105">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="5a760-106">구문</span><span class="sxs-lookup"><span data-stu-id="5a760-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="5a760-107">설명</span><span class="sxs-lookup"><span data-stu-id="5a760-107">Remarks</span></span>

<span data-ttu-id="5a760-108">일련의 패턴으로 테스트 식의 비교를 기반으로 복잡 한 분기에 대 한 패턴 일치 하는 식을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-108">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="5a760-109">에 `match` 식은 *테스트 식* 차례로 일치 하는 항목이 발견 되 면 해당 각 패턴와 비교 됩니다 *결과 식* 평가 결과 값이 고 일치 식의 값으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-109">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="5a760-110">패턴 일치 위 구문에서 표시 된 함수에는 패턴 일치는 즉시 인수에 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-110">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="5a760-111">패턴 일치 위 구문에서 표시 된 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-111">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```    

<span data-ttu-id="5a760-112">람다 식에 대 한 자세한 내용은 참조 [람다 식:는 `fun` 키워드](functions/lambda-expressions-the-fun-keyword.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-112">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="5a760-113">패턴의 전체 집합 입력 변수의 가능한 모든 일치 항목을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-113">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="5a760-114">와일드 카드 패턴을 사용 하는 자주 (`_`) 이전에 일치 하지 않는 입력된 값에 맞게 마지막 패턴으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-114">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="5a760-115">다음 코드에서는 있는 방법 중 일부는 `match` 식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-115">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="5a760-116">대 한 참조 및 사용할 수 있는 모든 패턴의 예제를 참조 하세요. [패턴 일치](pattern-matching.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-116">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="5a760-117">패턴 가드</span><span class="sxs-lookup"><span data-stu-id="5a760-117">Guards on Patterns</span></span>

<span data-ttu-id="5a760-118">사용할 수 있습니다는 `when` 절 변수 패턴과 일치 하도록 만족 해야 하는 추가 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-118">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="5a760-119">이러한 절의 라고는 *가드*합니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-119">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="5a760-120">식은 다음의 `when` 해당 가드와 관련 된 패턴에 일치 하는 항목이 있어야만 키워드는 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-120">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="5a760-121">다음 예제에서는 변수 패턴에 대 한 숫자 범위를 지정 하는 가드의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-121">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="5a760-122">참고 여러 조건은 부울 연산자를 사용 하 여 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-122">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="5a760-123">패턴의 리터럴 이외의 값을 사용할 수 없으므로, 있습니다를 사용 해야는 `when` 절 값에 대해 입력의 일부 비교 해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="5a760-123">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="5a760-124">다음 코드에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a760-124">This is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

## <a name="see-also"></a><span data-ttu-id="5a760-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a760-125">See Also</span></span>

[<span data-ttu-id="5a760-126">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="5a760-126">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="5a760-127">활성 패턴</span><span class="sxs-lookup"><span data-stu-id="5a760-127">Active Patterns</span></span>](active-patterns.md)

[<span data-ttu-id="5a760-128">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="5a760-128">Pattern Matching</span></span>](pattern-matching.md)
