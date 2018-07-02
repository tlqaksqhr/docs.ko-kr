---
title: 식 트리 작성
description: 식 트리를 빌드하기 위한 기술을 알아봅니다.
ms.date: 06/20/2016
ms.assetid: 542754a9-7f40-4293-b299-b9f80241902c
ms.openlocfilehash: 7751af17aafa8e2d1a14125da43352108b1c1f95
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207191"
---
# <a name="building-expression-trees"></a><span data-ttu-id="eeab7-103">식 트리 작성</span><span class="sxs-lookup"><span data-stu-id="eeab7-103">Building Expression Trees</span></span>

[<span data-ttu-id="eeab7-104">이전 - 식 해석</span><span class="sxs-lookup"><span data-stu-id="eeab7-104">Previous -- Interpreting Expressions</span></span>](expression-trees-interpreting.md)

<span data-ttu-id="eeab7-105">지금까지 살펴본 모든 식 트리는 C# 컴파일러에서 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-105">All the expression trees you've seen so far have been created by the C# compiler.</span></span> <span data-ttu-id="eeab7-106">`Expression<Func<T>>` 또는 유사한 형식의 변수 형식에 할당된 람다 식을 만들기만 하면 됐습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-106">All you had to do was create a lambda expression that was assigned to a variable typed as an `Expression<Func<T>>` or some similar type.</span></span> <span data-ttu-id="eeab7-107">그러나 식 트리를 만드는 유일한 방법은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-107">That's not the only way to create an expression tree.</span></span> <span data-ttu-id="eeab7-108">대부분의 시나리오에서는 런타임에 메모리에서 식을 작성해야 함을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-108">For many scenarios you may find that you need to build an expression in memory at runtime.</span></span> 

<span data-ttu-id="eeab7-109">식 트리는 변경할 수 없다는 사실로 인해 식 트리 작성은 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-109">Building Expression Trees is complicated by the fact that those expression trees are immutable.</span></span> <span data-ttu-id="eeab7-110">변경할 수 없다는 것은 리프에서 루트까지 위로 트리를 작성해야 한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-110">Being immutable means that you must build the tree from the leaves up to the root.</span></span> <span data-ttu-id="eeab7-111">식 트리를 작성하는 데 사용할 API에 이 사실이 반영됩니다. 즉, 노드를 작성하는 데 사용되는 메서드는 모든 자식을 인수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-111">The APIs you'll use to build expression trees reflect this fact: The methods you'll use to build a node take all its children as arguments.</span></span> <span data-ttu-id="eeab7-112">이 기술을 보여 주는 몇 가지 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-112">Let's walk through a few examples to show you the techniques.</span></span>

## <a name="creating-nodes"></a><span data-ttu-id="eeab7-113">노드 만들기</span><span class="sxs-lookup"><span data-stu-id="eeab7-113">Creating Nodes</span></span>

<span data-ttu-id="eeab7-114">비교적 간단하게 다시 시작해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-114">Let's start relatively simply again.</span></span> <span data-ttu-id="eeab7-115">이러한 섹션 전체에서 사용한 더하기 식을 사용하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-115">We'll use the addition expression I've been working with throughout these sections:</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

