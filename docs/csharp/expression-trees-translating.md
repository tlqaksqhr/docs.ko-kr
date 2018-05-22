---
title: 식 트리 변환
description: 식 트리의 각 노드를 방문하고 해당 식 트리의 수정된 복사본을 작성하는 방법을 알아봅니다.
ms.date: 06/20/2016
ms.assetid: b453c591-acc6-4e08-8175-97e5bc65958e
ms.openlocfilehash: 9483cbe75b4bf5a38dd791633c852eb0b8473944
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="translating-expression-trees"></a><span data-ttu-id="31e73-103">식 트리 변환</span><span class="sxs-lookup"><span data-stu-id="31e73-103">Translating Expression Trees</span></span>

[<span data-ttu-id="31e73-104">이전 -- 식 작성</span><span class="sxs-lookup"><span data-stu-id="31e73-104">Previous -- Building Expressions</span></span>](expression-trees-building.md)

<span data-ttu-id="31e73-105">이 최종 섹션에서는 식 트리의 각 노드를 방문하고 해당 식 트리의 수정된 복사본을 작성하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-105">In this final section, you'll learn how to visit each node in an expression tree while building a modified copy of that expression tree.</span></span> <span data-ttu-id="31e73-106">이러한 기술은 두 가지 중요한 시나리오에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-106">These are the techniques that you will use in two important scenarios.</span></span> <span data-ttu-id="31e73-107">첫 번째는 다른 환경으로 변환할 수 있도록 식 트리로 표현되는 알고리즘을 이해하려는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-107">The first is to understand the algorithms expressed by an expression tree so that it can be translated into another environment.</span></span> <span data-ttu-id="31e73-108">두 번째는 생성된 알고리즘을 변경하려는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-108">The second is when you want to change the algorithm that has been created.</span></span> <span data-ttu-id="31e73-109">이 경우는 로깅 추가, 메서드 호출 가로채기 및 추적 또는 다른 목적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-109">This might be to add logging, intercept method calls and track them, or other purposes.</span></span>

## <a name="translating-is-visiting"></a><span data-ttu-id="31e73-110">변환은 방문임</span><span class="sxs-lookup"><span data-stu-id="31e73-110">Translating is Visiting</span></span>

<span data-ttu-id="31e73-111">식 트리를 변환하기 위해 작성하는 코드는 트리의 모든 노드를 방문하기 위해 이미 살펴본 코드의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-111">The code you build to translate an expression tree is an extension of what you've already seen to visit all the nodes in a tree.</span></span> <span data-ttu-id="31e73-112">식 트리를 변환할 때는 모든 노드를 방문하고 노드를 방문하는 동안 새 트리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-112">When you translate an expression tree, you visit all the nodes, and while visiting them, build the new tree.</span></span> <span data-ttu-id="31e73-113">새 트리에는 원래 노드에 대한 참조 또는 트리에 배치한 새 노드가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-113">The new tree may contain references to the original nodes, or new nodes that you have placed in the tree.</span></span>

<span data-ttu-id="31e73-114">식 트리를 방문하고 몇 가지 대체 노드로 새 트리를 만들어 실제로 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-114">Let's see this in action by visiting an expression tree, and creating a new tree with some replacement nodes.</span></span> <span data-ttu-id="31e73-115">이 예제에서는 특정 상수를 10배 더 큰 상수로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-115">In this example, let's replace any constant with a constant that is ten times larger.</span></span>
<span data-ttu-id="31e73-116">그러지 않으면 식 트리를 그대로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-116">Otherwise, we'll leave the expression tree intact.</span></span> <span data-ttu-id="31e73-117">상수의 값을 읽고 새 상수로 대체하는 대신 곱하기를 수행하는 새 노드로 상수 노드를 대체하여 이를 대체하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-117">Rather than reading the value of the constant, and replacing it with a new constant, we'll make this replacement by replacing the constant node with a new node that performs the multiplication.</span></span>

