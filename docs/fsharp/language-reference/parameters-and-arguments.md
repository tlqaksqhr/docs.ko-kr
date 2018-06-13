---
title: 매개 변수 및 인수(F#)
description: 'F # 언어 지원과 매개 변수를 정의 하 고 함수, 메서드 및 속성에 인수를 전달 하기 위한 방법을 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 319cf0e7346d498ce34e41a9993fe0160038461a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566222"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="6216f-103">매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="6216f-103">Parameters and Arguments</span></span>

<span data-ttu-id="6216f-104">이 항목에서는 매개 변수를 정의 하 고 함수, 메서드 및 속성에 인수 전달에 대 한 언어 지원에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="6216f-105">참조로 전달 하는 방법 및 정의 하 고 가변 개수의 인수를 사용할 수 있는 메서드를 사용 하는 방법에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>


## <a name="parameters-and-arguments"></a><span data-ttu-id="6216f-106">매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="6216f-106">Parameters and Arguments</span></span>
<span data-ttu-id="6216f-107">용어 *매개 변수* 제공 해야 하는 값의 이름을 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="6216f-108">용어 *인수* 각 매개 변수에 대해 제공 된 값에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="6216f-109">튜플 또는 변환된 형식으로 또는 둘 중 일부 조합 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="6216f-110">명시적 매개 변수 이름을 사용 하 여 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="6216f-111">메서드의 매개 변수 수 선택적으로 지정 되며 기본 값이 지정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-111">Parameters of methods can be specified as optional and given a default value.</span></span>


## <a name="parameter-patterns"></a><span data-ttu-id="6216f-112">매개 변수 패턴</span><span class="sxs-lookup"><span data-stu-id="6216f-112">Parameter Patterns</span></span>
<span data-ttu-id="6216f-113">함수 및 메서드를 제공 된 매개 변수가 일반적으로 공백으로 구분 되는 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="6216f-114">즉, 즉, 원칙적으로 된 패턴에 설명 된 [일치 식](match-expressions.md) 함수 또는 멤버에 대 한 매개 변수 목록에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="6216f-115">메서드는 일반적으로 인수 전달의 튜플 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="6216f-116">튜플 형식 인수는.NET 메서드에 전달 하는 방식과 일치 하기 때문에 다른.NET 언어의 관점에서 더 명확한 결과 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="6216f-117">사용 하 여 만든 함수 가장 자주 사용 되는 커리 된 형태의 `let` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="6216f-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="6216f-118">다음 의사 코드 튜플 및 커리 된 인수가 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="6216f-119">일부 인수 튜플을 있고 일부 없는 결합 된 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="6216f-120">다른 패턴 매개 변수 목록에도 사용할 수 있습니다 하지만 매개 변수 패턴 가능한 모든 입력이 일치 하지 않습니다 있을 수 있습니다 불완전 한 일치 하는 런타임 시.</span><span class="sxs-lookup"><span data-stu-id="6216f-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="6216f-121">예외 `MatchFailureException` 인수 값 매개 변수 목록에 지정 된 패턴과 일치 하지 않을 때 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="6216f-122">불완전 한 일치 항목에 대 한 매개 변수 패턴을 허용 하는 경우 컴파일러는 경고가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="6216f-123">다른 하나 이상 패턴은 일반적으로 매개 변수 목록에 대 한 유용 있고 와일드 카드 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="6216f-124">제공 된 인수를 무시 하려면 단순히 매개 변수 목록에 와일드 카드 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="6216f-125">다음 코드를 인수 목록에는 와일드 카드 패턴의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="6216f-126">와일드 카드 패턴은 일반적으로 다음 코드 에서처럼 문자열 배열로 제공 되는 명령줄 인수에 관심이 없는 경우 전달 된 인수를 불필요 때마다 유용 하 고 프로그램에 기본 요소와 같이 해당 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="6216f-127">인수에 자주 사용 되는 다른 패턴은 `as` 패턴과 관련 된 구별 된 공용 구조체 및 활성 패턴 식별자 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="6216f-128">다음과 같이 단일 대/소문자 구별 된 공용 구조체 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="6216f-129">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-129">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="6216f-130">인수는 다음 예제 에서처럼를 원하는 형식으로 변형 하는 경우 활성 패턴은 예를 들어 매개 변수로 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="6216f-131">사용할 수는 `as` 다음 코드 줄에 표시 된 대로 로컬 값으로 일치 하는 값을 저장 하는 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="6216f-132">다른 가끔씩 사용 되는 방법은 마지막 인수는 함수 본문으로 제공 하 여 명명 되지 않은 상태로 유지 하는 함수, 즉시 암시적 인수에 대해 패턴 일치를 수행 하는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="6216f-133">이 예제는 코드의 다음 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="6216f-134">이 코드에서는 제네릭 목록을 사용 하 고 반환 하는 함수를 정의 `true` 목록이 비어 있으면 및 `false` 그렇지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="6216f-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="6216f-135">이와 같은 기술을 사용 하 여 사용 코드를 읽을 더 어렵게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="6216f-136">경우에 따라서는 불완전 한 일치 항목을 포함 하는 패턴은 유용를 예를 들어 프로그램의 목록에 세 개의 요소만 있는 있는지 알고 있는 경우 수 사용 다음과 같은 패턴 매개 변수 목록에서.</span><span class="sxs-lookup"><span data-stu-id="6216f-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="6216f-137">불완전 한 일치 하는 패턴을 사용 하 여 빠른 프로토타입 및 임시 다른 사용에 가장 잘 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="6216f-138">컴파일러에서 해당 코드에 대 한 경고를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="6216f-139">이러한 패턴은 일반적인 경우의 가능한 모든 입력을 처리할 수 없으므로 및 Api 구성 요소에 대해 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="6216f-140">명명된 인수</span><span class="sxs-lookup"><span data-stu-id="6216f-140">Named Arguments</span></span>
<span data-ttu-id="6216f-141">메서드에 대 한 인수는 쉼표로 구분 된 인수 목록에서 위치에 따라 지정할 수 있습니다 또는 전달할 수도 있습니다는 메서드를 명시적으로 뒤에 등호와 값에 전달 되도록 하는 이름을 제공 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="6216f-142">이름을 제공 하 여 지정 하는 경우에 선언에 사용 되는 다른 순서로 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="6216f-143">명명 된 인수에 수행할 수 코드 더 쉽게 읽을 수 및 보다 융통성 있는 특정 형식의 메서드 매개 변수 다시 정렬 등의 API의 변경 내용.</span><span class="sxs-lookup"><span data-stu-id="6216f-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="6216f-144">명명 된 인수를 사용할 수 방법에 대해서만 아니라 `let`-바인딩된 함수, 함수 값 또는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="6216f-145">다음 코드 예제에서는 명명 된 인수를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="6216f-146">클래스 생성자에 대 한 호출에서 명명 된 인수에서와 유사한 구문을 사용 하 여 클래스의 속성 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="6216f-147">다음 예제에서는이 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="6216f-148">자세한 내용은 참조 [생성자 (F #)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="6216f-149">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="6216f-149">Optional Parameters</span></span>
<span data-ttu-id="6216f-150">매개 변수 이름 앞에 매개 변수를 사용 하 여는 방법에 대 한 선택적 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="6216f-151">선택적 매개 변수를 사용 하 여 옵션 종류를 쿼리 하는 일반적인 방법에서 쿼리할 수 있습니다는 F # 옵션 형식으로 해석 되므로 `match` 식 `Some` 및 `None`합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="6216f-152">선택적 매개 변수를 사용 하 여 만든 함수에 없는 멤버에 대해서만 허용 됩니다 `let` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="6216f-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="6216f-153">함수를 사용할 수도 `defaultArg`, 선택적 인수는 기본 값을 설정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-153">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="6216f-154">`defaultArg` 함수는 첫 번째 인수는 선택적 매개 변수 및 기본값을 두 번째 인수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-154">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="6216f-155">다음 예에서는 선택적 매개 변수 사용을 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-155">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="6216f-156">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-156">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a><span data-ttu-id="6216f-157">참조로 전달</span><span class="sxs-lookup"><span data-stu-id="6216f-157">Passing by Reference</span></span>
<span data-ttu-id="6216f-158">F #에서는 `byref` 키워드는 매개 변수 참조로 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-158">F# supports the `byref` keyword, which specifies that a parameter is passed by reference.</span></span> <span data-ttu-id="6216f-159">즉, 모든 값을 변경 하는 함수를 실행 한 후 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-159">This means that any changes to the value are retained after the execution of the function.</span></span> <span data-ttu-id="6216f-160">에 제공 된 값을 `byref` 매개 변수를 변경할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-160">Values provided to a `byref` parameter must be mutable.</span></span> <span data-ttu-id="6216f-161">또는 적절 한 형식의 참조 셀을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-161">Alternatively, you can pass reference cells of the appropriate type.</span></span>

<span data-ttu-id="6216f-162">함수에서 둘 이상의 값을 반환 하는 방법으로 발전 하 고.NET 언어에서는 참조로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-162">Passing by reference in .NET languages evolved as a way to return more than one value from a function.</span></span> <span data-ttu-id="6216f-163">F #에서이 위해 튜플을 반환 수도 있고 변경 가능한 참조 셀을 매개 변수로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-163">In F#, you can return a tuple for this purpose, or use a mutable reference cell as a parameter.</span></span> <span data-ttu-id="6216f-164">`byref` .NET 라이브러리와의 상호 운용성에 대 한 매개 변수는 주로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-164">The `byref` parameter is mainly provided for interoperability with .NET libraries.</span></span>

<span data-ttu-id="6216f-165">다음 예에서는 사용을 보여 주기는 `byref` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-165">The following examples illustrate the use of the `byref` keyword.</span></span> <span data-ttu-id="6216f-166">매개 변수로 참조 셀을 사용 하는 경우 있습니다 해야 명명된 된 값으로 참조 셀을 만들 및 매개 변수로 사용 하는, 뿐 아니라 추가 `ref` 연산자에 대 한 첫 번째 호출에서와 같이 `Increment` 다음 코드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-166">Note that when you use a reference cell as a parameter, you must create a reference cell as a named value and use that as the parameter, not just add the `ref` operator as shown in the first call to `Increment` in the following code.</span></span> <span data-ttu-id="6216f-167">참조 셀을 만드는 기본 값의 복사본을 만들기 때문에 첫 번째 호출에만 임시 값을 증가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-167">Because creating a reference cell creates a copy of the underlying value, the first call just increments a temporary value.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3809.fs)]

<span data-ttu-id="6216f-168">저장을 튜플을 반환 값으로 사용할 수 있습니다 `out` .NET 라이브러리 메서드의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-168">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="6216f-169">처리할 수 있습니다는 `out` 로 매개 변수는 `byref` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-169">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="6216f-170">다음 코드 예제에서는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-170">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="6216f-171">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="6216f-171">Parameter Arrays</span></span>
<span data-ttu-id="6216f-172">임의 개수의 유형이 다른 형식의 매개 변수를 사용 하는 함수를 정의 해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-172">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="6216f-173">사용할 수 있는 모든 형식에 대 한 설명 하기 위해 가능한 모든 오버 로드 된 메서드를 만드는 유용한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-173">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="6216f-174">매개 변수 배열 기능을 통해 이러한 메서드에 대 한 지원을 제공 하는.NET 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-174">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="6216f-175">시그니처에 매개 변수 배열을 사용 하는 메서드는 임의 개수의 매개 변수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-175">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="6216f-176">매개 변수를 배열에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-176">The parameters are put into an array.</span></span> <span data-ttu-id="6216f-177">배열 요소의 형식에는 함수에 전달 될 수 있는 매개 변수 형식이 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-177">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="6216f-178">매개 변수 배열을 정의 하는 경우 `System.Object` 요소 유형으로 다음 클라이언트 코드 전달할 수 형식의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-178">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="6216f-179">매개 변수 배열 F #에서 메서드에서만에서 정의할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-179">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="6216f-180">독립 실행형 함수나 모듈에 정의 된 함수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-180">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="6216f-181">매개 변수 배열을 사용 하 여 정의 된 `ParamArray` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-181">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="6216f-182">`ParamArray` 특성은 마지막 매개 변수에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-182">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="6216f-183">다음 코드에 나와 있는 매개 변수 배열을 사용 하는 메서드가 있는 F #에 매개 변수 배열 및 형식 정의 사용 하는.NET 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-183">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="6216f-184">프로젝트를 실행 하는 경우 앞의 코드 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6216f-184">When run in a project, the output of the previous code is as follows:</span></span>

```
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="6216f-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6216f-185">See Also</span></span>
[<span data-ttu-id="6216f-186">멤버</span><span class="sxs-lookup"><span data-stu-id="6216f-186">Members</span></span>](members/index.md)
