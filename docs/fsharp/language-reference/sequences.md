---
title: 시퀀스(F#)
description: '대규모 데이터의 컬렉션을 정렬 되어 있지만 모든 요소를 사용 하려면 반드시 원하지 때 F # 시퀀스를 사용 하는 방법을 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: a3521037112d40998ed00cd6fed376882c2f2c88
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="sequences"></a><span data-ttu-id="d38ee-103">시퀀스</span><span class="sxs-lookup"><span data-stu-id="d38ee-103">Sequences</span></span>

> [!NOTE]
<span data-ttu-id="d38ee-104">이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="d38ee-105">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="d38ee-106">A *시퀀스* 논리는 일련의 요소는 특정 형식의 모든 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-106">A *sequence* is a logical series of elements all of one type.</span></span> <span data-ttu-id="d38ee-107">시퀀스는는 대형 데이터의 컬렉션을 정렬 되어 있지만 주로 모든 요소를 사용 하는 경우에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-107">Sequences are particularly useful when you have a large, ordered collection of data but do not necessarily expect to use all of the elements.</span></span> <span data-ttu-id="d38ee-108">시퀀스에 있는 요소를 모두 사용 되는 상황에서 목록 보다 더 나은 성능을 제공할 수 있도록 요소로만 계산 되는 개별 시퀀스 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-108">Individual sequence elements are computed only as required, so a sequence can provide better performance than a list in situations in which not all the elements are used.</span></span> <span data-ttu-id="d38ee-109">시퀀스도 표시 됩니다는 `seq<'T>` 별칭 형식에 대 한 `System.Collections.Generic.IEnumerable`합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-109">Sequences are represented by the `seq<'T>` type, which is an alias for `System.Collections.Generic.IEnumerable`.</span></span> <span data-ttu-id="d38ee-110">따라서 구현 하는.NET Framework 형식 `System.IEnumerable` 시퀀스도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-110">Therefore, any .NET Framework type that implements `System.IEnumerable` can be used as a sequence.</span></span> <span data-ttu-id="d38ee-111">[Seq 모듈](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) 시퀀스가 관련 된 조작을 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-111">The [Seq module](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) provides support for manipulations involving sequences.</span></span>

## <a name="sequence-expressions"></a><span data-ttu-id="d38ee-112">시퀀스 식</span><span class="sxs-lookup"><span data-stu-id="d38ee-112">Sequence Expressions</span></span>
<span data-ttu-id="d38ee-113">A *식 시퀀스* 시퀀스에 계산 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-113">A *sequence expression* is an expression that evaluates to a sequence.</span></span> <span data-ttu-id="d38ee-114">시퀀스 식에는 여러 가지 형식 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-114">Sequence expressions can take a number of forms.</span></span> <span data-ttu-id="d38ee-115">가장 간단한 형태는 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-115">The simplest form specifies a range.</span></span> <span data-ttu-id="d38ee-116">예를 들어 `seq { 1 .. 5 }` 1과 5 끝점을 포함 하 여 다섯 개의 요소를 포함 하는 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-116">For example, `seq { 1 .. 5 }` creates a sequence that contains five elements, including the endpoints 1 and 5.</span></span> <span data-ttu-id="d38ee-117">있습니다 하거나 지정할 수는 증가 (감소) 두 double 기간 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-117">You can also specify an increment (or decrement) between two double periods.</span></span> <span data-ttu-id="d38ee-118">예를 들어 다음 코드는 10을 곱한 값의 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-118">For example, the following code creates the sequence of multiples of 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

<span data-ttu-id="d38ee-119">시퀀스 식은 F # 식을 시퀀스의 값을 생성 하는 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-119">Sequence expressions are made up of F# expressions that produce values of the sequence.</span></span> <span data-ttu-id="d38ee-120">사용할 수는 `yield` 키워드 시퀀스에 포함 되는 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-120">They can use the `yield` keyword to produce values that become part of the sequence.</span></span>

<span data-ttu-id="d38ee-121">다음은 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-121">Following is an example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

<span data-ttu-id="d38ee-122">사용할 수 있습니다는 `->` 연산자 대신 `yield`, 생략할 수는 쿼리에서 `do` 키워드에 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-122">You can use the `->` operator instead of `yield`, in which case you can omit the `do` keyword, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

<span data-ttu-id="d38ee-123">다음 코드에서 눈금을 나타내는 배열 인덱스 함께 좌표 쌍 목록을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-123">The following code generates a list of coordinate pairs along with an index into an array that represents the grid.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

<span data-ttu-id="d38ee-124">`if` 시퀀스에 사용 된 식에는 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-124">An `if` expression used in a sequence is a filter.</span></span> <span data-ttu-id="d38ee-125">예를 들어, 소수로 함수 했다고 가정의 시퀀스를 생성 하려면 `isprime` 형식의 `int -> bool`, 시퀀스를 다음과 같이 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-125">For example, to generate a sequence of only prime numbers, assuming that you have a function `isprime` of type `int -> bool`, construct the sequence as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

<span data-ttu-id="d38ee-126">사용 하는 경우 `yield` 또는 `->` 반복에서 각 반복 하는 예상 되는 시퀀스의 단일 요소를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-126">When you use `yield` or `->` in an iteration, each iteration is expected to generate a single element of the sequence.</span></span> <span data-ttu-id="d38ee-127">요소 시퀀스를 생성 하는 각 반복을 사용 하 여 `yield!`합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-127">If each iteration produces a sequence of elements, use `yield!`.</span></span> <span data-ttu-id="d38ee-128">이 경우 각 반복에 대해 생성 된 요소는 최종 시퀀스를 생성 하기 위해 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-128">In that case, the elements generated on each iteration are concatenated to produce the final sequence.</span></span>

<span data-ttu-id="d38ee-129">여러 개의 식을 시퀀스 식에서 함께 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-129">You can combine multiple expressions together in a sequence expression.</span></span> <span data-ttu-id="d38ee-130">각 식에서 생성 된 요소를 서로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-130">The elements generated by each expression are concatenated together.</span></span> <span data-ttu-id="d38ee-131">예를 들어이 항목의 "예" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d38ee-131">For an example, see the "Examples" section of this topic.</span></span>

## <a name="examples"></a><span data-ttu-id="d38ee-132">예제</span><span class="sxs-lookup"><span data-stu-id="d38ee-132">Examples</span></span>
<span data-ttu-id="d38ee-133">첫 번째 예제에서는 반복, 필터 및 yield 배열을 생성을 포함 하는 시퀀스 식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-133">The first example uses a sequence expression that contains an iteration, a filter, and a yield to generate an array.</span></span> <span data-ttu-id="d38ee-134">이 코드는 1에서 콘솔에는 100 사이의 소수 숫자 시퀀스를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-134">This code prints a sequence of prime numbers between 1 and 100 to the console.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

<span data-ttu-id="d38ee-135">다음 코드에서는 `yield` 각각의 두 가지 요소 및 제품 구성 된 3 개 요소의 튜플로 구성 된 곱하기 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-135">The following code uses `yield` to create a multiplication table that consists of tuples of three elements, each consisting of two factors and the product.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

<span data-ttu-id="d38ee-136">다음 예제에서는 `yield!` 개별 시퀀스를 단일 마지막 시퀀스에 결합 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-136">The following example demonstrates the use of `yield!` to combine individual sequences into a single final sequence.</span></span> <span data-ttu-id="d38ee-137">이 경우 이진 트리의 각 하위 트리의 시퀀스는 마지막 시퀀스를 생성 하는 재귀 함수에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-137">In this case, the sequences for each subtree in a binary tree are concatenated in a recursive function to produce the final sequence.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]
    