<span data-ttu-id="31e73-118">여기에서 상수 노드를 찾은 다음에는 자식이 원래 상수 및 상수 `10`인 새 곱하기 노드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-118">Here, once you find a constant node, you create a new multiplication node whose children are the original constant, and the constant `10`:</span></span>

```csharp
private static Expression ReplaceNodes(Expression original)
{
    if (original.NodeType == ExpressionType.Constant)
    {
        return Expression.Multiply(original, Expression.Constant(10));
    }
    else if (original.NodeType == ExpressionType.Add)
    {
        var binaryExpression = (BinaryExpression)original;
        return Expression.Add(
            ReplaceNodes(binaryExpression.Left),
            ReplaceNodes(binaryExpression.Right));
    }
    return original;
}
```

<span data-ttu-id="31e73-119">원래 노드를 대체 노드로 바꾸면 수정 사항을 포함하는 새 트리가 형성됩니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-119">By replacing the original node with the substitute, a new tree is formed that contains our modifications.</span></span> <span data-ttu-id="31e73-120">대체된 트리를 컴파일하고 실행하여 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-120">We can verify that by compiling and executing the replaced tree.</span></span>

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
var sum = ReplaceNodes(addition);
var executableFunc = Expression.Lambda(sum);

var func = (Func<int>)executableFunc.Compile();
var answer = func();
Console.WriteLine(answer);
```

<span data-ttu-id="31e73-121">새 트리 작성은 기존 트리의 노드를 방문하고 새 노드를 만들어 트리에 삽입하는 작업의 조합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-121">Building a new tree is a combination of visiting the nodes in the existing tree, and creating new nodes and inserting them into the tree.</span></span>

<span data-ttu-id="31e73-122">이 예제에서는 변경할 수 없는 식 트리의 중요도를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-122">This example shows the importance of expression trees being immutable.</span></span> <span data-ttu-id="31e73-123">위에서 만든 새 트리에는 새로 만든 노드와 기존 트리의 노드가 함께 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-123">Notice that the new tree created above contains a mixture of newly created nodes, and nodes from the existing tree.</span></span> <span data-ttu-id="31e73-124">기존 트리의 노드를 수정할 수 없기 때문에 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-124">That's safe, because the nodes in the existing tree cannot be modified.</span></span> <span data-ttu-id="31e73-125">이렇게 하면 중요한 메모리 효율성이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-125">This can result in significant memory efficiencies.</span></span>
<span data-ttu-id="31e73-126">트리 전체 또는 여러 식 트리에서 같은 노드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-126">The same nodes can be used throughout a tree, or in multiple expression trees.</span></span> <span data-ttu-id="31e73-127">노드는 수정할 수 없기 때문에 필요할 때마다 같은 노드를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-127">Since nodes can't be modified, the same node can be reused whenever its needed.</span></span>

## <a name="traversing-and-executing-an-addition"></a><span data-ttu-id="31e73-128">더하기 트래버스 및 실행</span><span class="sxs-lookup"><span data-stu-id="31e73-128">Traversing and Executing an Addition</span></span>

<span data-ttu-id="31e73-129">더하기 노드 트리를 이동하고 결과를 계산하는 두 번째 방문자를 작성하여 확인해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-129">Let's verify this by building a second visitor that walks the tree of addition nodes and computes the result.</span></span> <span data-ttu-id="31e73-130">이렇게 하려면 지금까지 살펴본 방문자를 여러 번 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-130">You can do this by making a couple modifications to the vistor that you've seen so far.</span></span> <span data-ttu-id="31e73-131">이 새 버전에서 방문자는 이 지점까지 더하기 작업의 부분합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-131">In this new version, the visitor will return the partial sum of the addition operation up to this point.</span></span> <span data-ttu-id="31e73-132">상수 식의 경우 단순히 상수 식의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-132">For a constant expression, that is simply the value of the constant expression.</span></span> <span data-ttu-id="31e73-133">더하기 식의 경우 해당 트리가 트래버스된 후의 결과는 왼쪽 및 오른쪽 피연산자의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-133">For an addition expression, the result is the sum of the left and right operands, once those trees have been traversed.</span></span>

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var three= Expression.Constant(3, typeof(int));
var four = Expression.Constant(4, typeof(int));
var addition = Expression.Add(one, two);
var add2 = Expression.Add(three, four);
var sum = Expression.Add(addition, add2);

// Declare the delegate, so we can call it 
// from itself recursively:
Func<Expression, int> aggregate = null;
// Aggregate, return constants, or the sum of the left and right operand.
// Major simplification: Assume every binary expression is an addition.
aggregate = (exp) =>
    exp.NodeType == ExpressionType.Constant ?
    (int)((ConstantExpression)exp).Value :
    aggregate(((BinaryExpression)exp).Left) + aggregate(((BinaryExpression)exp).Right);

var theSum = aggregate(sum);
Console.WriteLine(theSum);
```

