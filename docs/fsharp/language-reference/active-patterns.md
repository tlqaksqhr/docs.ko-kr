---
title: "활성 패턴(F#)"
description: "F # 프로그래밍 언어의 입력된 데이터를 분할 하는 명명 된 파티션을 정의 하려면 활성 패턴을 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 11a724ff-f9ff-4056-b5e0-87e9ed986f4a
ms.openlocfilehash: 845184e6150cf0b93393038ca3d39f0e6d898a2e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="active-patterns"></a><span data-ttu-id="00925-104">활성 패턴</span><span class="sxs-lookup"><span data-stu-id="00925-104">Active Patterns</span></span>

<span data-ttu-id="00925-105">*활성 패턴* 사용 패턴 일치 구별된 된 공용 구조체에 대 한 것 처럼 식에에서 이러한 이름을 사용할 수 있도록 입력된 데이터를 분할 하는 명명 된 파티션을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-105">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="00925-106">활성 패턴을 사용하여 각 파티션에 대한 사용자 지정 방식으로 데이터를 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-106">You can use active patterns to decompose data in a customized manner for each partition.</span></span>


## <a name="syntax"></a><span data-ttu-id="00925-107">구문</span><span class="sxs-lookup"><span data-stu-id="00925-107">Syntax</span></span>

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a><span data-ttu-id="00925-108">설명</span><span class="sxs-lookup"><span data-stu-id="00925-108">Remarks</span></span>
<span data-ttu-id="00925-109">위 구문에는 식별자가 나타내는 입력된 데이터의 파티션에 대 한 이름 *인수*, 또는 즉, 인수의 모든 값의 집합의 하위 집합에 대 한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="00925-109">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="00925-110">활성 패턴 정의에 최대 7 개의 파티션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-110">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="00925-111">*식* 데이터를 분해 하는 폼을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="00925-111">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="00925-112">명명 된 파티션을에 속해 주어진 값을 확인 하기 위한 규칙을 정의 하는 활성 패턴 정의 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-112">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="00925-113">(| 및 |) 기호 이라고 *바나나 클립* let 바인딩의이 형식에 의해 생성 함수를 호출 하 고는 *활성 인식기*합니다.</span><span class="sxs-lookup"><span data-stu-id="00925-113">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="00925-114">예를 들어, 다음과 같은 활성 패턴을 인수가 지정 된 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-114">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="00925-115">다음 예제와 같이 식과 일치 하는 패턴에서 활성 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-115">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="00925-116">이 프로그램의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-116">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="00925-117">활성 패턴의 또 다른 용도 동일한 기본 데이터 다양 한 가능한 표현 하는 경우와 같은 여러 가지 방법으로 데이터 형식을 분해 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="00925-117">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="00925-118">예를 들어 한 `Color` 개체 RGB 표현 또는 HSB 표현으로 분해할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-118">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="00925-119">위의 프로그램의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-119">The output of the above program is as follows:</span></span>

```
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

<span data-ttu-id="00925-120">와 함께에서 활성 패턴의 두 가지 파티션 수 있게 해만 적절 한 형태의 데이터를 분해 및 계산에 대 한 가장 편리 하 게 폼의 적절 한 데이터에 적절 한 계산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="00925-120">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="00925-121">결과 패턴 일치 하는 식을 사용 데이터를 읽을 수 있는 매우를 크게 간소화 잠재적으로 복잡 한 분기 및 코드 분석 데이터를 편리 하 게 방식에서 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-121">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>


## <a name="partial-active-patterns"></a><span data-ttu-id="00925-122">부분 활성 패턴</span><span class="sxs-lookup"><span data-stu-id="00925-122">Partial Active Patterns</span></span>
<span data-ttu-id="00925-123">경우에 따라 입력 공간의 일부만 분할 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-123">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="00925-124">이 경우에는 일부 입력 사항이 일치 하지만 다른 입력과 일치 하지 않게 부분 패턴 집합을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="00925-124">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="00925-125">값을 생성 하지 않을 수 있는 활성 패턴 이라고 *부분 활성 패턴*; 옵션 형식으로 반환 값을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-125">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="00925-126">부분 활성 패턴을 정의 하려면 바나나 클립 내에서 패턴 목록의 끝에 와일드 카드 문자 (_)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="00925-126">To define a partial active pattern, you use a wildcard character (_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="00925-127">다음 코드 부분 활성 패턴 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00925-127">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="00925-128">이전 예의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-128">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="00925-129">부분 활성 패턴을 사용 하는 경우 때로는 개별 선택 비연속 또는 수 상호 배타적인 있지만 될 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-129">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="00925-130">다음 예제에서는 패턴 제곱와 큐브 패턴 높지 않습니다이 일부 숫자는 사각형인 64와 같은 큐브 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-130">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="00925-131">다음 프로그램은 사각형인 큐브 1000000 최대 모든 정수 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="00925-131">The following program prints out all integers up to 1000000 that are both squares and cubes.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="00925-132">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-132">The output is as follows:</span></span>

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="00925-133">매개 변수가 있는 활성 패턴</span><span class="sxs-lookup"><span data-stu-id="00925-133">Parameterized Active Patterns</span></span>
<span data-ttu-id="00925-134">활성 패턴은 항상 일치 여부를 확인할 항목에 대 한 하나 이상의 인수를 사용 하지만 경우에 이름에 인수를 추가로 소요 될 수 있습니다 *매개 변수가 있는 활성 패턴* 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00925-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="00925-135">추가 인수는 특수화 된 것으로 되는 일반적인 패턴을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="00925-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="00925-136">문자열을 구문 분석 종종 정규식을 사용 하 여 활성 패턴 또한 부분 활성 패턴을 사용 하 여 다음 코드 처럼 추가 매개 변수로 정규식을 포함 하는 예를 들어 `Integer` 이전 코드 예제에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="00925-137">이 예제에서는 다양 한 날짜 형식에 대 한 정규식을 사용 하는 문자열 일반 ParseRegex 활성 패턴에 맞게 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00925-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="00925-138">정수 활성 패턴은 DateTime 생성자에 전달 될 수 있는 정수에 일치 하는 문자열을 변환 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00925-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="00925-139">이전 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-139">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="00925-140">활성 패턴 일치 하는 식을 패턴에 제한 되지 않습니다., let 바인딩에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="00925-141">이전 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00925-141">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="00925-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00925-142">See Also</span></span>
[<span data-ttu-id="00925-143">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="00925-143">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="00925-144">일치 식</span><span class="sxs-lookup"><span data-stu-id="00925-144">Match Expressions</span></span>](match-expressions.md)