## <a name="using-sequences"></a><span data-ttu-id="d38ee-138">시퀀스 사용</span><span class="sxs-lookup"><span data-stu-id="d38ee-138">Using Sequences</span></span>
<span data-ttu-id="d38ee-139">시퀀스를 지 원하는 다양 한 동일한 기능을 지원 [나열](lists.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-139">Sequences support many of the same functions as [lists](lists.md).</span></span> <span data-ttu-id="d38ee-140">시퀀스는 그룹화 키 생성 함수를 사용 하 여 계산 등 작업을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-140">Sequences also support operations such as grouping and counting by using key-generating functions.</span></span> <span data-ttu-id="d38ee-141">시퀀스는 또한 하위 시퀀스를 추출 하기 위한 더 다양 한 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-141">Sequences also support more diverse functions for extracting subsequences.</span></span>

<span data-ttu-id="d38ee-142">목록, 배열, 집합, 지도 등 대부분의 데이터 형식이 열거 가능한 컬렉션을 되기 때문에 암시적으로 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-142">Many data types, such as lists, arrays, sets, and maps are implicitly sequences because they are enumerable collections.</span></span> <span data-ttu-id="d38ee-143">상황에 따라 인수는 일반 F # 데이터 형식를 사용 하 여 또한 구현 하는 모든.NET Framework 데이터 형식에는 시퀀스를 사용 하는 함수 `System.Collections.Generic.IEnumerable<'T>`합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-143">A function that takes a sequence as an argument works with any of the common F# data types, in addition to any .NET Framework data type that implements `System.Collections.Generic.IEnumerable<'T>`.</span></span> <span data-ttu-id="d38ee-144">이 목록에만 사용할 수 있습니다를 인수로 목록을 사용 하는 함수에는 대조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-144">Contrast this to a function that takes a list as an argument, which can only take lists.</span></span> <span data-ttu-id="d38ee-145">형식 `seq<'T>` 형식 약어에 대 한 `IEnumerable<'T>`합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-145">The type `seq<'T>` is a type abbreviation for `IEnumerable<'T>`.</span></span> <span data-ttu-id="d38ee-146">즉, 제네릭 구현 하는 형식 `System.Collections.Generic.IEnumerable<'T>`, 배열, 목록, 포함 된 설정 및 F #, 및도 대부분.NET Framework 컬렉션 형식을, 지도와 호환 되는 `seq` 입력 하 고 시퀀스 필요한 곳 마다 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-146">This means that any type that implements the generic `System.Collections.Generic.IEnumerable<'T>`, which includes arrays, lists, sets, and maps in F#, and also most .NET Framework collection types, is compatible with the `seq` type and can be used wherever a sequence is expected.</span></span>


## <a name="module-functions"></a><span data-ttu-id="d38ee-147">모듈 함수</span><span class="sxs-lookup"><span data-stu-id="d38ee-147">Module Functions</span></span>
<span data-ttu-id="d38ee-148">[Seq 모듈](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) 에 [Microsoft.FSharp.Collections 네임 스페이스](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) 시퀀스를 사용 하기 위한 함수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-148">The [Seq module](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) in the [Microsoft.FSharp.Collections namespace](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) contains functions for working with sequences.</span></span> <span data-ttu-id="d38ee-149">이러한 함수 작업할 목록, 배열, 맵 및 집합도은 열거할 모든 해당 형식 이어서 시퀀스로 취급 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-149">These functions work with lists, arrays, maps, and sets as well, because all of those types are enumerable, and therefore can be treated as sequences.</span></span>


## <a name="creating-sequences"></a><span data-ttu-id="d38ee-150">시퀀스 만들기</span><span class="sxs-lookup"><span data-stu-id="d38ee-150">Creating Sequences</span></span>
<span data-ttu-id="d38ee-151">이전에 설명한 대로 시퀀스 식을 사용 하 여 또는 특정 기능을 사용 하 여 시퀀스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-151">You can create sequences by using sequence expressions, as described previously, or by using certain functions.</span></span>

<span data-ttu-id="d38ee-152">사용 하 여 빈 시퀀스를 만들 수 있습니다 [Seq.empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59), 하나만 지정 된 요소 시퀀스를 사용 하 여 만들 수 있습니다 또는 [Seq.singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7)합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-152">You can create an empty sequence by using [Seq.empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59), or you can create a sequence of just one specified element by using [Seq.singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet9.fs)]

<span data-ttu-id="d38ee-153">사용할 수 있습니다 [Seq.init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) 요소 제공 하는 함수를 사용 하 여 생성 됩니다는 순서를 만들려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-153">You can use [Seq.init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) to create a sequence for which the elements are created by using a function that you provide.</span></span> <span data-ttu-id="d38ee-154">또한 시퀀스에 대 한 크기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-154">You also provide a size for the sequence.</span></span> <span data-ttu-id="d38ee-155">이 함수는 마찬가지로 [List.init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83)한다는 점을 제외 하는 요소 시퀀스를 반복 될 때까지 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-155">This function is just like [List.init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83), except that the elements are not created until you iterate through the sequence.</span></span> <span data-ttu-id="d38ee-156">다음 코드에서는 `Seq.init`합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-156">The following code illustrates the use of `Seq.init`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet10.fs)]