<span data-ttu-id="31e73-134">코드는 상당히 많지만 개념은 아주 쉽게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-134">There's quite a bit of code here, but the concepts are very approachable.</span></span>
<span data-ttu-id="31e73-135">이 코드는 깊이 우선 검색으로 자식을 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-135">This code visits children in a depth first search.</span></span> <span data-ttu-id="31e73-136">상수 노드가 나타나면 방문자는 상수의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-136">When it encounters a constant node, the visitor returns the value of the constant.</span></span> <span data-ttu-id="31e73-137">방문자가 두 자식을 방문한 후에 자식은 해당 하위 트리에 대해 계산된 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-137">After the visitor has visited both children, those children will have computed the sum computed for that sub-tree.</span></span> <span data-ttu-id="31e73-138">이제 더하기 노드에서 해당 합계를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-138">The addition node can now compute its sum.</span></span>
<span data-ttu-id="31e73-139">식 트리의 모든 노드를 방문하면 합계가 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-139">Once all the nodes in the expression tree have been visited, the sum will have been computed.</span></span> <span data-ttu-id="31e73-140">디버거에서 샘플을 실행하고 실행을 추적하여 실행을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-140">You can trace the execution by running the sample in the debugger and tracing the execution.</span></span>

<span data-ttu-id="31e73-141">노드가 분석되는 방법 및 트리를 트래버스하여 합계를 계산하는 방법을 더 쉽게 추적할 수 있도록 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-141">Let's make it easier to trace how the nodes are analyzed and how the sum is computed by travsersing the tree.</span></span> <span data-ttu-id="31e73-142">다음은 매우 많은 추적 정보를 포함하는 집계 메서드의 업데이트된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-142">Here's an updated version of the Aggregate method that includes quite a bit of tracing information:</span></span>

```csharp
private static int Aggregate(Expression exp)
{
    if (exp.NodeType == ExpressionType.Constant)
    {
        var constantExp = (ConstantExpression)exp;
        Console.Error.WriteLine($"Found Constant: {constantExp.Value}");
        return (int)constantExp.Value;
    }
    else if (exp.NodeType == ExpressionType.Add)
    {
        var addExp = (BinaryExpression)exp;
        Console.Error.WriteLine("Found Addition Expression");
        Console.Error.WriteLine("Computing Left node");
        var leftOperand = Aggregate(addExp.Left);
        Console.Error.WriteLine($"Left is: {leftOperand}");
        Console.Error.WriteLine("Computing Right node");
        var rightOperand = Aggregate(addExp.Right);
        Console.Error.WriteLine($"Right is: {rightOperand}");
        var sum = leftOperand + rightOperand;
        Console.Error.WriteLine($"Computed sum: {sum}");
        return sum;
    }
    else throw new NotSupportedException("Haven't written this yet");
}
```

<span data-ttu-id="31e73-143">같은 식에서 이 메서드를 실행하면 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-143">Running it on the same expression yields the following output:</span></span>

```
10
Found Addition Expression
Computing Left node
Found Addition Expression
Computing Left node
Found Constant: 1
Left is: 1
Computing Right node
Found Constant: 2
Right is: 2
Computed sum: 3
Left is: 3
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 3
Left is: 3
Computing Right node
Found Constant: 4
Right is: 4
Computed sum: 7
Right is: 7
Computed sum: 10
10
```

