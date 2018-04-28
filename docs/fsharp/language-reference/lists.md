---
title: 목록(F#)
description: 'F # 목록, 동일한 형식의 요소는 정렬 되 고 변경할 수 없는 계열에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: e29dbdac5e920c009bf7758fd2cc1ad486041cad
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="lists"></a><span data-ttu-id="ab4de-103">목록</span><span class="sxs-lookup"><span data-stu-id="ab4de-103">Lists</span></span>

> [!NOTE]
<span data-ttu-id="ab4de-104">이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="ab4de-105">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="ab4de-106">F#의 목록은 순서가 지정되고 변경할 수 없는 일련의 동일 형식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-106">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="ab4de-107">목록에 대 한 기본 작업을 수행 하려면에 함수를 사용 하 여는 [List 모듈](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-107">To perform basic operations on lists, use the functions in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>


## <a name="creating-and-initializing-lists"></a><span data-ttu-id="ab4de-108">목록 만들기 및 초기화</span><span class="sxs-lookup"><span data-stu-id="ab4de-108">Creating and Initializing Lists</span></span>
<span data-ttu-id="ab4de-109">아래 코드 줄에 나와 있는 것처럼 세미콜론으로 구분되고 대괄호로 묶인 요소를 명시적으로 목록 처리하여 목록을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-109">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="ab4de-110">요소 간에 줄 바꿈을 삽입하고 필요에 따라 세미콜론을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-110">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="ab4de-111">요소 초기화 식이 더 길거나 각 요소에 대해 주석을 추가하려는 경우에는 이 두 번째 구문을 사용하면 코드를 더 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-111">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="ab4de-112">일반적으로 모든 목록 요소는 같은 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-112">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="ab4de-113">단, 요소가 기본 형식으로 지정된 목록에는 파생 형식 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-113">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="ab4de-114">그러므로 `Button` 및 `CheckBox`가 모두 `Control`에서 파생되는 아래 코드는 정상적으로 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-114">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="ab4de-115">아래 코드에 나와 있는 것처럼 범위 연산자(`..`)로 구분된 정수로 표시되는 범위를 사용하여 목록 요소를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-115">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="ab4de-116">빈 목록은 안에 아무 내용이 없는 대괄호 쌍으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-116">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="ab4de-117">시퀀스 식을 사용하여 목록을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-117">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="ab4de-118">참조 [시퀀스 식](sequences.md#sequence-expressions) 자세한 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-118">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="ab4de-119">예를 들어 다음 코드는 정수 1~10의 제곱 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-119">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="ab4de-120">목록 사용을 위한 연산자</span><span class="sxs-lookup"><span data-stu-id="ab4de-120">Operators for Working with Lists</span></span>
<span data-ttu-id="ab4de-121">`::`(cons) 연산자를 사용하여 목록에 요소를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-121">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="ab4de-122">`list1`이 `[2; 3; 4]`이면 다음 코드는 `list2`를 `[100; 2; 3; 4]`로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-122">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="ab4de-123">다음 코드와 같이 `@` 연산자를 사용하여 호환 형식을 포함하는 목록을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-123">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="ab4de-124">`list1`이 `[2; 3; 4]`이고 `list2`가 `[100; 2; 3; 4 ]`이면 다음 코드는 `list3`을 `[2; 3; 4; 100; 2; 3; 4]`로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-124">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4 ]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="ab4de-125">목록에 대 한 작업을 수행 하기 위한 함수에서 사용할 수 있는 [List 모듈](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-125">Functions for performing operations on lists are available in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>

<span data-ttu-id="ab4de-126">F#의 목록은 변경이 불가능하므로 수정 작업을 수행하면 기존 목록이 수정되는 대신 새 목록이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-126">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="ab4de-127">F #의 목록은 이면 목록 헤드에만 액세스 하는 작업은 o (1), 단일 연결된 목록으로 구현 되 고 요소 액세스는 O (*n*).</span><span class="sxs-lookup"><span data-stu-id="ab4de-127">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>


## <a name="properties"></a><span data-ttu-id="ab4de-128">속성</span><span class="sxs-lookup"><span data-stu-id="ab4de-128">Properties</span></span>
<span data-ttu-id="ab4de-129">목록 형식이 지원하는 속성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-129">The list type supports the following properties:</span></span>

|<span data-ttu-id="ab4de-130">속성</span><span class="sxs-lookup"><span data-stu-id="ab4de-130">Property</span></span>|<span data-ttu-id="ab4de-131">형식</span><span class="sxs-lookup"><span data-stu-id="ab4de-131">Type</span></span>|<span data-ttu-id="ab4de-132">설명</span><span class="sxs-lookup"><span data-stu-id="ab4de-132">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="ab4de-133">H e a d</span><span class="sxs-lookup"><span data-stu-id="ab4de-133">Head</span></span>](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740)|`'T`|<span data-ttu-id="ab4de-134">첫 번째 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-134">The first element.</span></span>|
|[<span data-ttu-id="ab4de-135">빈</span><span class="sxs-lookup"><span data-stu-id="ab4de-135">Empty</span></span>](https://msdn.microsoft.com/library/44406ecb-1918-4d32-b32a-ca1f69840386)|`'T list`|<span data-ttu-id="ab4de-136">해당 형식의 빈 목록을 반환하는 정적 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-136">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="ab4de-137">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="ab4de-137">IsEmpty</span></span>](https://msdn.microsoft.com/library/3ba087b2-2fc2-406d-b10a-cff6a19322da)|`bool`|<span data-ttu-id="ab4de-138">목록에 요소가 없으면 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-138">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="ab4de-139">Item</span><span class="sxs-lookup"><span data-stu-id="ab4de-139">Item</span></span>](https://msdn.microsoft.com/library/bdb2553a-0e54-4ff8-baed-ab1aac8f5dae)|`'T`|<span data-ttu-id="ab4de-140">지정한 인덱스에 있는 요소로서 0부터 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-140">The element at the specified index (zero-based).</span></span>|
|[<span data-ttu-id="ab4de-141">길이</span><span class="sxs-lookup"><span data-stu-id="ab4de-141">Length</span></span>](https://msdn.microsoft.com/library/25f715c8-9daa-4c4d-a6c7-26772f9dab4d)|`int`|<span data-ttu-id="ab4de-142">요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-142">The number of elements.</span></span>|
|[<span data-ttu-id="ab4de-143">비상</span><span class="sxs-lookup"><span data-stu-id="ab4de-143">Tail</span></span>](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91)|`'T list`|<span data-ttu-id="ab4de-144">첫 번째 요소가 없는 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-144">The list without the first element.</span></span>|
<span data-ttu-id="ab4de-145">이러한 속성을 사용하는 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-145">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]
    
## <a name="using-lists"></a><span data-ttu-id="ab4de-146">목록 사용</span><span class="sxs-lookup"><span data-stu-id="ab4de-146">Using Lists</span></span>
<span data-ttu-id="ab4de-147">목록을 사용하여 프로그래밍할 때는 적은 양의 코드만으로도 복잡한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-147">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="ab4de-148">이 섹션에서는 기능적인 프로그래밍에 중요한 일반적인 목록 관련 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-148">This section describes common operations on lists that are important to functional programming.</span></span>


### <a name="recursion-with-lists"></a><span data-ttu-id="ab4de-149">목록을 사용한 재귀</span><span class="sxs-lookup"><span data-stu-id="ab4de-149">Recursion with Lists</span></span>
<span data-ttu-id="ab4de-150">목록을 고유한 방식으로 재귀 프로그래밍 기술에 맞게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-150">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="ab4de-151">목록의 모든 요소에 대해 수행해야 하는 작업을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="ab4de-151">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="ab4de-152">목록 헤드에 대해 작업을 수행한 다음 목록 꼬리(첫 번째 요소를 제외한 원래 목록으로 구성되는 더 작은 목록)를 다음 재귀 수준으로 다시 전달하는 재귀적인 방식으로 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-152">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="ab4de-153">이러한 재귀 함수를 작성하려면 패턴 일치에서 cons 연산자(`::`)를 사용합니다. 그러면 목록 헤드를 꼬리에서 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-153">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="ab4de-154">다음 코드 예제에서는 패턴 일치를 사용하여 목록에 대해 작업을 수행하는 재귀 함수를 구현하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-154">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="ab4de-155">위의 코드는 작은 목록에서는 효율적으로 작동하지만 큰 목록에서는 스택이 오버플로될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-155">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="ab4de-156">위의 코드보다 개선된 다음 코드에서는 재귀 함수 사용을 위한 표준 기술인 누적기 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-156">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="ab4de-157">누적기 인수를 사용하면 함수 꼬리가 재귀적으로 적용되므로 스택 공간이 절약됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-157">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="ab4de-158">`RemoveAllMultiples` 함수는 목록 두 개를 사용하는 재귀 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-158">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="ab4de-159">첫 번째 목록은 배수를 제거할 숫자를 포함하며 두 번째 목록은 숫자를 제거할 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-159">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="ab4de-160">다음 예의 코드에서는 이 재귀 함수를 사용하여 목록에서 소수가 아닌 숫자를 모두 삭제해 소수만 포함된 목록을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-160">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="ab4de-161">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-161">The output is as follows:</span></span>

```
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="ab4de-162">모듈 함수</span><span class="sxs-lookup"><span data-stu-id="ab4de-162">Module Functions</span></span>
<span data-ttu-id="ab4de-163">[List 모듈](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) 목록의 요소에 액세스 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-163">The [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) provides functions that access the elements of a list.</span></span> <span data-ttu-id="ab4de-164">가장 빠르고 쉽게 액세스할 수 있는 요소는 헤드 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-164">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="ab4de-165">속성을 사용 하 여 [h e a d](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) 또는 모듈 함수 [List.head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-165">Use the property [Head](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) or the module function [List.head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2).</span></span> <span data-ttu-id="ab4de-166">사용 하 여 목록의 꼬리에 액세스할 수 있습니다는 [꼬리](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) 속성 또는 [List.tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-166">You can access the tail of a list by using the [Tail](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) property or the [List.tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) function.</span></span> <span data-ttu-id="ab4de-167">인덱스 별로 요소를 찾으려면는 [List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-167">To find an element by index, use the [List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) function.</span></span> <span data-ttu-id="ab4de-168">`List.nth`는 목록을 트래버스하므로</span><span class="sxs-lookup"><span data-stu-id="ab4de-168">`List.nth` traverses the list.</span></span> <span data-ttu-id="ab4de-169">따라서 것은 O (*n*).</span><span class="sxs-lookup"><span data-stu-id="ab4de-169">Therefore, it is O(*n*).</span></span> <span data-ttu-id="ab4de-170">코드에서 `List.nth`를 자주 사용하는 경우 목록 대신 배열을 사용해볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-170">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="ab4de-171">배열의 요소 액세스는 O(1)입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-171">Element access in arrays is O(1).</span></span>


### <a name="boolean-operations-on-lists"></a><span data-ttu-id="ab4de-172">목록에 대한 부울 작업</span><span class="sxs-lookup"><span data-stu-id="ab4de-172">Boolean Operations on Lists</span></span>
<span data-ttu-id="ab4de-173">[List.isEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) 함수 목록에 요소가 하나라도 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-173">The [List.isEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) function determines whether a list has any elements.</span></span>

<span data-ttu-id="ab4de-174">[List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) 함수 적용 하는 부울 값의 목록 및 반환 하는 요소는 테스트 `true` 테스트를 만족 하는 요소가 있으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-174">The [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="ab4de-175">[List.exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) 도 이와 비슷하지만 두 목록의 요소 연속적인 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-175">[List.exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="ab4de-176">다음 코드는 `List.exists`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-176">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="ab4de-177">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-177">The output is as follows:</span></span>

```
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="ab4de-178">다음 예에서는 `List.exists2`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-178">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="ab4de-179">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-179">The output is as follows:</span></span>

```
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="ab4de-180">사용할 수 있습니다 [List.forall](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) 목록의 모든 요소가 조건을 만족 하는지 여부를 테스트 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="ab4de-180">You can use [List.forall](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="ab4de-181">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-181">The output is as follows:</span></span>

```
true
false
```

<span data-ttu-id="ab4de-182">마찬가지로, [List.forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) 두 목록의 해당 위치의 모든 요소가 각 요소 쌍을 포함 하는 부울 식에 맞는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-182">Similarly, [List.forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="ab4de-183">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-183">The output is as follows:</span></span>

```
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="ab4de-184">목록에 대한 정렬 작업</span><span class="sxs-lookup"><span data-stu-id="ab4de-184">Sort Operations on Lists</span></span>
<span data-ttu-id="ab4de-185">[List.sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [List.sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359), 및 [List.sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) 함수는 목록을 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-185">The [List.sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [List.sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359), and [List.sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) functions sort lists.</span></span> <span data-ttu-id="ab4de-186">정렬 함수는 이 세 함수 중 사용할 함수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-186">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="ab4de-187">`List.sort`는 기본 제네릭 비교를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-187">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="ab4de-188">제네릭 비교에서는 제네릭 비교 함수를 기반으로 전역 연산자를 사용해 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-188">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="ab4de-189">이 함수는 단순한 숫자 형식, 튜플, 레코드, 구분된 공용 구조체, 목록, 배열, 그리고 `System.IComparable`을 구현하는 모든 형식과 같은 광범위한 요소 형식에서 효율적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-189">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="ab4de-190">`System.IComparable`을 구현하는 형식의 경우 제네릭 비교에서는 `System.IComparable.CompareTo()` 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-190">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="ab4de-191">제네릭 비교는 문자열에도 작동하지만 이 경우에는 문화권과 독립적인 정렬 순서를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-191">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="ab4de-192">함수 형식 등의 지원되지 않는 형식에는 제네릭 비교를 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-192">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="ab4de-193">또한 기본 제네릭 비교의 성능은 작은 구조의 형식에서 가장 우수합니다. 자주 비교하고 정렬해야 하는 큰 구조의 형식에 대해서는 `System.IComparable`을 구현하고 효율적인 `System.IComparable.CompareTo()` 메서드 구현을 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-193">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="ab4de-194">`List.sortBy`는 정렬 기준으로 사용되는 값을 반환하는 함수를 사용하며 `List.sortWith`는 비교 함수를 인수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-194">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="ab4de-195">비교를 지원하지 않는 형식으로 작업 중이거나 비교 시 문화권 인식 문자열과 같이 보다 복잡한 비교 의미 체계를 사용할 때는 이 두 함수가 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-195">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="ab4de-196">다음 예에서는 `List.sort`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-196">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="ab4de-197">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-197">The output is as follows:</span></span>

```
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="ab4de-198">다음 예에서는 `List.sortBy`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-198">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="ab4de-199">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-199">The output is as follows:</span></span>

```
[1; -2; 4; 5; 8]
```

<span data-ttu-id="ab4de-200">다음 예에서는 `List.sortWith`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-200">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="ab4de-201">이 예에서는 사용자 지정 비교 함수 `compareWidgets`를 사용하여 먼저 사용자 지정 형식의 한 필드를 비교한 다음 첫 필드의 값이 같으면 다른 필드를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-201">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="ab4de-202">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-202">The output is as follows:</span></span>

```
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="ab4de-203">목록에 대한 검색 작업</span><span class="sxs-lookup"><span data-stu-id="ab4de-203">Search Operations on Lists</span></span>
<span data-ttu-id="ab4de-204">목록에는 다양한 검색 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-204">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="ab4de-205">가장 단순한 [List.find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), 지정된 된 조건과 일치 하는 첫 번째 요소를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-205">The simplest, [List.find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="ab4de-206">다음 코드 예제에서는 `List.find`를 사용하여 목록에서 5로 나눌 수 있는 첫 번째 숫자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-206">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="ab4de-207">해당 결과는 5입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-207">The result is 5.</span></span>

<span data-ttu-id="ab4de-208">요소를 먼저 변형 해야, 경우에 호출 [List.pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), 함수 반환 하는 옵션 및 첫 번째 옵션에 대 한 검색 값은 `Some(x)`합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-208">If the elements must be transformed first, call [List.pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="ab4de-209">`List.pick`은 요소를 반환하는 대신 `x` 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-209">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="ab4de-210">일치하는 요소가 없으면 `List.pick`은 `System.Collections.Generic.KeyNotFoundException`을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-210">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="ab4de-211">다음 코드는 `List.pick`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-211">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="ab4de-212">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-212">The output is as follows:</span></span>

```
"b"
```

<span data-ttu-id="ab4de-213">다른 그룹 검색 작업 그룹인 [List.tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) 및 관련된 함수는 옵션 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-213">Another group of search operations, [List.tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) and related functions, return an option value.</span></span> <span data-ttu-id="ab4de-214">`List.tryFind` 함수는 조건을 만족하는 목록의 첫 번째 요소가 있으면 해당 요소를 반환하고 요소가 없으면 옵션 값 `None`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-214">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="ab4de-215">변형을 [List.tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) 요소 자체가 아닌 발견 되는 요소의 인덱스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-215">The variation [List.tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="ab4de-216">다음 코드에서는 이러한 함수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-216">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="ab4de-217">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-217">The output is as follows:</span></span>

```
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="ab4de-218">목록에 대한 산술 연산</span><span class="sxs-lookup"><span data-stu-id="ab4de-218">Arithmetic Operations on Lists</span></span>
<span data-ttu-id="ab4de-219">합계 및 평균과 같은 일반적인 산술 연산을에 기본 제공 되는 [List 모듈](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-219">Common arithmetic operations such as sum and average are built into the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="ab4de-220">작업할 [List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), 목록 요소 형식이 지원 해야 합니다는 `+` 연산자 및 값이 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-220">To work with [List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="ab4de-221">모든 기본 제공 연산 형식은 이러한 조건을 만족합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-221">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="ab4de-222">작업할 [List.average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), 요소 형식이 부동 소수점 형식에 대 한 허용 하지만 정수 형식은 제외 나머지가 없는 나누기를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-222">To work with [List.average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="ab4de-223">[List.sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) 및 [List.averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) 함수를 매개 변수로 함수를 사용 하 고이 함수의 결과 합 또는 평균에 대 한 값을 계산 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-223">The [List.sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) and [List.averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="ab4de-224">다음 코드는 `List.sum`, `List.sumBy` 및 `List.average`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-224">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="ab4de-225">출력은 `1.000000`입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-225">The output is `1.000000`.</span></span>

<span data-ttu-id="ab4de-226">다음 코드는 `List.averageBy`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-226">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="ab4de-227">출력은 `5.5`입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-227">The output is `5.5`.</span></span>


### <a name="lists-and-tuples"></a><span data-ttu-id="ab4de-228">목록 및 튜플</span><span class="sxs-lookup"><span data-stu-id="ab4de-228">Lists and Tuples</span></span>
<span data-ttu-id="ab4de-229">튜플을 포함하는 목록은 zip 및 unzip 함수를 통해 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-229">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="ab4de-230">이러한 함수는 단일 값의 두 목록을 튜플 목록 하나로 결합하거나 튜플 목록 하나를 단일 값의 두 목록으로 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-230">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="ab4de-231">가장 간단한 [List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) 함수는 단일 요소의 두 목록 및 단일 튜플 쌍 목록을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-231">The simplest [List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="ab4de-232">다른 버전 [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b)은 단일 요소의 목록 및 단일 요소 세 튜플 목록을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-232">Another version, [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="ab4de-233">다음 코드 예제에서는 `List.zip`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-233">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="ab4de-234">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-234">The output is as follows:</span></span>

```
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="ab4de-235">다음 코드 예제에서는 `List.zip3`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-235">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="ab4de-236">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-236">The output is as follows:</span></span>

```
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="ab4de-237">해당 하는 unzip 버전인 [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) 및 [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4)튜플 목록을 걸리고에 첫 번째 목록에는 각 튜플의 첫 번째는 모든 요소가 포함 된, 여 튜플에 목록을 반환 하며 두 번째 목록에 각 튜플 및 등의 두 번째 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-237">The corresponding unzip versions, [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) and [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="ab4de-238">다음 코드 예제에서는 [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-238">The following code example demonstrates the use of [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="ab4de-239">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-239">The output is as follows:</span></span>

```
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="ab4de-240">다음 코드 예제에서는 [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-240">The following code example demonstrates the use of [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="ab4de-241">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-241">The output is as follows:</span></span>

```
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="ab4de-242">목록 요소에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="ab4de-242">Operating on List Elements</span></span>
<span data-ttu-id="ab4de-243">F#에서는 목록 요소에 대한 여러 작업을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-243">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="ab4de-244">가장 단순한 [List.iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), 목록의 모든 요소에는 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-244">The simplest is [List.iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="ab4de-245">변형이 포함 [List.iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), 두 목록의 요소에 대 한 작업을 수행할 수 있습니다 [List.iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), 하는 것 처럼 `List.iter` 제외 하 고 각 요소의 인덱스 변수로 전달 되는 각 요소에 대해 호출 하는 함수에 인수 및 [List.iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c)의 기능을 결합 한 것입니다 `List.iter2` 및 `List.iteri`합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-245">Variations include [List.iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), which enables you to perform an operation on elements of two lists, [List.iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="ab4de-246">다음 코드 예제에서는 이러한 함수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-246">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="ab4de-247">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-247">The output is as follows:</span></span>

```
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

<span data-ttu-id="ab4de-248">목록 요소를 변환 하는 또 다른 자주 사용 되는 함수는 [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), 목록의 각 요소에 함수를 적용 하 고 새 목록에 모든 결과 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-248">Another frequently used function that transforms list elements is [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="ab4de-249">[List.map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) 및 [List.map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) 여러 목록을 사용 하는 변형 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-249">[List.map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) and [List.map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) are variations that take multiple lists.</span></span> <span data-ttu-id="ab4de-250">사용할 수도 있습니다 [List.mapi](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) 및 [List.mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49)요소, 외에도 함수 각 요소의 인덱스 전달 해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="ab4de-250">You can also use [List.mapi](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) and [List.mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="ab4de-251">`List.mapi2`와 `List.mapi`의 차이점은 `List.mapi2`의 경우 목록 두 개를 사용한다는 것뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-251">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="ab4de-252">다음 예제에서는 [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-252">The following example illustrates [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="ab4de-253">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-253">The output is as follows:</span></span>

```
[2; 3; 4]
```

<span data-ttu-id="ab4de-254">다음 예에서는 `List.map2`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-254">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="ab4de-255">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-255">The output is as follows:</span></span>

```
[5; 7; 9]
```

<span data-ttu-id="ab4de-256">다음 예에서는 `List.map3`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-256">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="ab4de-257">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-257">The output is as follows:</span></span>

```
[7; 10; 13]
```

<span data-ttu-id="ab4de-258">다음 예에서는 `List.mapi`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-258">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="ab4de-259">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-259">The output is as follows:</span></span>

```
[1; 3; 5]
```

<span data-ttu-id="ab4de-260">다음 예에서는 `List.mapi2`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-260">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="ab4de-261">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-261">The output is as follows:</span></span>

```
[0; 7; 18]
```

<span data-ttu-id="ab4de-262">[List.collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) 비슷합니다 `List.map`제외 하 고 각 요소가 목록을 생성 하 고 이러한 모든 목록이 최종 목록으로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-262">[List.collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="ab4de-263">다음 코드에서는 목록의 각 요소가 숫자 3개를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-263">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="ab4de-264">이러한 숫자는 모두 목록 하나에 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-264">These are all collected into one list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="ab4de-265">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-265">The output is as follows:</span></span>

```
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="ab4de-266">사용할 수도 있습니다 [List.filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), 부울 조건을 사용 하 고 지정된 된 조건을 만족 하는 요소만으로 구성 된 새 목록을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-266">You can also use [List.filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="ab4de-267">그러면 `[2; 4; 6]` 목록이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-267">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="ab4de-268">맵과 필터의 조합인 [List.choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) 변환 하 고 동시에 요소를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-268">A combination of map and filter, [List.choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="ab4de-269">`List.choose`는 목록의 각 요소에 대한 옵션을 반환하는 함수를 적용하고, 함수가 옵션 값 `Some`을 반환하면 요소에 대해 새 결과 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-269">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="ab4de-270">다음 코드는 `List.choose`를 사용하여 단어 목록에서 대문자로 표기된 단어를 선택하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-270">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="ab4de-271">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-271">The output is as follows:</span></span>

```
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="ab4de-272">여러 목록에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="ab4de-272">Operating on Multiple Lists</span></span>
<span data-ttu-id="ab4de-273">여러 목록을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-273">Lists can be joined together.</span></span> <span data-ttu-id="ab4de-274">사용 하 여 두 목록을 하나로 연결할 [List.append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-274">To join two lists into one, use [List.append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426).</span></span> <span data-ttu-id="ab4de-275">사용 하 여 두 개 이상의 목록에 참여 하기 [List.concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-275">To join more than two lists, use [List.concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet26.fs)]
    
### <a name="fold-and-scan-operations"></a><span data-ttu-id="ab4de-276">접기 및 검사 작업</span><span class="sxs-lookup"><span data-stu-id="ab4de-276">Fold and Scan Operations</span></span>
<span data-ttu-id="ab4de-277">모든 목록 요소가 상호 종속되어야 하는 목록 작업도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-277">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="ab4de-278">접기 및 검사 작업은 `List.iter` 및 `List.map` 각 요소에 대해 함수를 호출 하면 이러한 작업 라는 추가 매개 변수를 제공 한다는 점에서 *누적기* 를 통해 정보를 전달 하는 계산입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-278">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="ab4de-279">목록에 대해 계산을 수행하려면 `List.fold`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-279">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="ab4de-280">다음 코드 예제에서는 [List.fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) 다양 한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-280">The following code example demonstrates the use of [List.fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) to perform various operations.</span></span>

<span data-ttu-id="ab4de-281">이 함수는 목록을 트래버스합니다. 누적기 `acc`는 계산이 진행되면서 전달되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-281">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="ab4de-282">첫 번째 인수는 누적기와 목록 요소를 사용하여 해당 목록 요소에 대한 계산의 중간 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-282">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="ab4de-283">두 번째 인수는 누적기의 초기 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-283">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="ab4de-284">이러한 함수 중 함수 이름에 숫자가 있는 버전은 둘 이상의 목록에 대해 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-284">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="ab4de-285">예를 들어 [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) 두 개의 목록에는 계산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-285">For example, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) performs computations on two lists.</span></span>

<span data-ttu-id="ab4de-286">다음 예에서는 `List.fold2`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-286">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="ab4de-287">`List.fold` 및 [List.scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) 한다는 점에서 차이가 `List.fold` 은 추가 매개 변수의 최종 값을 반환 하지만 `List.scan` 의 추가 매개 변수의 최종 값) (함께 중간 값의 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-287">`List.fold` and [List.scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="ab4de-288">예를 들어 같은 역방향 변형을 포함 되어 이러한 각 함수 [List.foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7)를 순서 대로 다른는 목록 트래버스 순서와 인수 순서가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-288">Each of these functions includes a reverse variation, for example, [List.foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="ab4de-289">또한 `List.fold` 및 `List.foldBack` 변형이 [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) 및 [List.foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), 길이가 같은 두 목록을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-289">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) and [List.foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), that take two lists of equal length.</span></span> <span data-ttu-id="ab4de-290">각 요소에 대해 실행되는 함수는 두 목록의 해당 요소를 사용하여 일부 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-290">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="ab4de-291">다음 예에서와 같이 두 목록의 요소 형식은 다를 수 있습니다. 여기서 한 목록은 은행 계좌의 거래 금액을 포함하고 다른 목록은 거래 형식(입금 또는 출금)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-291">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="ab4de-292">합계와 같은 계산의 경우 `List.fold` 및 `List.foldBack`을 사용해도 결과는 동일합니다. 트래버스 순서에 따라 결과가 달라지지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-292">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="ab4de-293">다음 예에서는 `List.foldBack`을 사용하여 목록에 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-293">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="ab4de-294">다음 예에서는 은행 계좌 예로 다시 돌아옵니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-294">The following example returns to the bank account example.</span></span> <span data-ttu-id="ab4de-295">이번에는 새로운 거래 형식인 이자 계산을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-295">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="ab4de-296">따라서 최종 잔액은 거래 순서에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-296">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="ab4de-297">함수 [List.reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) 다소 비슷합니다 `List.fold` 및 `List.scan`점을 제외 하 고, 별도 누적기를 전달 하는 대신 `List.reduce` 아닌 요소 형식의 두 인수를 사용 하는 함수 하나 및 두 인수 중 하나가 누적기 계산의 중간 결과 저장 하는 것으로 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-297">The function [List.reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="ab4de-298">`List.reduce`는 먼저 처음 두 목록 요소에 대해 실행된 후 해당 작업의 결과를 다음 요소와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-298">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="ab4de-299">고유한 형식이 지정된 별도의 누적기가 없으므로 `List.reduce`는 누적기와 요소 형식이 같을 때만 `List.fold` 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-299">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="ab4de-300">다음 코드는 `List.reduce`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-300">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="ab4de-301">제공된 목록에 요소가 없으면 `List.reduce`는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-301">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="ab4de-302">다음 코드에서는 첫 번째 람다 식 호출에 인수 2와 4가 사용되며 결과로 6이 반환됩니다. 그 다음 호출에는 인수 6과 10이 사용되며 결과로 16이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-302">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet33.fs)]
    
### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="ab4de-303">목록과 기타 컬렉션 형식 간 변환</span><span class="sxs-lookup"><span data-stu-id="ab4de-303">Converting Between Lists and Other Collection Types</span></span>
<span data-ttu-id="ab4de-304">`List` 모듈은 시퀀스와 배열 간 변환을 위한 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-304">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="ab4de-305">으로 변환 하는 시퀀스에서를 사용 하 여 [List.toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) 또는 [List.ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-305">To convert to or from a sequence, use [List.toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) or [List.ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0).</span></span> <span data-ttu-id="ab4de-306">사용 하 여 배열에서 변환할 [List.toArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) 또는 [List.ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-306">To convert to or from an array, use [List.toArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) or [List.ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).</span></span>


### <a name="additional-operations"></a><span data-ttu-id="ab4de-307">추가 작업</span><span class="sxs-lookup"><span data-stu-id="ab4de-307">Additional Operations</span></span>
<span data-ttu-id="ab4de-308">목록에 추가 작업에 대 한 내용은 라이브러리 참조 항목을 참조 하십시오. [Collections.List 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4de-308">For information about additional operations on lists, see the library reference topic [Collections.List Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d).</span></span>


## <a name="see-also"></a><span data-ttu-id="ab4de-309">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab4de-309">See Also</span></span>
[<span data-ttu-id="ab4de-310">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="ab4de-310">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="ab4de-311">F# 형식</span><span class="sxs-lookup"><span data-stu-id="ab4de-311">F# Types</span></span>](fsharp-types.md)

[<span data-ttu-id="ab4de-312">시퀀스</span><span class="sxs-lookup"><span data-stu-id="ab4de-312">Sequences</span></span>](sequences.md)

[<span data-ttu-id="ab4de-313">배열</span><span class="sxs-lookup"><span data-stu-id="ab4de-313">Arrays</span></span>](arrays.md)

[<span data-ttu-id="ab4de-314">옵션</span><span class="sxs-lookup"><span data-stu-id="ab4de-314">Options</span></span>](options.md)