<span data-ttu-id="d38ee-157">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-157">The output is</span></span>

```
0 10 20 30 40
```

<span data-ttu-id="d38ee-158">사용 하 여 [Seq.ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) 및 [Seq.ofList&#60;' T&#62; 함수](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), 배열 및 목록에서 순서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-158">By using [Seq.ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) and [Seq.ofList&#60;'T&#62; Function](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), you can create sequences from arrays and lists.</span></span> <span data-ttu-id="d38ee-159">그러나 변환할 수도 있습니다 배열과 목록을 시퀀스에는 캐스트 연산자를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-159">However, you can also convert arrays and lists to sequences by using a cast operator.</span></span> <span data-ttu-id="d38ee-160">두 가지 방법은 모두 다음 코드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-160">Both techniques are shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet11.fs)]

<span data-ttu-id="d38ee-161">사용 하 여 [Seq.cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334)에 정의 된 등의 약한 형식의 컬렉션에서 시퀀스를 만들 수 있습니다 `System.Collections`합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-161">By using [Seq.cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334), you can create a sequence from a weakly typed collection, such as those defined in `System.Collections`.</span></span> <span data-ttu-id="d38ee-162">이러한 약하게 형식화 된 컬렉션에서 요소 형식을 사용할 `System.Object` 하 고 제네릭이 아닌를 사용 하 여 열거 `System.Collections.Generic.IEnumerable&#96;1` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-162">Such weakly typed collections have the element type `System.Object` and are enumerated by using the non-generic `System.Collections.Generic.IEnumerable&#96;1` type.</span></span> <span data-ttu-id="d38ee-163">다음 코드에서는 `Seq.cast` 변환 하는 `System.Collections.ArrayList` 시퀀스로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-163">The following code illustrates the use of `Seq.cast` to convert an `System.Collections.ArrayList` into a sequence.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet12.fs)]

<span data-ttu-id="d38ee-164">사용 하 여 무한 시퀀스를 정의할 수 있습니다는 [Seq.initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-164">You can define infinite sequences by using the [Seq.initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) function.</span></span> <span data-ttu-id="d38ee-165">이러한 시퀀스에 대 한 요소의 인덱스에서 각 요소를 생성 하는 함수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-165">For such a sequence, you provide a function that generates each element from the index of the element.</span></span> <span data-ttu-id="d38ee-166">지연 계산; 인해 무한 시퀀스 생성할 수 있습니다. 요소를 지정 하는 함수를 호출 하 여 필요에 따라 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-166">Infinite sequences are possible because of lazy evaluation; elements are created as needed by calling the function that you specify.</span></span> <span data-ttu-id="d38ee-167">다음 코드 예제에서는 부동 소수점 숫자를이 사례에서 교대로 반복 되는 일련의 연속 된 정수 제곱 평균은의 시퀀스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-167">The following code example produces an infinite sequence of floating point numbers, in this case the alternating series of reciprocals of squares of successive integers.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet13.fs)]