<span data-ttu-id="eeab7-116">해당 식 트리를 생성하려면 리프 노드를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-116">To construct that expression tree, you must construct the leaf nodes.</span></span>
<span data-ttu-id="eeab7-117">리프 노드는 상수이므로 `Expression.Constant` 메서드를 사용하여 노드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-117">The leaf nodes are constants, so you can use the `Expression.Constant` method to create the nodes:</span></span>

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
```

<span data-ttu-id="eeab7-118">다음으로 더하기 식을 작성해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-118">Next, you'll build the addition expression:</span></span>

```csharp
var addition = Expression.Add(one, two);
```

<span data-ttu-id="eeab7-119">더하기 식을 작성했으면 람다 식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-119">Once you've got the addition expression, you can create the lambda expression:</span></span>

```csharp
var lambda = Expression.Lambda(addition);
```

<span data-ttu-id="eeab7-120">이 식은 인수가 없기 때문에 매우 간단한 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-120">This is a very simple lambda expression, because it contains no arguments.</span></span>
<span data-ttu-id="eeab7-121">이 섹션의 뒷부분에서는 인수를 매개 변수에 매핑하고 더 복잡한 식을 작성하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-121">Later in this section, you'll see how to map arguments to parameters and build more complicated expressions.</span></span>

<span data-ttu-id="eeab7-122">이 식처럼 간단한 식의 경우 모든 호출을 단일 문으로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-122">For expressions that are as simple as this one, you may combine all the calls into a single statement:</span></span>

```csharp
var lambda = Expression.Lambda(
    Expression.Add(
        Expression.Constant(1, typeof(int)),
        Expression.Constant(2, typeof(int))
    )
);
```

## <a name="building-a-tree"></a><span data-ttu-id="eeab7-123">트리 작성</span><span class="sxs-lookup"><span data-stu-id="eeab7-123">Building a Tree</span></span>

<span data-ttu-id="eeab7-124">메모리에서 식 트리를 작성할 때의 기본 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-124">That's the basics of building an expression tree in memory.</span></span> <span data-ttu-id="eeab7-125">좀 더 복잡한 트리는 일반적으로 노드 유형과 트리의 노드가 더 많음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-125">More complex trees generally mean more node types, and more nodes in the tree.</span></span> <span data-ttu-id="eeab7-126">예제를 하나 더 실행하고 식 트리를 만들 때 일반적으로 작성하는 인수 노드와 메서드 호출 노드라는 노드 유형을 두 개 더 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-126">Let's run through one more example and show two more node types that you will typically build when you create expression trees: the argument nodes, and method call nodes.</span></span>

<span data-ttu-id="eeab7-127">식 트리를 작성하여 다음 식을 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-127">Let's build an expression tree to create this expression:</span></span>

```csharp
Expression<Func<double, double, double>> distanceCalc =
    (x, y) => Math.Sqrt(x * x + y * y);
```
 
<span data-ttu-id="eeab7-128">`x` 및 `y`에 대한 매개 변수 식부터 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-128">You'll start by creating parameter expressions for `x` and `y`:</span></span>

```csharp
var xParameter = Expression.Parameter(typeof(double), "x");
var yParameter = Expression.Parameter(typeof(double), "y");
```

<span data-ttu-id="eeab7-129">곱하기와 더하기 식을 만들 때 이미 살펴본 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-129">Creating the multiplication and addition expressions follows the pattern you've already seen:</span></span>

```csharp
var xSquared = Expression.Multiply(xParameter, xParameter);
var ySquared = Expression.Multiply(yParameter, yParameter);
var sum = Expression.Add(xSquared, ySquared);
```

<span data-ttu-id="eeab7-130">다음으로 `Math.Sqrt`를 호출하기 위한 메서드 호출 식을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-130">Next, you need to create a method call expression for the call to `Math.Sqrt`.</span></span>

```csharp
var sqrtMethod = typeof(Math).GetMethod("Sqrt", new[] { typeof(double) });
var distance = Expression.Call(sqrtMethod, sum);
```

<span data-ttu-id="eeab7-131">그런 다음 마지막으로 메서드 호출을 람다 식에 넣고 람다 식에 대한 인수를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-131">And  then finally, you put the method call into a lambda expression, and make sure to define the arguments to the lambda expression:</span></span>

```csharp
var distanceLambda = Expression.Lambda(
    distance,
    xParameter,
    yParameter);
