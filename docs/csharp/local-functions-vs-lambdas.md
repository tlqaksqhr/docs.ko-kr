---
title: "로컬 함수 및 람다 식"
description: "로컬 함수가 람다 식보다 더 적합한 선택일 수 있는 이유를 알아봅니다."
keywords: "C#, .NET, .NET Core, 최신 기능, 새로운 기능, 로컬 함수, 람다 식"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.translationtype: HT
ms.sourcegitcommit: 9bb17207ba72bb22f5d6db55e9d1bd77e3013445
ms.openlocfilehash: 0730e7b7d6e3ef7b5c534d16baacde6a7dafacfc
ms.contentlocale: ko-kr
ms.lasthandoff: 08/25/2017

---
# <a name="local-functions-compared-to-lambda-expressions"></a><span data-ttu-id="dcc5b-104">로컬 함수 및 람다 식 비교</span><span class="sxs-lookup"><span data-stu-id="dcc5b-104">Local functions compared to Lambda expressions</span></span>

<span data-ttu-id="dcc5b-105">얼핏 보기에 [로컬 함수](programming-guide/classes-and-structs/local-functions.md)와 [람다 식](lambda-expressions.md)은 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-105">At first glance, [local functions](programming-guide/classes-and-structs/local-functions.md) and [lambda expressions](lambda-expressions.md) are very similar.</span></span>
<span data-ttu-id="dcc5b-106">필요에 따라 로컬 함수가 훨씬 더 효율적이고 간단한 솔루션일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-106">Depending on your needs, local functions may be a much better and simpler solution.</span></span>

<span data-ttu-id="dcc5b-107">계승 알고리즘의 로컬 함수 및 람다 식 구현 간의 차이점을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-107">Let's examine the differences between the local function and lambda expression implementations of the factorial algorithm.</span></span> <span data-ttu-id="dcc5b-108">먼저 로컬 함수를 사용하는 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-108">First the version using a local function:</span></span>

<span data-ttu-id="dcc5b-109">[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "로컬 함수를 사용하는 재귀 계승")]</span><span class="sxs-lookup"><span data-stu-id="dcc5b-109">[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]</span></span>

<span data-ttu-id="dcc5b-110">람다 식을 사용하는 버전과 해당 구현을 비교해 보세요.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-110">Contrast that implementation with a version that uses lambda expressions:</span></span>

<span data-ttu-id="dcc5b-111">[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "람다 식을 사용하는 재귀 계승")]</span><span class="sxs-lookup"><span data-stu-id="dcc5b-111">[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]</span></span>

<span data-ttu-id="dcc5b-112">첫째, 람다 식은 대리자를 인스턴스화하고 해당 대리자를 호출하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-112">First, lambda expressions are implemented by instantiating a delegate and invoking that delegate.</span></span> <span data-ttu-id="dcc5b-113">로컬 함수는 메서드 호출로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-113">Local functions are implemented as method calls.</span></span>
<span data-ttu-id="dcc5b-114">람다 식에 필요한 인스턴스화는 추가 메모리 할당을 의미하며, 시간이 중요한 코드 경로에서 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-114">The instantiation necessary for lambda expressions means extra memory allocations, which may be a performance factor in time critical code paths.</span></span>
<span data-ttu-id="dcc5b-115">로컬 함수는 이러한 오버헤드를 유발하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-115">Local functions do not incur this overhead.</span></span> <span data-ttu-id="dcc5b-116">위의 예제에서 로컬 함수 버전은 람다 식 버전보다 할당 수가 2개 더 적습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-116">In the example above, the local functions version has 2 fewer allocations than the lambda expression version.</span></span>

<span data-ttu-id="dcc5b-117">이 재귀 메서드는 로컬 함수가 컴파일러에서 생성된 이름을 가진 private 메서드로 구현될 만큼 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-117">This recursive method is simple enough that the local function is implemented as a private method with a compiler generated name.</span></span> <span data-ttu-id="dcc5b-118">다른 private 메서드와의 유일한 차이점은 의미 체계가 외부 함수의 내부 범위로 지정된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-118">Its only difference from other private methods is that it is semantically scoped inside the outer function.</span></span>