<span data-ttu-id="d38ee-168">[Seq.unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) 계산 함수는 상태를 사용 하는 시퀀스의 각 후속 요소를 만드는 로부터 시퀀스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-168">[Seq.unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) generates a sequence from a computation function that takes a state and transforms it to produce each subsequent element in the sequence.</span></span> <span data-ttu-id="d38ee-169">상태는 각 요소를 계산 하는 데 사용 되 고 각 요소는 계산 된 변경할 수 있는 값 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-169">The state is just a value that is used to compute each element, and can change as each element is computed.</span></span> <span data-ttu-id="d38ee-170">두 번째 인수를 `Seq.unfold` 는 시퀀스를 시작 하는 데 사용 되는 초기 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-170">The second argument to `Seq.unfold` is the initial value that is used to start the sequence.</span></span> <span data-ttu-id="d38ee-171">`Seq.unfold` 시퀀스를 반환 하 여 종료를 사용할 수 있는 상태에 대 한 옵션 종류를 사용 하 여 `None` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-171">`Seq.unfold` uses an option type for the state, which enables you to terminate the sequence by returning the `None` value.</span></span> <span data-ttu-id="d38ee-172">다음 코드는 시퀀스는 두 가지 예를 보여 줍니다. `seq1` 및 `fib`를 통해 생성 된는 `unfold` 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-172">The following code shows two examples of sequences, `seq1` and `fib`, that are generated by an `unfold` operation.</span></span> <span data-ttu-id="d38ee-173">첫 번째 `seq1`, 100 까지의 숫자로 이루어진 단순한 시퀀스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-173">The first, `seq1`, is just a simple sequence with numbers up to 100.</span></span> <span data-ttu-id="d38ee-174">두 번째 `fib`, 사용 하 여 `unfold` 피보나치를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-174">The second, `fib`, uses `unfold` to compute the Fibonacci sequence.</span></span> <span data-ttu-id="d38ee-175">각 요소는 피보나치에서 이전 두 피보나치 숫자의 합 이기 때문에 상태 값은 시퀀스에서 이전 두 숫자의 구성 된 튜플을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-175">Because each element in the Fibonacci sequence is the sum of the previous two Fibonacci numbers, the state value is a tuple that consists of the previous two numbers in the sequence.</span></span> <span data-ttu-id="d38ee-176">초기 값은 `(1,1)`, 시퀀스에서 처음 두 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-176">The initial value is `(1,1)`, the first two numbers in the sequence.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet14.fs)]

<span data-ttu-id="d38ee-177">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-177">The output is as follows:</span></span>