```

<span data-ttu-id="eeab7-132">더 복잡한 이 예제에서는 식 트리를 만드는 데 자주 필요한 기술을 몇 가지 더 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-132">In this more complicated example, you see a couple more techniques that you will often need to create expression trees.</span></span>

<span data-ttu-id="eeab7-133">먼저 매개 변수 또는 지역 변수를 나타내는 개체를 만든 후에 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-133">First, you need to create the objects that represent parameters or local variables before you use them.</span></span> <span data-ttu-id="eeab7-134">이러한 개체를 만들었으면 필요할 때마다 식 트리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-134">Once you've created those objects, you can use them in your expression tree wherever you need.</span></span>

<span data-ttu-id="eeab7-135">두 번째로 해당 메서드에 액세스하는 식 트리를 만들 수 있도록 리플렉션 API의 하위 집합을 사용하여 `MethodInfo` 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-135">Second, you need to use a subset of the Reflection APIs to create a `MethodInfo` object so that you can create an expression tree to access that method.</span></span> <span data-ttu-id="eeab7-136">.NET Core 플랫폼에서 사용할 수 있는 리플렉션 API의 하위 집합으로 제한해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-136">You must limit yourself to the subset of the Reflection APIs that are available on the .NET Core platform.</span></span> <span data-ttu-id="eeab7-137">이제 이러한 기술은 다른 식 트리로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-137">Again, these techniques will extend to other expression trees.</span></span>

## <a name="building-code-in-depth"></a><span data-ttu-id="eeab7-138">코드 빌드에 대한 자세한 설명</span><span class="sxs-lookup"><span data-stu-id="eeab7-138">Building Code In Depth</span></span>

<span data-ttu-id="eeab7-139">이러한 API를 사용하여 빌드할 수 있는 항목으로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-139">You aren't limited in what you can build using these APIs.</span></span> <span data-ttu-id="eeab7-140">그러나 작성하려는 식 트리가 복잡할수록 코드를 관리하고 읽기가 더 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-140">However, the more complicated expression tree that you want to build, the more difficult the code is to manage and to read.</span></span> 

<span data-ttu-id="eeab7-141">다음 코드에 해당하는 식 트리를 작성해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-141">Let's build an expression tree that is the equivalent of this code:</span></span>

```csharp
Func<int, int> factorialFunc = (n) =>
{
    var res = 1;
    while (n > 1)
    {
        res = res * n;
        n--;
    }
    return res;
};
```

<span data-ttu-id="eeab7-142">위의 예제에서는 식 트리를 작성하지 않고 대리자만 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-142">Notice above that I did not build the expression tree, but simply the delegate.</span></span> <span data-ttu-id="eeab7-143">`Expression` 클래스를 사용하여 문 람다를 빌드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-143">Using the `Expression` class, you can't build statement lambdas.</span></span> <span data-ttu-id="eeab7-144">다음은 동일한 기능을 빌드하는 데 필요한 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-144">Here's the code that is required to build the same functionality.</span></span> <span data-ttu-id="eeab7-145">`while` 루프를 빌드하는 API가 없기 때문에 복잡합니다. 대신 루프를 중단하려면 조건부 테스트를 포함하는 루프와 레이블 대상을 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-145">It's complicated by the fact that there isn't an API to build a `while` loop, instead you need to build a loop that contains a conditional test, and a label target to break out of the loop.</span></span> 

```csharp
var nArgument = Expression.Parameter(typeof(int), "n");
var result = Expression.Variable(typeof(int), "result");

// Creating a label that represents the return value
LabelTarget label = Expression.Label(typeof(int));

var initializeResult = Expression.Assign(result, Expression.Constant(1));

// This is the inner block that performs the multiplication,
// and decrements the value of 'n'
var block = Expression.Block(
    Expression.Assign(result,
        Expression.Multiply(result, nArgument)),
    Expression.PostDecrementAssign(nArgument)
);

