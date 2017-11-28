---
title: "식 트리를 지원하는 프레임워크 형식"
description: "식 트리를 지원하는 프레임워크 형식, 식 트리 만들기, 식 트리 API 작업을 위한 기술에 대해 알아봅니다."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: e9c85021-0d36-48af-91b7-aaaa66f22654
ms.openlocfilehash: ed89b286eee9b4c2e11bb27d18e50f777f94f33e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="framework-types-supporting-expression-trees"></a><span data-ttu-id="a2613-104">식 트리를 지원하는 프레임워크 형식</span><span class="sxs-lookup"><span data-stu-id="a2613-104">Framework Types Supporting Expression Trees</span></span>

[<span data-ttu-id="a2613-105">이전 -- 식 트리 설명</span><span class="sxs-lookup"><span data-stu-id="a2613-105">Previous -- Expression Trees Explained</span></span>](expression-trees-explained.md)

<span data-ttu-id="a2613-106">.NET Core 프레임워크에는 식 트리에서 작동하는 클래스 목록이 많습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-106">There is a large list of classes in the .NET Core framework that work with Expression Trees.</span></span>
<span data-ttu-id="a2613-107">전체 목록은 [여기](/dotnet/core/api/System.Linq.Expressions)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-107">You can see the full list [here](/dotnet/core/api/System.Linq.Expressions).</span></span>
<span data-ttu-id="a2613-108">전체 목록을 실행하는 대신 프레임워크 클래스가 어떻게 디자인되었는지 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-108">Rather than run through the full list, let's understand how the framework classes have been designed.</span></span>