```
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

<span data-ttu-id="d38ee-178">다음 코드는 다양 한 여기에서 설명 생성 하 고 무한 시퀀스의 값을 계산 하는 시퀀스 모듈 함수를 사용 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-178">The following code is an example that uses many of the sequence module functions described here to generate and compute the values of infinite sequences.</span></span> <span data-ttu-id="d38ee-179">코드를 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-179">The code might take a few minutes to run.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet15.fs)]
    
## <a name="searching-and-finding-elements"></a><span data-ttu-id="d38ee-180">요소 검색 및 찾기</span><span class="sxs-lookup"><span data-stu-id="d38ee-180">Searching and Finding Elements</span></span>
<span data-ttu-id="d38ee-181">시퀀스 목록을 사용 하 여 사용할 수 있는 기능을 지 원하는 지원: [Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [ Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq.tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47), 및 [Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a)합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-181">Sequences support functionality available with lists: [Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq.tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47), and [Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a).</span></span> <span data-ttu-id="d38ee-182">시퀀스에 사용할 수 있는 이러한 함수 버전에 대 한 검색 되는 요소까지만 시퀀스를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-182">The versions of these functions that are available for sequences evaluate the sequence only up to the element that is being searched for.</span></span> <span data-ttu-id="d38ee-183">예제를 보려면 [나열](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-183">For examples, see [Lists](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).</span></span>


## <a name="obtaining-subsequences"></a><span data-ttu-id="d38ee-184">시퀀스 가져오기</span><span class="sxs-lookup"><span data-stu-id="d38ee-184">Obtaining Subsequences</span></span>
<span data-ttu-id="d38ee-185">[Seq.filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) 및 [Seq.choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) 해당 함수는 필터링과 선택 시퀀스 요소를 계산할 때까지 발생 하지 않는 점을 제외 하 고 목록에 사용할 수 있는 같은 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-185">[Seq.filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) and [Seq.choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) are like the corresponding functions that are available for lists, except that the filtering and choosing does not occur until the sequence elements are evaluated.</span></span>

<span data-ttu-id="d38ee-186">[Seq.truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) 다른 시퀀스에서 시퀀스를 만들지만 시퀀스 요소의 지정 된 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-186">[Seq.truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) creates a sequence from another sequence, but limits the sequence to a specified number of elements.</span></span> <span data-ttu-id="d38ee-187">[Seq.take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) 요소 시퀀스의 시작 부분부터 지정한 수만 포함 하는 새 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-187">[Seq.take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) creates a new sequence that contains only a specified number of elements from the start of a sequence.</span></span> <span data-ttu-id="d38ee-188">지정한 것 보다 더 적은 요소가 시퀀스에 있는 경우 `Seq.take` throw 한 `System.InvalidOperationException`합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-188">If there are fewer elements in the sequence than you specify to take, `Seq.take` throws a `System.InvalidOperationException`.</span></span> <span data-ttu-id="d38ee-189">차이 `Seq.take` 및 `Seq.truncate` 은 `Seq.truncate` 요소의 수는 지정한 숫자 보다 적은 경우 오류를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-189">The difference between `Seq.take` and `Seq.truncate` is that `Seq.truncate` does not produce an error if the number of elements is fewer than the number you specify.</span></span>

<span data-ttu-id="d38ee-190">다음 코드의 동작을 보여 줍니다과 차이점이 `Seq.truncate` 및 `Seq.take`합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-190">The following code shows the behavior of and differences between `Seq.truncate` and `Seq.take`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet16.fs)]

<span data-ttu-id="d38ee-191">출력 오류가 발생 하기 전에 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-191">The output, before the error occurs, is as follows.</span></span>

```
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100 
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100
```

<span data-ttu-id="d38ee-192">사용 하 여 [Seq.takeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), 조건자 함수 (부울 함수)를 지정 하 고 조건자는 원래 시퀀스의 해당 요소의 다른 시퀀스에서 시퀀스를 만들 수 있습니다 `true`, 하지만 중지 조건자 반환 하는 첫 번째 요소 앞 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-192">By using [Seq.takeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), you can specify a predicate function (a Boolean function) and create a sequence from another sequence made up of those elements of the original sequence for which the predicate is `true`, but stop before the first element for which the predicate returns `false`.</span></span> <span data-ttu-id="d38ee-193">[Seq.skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) 지정 된 수의 다른 시퀀스의 첫 번째 요소를 건너뛰고 나머지 요소를 반환 하는 시퀀스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-193">[Seq.skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) returns a sequence that skips a specified number of the first elements of another sequence and returns the remaining elements.</span></span> <span data-ttu-id="d38ee-194">[Seq.skipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) 시퀀스 조건자 반환 다른 시퀀스의 첫 번째 요소를 반환 `true`, 다음 조건자 반환하는첫번째요소부터시작하고나머지요소를반환하고`false`.</span><span class="sxs-lookup"><span data-stu-id="d38ee-194">[Seq.skipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) returns a sequence that skips the first elements of another sequence as long as the predicate returns `true`, and then returns the remaining elements, starting with the first element for which the predicate returns `false`.</span></span>

<span data-ttu-id="d38ee-195">다음 코드 예제에서는의 동작을 보여 줍니다과 차이점이 `Seq.takeWhile`, `Seq.skip`, 및 `Seq.skipWhile`합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-195">The following code example illustrates the behavior of and differences between `Seq.takeWhile`, `Seq.skip`, and `Seq.skipWhile`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet17.fs)]

<span data-ttu-id="d38ee-196">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-196">The output is as follows.</span></span>

```
1 4 9 
36 49 64 81 100 
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a><span data-ttu-id="d38ee-197">시퀀스 변환</span><span class="sxs-lookup"><span data-stu-id="d38ee-197">Transforming Sequences</span></span>
<span data-ttu-id="d38ee-198">[Seq.pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) 튜플로 입력된 시퀀스의 연속 요소 그룹화 되는 새 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-198">[Seq.pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) creates a new sequence in which successive elements of the input sequence are grouped into tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet18.fs)]