// Creating a method body.
BlockExpression body = Expression.Block(
    new[] { result },
    initializeResult,
    Expression.Loop(
        Expression.IfThenElse(
            Expression.GreaterThan(nArgument, Expression.Constant(1)),
            block,
            Expression.Break(label, result)
        ),
        label
    )
);
```

<span data-ttu-id="eeab7-146">계승 함수에 대한 식 트리를 작성하는 코드는 훨씬 더 길고 더 복잡하며, 레이블과 break 문 및 일상적인 코딩 작업에서 방지하려는 기타 요소로 인해 복잡해집니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-146">The code to build the expression tree for the factorial function is quite a bit longer, more complicated, and it's riddled with labels and break statements and other elements we'd like to avoid in our everyday coding tasks.</span></span> 

<span data-ttu-id="eeab7-147">이 섹션에서는 이 식 트리의 모든 노드를 방문하는 방문자 코드도 업데이트하고 이 샘플에서 만들어진 노드에 대한 정보를 기록했습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-147">For this section, I've also updated the visitor code to visit every node in this expression tree and write out information about the nodes that are created in this sample.</span></span> <span data-ttu-id="eeab7-148">GitHub의 dotnet/docs 리포지토리에서 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/samples/tree/master/csharp/expression-trees)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-148">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/csharp/expression-trees) at the dotnet/docs GitHub repository.</span></span> <span data-ttu-id="eeab7-149">샘플을 빌드하고 실행하여 직접 실험합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-149">Experiment for yourself by building and running the samples.</span></span> <span data-ttu-id="eeab7-150">다운로드 지침은 [샘플 및 자습서](../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eeab7-150">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="examining-the-apis"></a><span data-ttu-id="eeab7-151">API 검사</span><span class="sxs-lookup"><span data-stu-id="eeab7-151">Examining the APIs</span></span>

<span data-ttu-id="eeab7-152">식 트리 API는 .NET Core에서 탐색하기가 더 어렵지만 괜찮습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-152">The expression tree APIs are some of the more difficult to navigate in .NET Core, but that's fine.</span></span> <span data-ttu-id="eeab7-153">용도는 런타임에 코드를 생성하는 코드를 작성하는 경우처럼 다소 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-153">Their purpose is a rather complex undertaking: writing code that generates code at runtime.</span></span> <span data-ttu-id="eeab7-154">C# 언어에서 사용할 수 있는 모든 제어 구조를 지원하고 API의 노출 영역을 적절히 작게 유지하는 작업 간에 균형을 맞추려면 복잡할 수 밖에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-154">They are necessarily complicated to provide a balance between supporting all the control structures available in the C# language and keeping the surface area of the APIs as small as reasonable.</span></span> <span data-ttu-id="eeab7-155">이러한 균형은 많은 제어 구조가 C# 구문이 아니라 컴파일러가 더 높은 수준의 구조체에서 생성하는 기본 논리를 나타내는 구조체에 의해 표시됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-155">This balance means that many control structures are represented not by their C# constructs, but by constructs that represent the underlying logic that the compiler generates from these higher level constructs.</span></span> 

<span data-ttu-id="eeab7-156">또한 `Expression` 클래스 메서드를 사용하여 직접 작성할 수 없는 C# 식도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-156">Also, at this time, there are C# expressions that cannot be built directly using `Expression` class methods.</span></span> <span data-ttu-id="eeab7-157">일반적으로 C# 5 및 C# 6에서 추가된 최신 연산자 및 식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-157">In general, these will be the newest operators and expressions added in C# 5 and C# 6.</span></span> <span data-ttu-id="eeab7-158">예를 들어 `async` 식을 작성할 수 없으며 새로운 `?.` 연산자를 직접 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeab7-158">(For example, `async` expressions cannot be built, and the new `?.` operator cannot be directly created.)</span></span>

[<span data-ttu-id="eeab7-159">다음 -- 식 변환</span><span class="sxs-lookup"><span data-stu-id="eeab7-159">Next -- Translating Expressions</span></span>](expression-trees-translating.md)