<span data-ttu-id="31e73-144">출력을 추적하고 위의 코드도 함께 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-144">Trace the output and follow along in the code above.</span></span> <span data-ttu-id="31e73-145">코드가 트리를 이동하고 합계를 찾을 때 각 노드를 방문하고 합계를 계산하는 방법을 이해할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-145">You should be able to work out how the code visits each node and computes the sum as it goes through the tree and finds the sum.</span></span>

<span data-ttu-id="31e73-146">이제 `sum1`에 지정된 식을 사용하여 다른 실행을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-146">Now, let's look at a different run, with the expression given by `sum1`:</span></span>

```csharp
Expression<Func<int> sum1 = () => 1 + (2 + (3 + 4));
```

<span data-ttu-id="31e73-147">이 식을 검사한 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-147">Here's the output from examining this expression:</span></span>

```
Found Addition Expression
Computing Left node
Found Constant: 1
Left is: 1
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 2
Left is: 2
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 3
Left is: 3
Computing Right node
Found Constant: 4
Right is: 4
Computed sum: 7
Right is: 7
Computed sum: 9
Right is: 9
Computed sum: 10
10
```

<span data-ttu-id="31e73-148">최종 해답은 동일하지만 트리 통과는 완전히 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-148">While the final answer is the same, the tree traversal is completely different.</span></span> <span data-ttu-id="31e73-149">먼저 발생하는 다른 작업으로 트리가 생성되었기 때문에 다른 순서로 노드를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-149">The nodes are traveled in a different order, because the tree was constructed with different operations occurring first.</span></span>

## <a name="learning-more"></a><span data-ttu-id="31e73-150">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="31e73-150">Learning More</span></span>

<span data-ttu-id="31e73-151">이 샘플에서는 식 트리로 표시되는 알고리즘을 트래버스하고 해석하기 위해 작성하는 코드의 작은 하위 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-151">This sample shows a small subset of the code you would build to traverse and interpret the algorithms represented by an expression tree.</span></span> <span data-ttu-id="31e73-152">식 트리를 다른 언어로 변환하는 일반적인 용도의 라이브러리를 작성하는 데 필요한 모든 작업에 대한 자세한 내용은 Matt Warren의 [이 시리즈](http://blogs.msdn.com/b/mattwar/archive/2008/11/18/linq-links.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31e73-152">For a complete discussion of all the work necessary to build a general purpose library that translates expression trees into another language, please read [this series](http://blogs.msdn.com/b/mattwar/archive/2008/11/18/linq-links.aspx) by Matt Warren.</span></span> <span data-ttu-id="31e73-153">이 시리즈는 식 트리에서 찾을 수 있는 코드를 변환하는 방법에 대해 상세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-153">It goes into great detail on how to translate any of the code you might find in an expression tree.</span></span>

<span data-ttu-id="31e73-154">식 트리의 진정한 기능을 확인하셨길 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-154">I hope you've now seen the true power of expression trees.</span></span>
<span data-ttu-id="31e73-155">코드 집합을 검사하고, 해당 코드를 원하는 대로 변경하고, 변경된 버전을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-155">You can examine a set of code, make any changes you'd like to that code, and execute the changed version.</span></span> <span data-ttu-id="31e73-156">식 트리는 변경할 수 없기 때문에 기존 트리의 구성 요소를 사용하여 새 트리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-156">Because the expression trees are immutable, you can create new trees by using the components of existing trees.</span></span> <span data-ttu-id="31e73-157">이렇게 하면 수정된 식 트리를 만드는 데 필요한 메모리 양이 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="31e73-157">This minimizes the amount of memory needed to create modified expression trees.</span></span>

[<span data-ttu-id="31e73-158">다음 -- 요약</span><span class="sxs-lookup"><span data-stu-id="31e73-158">Next -- Summing up</span></span>](expression-trees-summary.md)