<span data-ttu-id="a2613-109">언어 디자인에서 식이란 값을 계산하고 반환하는 코드의 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-109">In language design, an expression is a body of code that evaluates and returns a value.</span></span> <span data-ttu-id="a2613-110">식은 매우 간단할 수 있습니다. 상수 식 `1`은 상수 값 1을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-110">Expressions may be very simple: the constant expression `1` returns the constant value of 1.</span></span> <span data-ttu-id="a2613-111">식은 더 복잡할 수도 있습니다. `(-B + Math.Sqrt(B*B + 4 * A * C)) / (2 * A)` 식은 2차 방정식의 근을 반환합니다(방정식에 솔루션이 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="a2613-111">They may be more complicated: The expression `(-B + Math.Sqrt(B*B + 4 * A * C)) / (2 * A)` returns one root for a quadratic equation (in the case where the equation has a solution).</span></span>  

## <a name="it-all-starts-with-systemlinqexpression"></a><span data-ttu-id="a2613-112">모두 System.Linq.Expression으로 시작</span><span class="sxs-lookup"><span data-stu-id="a2613-112">It all starts with System.Linq.Expression</span></span>

<span data-ttu-id="a2613-113">식 트리 사용의 복잡성 중 하나는 많은 종류의 식이 프로그램의 여러 위치에서 유효하다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-113">One of the complexities of working with expression trees is that many different kinds of expressions are valid in many places in programs.</span></span> <span data-ttu-id="a2613-114">대입 식을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="a2613-114">Consider an assignment expression.</span></span> <span data-ttu-id="a2613-115">대입 식의 오른쪽은 상수 값, 변수, 메서드 호출 식 등이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-115">The right hand side of an assignment could be a constant value, a variable, a method call expression, or others.</span></span> <span data-ttu-id="a2613-116">해당 언어 유연성은 식 트리를 트래버스할 때 트리 노드의 모든 위치에서 여러 가지 다른 식 형식이 표시될 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-116">That language flexibility means that you may encounter many different expression types anywhere in the nodes of a tree when you traverse an expression tree.</span></span> <span data-ttu-id="a2613-117">따라서 기본 식 형식으로 작업하는 것이 가장 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-117">Therefore, when you can work with the base expression type, that's the simplest way to work.</span></span> <span data-ttu-id="a2613-118">그러나 더 많은 것을 알아야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-118">However, sometimes you need to know more.</span></span>
<span data-ttu-id="a2613-119">기본 식 클래스에는 `NodeType` 속성이 이러한 용도로 포함되어 있으며,</span><span class="sxs-lookup"><span data-stu-id="a2613-119">The base Expression class contains a `NodeType` property for this purpose.</span></span>
<span data-ttu-id="a2613-120">가능한 식 형식의 열거형인 `ExpressionType`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-120">It returns an `ExpressionType` which is an enumeration of possible expression types.</span></span>
<span data-ttu-id="a2613-121">노드의 형식을 알고 있다면 해당 형식으로 캐스트할 수 있으며 식 노드의 형식을 알고 있으면 특정 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-121">Once you know the type of the node, you can cast it to that type, and perform specific actions knowing the type of the expression node.</span></span> <span data-ttu-id="a2613-122">특정 노드 유형을 검색한 다음 이러한 식의 특정 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-122">You can search for certain node types, and then work with the specific properties of that kind of expression.</span></span>

<span data-ttu-id="a2613-123">예를 들어 다음 코드는 변수 액세스 식에서 변수의 이름을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-123">For example, this code will print the name of a variable for a variable access expression.</span></span> <span data-ttu-id="a2613-124">노드 유형을 확인하고 변수 액세스 식에 캐스트한 다음 특정 식 형식의 속성을 확인하는 방법을 따랐습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-124">I've followed the practice of checking the node type, then casting to a variable access expression and then checking the properties of the specific expression type:</span></span>

```csharp
Expression<Func<int, int>> addFive = (num) => num + 5;

if (addFive.NodeType == ExpressionType.Lambda)
{
    var lambdaExp = (LambdaExpression)addFive;

    var parameter = lambdaExp.Parameters.First();

    Console.WriteLine(parameter.Name);
    Console.WriteLine(parameter.Type);
}
```

## <a name="creating-expression-trees"></a><span data-ttu-id="a2613-125">식 트리 만들기</span><span class="sxs-lookup"><span data-stu-id="a2613-125">Creating Expression Trees</span></span>

<span data-ttu-id="a2613-126">`System.Linq.Expression` 클래스에는 식을 만드는 많은 정적 메서드도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-126">The `System.Linq.Expression` class also contains many static methods to create expressions.</span></span> <span data-ttu-id="a2613-127">이러한 메서드는 자식에 대해 제공된 인수를 사용하여 식 노드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-127">These methods create an expression node using the arguments supplied for its children.</span></span> <span data-ttu-id="a2613-128">이러한 방식으로 리프 노드에서 위로 식을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-128">In this way, you build an expression up from its leaf nodes.</span></span> <span data-ttu-id="a2613-129">예를 들어 다음 코드는 더하기 식을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-129">For example, this code builds an Add expression:</span></span>

```csharp
// Addition is an add expression for "1 + 2"
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
```

<span data-ttu-id="a2613-130">이 간단한 예제를 통해 식 트리를 만들고 사용하는 데 많은 형식이 관련됨을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-130">You can see from this simple example that many types are involved in creating and working with expression trees.</span></span> <span data-ttu-id="a2613-131">이러한 복잡성은 C# 언어에서 제공하는 풍부한 어휘의 기능을 제공하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-131">That complexity is necessary to provide the capabilities of the rich vocabulary provided by the C# language.</span></span>

## <a name="navigating-the-apis"></a><span data-ttu-id="a2613-132">API 탐색</span><span class="sxs-lookup"><span data-stu-id="a2613-132">Navigating the APIs</span></span>
<span data-ttu-id="a2613-133">C# 언어의 거의 모든 구문 요소에 매핑되는 식 노드 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-133">There are Expression node types that map to almost all of the syntax elements of the C# language.</span></span> <span data-ttu-id="a2613-134">각 형식에는 해당 언어 요소 형식에 대한 특정 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-134">Each type has specific methods for that type of language element.</span></span> <span data-ttu-id="a2613-135">한 번에 기억해야 할 사항이 많습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-135">It's a lot to keep in your head at one time.</span></span> <span data-ttu-id="a2613-136">다음은 모든 사항을 기억하는 대신 식 트리로 작업할 때 사용할 수 있는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-136">Rather than try to memorize everything, here are the techniques I use to work with Expression trees:</span></span>
1. <span data-ttu-id="a2613-137">`ExpressionType` 열거형의 멤버를 확인하여 검색할 수 있는 노드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-137">Look at the members of the `ExpressionType` enum to determine possible nodes you should be examining.</span></span> <span data-ttu-id="a2613-138">실제로 식 트리를 트래버스하고 이해하려는 경우에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-138">This really helps when you want to traverse and understand an expression tree.</span></span>
2. <span data-ttu-id="a2613-139">`Expression` 클래스의 정적 멤버를 확인하여 식을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-139">Look at the static members of the `Expression` class to build an expression.</span></span> <span data-ttu-id="a2613-140">이러한 메서드는 자식 노드 집합에서 모든 식 형식을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-140">Those methods can build any expression type from a set of its child nodes.</span></span>
3. <span data-ttu-id="a2613-141">`ExpressionVisitor` 클래스를 확인하여 수정된 식 트리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-141">Look at the `ExpressionVisitor` class to build a modified expression tree.</span></span>

<span data-ttu-id="a2613-142">세 영역을 각각 확인하면 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-142">You'll find more as you look at each of those three areas.</span></span> <span data-ttu-id="a2613-143">이러한 세 단계 중 한 단계로 시작하면 반드시 필요한 항목을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2613-143">Invariably, you will find what you need when you start with one of those three steps.</span></span>
 
 [<span data-ttu-id="a2613-144">다음 -- 식 트리 실행</span><span class="sxs-lookup"><span data-stu-id="a2613-144">Next -- Executing Expression Trees</span></span>](expression-trees-execution.md)
 