<span data-ttu-id="d38ee-199">[Seq.windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) 비슷합니다 `Seq.pairwise`제외 튜플 시퀀스를 생성 하는 대신 인접 요소의 복사본을 포함 하는 배열의 시퀀스를 생성 하 고, (한 *창*) 시퀀스에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-199">[Seq.windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) is like `Seq.pairwise`, except that instead of producing a sequence of tuples, it produces a sequence of arrays that contain copies of adjacent elements (a *window*) from the sequence.</span></span> <span data-ttu-id="d38ee-200">각 배열에 원하는 인접 한 요소 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-200">You specify the number of adjacent elements you want in each array.</span></span>

<span data-ttu-id="d38ee-201">다음 코드 예제에서는 `Seq.windowed`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-201">The following code example demonstrates the use of `Seq.windowed`.</span></span> <span data-ttu-id="d38ee-202">이 경우에 창에 있는 요소의 수는 3입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-202">In this case the number of elements in the window is 3.</span></span> <span data-ttu-id="d38ee-203">이 예제에서는 사용 `printSeq`를 이전 코드 예제에 정의 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-203">The example uses `printSeq`, which is defined in the previous code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet180.fs)]

<span data-ttu-id="d38ee-204">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-204">The output is as follows.</span></span>

<span data-ttu-id="d38ee-205">초기 시퀀스:</span><span class="sxs-lookup"><span data-stu-id="d38ee-205">Initial sequence:</span></span>