<span data-ttu-id="dcc5b-119">둘째, 로컬 함수는 정의하기 전에 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-119">Second, local functions can be called before they are defined.</span></span> <span data-ttu-id="dcc5b-120">람다 식은 정의하기 전에 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-120">Lambda expressions must be declared before they are defined.</span></span> <span data-ttu-id="dcc5b-121">즉, 위에 표시된 대로 로컬 함수는 재귀 알고리즘에서 사용하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-121">This means local functions are easier to use in recursive algorithms, as shown above.</span></span>

<span data-ttu-id="dcc5b-122">람다 식을 사용하는 버전은 람다 식 `nthFactorial`을 정의하기 전에 선언하고 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-122">Notice that the version using the lambda expression must declare and initialize the lambda expression, `nthFactorial` before defining it.</span></span> <span data-ttu-id="dcc5b-123">이렇게 하지 않으면 `nthFactorial`을 할당하기 전에 참조하여 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-123">Not doing so results in a compile time error for referencing `nthFactorial` before assigning it.</span></span>
<span data-ttu-id="dcc5b-124">로컬 함수를 사용하면 재귀 알고리즘을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-124">Recursive algorithms are easier to create using local functions.</span></span>

<span data-ttu-id="dcc5b-125">셋째, 람다 식의 경우 컴파일러가 클로저에 의해 캡처된 변수를 저장하기 위해 항상 무명 클래스 및 해당 클래스의 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-125">Third, for lambda expressions, the compiler must always create an anonymous class and an instance of that class to store any variables captured by the closure.</span></span> <span data-ttu-id="dcc5b-126">다음 비동기 예제를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-126">Consider this async example:</span></span>

<span data-ttu-id="dcc5b-127">[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "람다 식을 사용하여 메서드를 반환하는 작업")]</span><span class="sxs-lookup"><span data-stu-id="dcc5b-127">[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]</span></span>

<span data-ttu-id="dcc5b-128">이 람다 식의 클로저에는 `address`, `index` 및 `name` 변수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-128">The closure for this lambda expression contains the `address`, `index` and `name` variables.</span></span> <span data-ttu-id="dcc5b-129">로컬 함수의 경우 클로저를 구현하는 개체는 `struct` 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-129">In the case of local functions, the object that implements the closure may be a `struct` type.</span></span> <span data-ttu-id="dcc5b-130">이 경우 할당에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-130">That would save on an allocation.</span></span>

> [!NOTE]
> <span data-ttu-id="dcc5b-131">이 메서드에 해당하는 로컬 함수는 클로저에 클래스도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-131">The local function equivalent of this method also uses a class for the closure.</span></span> <span data-ttu-id="dcc5b-132">로컬 함수의 클로저가 `class` 또는 `struct`로 구현되는지 여부는 구현 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-132">Whether the closure for a local function is implemented as a `class` or a `struct` is an implementation detail.</span></span> <span data-ttu-id="dcc5b-133">로컬 함수는 `struct`를 사용할 수 있는 반면, 람다는 항상 `class`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-133">A local function may use a `struct` whereas a lambda will always use a `class`.</span></span>

<span data-ttu-id="dcc5b-134">[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "로컬 함수가 포함된 메서드를 반환하는 작업")]</span><span class="sxs-lookup"><span data-stu-id="dcc5b-134">[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]</span></span>

<span data-ttu-id="dcc5b-135">이 샘플에서 설명하지 않은 한 가지 최종 장점은 `yield return` 구문을 사용해서 로컬 함수를 반복기로 구현하여 값 시퀀스를 생성할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-135">One final advantage not demonstrated in this sample is that local functions can be implemented as iterators, using the `yield return` syntax to produce a sequence of values.</span></span>

<span data-ttu-id="dcc5b-136">로컬 함수는 람다 식과 중복되는 것처럼 보일 수도 있지만, 실제로 다른 용도로 다르게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-136">While local functions may seem redundant to lambda expressions, they actually serve different purposes and have different uses.</span></span>
<span data-ttu-id="dcc5b-137">로컬 함수는 다른 메서드의 컨텍스트에서만 호출되는 함수를 작성하려는 경우에 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc5b-137">Local functions are more efficient for the case when you want to write a function that is called only from the context of another method.</span></span>

