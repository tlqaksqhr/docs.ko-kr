---
title: "함수를 고급 값으로 상승(F#)"
description: "함수는 F # 프로그래밍 언어에 대 한 고급 상태로 승격 되는 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6b76b93b-a141-40f4-976c-7f0c558d6d09
ms.openlocfilehash: bca0e09edbe0aa86f0db746282acd4f4b3237a03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="functions-as-first-class-values"></a><span data-ttu-id="bf832-104">함수를 고급 값으로 상승</span><span class="sxs-lookup"><span data-stu-id="bf832-104">Functions as First-Class Values</span></span>

<span data-ttu-id="bf832-105">함수형 프로그래밍 언어의 특징은 함수를 고급 상태 상승입니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-105">A defining characteristic of functional programming languages is the elevation of functions to first-class status.</span></span> <span data-ttu-id="bf832-106">모든 다른 기본 제공 형식의 값을 사용 하 여 수행할 수 있고 상대적으로 적은 노력 이렇게 할 수는 함수를 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-106">You should be able to do with a function whatever you can do with values of the other built-in types, and be able to do so with a comparable degree of effort.</span></span>

<span data-ttu-id="bf832-107">일반적인 측정값 고급 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-107">Typical measures of first-class status include the following:</span></span>

- <span data-ttu-id="bf832-108">식별자에 함수를 바인딩할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="bf832-108">Can you bind functions to identifiers?</span></span> <span data-ttu-id="bf832-109">즉, 사용자 이름을 지정할 수에?</span><span class="sxs-lookup"><span data-stu-id="bf832-109">That is, can you give them names?</span></span>

- <span data-ttu-id="bf832-110">저장할 수의 데이터 구조를 함수과 같은 목록에서?</span><span class="sxs-lookup"><span data-stu-id="bf832-110">Can you store functions in data structures, such as in a list?</span></span>

- <span data-ttu-id="bf832-111">함수는 함수 호출에서 인수로 전달할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="bf832-111">Can you pass a function as an argument in a function call?</span></span>

- <span data-ttu-id="bf832-112">함수 호출에서 함수를 반환할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="bf832-112">Can you return a function from a function call?</span></span>

<span data-ttu-id="bf832-113">마지막 두 개의 측정값 정의 일명 *고차 연산* 또는 *고차 함수*합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-113">The last two measures define what are known as *higher-order operations* or *higher-order functions*.</span></span> <span data-ttu-id="bf832-114">고차 함수는 함수를 인수로 받아들이고 함수 호출 값으로 함수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-114">Higher-order functions accept functions as arguments and return functions as the value of function calls.</span></span> <span data-ttu-id="bf832-115">이러한 작업에는 매핑 함수 및 함수 컴퍼지션으로 함수형 프로그래밍의 핵심적 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-115">These operations support such mainstays of functional programming as mapping functions and composition of functions.</span></span>


## <a name="give-the-value-a-name"></a><span data-ttu-id="bf832-116">값에 이름을 지정합니다</span><span class="sxs-lookup"><span data-stu-id="bf832-116">Give the Value a Name</span></span>

<span data-ttu-id="bf832-117">함수는 첫 번째 클래스 값 이면 있습니다 수 있어야 이름을 것 처럼 정수, 문자열 및 다른 기본 제공 형식 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-117">If a function is a first-class value, you must be able to name it, just as you can name integers, strings, and other built-in types.</span></span> <span data-ttu-id="bf832-118">이 식별자 값에 바인딩할으로 함수형 프로그래밍 연구에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-118">This is referred to in functional programming literature as binding an identifier to a value.</span></span> <span data-ttu-id="bf832-119">사용 하 여 F # [ `let` 바인딩](../language-reference/functions/let-bindings.md) 이름 값에 바인딩할: `let <identifier> = <value>`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-119">F# uses [`let` bindings](../language-reference/functions/let-bindings.md) to bind names to values: `let <identifier> = <value>`.</span></span> <span data-ttu-id="bf832-120">다음 코드는 두 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-120">The following code shows two examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