```
1.0 1.5 2.0 1.5 1.0 1.5 

Windows of length 3: 
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|] 

Moving average: 
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a><span data-ttu-id="d38ee-206">여러 개의 시퀀스를 사용 하는 작업</span><span class="sxs-lookup"><span data-stu-id="d38ee-206">Operations with Multiple Sequences</span></span>
<span data-ttu-id="d38ee-207">[Seq.zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) 및 [Seq.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) 시퀀스 두 개 또는 세 개의 및 튜플 시퀀스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-207">[Seq.zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) and [Seq.zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) take two or three sequences and produce a sequence of tuples.</span></span> <span data-ttu-id="d38ee-208">이러한 함수는 해당 함수에 사용할 수 있는 유사 [나열](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-208">These functions are like the corresponding functions available for [lists](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).</span></span> <span data-ttu-id="d38ee-209">시퀀스를 두 개 이상의 한 개의 시퀀스를 구분 하는 해당 기능은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-209">There is no corresponding functionality to separate one sequence into two or more sequences.</span></span> <span data-ttu-id="d38ee-210">시퀀스에 대 한이 기능을 해야 할 경우 목록에 시퀀스를 변환 하 고 사용 하 여 [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-210">If you need this functionality for a sequence, convert the sequence to a list and use [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>


## <a name="sorting-comparing-and-grouping"></a><span data-ttu-id="d38ee-211">정렬, 비교 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="d38ee-211">Sorting, Comparing, and Grouping</span></span>
<span data-ttu-id="d38ee-212">목록에 대 한 지원 되는 정렬 함수 시퀀스와도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-212">The sorting functions supported for lists also work with sequences.</span></span> <span data-ttu-id="d38ee-213">여기에 [Seq.sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) 및 [Seq.sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f)합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-213">This includes [Seq.sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) and [Seq.sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f).</span></span> <span data-ttu-id="d38ee-214">이러한 함수는 전체 시퀀스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-214">These functions iterate through the whole sequence.</span></span>

<span data-ttu-id="d38ee-215">사용 하 여 두 시퀀스를 비교는 [Seq.compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-215">You compare two sequences by using the [Seq.compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) function.</span></span> <span data-ttu-id="d38ee-216">연속 요소를 비교 하 고 같지 않은 첫 번째 쌍 발생 하면 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-216">The function compares successive elements in turn, and stops when it encounters the first unequal pair.</span></span> <span data-ttu-id="d38ee-217">추가 요소는 비교에 기여 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-217">Any additional elements do not contribute to the comparison.</span></span>

<span data-ttu-id="d38ee-218">다음 코드는 `Seq.compareWith`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-218">The following code shows the use of `Seq.compareWith`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet19.fs)]

<span data-ttu-id="d38ee-219">이전 코드에서 첫 번째 요소에만 계산 및 조사를 하 고 결과-1입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-219">In the previous code, only the first element is computed and examined, and the result is -1.</span></span>

<span data-ttu-id="d38ee-220">[Seq.countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) 라고 하는 값을 생성 하는 함수는 *키* 각 요소에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-220">[Seq.countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) takes a function that generates a value called a *key* for each element.</span></span> <span data-ttu-id="d38ee-221">각 요소에 대해이 함수를 호출 하 여 각 요소에 대 한 키가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-221">A key is generated for each element by calling this function on each element.</span></span> <span data-ttu-id="d38ee-222">`Seq.countBy` 키 값 및 키의 각 값을 생성 하는 요소의 수를 포함 하는 시퀀스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-222">`Seq.countBy` then returns a sequence that contains the key values, and a count of the number of elements that generated each value of the key.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet201.fs)]

<span data-ttu-id="d38ee-223">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-223">The output is as follows.</span></span>

```
(1, 34) (2, 33) (0, 33)
```

<span data-ttu-id="d38ee-224">이전 출력 2, 키를 생성 하는 33 값과 0 키를 생성 하는 33 값 1, 키를 생성 하는 원래 시퀀스의 34 요소 했음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-224">The previous output shows that there were 34 elements of the original sequence that produced the key 1, 33 values that produced the key 2, and 33 values that produced the key 0.</span></span>

<span data-ttu-id="d38ee-225">호출 하 여 시퀀스의 요소를 그룹화 할 수 있습니다 [Seq.groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd)합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-225">You can group elements of a sequence by calling [Seq.groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd).</span></span> <span data-ttu-id="d38ee-226">`Seq.groupBy` 시퀀스 및 요소에서 키를 생성 하는 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-226">`Seq.groupBy` takes a sequence and a function that generates a key from an element.</span></span> <span data-ttu-id="d38ee-227">함수는 시퀀스의 각 요소에 대해 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-227">The function is executed on each element of the sequence.</span></span> <span data-ttu-id="d38ee-228">`Seq.groupBy` 튜플, 여기서 각 튜플의 첫 번째 요소는 키가 고 두 번째는 해당 키를 생성 하는 요소의 시퀀스의 시퀀스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-228">`Seq.groupBy` returns a sequence of tuples, where the first element of each tuple is the key and the second is a sequence of elements that produce that key.</span></span>

<span data-ttu-id="d38ee-229">다음 코드 예제에서는 사용을 보여 줍니다. `Seq.groupBy` 100부터 1 까지의 숫자 시퀀스 키 값이 각각 0, 1 및 2 3 개의 그룹으로 분할 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-229">The following code example shows the use of `Seq.groupBy` to partition the sequence of numbers from 1 to 100 into three groups that have the distinct key values 0, 1, and 2.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet202.fs)]

<span data-ttu-id="d38ee-230">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-230">The output is as follows.</span></span>

```
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

<span data-ttu-id="d38ee-231">호출 하 여 중복 요소를 제거 하는 시퀀스를 만들 수 [Seq.distinct](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401)합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-231">You can create a sequence that eliminates duplicate elements by calling [Seq.distinct](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401).</span></span> <span data-ttu-id="d38ee-232">사용할 수 있습니다 또는 [Seq.distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), 각 요소에 대해 호출 되는 키 생성 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-232">Or you can use [Seq.distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), which takes a key-generating function to be called on each element.</span></span> <span data-ttu-id="d38ee-233">결과 시퀀스; 고유 키가 원래 시퀀스의 요소를 포함 합니다. 이전 요소에 중복 키를 생성 하는 요소는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-233">The resulting sequence contains elements of the original sequence that have unique keys; later elements that produce a duplicate key to an earlier element are discarded.</span></span>

<span data-ttu-id="d38ee-234">다음 코드 예제에서는 `Seq.distinct`합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-234">The following code example illustrates the use of `Seq.distinct`.</span></span> <span data-ttu-id="d38ee-235">`Seq.distinct` 이진 숫자를 나타내는 시퀀스를 생성 한 다음만 고유 요소가 0과 1을 표시 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-235">`Seq.distinct` is demonstrated by generating sequences that represent binary numbers, and then showing that the only distinct elements are 0 and 1.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet22.fs)]

