---
title: '루프: for...in 식(F#)'
description: '참조 방식을 F # >for.. 식에 구문 반복 하는 데 열거 가능한 컬렉션 패턴 일치 하는 항목을 반복 합니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: eaf0f4fc6419d8e0bff46795120ee5e42c4efe1d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="loops-forin-expression"></a><span data-ttu-id="7aa2e-103">루프: for...in 식</span><span class="sxs-lookup"><span data-stu-id="7aa2e-103">Loops: for...in Expression</span></span>

<span data-ttu-id="7aa2e-104">이 루프 구문은 열거 가능한 컬렉션 범위 식, 시퀀스, 목록, 배열 또는 열거형을 지 원하는 다른 생성자와 같은 패턴 일치 하는 항목을 반복 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>


## <a name="syntax"></a><span data-ttu-id="7aa2e-105">구문</span><span class="sxs-lookup"><span data-stu-id="7aa2e-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="7aa2e-106">설명</span><span class="sxs-lookup"><span data-stu-id="7aa2e-106">Remarks</span></span>
<span data-ttu-id="7aa2e-107">`for...in` 식과 비교할 수는 `for each` 다른.NET 언어의 문과 하는 값 열거 가능한 컬렉션을 반복 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="7aa2e-108">그러나 `for...in` 패턴 전체 컬렉션 단순히 반복 하는 대신 컬렉션에 대해 일치도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="7aa2e-109">열거 가능한 컬렉션 또는 사용 하 여 열거 가능한 식을 지정할 수는 `..` 정수 계열 형식에 대 한 범위로 연산자.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="7aa2e-110">열거 가능한 컬렉션 목록, 시퀀스, 배열, 집합, 지도, 및에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="7aa2e-111">구현 하는 형식 `System.Collections.IEnumerable` 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="7aa2e-112">사용 하 여 범위를 표현할는 `..` 연산자는 다음 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="7aa2e-113">*시작* ...</span><span class="sxs-lookup"><span data-stu-id="7aa2e-113">*start* ..</span></span> <span data-ttu-id="7aa2e-114">*마침*</span><span class="sxs-lookup"><span data-stu-id="7aa2e-114">*finish*</span></span>

<span data-ttu-id="7aa2e-115">라는 증분을 포함 하는 버전을 사용할 수도 있습니다는 *건너뛸*, 다음 코드 에서처럼에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="7aa2e-116">*시작* ...</span><span class="sxs-lookup"><span data-stu-id="7aa2e-116">*start* ..</span></span> <span data-ttu-id="7aa2e-117">*건너뛸* ...</span><span class="sxs-lookup"><span data-stu-id="7aa2e-117">*skip* ..</span></span> <span data-ttu-id="7aa2e-118">*마침*</span><span class="sxs-lookup"><span data-stu-id="7aa2e-118">*finish*</span></span>

<span data-ttu-id="7aa2e-119">일반적인 동작은 카운터 변수 반복 될 때마다 1 씩 증가 하는 패턴으로 정수 범위와 단순 카운터 변수를 사용 하면 하지만 범위는 skip 값을 포함 하는 경우 카운터는 증가 된 건너뛰기 값으로 대신.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="7aa2e-120">패턴에 일치 하는 값을 본문 식에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="7aa2e-121">다음 코드 예제는 사용법을 보여 줍니다.는 `for...in` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="7aa2e-122">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="7aa2e-123">다음 예제에는 시퀀스에 대해 반복 하는 방법과 단순 변수 대신 튜플 패턴을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="7aa2e-124">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-124">The output is as follows.</span></span>

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

<span data-ttu-id="7aa2e-125">다음 예제에서는 단순한 정수 범위를 반복 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="7aa2e-126">Function1의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="7aa2e-127">다음 예제에서는 범위에 있는 다른 모든 요소를 포함 하는 2, 건너뛰기로 범위를 반복 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="7aa2e-128">출력 `function2` 는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="7aa2e-129">다음 예제에서는 문자 범위를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="7aa2e-130">출력 `function3` 는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="7aa2e-131">다음 예제에는 역방향 반복에 대 한 음수 건너뛰기 값을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="7aa2e-132">출력 `function4` 는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="7aa2e-133">시작과 범위의 끝에 다음 코드 에서처럼 함수 등의 식을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="7aa2e-134">출력 `function5` 이 입력으로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="7aa2e-135">다음 예제에서는 루프에서 요소가 필요 하지 않은 경우 와일드 카드 문자 (_) 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-135">The next example shows the use of a wildcard character (_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="7aa2e-136">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="7aa2e-137">`Note` 사용할 수 있습니다 `for...in` 시퀀스 식 및 다른 계산 식, 사용자 지정된 된 버전의 경우는 `for...in` 식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="7aa2e-138">자세한 내용은 참조 [시퀀스](sequences.md), [비동기 워크플로](asynchronous-workflows.md), 및 [계산 식](computation-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa2e-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="7aa2e-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7aa2e-139">See Also</span></span>
[<span data-ttu-id="7aa2e-140">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="7aa2e-140">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="7aa2e-141">루프: `for...to` 식</span><span class="sxs-lookup"><span data-stu-id="7aa2e-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)

[<span data-ttu-id="7aa2e-142">루프: `while...do` 식</span><span class="sxs-lookup"><span data-stu-id="7aa2e-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