<span data-ttu-id="bf832-121">쉽게 함수를 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-121">You can name a function just as easily.</span></span> <span data-ttu-id="bf832-122">다음 예제에서는 라는 함수를 정의 `squareIt` 식별자를 바인딩하여 `squareIt` 에 [람다 식을](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-122">The following example defines a function named `squareIt` by binding the identifier `squareIt` to the [lambda expression](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span></span> <span data-ttu-id="bf832-123">함수 `squareIt` 하나의 매개 변수가 `n`, 해당 매개 변수에 대 한 제곱을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-123">Function `squareIt` has one parameter, `n`, and it returns the square of that parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

<span data-ttu-id="bf832-124">F #는 다음과 같은 장점이 더 간결한 구문을 입력으로 동일한 결과 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-124">F# provides the following more concise syntax to achieve the same result with less typing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

<span data-ttu-id="bf832-125">첫 번째 스타일을 사용 하 여이 예제에서는 주로 `let <function-name> = <lambda-expression>`, 함수 선언과 다른 유형의 값 사이의 유사성을 강조 하기.</span><span class="sxs-lookup"><span data-stu-id="bf832-125">The examples that follow mostly use the first style, `let <function-name> = <lambda-expression>`, to emphasize the similarities between the declaration of functions and the declaration of other types of values.</span></span> <span data-ttu-id="bf832-126">그러나 모든 명명 된 함수 간결한 구문을 사용 하 여 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-126">However, all the named functions can also be written with the concise syntax.</span></span> <span data-ttu-id="bf832-127">일부 예제는 두 가지 방식으로 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-127">Some of the examples are written in both ways.</span></span>


## <a name="store-the-value-in-a-data-structure"></a><span data-ttu-id="bf832-128">데이터 구조에서 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-128">Store the Value in a Data Structure</span></span>

<span data-ttu-id="bf832-129">데이터 구조에는 첫 번째 클래스 값을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-129">A first-class value can be stored in a data structure.</span></span> <span data-ttu-id="bf832-130">다음 코드는 목록 및 튜플 값을 저장 하는 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-130">The following code shows examples that store values in lists and in tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

<span data-ttu-id="bf832-131">함수에 튜플을 저장 된 함수 이름이 계산 실제로 않습니다를 확인 하려면 다음 예제에서는 `fst` 및 `snd` 튜플 로부터 첫 번째 및 두 번째 요소를 추출 하는 연산자 `funAndArgTuple`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-131">To verify that a function name stored in a tuple does in fact evaluate to a function, the following example uses the `fst` and `snd` operators to extract the first and second elements from tuple `funAndArgTuple`.</span></span> <span data-ttu-id="bf832-132">튜플의 첫 번째 요소는 `squareIt` 두 번째 요소는 `num`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-132">The first element in the tuple is `squareIt` and the second element is `num`.</span></span> <span data-ttu-id="bf832-133">식별자 `num` 정수, 10에 대 한 유효한 인수에는 앞의 예에서 바인딩되는 `squareIt` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-133">Identifier `num` is bound in a previous example to integer 10, a valid argument for the `squareIt` function.</span></span> <span data-ttu-id="bf832-134">두 번째 식은 튜플의 첫 번째 요소 튜플의 두 번째 요소에 적용: `squareIt num`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-134">The second expression applies the first element in the tuple to the second element in the tuple: `squareIt num`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

<span data-ttu-id="bf832-135">마찬가지로, 식별자로 `num` 정수 10 일 수 있습니다 및 식별자를 수 있으므로 서로 교대로 사용 `squareIt` 람다 식과 `fun n -> n * n`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-135">Similarly, just as identifier `num` and integer 10 can be used interchangeably, so can identifier `squareIt` and lambda expression `fun n -> n * n`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]
    
## <a name="pass-the-value-as-an-argument"></a><span data-ttu-id="bf832-136">값을 인수로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-136">Pass the Value as an Argument</span></span>

<span data-ttu-id="bf832-137">값에 있는 경우 고급 상태는 언어에서를 함수에 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-137">If a value has first-class status in a language, you can pass it as an argument to a function.</span></span> <span data-ttu-id="bf832-138">예를 들어 일반적으로 정수 및 문자열 인수로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-138">For example, it is common to pass integers and strings as arguments.</span></span> <span data-ttu-id="bf832-139">다음 코드에서는 정수 및 F #에 인수로 전달 된 문자열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-139">The following code shows integers and strings passed as arguments in F#.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

<span data-ttu-id="bf832-140">함수의 첫 번째 클래스 상태가 있으면 같은 방식으로 인수로 전달할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-140">If functions have first-class status, you must be able to pass them as arguments in the same way.</span></span> <span data-ttu-id="bf832-141">고차 함수의 첫 번째 특성 임을 기억 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-141">Remember that this is the first characteristic of higher-order functions.</span></span>

<span data-ttu-id="bf832-142">다음 예제에서에서 함수 `applyIt` 2 개의 매개 변수가 `op` 및 `arg`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-142">In the following example, function `applyIt` has two parameters, `op` and `arg`.</span></span> <span data-ttu-id="bf832-143">에 대 한 1 개의 매개 변수가 있는 함수에서 보낼 `op` 및 적절 한 인수를 함수에 대 한 `arg`, 함수를 적용 한 결과 반환 `op` 를 `arg`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-143">If you send in a function that has one parameter for `op` and an appropriate argument for the function to `arg`, the function returns the result of applying `op` to `arg`.</span></span> <span data-ttu-id="bf832-144">다음 예제에서는 함수 인수 및 정수 인수를 모두는 동일한 방식으로 전송 됩니다는 이름을 사용 하 여.</span><span class="sxs-lookup"><span data-stu-id="bf832-144">In the following example, both the function argument and the integer argument are sent in the same way, by using their names.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

<span data-ttu-id="bf832-145">다른 함수에 대 한 인수로 함수를 보낼 수 있는 기능에는 일반적인 추상화 맵 또는 필터 작업과 같은 함수형 프로그래밍 언어에서의 기초가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-145">The ability to send a function as an argument to another function underlies common abstractions in functional programming languages, such as map or filter operations.</span></span> <span data-ttu-id="bf832-146">예를 들어 맵 작업 목록을 단계별로 각 요소에 작업을 수행 하 고 다음 결과의 목록을 반환 하는 함수에서 공유 하는 계산을 캡처하는 고차 함수를입니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-146">A map operation, for example, is a higher-order function that captures the computation shared by functions that step through a list, do something to each element, and then return a list of the results.</span></span> <span data-ttu-id="bf832-147">정수, 목록의 각 요소를 늘리거나 각 요소를 제곱 또는 문자열의 목록에서 각 요소를 대문자로 변경 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-147">You might want to increment each element in a list of integers, or to square each element, or to change each element in a list of strings to uppercase.</span></span> <span data-ttu-id="bf832-148">계산의 오류가 발생 하기 쉬운 부분은 재귀 프로세스를 단계별로 실행 목록 및 반환 하도록 결과 목록을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-148">The error-prone part of the computation is the recursive process that steps through the list and builds a list of the results to return.</span></span> <span data-ttu-id="bf832-149">해당 파트는 매핑 함수에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-149">That part is captured in the mapping function.</span></span> <span data-ttu-id="bf832-150">특정 응용 프로그램에 대 한 작성 해야 할 모든는 개별적으로 목록의 각 요소에 적용 하려는 되는 함수 (추가, 제곱 대/소문자 변경).</span><span class="sxs-lookup"><span data-stu-id="bf832-150">All you have to write for a particular application is the function that you want to apply to each list element individually (adding, squaring, changing case).</span></span> <span data-ttu-id="bf832-151">함수를 보내 인수로 하도록 매핑 함수 처럼 `squareIt` 보내집니다 `applyIt` 이전 예에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-151">That function is sent as an argument to the mapping function, just as `squareIt` is sent to `applyIt` in the previous example.</span></span>

<span data-ttu-id="bf832-152">F # 같은 대부분의 컬렉션 형식에 대 한 지도 메서드를 제공 합니다. [나열](../language-reference/lists.md), [배열](../language-reference/arrays.md), 및 [시퀀스](../language-reference/sequences.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-152">F# provides map methods for most collection types, including [lists](../language-reference/lists.md), [arrays](../language-reference/arrays.md), and [sequences](../language-reference/sequences.md).</span></span> <span data-ttu-id="bf832-153">다음 예에서는 목록을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-153">The following examples use lists.</span></span> <span data-ttu-id="bf832-154">구문은 `List.map <the function> <the list>`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-154">The syntax is `List.map <the function> <the list>`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

<span data-ttu-id="bf832-155">자세한 내용은 참조 [나열](../language-reference/lists.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-155">For more information, see [Lists](../language-reference/lists.md).</span></span>

## <a name="return-the-value-from-a-function-call"></a><span data-ttu-id="bf832-156">함수 호출에서 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-156">Return the Value from a Function Call</span></span>

<span data-ttu-id="bf832-157">마지막으로, 함수 언어의 고급 상태 있으면 있어야 함수 호출의 값으로 반환 하려면 정수 및 문자열과 같은 다른 형식을 반환 하는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-157">Finally, if a function has first-class status in a language, you must be able to return it as the value of a function call, just as you return other types, such as integers and strings.</span></span>

<span data-ttu-id="bf832-158">다음 함수 호출에서는 정수를 반환 하 고 주석이 표시.</span><span class="sxs-lookup"><span data-stu-id="bf832-158">The following function calls return integers and display them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

<span data-ttu-id="bf832-159">다음 함수 호출은 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-159">The following function call returns a string.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

<span data-ttu-id="bf832-160">를 인라인으로 선언한 다음 함수 호출에는 부울 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-160">The following function call, declared inline, returns a Boolean value.</span></span> <span data-ttu-id="bf832-161">표시 되는 값은 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-161">The value displayed is `True`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

<span data-ttu-id="bf832-162">함수 호출의 값으로 함수를 반환 하는 기능이 더 높은 순서 함수의 두 번째 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-162">The ability to return a function as the value of a function call is the second characteristic of higher-order functions.</span></span> <span data-ttu-id="bf832-163">다음 예에서 `checkFor` 하나의 인수를 사용 하는 함수 정의 됩니다. `item`, 해당 값으로 새 함수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-163">In the following example, `checkFor` is defined to be a function that takes one argument, `item`, and returns a new function as its value.</span></span> <span data-ttu-id="bf832-164">반환 된 함수에서는 인수로 목록과 `lst`, 검색 및 `item` 에서 `lst`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-164">The returned function takes a list as its argument, `lst`, and searches for `item` in `lst`.</span></span> <span data-ttu-id="bf832-165">경우 `item` 가 있으면 반환 하 고 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-165">If `item` is present, the function returns `true`.</span></span> <span data-ttu-id="bf832-166">경우 `item` 없으면, 함수 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-166">If `item` is not present, the function returns `false`.</span></span> <span data-ttu-id="bf832-167">이전 단원에서와 마찬가지로 다음 코드에서는 제공 된 목록 함수 [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), 목록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-167">As in the previous section, the following code uses a provided list function, [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), to search the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="bf832-168">다음 코드에서는 `checkFor` 목록에서 하나의 인수, 목록 및 7에 대 한 검색을 사용 하는 새 함수를 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-168">The following code uses `checkFor` to create a new function that takes one argument, a list, and searches for 7 in the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

<span data-ttu-id="bf832-169">다음 예제를 사용 하 여 함수의 고급 상태 F #에 함수 선언 `compose`, 두 개의 함수 인수 컴퍼지션을 반환 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-169">The following example uses the first-class status of functions in F# to declare a function, `compose`, that returns a composition of two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]
    
>[!NOTE]
<span data-ttu-id="bf832-170">더 짧게 버전을 다음 섹션인 "Curried 함수입니다."를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf832-170">For an even shorter version, see the following section, "Curried Functions."</span></span>


<span data-ttu-id="bf832-171">다음 코드에 대 한 인수도 두 개의 함수를 보냅니다 `compose`모두의 동일한 형식의 단일 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-171">The following code sends two functions as arguments to `compose`, both of which take a single argument of the same type.</span></span> <span data-ttu-id="bf832-172">반환 값은 새 함수 두 함수 인수의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-172">The return value is a new function that is a composition of the two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]
    
>[!NOTE] 
<span data-ttu-id="bf832-173">F #-두 연산자를 제공 하는 중 `<<` 및 `>>`, 함수를 작성 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-173">F# provides two operators, `<<` and `>>`, that compose functions.</span></span> <span data-ttu-id="bf832-174">예를 들어 `let squareAndDouble2 = doubleIt << squareIt` 같습니다 `let squareAndDouble = compose doubleIt squareIt` 이전 예에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-174">For example, `let squareAndDouble2 = doubleIt << squareIt` is equivalent to `let squareAndDouble = compose doubleIt squareIt` in the previous example.</span></span>

<span data-ttu-id="bf832-175">함수 호출의 값으로 함수를 반환의 다음 예제에서는 간단한 추측 게임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-175">The following example of returning a function as the value of a function call creates a simple guessing game.</span></span> <span data-ttu-id="bf832-176">게임을 만들려면 호출 `makeGame` 값을 사용 해야 할지 추측 하기가 사용자 하려는 전달 `target`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-176">To create a game, call `makeGame` with the value that you want someone to guess sent in for `target`.</span></span> <span data-ttu-id="bf832-177">함수에서 반환 값 `makeGame` (추측) 인수를 하나만 사용 하 여 추측이 올바른지 여부를 보고 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-177">The return value from function `makeGame` is a function that takes one argument (the guess) and reports whether the guess is correct.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

<span data-ttu-id="bf832-178">다음 호출 코드 `makeGame`, 값 보내는 `7` 에 대 한 `target`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-178">The following code calls `makeGame`, sending the value `7` for `target`.</span></span> <span data-ttu-id="bf832-179">식별자 `playGame` 반환 된 람다 식에 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-179">Identifier `playGame` is bound to the returned lambda expression.</span></span> <span data-ttu-id="bf832-180">따라서 `playGame` 에 대 한 값을 하나의 인수로 사용 하는 함수는 `guess`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-180">Therefore, `playGame` is a function that takes as its one argument a value for `guess`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]
    
## <a name="curried-functions"></a><span data-ttu-id="bf832-181">커리 된 함수</span><span class="sxs-lookup"><span data-stu-id="bf832-181">Curried Functions</span></span>

<span data-ttu-id="bf832-182">암시적의 이용 하 여 더 간결 하 게 쓸 수의 많은 예제에서는 이전 단원의 *커리* F # 함수 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-182">Many of the examples in the previous section can be written more concisely by taking advantage of the implicit *currying* in F# function declarations.</span></span> <span data-ttu-id="bf832-183">커리 둘 이상의 매개 변수는 각각 단일 매개 변수를 갖는 일련의 포함 된 함수에 포함 된 함수를 변환 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-183">Currying is a process that transforms a function that has more than one parameter into a series of embedded functions, each of which has a single parameter.</span></span> <span data-ttu-id="bf832-184">F #에서 둘 이상의 매개 변수는 함수를 기본적으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-184">In F#, functions that have more than one parameter are inherently curried.</span></span> <span data-ttu-id="bf832-185">예를 들어 `compose` 이전 섹션에서로 작성할 수 있는 세 개의 매개 변수가 있는 다음 간결한 스타일에 표시 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-185">For example, `compose` from the previous section can be written as shown in the following concise style, with three parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

<span data-ttu-id="bf832-186">그러나 결과 함수에 나와 있는 것 처럼 하나의 매개 변수는 다른 함수를 반환 하는 하나의 매개 변수는 함수를 반환 하는 하나의 매개의 `compose4curried`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-186">However, the result is a function of one parameter that returns a function of one parameter that in turn returns another function of one parameter, as shown in `compose4curried`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

<span data-ttu-id="bf832-187">여러 가지 방법으로이 함수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-187">You can access this function in several ways.</span></span> <span data-ttu-id="bf832-188">다음 예에서는 각 반환 하 고 18를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-188">Each of the following examples returns and displays 18.</span></span> <span data-ttu-id="bf832-189">바꿀 수 `compose4` 와 `compose4curried` 예 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-189">You can replace `compose4` with `compose4curried` in any of the examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

<span data-ttu-id="bf832-190">이전 처럼 함수 여전히 작동 하는지 확인 하려면 원래 테스트 사례를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-190">To verify that the function still works as it did before, try the original test cases again.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]
    
>[!NOTE] 
<span data-ttu-id="bf832-191">튜플에 매개 변수를 포함 하 여 커리 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-191">You can restrict currying by enclosing parameters in tuples.</span></span> <span data-ttu-id="bf832-192">자세한 내용은 "매개 변수 패턴"에서 참조 [매개 변수 및 인수](../language-reference/parameters-and-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-192">For more information, see "Parameter Patterns" in [Parameters and Arguments](../language-reference/parameters-and-arguments.md).</span></span>

<span data-ttu-id="bf832-193">다음 예제에서는 암시적 커리의 짧은 버전을 작성 `makeGame`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-193">The following example uses implicit currying to write a shorter version of `makeGame`.</span></span> <span data-ttu-id="bf832-194">방법 자세히 `makeGame` 생성 및 반환 된 `game` 함수는이 형식으로 명시적 덜 않지만 결과 동일는 원래 테스트 사례를 사용 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-194">The details of how `makeGame` constructs and returns the `game` function are less explicit in this format, but you can verify by using the original test cases that the result is the same.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

<span data-ttu-id="bf832-195">변환 하는 방법에 대 한 자세한 내용은의 "인수 부분 응용 프로그램" 참조 [함수](../language-reference/functions/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-195">For more information about currying, see "Partial Application of Arguments" in [Functions](../language-reference/functions/index.md).</span></span>


## <a name="identifier-and-function-definition-are-interchangeable"></a><span data-ttu-id="bf832-196">식별자 및 함수는 서로 전환이 가능</span><span class="sxs-lookup"><span data-stu-id="bf832-196">Identifier and Function Definition Are Interchangeable</span></span>
<span data-ttu-id="bf832-197">변수 이름 `num` 이전 예에서는 정수를 10으로 계산 되 고이 올바르기 때문 된 `num` 은 유효 10도를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-197">The variable name `num` in the previous examples evaluates to the integer 10, and it is no surprise that where `num` is valid, 10 is also valid.</span></span> <span data-ttu-id="bf832-198">기능 식별자 및 해당 값의 경우도 마찬가지: 함수의 이름을 사용할 수 원하는 위치에 연결 된 람다 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-198">The same is true of function identifiers and their values: anywhere the name of the function can be used, the lambda expression to which it is bound can be used.</span></span>

<span data-ttu-id="bf832-199">다음 예제에서는 정의 `Boolean` 함수를 호출 `isNegative`, 다음 함수의 이름과 함수 정의 같은 의미로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-199">The following example defines a `Boolean` function called `isNegative`, and then uses the name of the function and the definition of the function interchangeably.</span></span> <span data-ttu-id="bf832-200">다음 세 가지 예제 모두 반환 하 고 표시 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-200">The next three examples all return and display `False`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

<span data-ttu-id="bf832-201">한 단계 더, 값을 대체 하는 `applyIt` for에 바인딩된 `applyIt`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-201">To take it one step further, substitute the value that `applyIt` is bound to for `applyIt`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a><span data-ttu-id="bf832-202">함수는 F # 고급 값</span><span class="sxs-lookup"><span data-stu-id="bf832-202">Functions Are First-Class Values in F#</span></span> #

<span data-ttu-id="bf832-203">이전 섹션의 예제에서는 F #에서 F # 고급 값 되기 위한 조건을 충족 하는지 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-203">The examples in the previous sections demonstrate that functions in F# satisfy the criteria for being first-class values in F#:</span></span>

- <span data-ttu-id="bf832-204">함수 정의에 식별자를 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-204">You can bind an identifier to a function definition.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- <span data-ttu-id="bf832-205">데이터 구조에는 함수를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-205">You can store a function in a data structure.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- <span data-ttu-id="bf832-206">함수를 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-206">You can pass a function as an argument.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- <span data-ttu-id="bf832-207">함수는 함수 호출 값으로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-207">You can return a function as the value of a function call.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="bf832-208">F #에 대 한 자세한 내용은 참조는 [F # 언어 참조](../language-reference/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-208">For more information about F#, see the [F# Language Reference](../language-reference/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="bf832-209">예제</span><span class="sxs-lookup"><span data-stu-id="bf832-209">Example</span></span>

### <a name="description"></a><span data-ttu-id="bf832-210">설명</span><span class="sxs-lookup"><span data-stu-id="bf832-210">Description</span></span>

<span data-ttu-id="bf832-211">다음 코드는이 항목의 모든 예제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bf832-211">The following code contains all the examples in this topic.</span></span>

### <a name="code"></a><span data-ttu-id="bf832-212">코드</span><span class="sxs-lookup"><span data-stu-id="bf832-212">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]
    
## <a name="see-also"></a><span data-ttu-id="bf832-213">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf832-213">See Also</span></span>

[<span data-ttu-id="bf832-214">목록</span><span class="sxs-lookup"><span data-stu-id="bf832-214">Lists</span></span>](../language-reference/lists.md)

[<span data-ttu-id="bf832-215">튜플</span><span class="sxs-lookup"><span data-stu-id="bf832-215">Tuples</span></span>](../language-reference/tuples.md)

[<span data-ttu-id="bf832-216">함수</span><span class="sxs-lookup"><span data-stu-id="bf832-216">Functions</span></span>](../language-reference/functions/index.md)

[<span data-ttu-id="bf832-217">`let`바인딩</span><span class="sxs-lookup"><span data-stu-id="bf832-217">`let` Bindings</span></span>](../language-reference/functions/let-bindings.md)

[<span data-ttu-id="bf832-218">람다 식:는 `fun` 키워드</span><span class="sxs-lookup"><span data-stu-id="bf832-218">Lambda Expressions: The `fun` Keyword</span></span>](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