<span data-ttu-id="d38ee-236">다음 코드에서는 `Seq.distinctBy` 양수 및 음수를 포함 하는 시퀀스를 시작 하 고 키 생성 함수도 절대 값 함수를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-236">The following code demonstrates `Seq.distinctBy` by starting with a sequence that contains negative and positive numbers and using the absolute value function as the key-generating function.</span></span> <span data-ttu-id="d38ee-237">결과 시퀀스에 음수 시퀀스 앞에 같은 절대 있는 양수 대신 선택 되어 있기 때문에 음수 시퀀스에서 일치 하는 모든 양수 없습니다. 값 또는 키입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-237">The resulting sequence is missing all the positive numbers that correspond to the negative numbers in the sequence, because the negative numbers appear earlier in the sequence and therefore are selected instead of the positive numbers that have the same absolute value, or key.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet23.fs)]
    
## <a name="readonly-and-cached-sequences"></a><span data-ttu-id="d38ee-238">읽기 전용 및 캐시 된 시퀀스</span><span class="sxs-lookup"><span data-stu-id="d38ee-238">Readonly and Cached Sequences</span></span>
<span data-ttu-id="d38ee-239">[Seq.readonly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) 시퀀스의 읽기 전용 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-239">[Seq.readonly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) creates a read-only copy of a sequence.</span></span> <span data-ttu-id="d38ee-240">`Seq.readonly` 읽기 / 쓰기 컬렉션, 배열 등과 같이 있고 원래 컬렉션을 수정 하지 않을 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-240">`Seq.readonly` is useful when you have a read-write collection, such as an array, and you do not want to modify the original collection.</span></span> <span data-ttu-id="d38ee-241">이 함수는 데이터 캡슐화를 유지 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-241">This function can be used to preserve data encapsulation.</span></span> <span data-ttu-id="d38ee-242">다음 코드 예제에서는 배열이 포함 된 형식이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-242">In the following code example, a type that contains an array is created.</span></span> <span data-ttu-id="d38ee-243">속성을 노출 하 여 배열에 있지만 사용 하 여 배열에서 만든 하는 시퀀스를 반환 배열을 반환 하는 대신 `Seq.readonly`합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-243">A property exposes the array, but instead of returning an array, it returns a sequence that is created from the array by using `Seq.readonly`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet24.fs)]

<span data-ttu-id="d38ee-244">[Seq.cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) 시퀀스의 저장 된 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-244">[Seq.cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) creates a stored version of a sequence.</span></span> <span data-ttu-id="d38ee-245">사용 하 여 `Seq.cache` 때를 방지 하려면 재평가 또는 시퀀스의 시퀀스를 사용 하는 여러 스레드를 가질 수 있지만 각 요소에 한 번만 대상이 되는 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-245">Use `Seq.cache` to avoid reevaluation of a sequence, or when you have multiple threads that use a sequence, but you must make sure that each element is acted upon only one time.</span></span> <span data-ttu-id="d38ee-246">여러 스레드에서 사용 되는 시퀀스에 있으면를 열거 하 고 원래 순서에 대 한 값을 계산 하는 스레드 하나를 사용할 수 있습니다 및 나머지 스레드 캐시 된 시퀀스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-246">When you have a sequence that is being used by multiple threads, you can have one thread that enumerates and computes the values for the original sequence, and remaining threads can use the cached sequence.</span></span>


## <a name="performing-computations-on-sequences"></a><span data-ttu-id="d38ee-247">시퀀스에 대 한 계산 수행</span><span class="sxs-lookup"><span data-stu-id="d38ee-247">Performing Computations on Sequences</span></span>
<span data-ttu-id="d38ee-248">단순 산술 연산에는 목록의 것과 같은 같은 [Seq.average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [Seq.sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [Seq.averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [Seq.sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)등입니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-248">Simple arithmetic operations are like those of lists, such as [Seq.average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [Seq.sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [Seq.averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [Seq.sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1), and so on.</span></span>

<span data-ttu-id="d38ee-249">[Seq.fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [Seq.reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9), 및 [Seq.scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) 목록에 사용할 수 있는 해당 함수 처럼 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-249">[Seq.fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [Seq.reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9), and [Seq.scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) are like the corresponding functions that are available for lists.</span></span> <span data-ttu-id="d38ee-250">시퀀스는 지원을 나열 하는 이러한 함수의 모든 변형의 하위 집합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-250">Sequences support a subset of the full variations of these functions that lists support.</span></span> <span data-ttu-id="d38ee-251">자세한 내용 및 예제에 대 한 참조 [나열](lists.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d38ee-251">For more information and examples, see [Lists](lists.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d38ee-252">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d38ee-252">See Also</span></span>
[<span data-ttu-id="d38ee-253">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="d38ee-253">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="d38ee-254">F# 형식</span><span class="sxs-lookup"><span data-stu-id="d38ee-254">F# Types</span></span>](fsharp-types.md)
