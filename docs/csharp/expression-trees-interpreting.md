---
title: "식 해석"
description: "식 트리의 구조를 검사하는 코드를 작성하는 방법을 알아봅니다."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: adf73dde-1e52-4df3-9929-2e0670e28e16
ms.openlocfilehash: e7c5f7404546c6f3812fc5cc3d0320c77816634d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="interpreting-expressions"></a><span data-ttu-id="edb50-104">식 해석</span><span class="sxs-lookup"><span data-stu-id="edb50-104">Interpreting Expressions</span></span>

[<span data-ttu-id="edb50-105">이전 -- 식 실행</span><span class="sxs-lookup"><span data-stu-id="edb50-105">Previous -- Executing Expressions</span></span>](expression-trees-execution.md)

<span data-ttu-id="edb50-106">이제 *식 트리*의 구조를 검사하는 몇 가지 코드를 작성해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-106">Now, let's write some code to examine the structure of an *expression tree*.</span></span> <span data-ttu-id="edb50-107">식 트리의 모든 노드는 `Expression`에서 파생되는 클래스의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-107">Every node in an expression tree will be an object of a class that is derived from `Expression`.</span></span>

<span data-ttu-id="edb50-108">해당 디자인은 식 트리의 모든 노드 방문을 비교적 간단한 재귀 작업으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-108">That design makes visiting all the nodes in an expression tree a relatively straight forward recursive operation.</span></span> <span data-ttu-id="edb50-109">일반적인 전략은 루트 노드에서 시작하고 노드의 종류를 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-109">The general strategy is to start at the root node and determine what kind of node it is.</span></span>

<span data-ttu-id="edb50-110">노드 형식에 자식이 있는 경우 자식을 재귀적으로 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-110">If the node type has children, recursively visit the children.</span></span> <span data-ttu-id="edb50-111">각 자식 노드에서 루트 노드에 사용된 프로세스를 반복합니다. 즉, 형식을 확인하고 형식에 자식이 있는 경우 각 자식을 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-111">At each child node, repeat the process used at the root node: determine the type, and if the type has children, visit each of the children.</span></span>

## <a name="examining-an-expression-with-no-children"></a><span data-ttu-id="edb50-112">자식이 없는 식 검사</span><span class="sxs-lookup"><span data-stu-id="edb50-112">Examining an Expression with No Children</span></span>
<span data-ttu-id="edb50-113">먼저 매우 간단한 식 트리의 각 노드를 방문해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-113">Let's start by visiting each node in a very simple expression tree.</span></span>
<span data-ttu-id="edb50-114">다음은 상수 식을 만든 다음 해당 속성을 검사하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-114">Here's the code that creates a constant expression and then examines its properties:</span></span>

```csharp
var constant = Expression.Constant(24, typeof(int));

Console.WriteLine($"This is a/an {constant.NodeType} expression type");
Console.WriteLine($"The type of the constant value is {constant.Type}");
Console.WriteLine($"The value of the constant value is {constant.Value}");
```

<span data-ttu-id="edb50-115">다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-115">This will print the following:</span></span>

```
This is an Constant expression type
The type of the constant value is System.Int32
The value of the constant value is 24
```

<span data-ttu-id="edb50-116">이제 이 식을 검색하고 식에 대해 몇 가지 중요한 속성을 작성하는 코드를 작성해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-116">Now, let's write the code that would examine this expression and write out some important properties about it.</span></span> <span data-ttu-id="edb50-117">해당 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-117">Here's that code:</span></span>

## <a name="examining-a-simple-addition-expression"></a><span data-ttu-id="edb50-118">간단한 더하기 식 검사</span><span class="sxs-lookup"><span data-stu-id="edb50-118">Examining a simple Addition Expression</span></span>

<span data-ttu-id="edb50-119">이 섹션의 소개 부분에 있는 더하기 샘플로 시작해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-119">Let's start with the addition sample from the introduction to this section.</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

> <span data-ttu-id="edb50-120">`var`을 사용하여 이 식 트리를 선언하지 않습니다. 왜냐하면 할당의 오른쪽이 암시적으로 형식화되어 있기 때문에 그렇게 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-120">I'm not using `var` to declare this expression tree, as it is not possible because the right-hand side of the assignment is implicitly typed.</span></span> <span data-ttu-id="edb50-121">이 사항을 좀더 자세히 이해하려면 [여기](implicitly-typed-lambda-expressions.md)를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="edb50-121">To understand this more deeply, read [here](implicitly-typed-lambda-expressions.md).</span></span>

<span data-ttu-id="edb50-122">루트 노드는 `LambdaExpression`입니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-122">The root node is a `LambdaExpression`.</span></span> <span data-ttu-id="edb50-123">`=>` 연산자의 오른쪽에서 흥미로운 코드를 가져오려면 `LambdaExpression`의 자식 중 하나를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-123">In order to get the interesting code on the right hand side of the `=>` operator, you need to find one of the children of the `LambdaExpression`.</span></span> <span data-ttu-id="edb50-124">이 섹션에서는 모든 식을 사용하여 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-124">We'll do that with all the expressions in this section.</span></span> <span data-ttu-id="edb50-125">부모 노드는 `LambdaExpression`의 반환 형식을 찾는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-125">The parent node does help us find the return type of the `LambdaExpression`.</span></span>

<span data-ttu-id="edb50-126">이 식의 각 노드를 검사하려면 많은 노드를 재귀적으로 방문해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-126">To examine each node in this expression, we'll need to recursively visit a number of nodes.</span></span> <span data-ttu-id="edb50-127">다음은 간단한 첫 번째 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-127">Here's a simple first implementation:</span></span>

```csharp
Expression<Func<int, int, int>> addition = (a, b) => a + b;

Console.WriteLine($"This expression is a {addition.NodeType} expression type");
Console.WriteLine($"The name of the lambda is {((addition.Name == null) ? "<null>" : addition.Name)}");
Console.WriteLine($"The return type is {addition.ReturnType.ToString()}");
Console.WriteLine($"The expression has {addition.Parameters.Count} arguments. They are:");
foreach(var argumentExpression in addition.Parameters)
{
    Console.WriteLine($"\tParameter Type: {argumentExpression.Type.ToString()}, Name: {argumentExpression.Name}");
}

var additionBody = (BinaryExpression)addition.Body;
Console.WriteLine($"The body is a {additionBody.NodeType} expression");
Console.WriteLine($"The left side is a {additionBody.Left.NodeType} expression");
var left = (ParameterExpression)additionBody.Left;
Console.WriteLine($"\tParameter Type: {left.Type.ToString()}, Name: {left.Name}");
Console.WriteLine($"The right side is a {additionBody.Right.NodeType} expression");
var right= (ParameterExpression)additionBody.Right;
Console.WriteLine($"\tParameter Type: {right.Type.ToString()}, Name: {right.Name}");
```

<span data-ttu-id="edb50-128">이 샘플은 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-128">This sample prints the following output:</span></span>

```
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 arguments. They are:
        Parameter Type: System.Int32, Name: a
        Parameter Type: System.Int32, Name: b
The body is a/an Add expression
The left side is a Parameter expression
        Parameter Type: System.Int32, Name: a
The right side is a Parameter expression
        Parameter Type: System.Int32, Name: b
```

<span data-ttu-id="edb50-129">위의 코드 샘플에서 많은 반복을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-129">You'll notice a lot of repetition in the code sample above.</span></span>
<span data-ttu-id="edb50-130">이러한 반복을 정리하고 보다 일반적인 용도의 식 노드 방문자를 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-130">Let's clean that up and build a more general purpose expression node visitor.</span></span> <span data-ttu-id="edb50-131">그러려면 재귀 알고리즘을 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-131">That's going to require us to write a recursive algorithm.</span></span> <span data-ttu-id="edb50-132">모든 노드는 자식이 있는 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-132">Any node could be of a type that might have children.</span></span>
<span data-ttu-id="edb50-133">자식이 있는 모든 노드에서는 해당 자식을 방문하여 해당 노드의 종류를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-133">Any node that has children requires us to visit those children and determine what that node is.</span></span> <span data-ttu-id="edb50-134">다음은 재귀를 활용하여 더하기 연산을 방문하는 정리된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-134">Here's the cleaned up version that utilizes recursion to visit the addition operations:</span></span>

```csharp
// Base Visitor class:
public abstract class Visitor
{
    private readonly Expression node;

    protected Visitor(Expression node)
    {
        this.node = node;
    }

    public abstract void Visit(string prefix);

    public ExpressionType NodeType => this.node.NodeType;
    public static Visitor CreateFromExpression(Expression node)
    {
        switch(node.NodeType)
        {
            case ExpressionType.Constant:
                return new ConstantVisitor((ConstantExpression)node);
            case ExpressionType.Lambda:
                return new LambdaVisitor((LambdaExpression)node);
            case ExpressionType.Parameter:
                return new ParameterVisitor((ParameterExpression)node);
            case ExpressionType.Add:
                return new BinaryVisitor((BinaryExpression)node);
            default:
                Console.Error.WriteLine($"Node not processed yet: {node.NodeType}");
                return default(Visitor);
        }
    }
}

// Lambda Visitor
public class LambdaVisitor : Visitor
{
    private readonly LambdaExpression node;
    public LambdaVisitor(LambdaExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression type");
        Console.WriteLine($"{prefix}The name of the lambda is {((node.Name == null) ? "<null>" : node.Name)}");
        Console.WriteLine($"{prefix}The return type is {node.ReturnType.ToString()}");
        Console.WriteLine($"{prefix}The expression has {node.Parameters.Count} argument(s). They are:");
        // Visit each parameter:
        foreach (var argumentExpression in node.Parameters)
        {
            var argumentVisitor = Visitor.CreateFromExpression(argumentExpression);
            argumentVisitor.Visit(prefix + "\t");
        }
        Console.WriteLine($"{prefix}The expression body is:");
        // Visit the body:
        var bodyVisitor = Visitor.CreateFromExpression(node.Body);
        bodyVisitor.Visit(prefix + "\t");
    }
}

// Binary Expression Visitor:
public class BinaryVisitor : Visitor
{
    private readonly BinaryExpression node;
    public BinaryVisitor(BinaryExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This binary expression is a {NodeType} expression");
        var left = Visitor.CreateFromExpression(node.Left);
        Console.WriteLine($"{prefix}The Left argument is:");
        left.Visit(prefix + "\t");
        var right = Visitor.CreateFromExpression(node.Right);
        Console.WriteLine($"{prefix}The Right argument is:");
        right.Visit(prefix + "\t");
    }
}

// Parameter visitor:
public class ParameterVisitor : Visitor
{
    private readonly ParameterExpression node;
    public ParameterVisitor(ParameterExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This is an {NodeType} expression type");
        Console.WriteLine($"{prefix}Type: {node.Type.ToString()}, Name: {node.Name}, ByRef: {node.IsByRef}");
    }
}

// Constant visitor:
public class ConstantVisitor : Visitor
{
    private readonly ConstantExpression node;
    public ConstantVisitor(ConstantExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This is an {NodeType} expression type");
        Console.WriteLine($"{prefix}The type of the constant value is {node.Type}");
        Console.WriteLine($"{prefix}The value of the constant value is {node.Value}");
    }
}
```

<span data-ttu-id="edb50-135">이 알고리즘은 임의의 `LambdaExpression`을 방문할 수 있는 알고리즘의 기반입니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-135">This algorithm is the basis of an algorithm that can visit any arbitrary `LambdaExpression`.</span></span> <span data-ttu-id="edb50-136">많은 허점이 있습니다. 즉, 만들어진 코드는 가능한 식 트리 노드 집합의 매우 작은 샘플만 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-136">There are a lot of holes, namely that the code I created only looks for a very small sample of the possible sets of expression tree nodes that it may encounter.</span></span> <span data-ttu-id="edb50-137">그러나 생성되는 항목에서 많은 부분을 익힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-137">However, you can still learn quite a bit from what it produces.</span></span> <span data-ttu-id="edb50-138">`Visitor.CreateFromExpression` 메서드의 기본 사례에서는 새 노드 형식이 나타나면 오류 콘솔에 메시지를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-138">(The default case in the `Visitor.CreateFromExpression` method prints a message to the error console when a new node type is encountered.</span></span> <span data-ttu-id="edb50-139">이런 방식으로 새로운 식 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-139">That way, you know to add a new expression type.)</span></span>

<span data-ttu-id="edb50-140">위에 표시된 더하기 식에서 이 방문자를 실행하면 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-140">When you run this visitor on the addition expression shown above, you get the following output:</span></span>

```
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
        This is an Parameter expression type
        Type: System.Int32, Name: b, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This is an Parameter expression type
                Type: System.Int32, Name: a, ByRef: False
        The Right argument is:
                This is an Parameter expression type
                Type: System.Int32, Name: b, ByRef: False
```

<span data-ttu-id="edb50-141">보다 일반적인 방문자 구현을 구축했으므로 훨씬 더 다양한 형식을 식을 방문하여 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-141">Now that you've built a more general visitor implementation, you can visit and process many more different types of expressions.</span></span>

## <a name="examining-an-addition-expression-with-many-levels"></a><span data-ttu-id="edb50-142">많은 수준으로 더하기 식 검사</span><span class="sxs-lookup"><span data-stu-id="edb50-142">Examining an Addition Expression with Many Levels</span></span>

<span data-ttu-id="edb50-143">더 복잡한 예제를 시도해 보겠지만 노드 형식은 여전히 더하기로만 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-143">Let's try a more complicated example, yet still limit the node types to addition only:</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2 + 3 + 4;
```

<span data-ttu-id="edb50-144">방문자 알고리즘에서 실행하기 전에 사고 연습을 통해 출력되는 사항을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-144">Before you run this on the visitor algorithm, try a thought exercise to work out what the output might be.</span></span> <span data-ttu-id="edb50-145">`+` 연산자는 *이진 연산자*임을 기억하세요. 이 연산자에는 왼쪽과 오른쪽 피연산자를 나타내는 두 개의 자식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-145">Remember that the `+` operator is a *binary operator*: it must have two children, representing the left and right operands.</span></span> <span data-ttu-id="edb50-146">여러 가지 방법으로 올바른 트리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-146">There are several possible ways to construct a tree that could be correct:</span></span>

```csharp
Expression<Func<int>> sum1 = () => 1 + (2 + (3 + 4));
Expression<Func<int>> sum2 = () => ((1 + 2) + 3) + 4;

Expression<Func<int>> sum3 = () => (1 + 2) + (3 + 4);
Expression<Func<int>> sum4 = () => 1 + ((2 + 3) + 4);
Expression<Func<int>> sum5 = () => (1 + (2 + 3)) + 4;
```

<span data-ttu-id="edb50-147">가장 유망한 해답을 강조하기 위해 두 가지 가능한 해답으로 분리된 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-147">You can see the separation into two possible answers to highlight the most promising.</span></span> <span data-ttu-id="edb50-148">첫 번째는 *오른쪽 결합성* 식을 나타내고,</span><span class="sxs-lookup"><span data-stu-id="edb50-148">The first represents *right associative* expressions.</span></span> <span data-ttu-id="edb50-149">두 번째는 *왼쪽 결합형* 식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-149">The second represent *left associative* expressions.</span></span>
<span data-ttu-id="edb50-150">이러한 두 형식의 장점은 형식이 임의 개수의 더하기 식으로 확장된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-150">The advantage of both of those two formats is that the format scales to any arbitrary number of addition expressions.</span></span> 

<span data-ttu-id="edb50-151">방문자를 통해 이 식을 실행하면 이 출력을 통해 간단한 더하기 식이 *왼쪽 결합성*이 있음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-151">If you do run this expression through the visitor, you will see this this output, verifying that the simple addition expression is *left associative*.</span></span> 

<span data-ttu-id="edb50-152">이 샘플을 실행하고 전체 식 트리를 보기 위해 소스 식 트리에서 한 가지를 변경해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-152">In order to run this sample, and see the full expression tree, I had to make one change to the source expression tree.</span></span> <span data-ttu-id="edb50-153">식 트리에 모든 상수가 포함되어 있으면 결과 트리에는 상수 값 `10`만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-153">When the expression tree contains all constants, the resulting tree simply contains the constant value of `10`.</span></span> <span data-ttu-id="edb50-154">컴파일러는 모든 더하기를 수행하고 가장 간단한 형태로 식을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-154">The compiler performs all the addition and reduces the expression to its simplest form.</span></span> <span data-ttu-id="edb50-155">식에서 하나의 변수를 추가하기만 하면 원래 트리를 확인하는 데 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-155">Simply adding one variable in the expression is sufficient to see the original tree:</span></span>

```csharp
Expression<Func<int, int>> sum = (a) => 1 + a + 3 + 4;
```

<span data-ttu-id="edb50-156">이 합계에 대한 방문자를 만들고 방문자를 실행하면 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-156">Create a visitor for this sum and run the visitor you'll see this output:</span></span>

```
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 1 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This binary expression is a Add expression
                        The Left argument is:
                                This is an Constant expression type
                                The type of the constant value is System.Int32
                                The value of the constant value is 1
                        The Right argument is:
                                This is an Parameter expression type
                                Type: System.Int32, Name: a, ByRef: False
                The Right argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 3
        The Right argument is:
                This is an Constant expression type
                The type of the constant value is System.Int32
                The value of the constant value is 4
```

<span data-ttu-id="edb50-157">방문자 코드를 통해 다른 샘플을 실행하고 해당 코드가 나타내는 트리를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-157">You can also run any of the other samples through the visitor code and see what tree it represents.</span></span> <span data-ttu-id="edb50-158">다음은 컴파일러가 상수를 계산할 수 없도록 하는 추가 매개 변수가 있는 위의 `sum3` 식에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-158">Here's an example of the `sum3` expression above (with an additional parameter to prevent the compiler from computing the constant):</span></span>

```csharp
Expression<Func<int, int, int>> sum3 = (a, b) => (1 + a) + (3 + b);
```

<span data-ttu-id="edb50-159">방문자의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-159">Here's the output from the visitor:</span></span>

```
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
        This is an Parameter expression type
        Type: System.Int32, Name: b, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 1
                The Right argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: a, ByRef: False
        The Right argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 3
                The Right argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: b, ByRef: False
```

<span data-ttu-id="edb50-160">괄호는 출력의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-160">Notice that the parentheses are not part of the output.</span></span> <span data-ttu-id="edb50-161">식 트리에는 입력 식의 괄호를 나타내는 노드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-161">There are no nodes in the expression tree that represent the parentheses in the input expression.</span></span> <span data-ttu-id="edb50-162">식 트리의 구조에는 우선 순위를 전달하는 데 필요한 모든 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-162">The structure of the expression tree contains all the information necessary to communicate the precedence.</span></span>

## <a name="extending-from-this-sample"></a><span data-ttu-id="edb50-163">이 샘플에서 확장</span><span class="sxs-lookup"><span data-stu-id="edb50-163">Extending from this sample</span></span>

<span data-ttu-id="edb50-164">이 샘플은 가장 기본적인 식 트리만 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-164">The sample deals with only the most rudimentary expression trees.</span></span> <span data-ttu-id="edb50-165">이 섹션에서 살펴본 코드는 상수 정수와 이진 `+` 연산자만 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-165">The code you've seen in this section only handles constant integers and the binary `+` operator.</span></span> <span data-ttu-id="edb50-166">최종 샘플로 방문자를 업데이트하여 더 복잡한 식을 처리해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-166">As a final sample, let's update the visitor to handle a more complicated expression.</span></span> <span data-ttu-id="edb50-167">다음 코드에 대해 작동하도록 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-167">Let's make it work for this:</span></span>

```csharp
Expression<Func<int, int>> factorial = (n) =>
    n == 0 ? 
    1 : 
    Enumerable.Range(1, n).Aggregate((product, factor) => product * factor);
```

<span data-ttu-id="edb50-168">이 코드는 수학 *계승* 함수에 가능한 한 가지 구현을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-168">This code represents one possible implementation for the mathematical *factorial* function.</span></span> <span data-ttu-id="edb50-169">이 코드를 작성한 방법에서는 식에 람다 식을 할당하여 식 트리를 작성할 때의 두 가지 제한을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-169">The way I've written this code highlights two limitiations of building expression trees by assigning lambda expressions to Expressions.</span></span> <span data-ttu-id="edb50-170">첫째, 문 람다는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-170">First, statement lambdas are not allowed.</span></span> <span data-ttu-id="edb50-171">즉, 루프, 블록, if/else 문 및 C#에서 일반적인 다른 제어 구조를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-171">That means I can't use loops, blocks, if / else statements, and other control structures common in C#.</span></span> <span data-ttu-id="edb50-172">식 사용으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-172">I'm limited to using expressions.</span></span> <span data-ttu-id="edb50-173">둘째, 같은 식을 재귀적으로 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-173">Second, I can't recursively call the same expression.</span></span>
<span data-ttu-id="edb50-174">이미 대리자인 경우에는 가능하지만 식 트리 형식으로는 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-174">I could if it were already a delegate, but I can't call it in its expression tree form.</span></span> <span data-ttu-id="edb50-175">[식 트리 작성](expression-trees-building.md)에 대한 섹션에서는 이러한 제한 사항을 해결하는 기술을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-175">In the section on [building expression trees](expression-trees-building.md) you'll learn techniques to overcome these limitations.</span></span>


<span data-ttu-id="edb50-176">이 식에서는 다음과 같은 형식의 노드가 모두 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-176">In this expression, you'll encounter nodes of all these types:</span></span>
1. <span data-ttu-id="edb50-177">같음(이진 식)</span><span class="sxs-lookup"><span data-stu-id="edb50-177">Equal (binary expression)</span></span>
2. <span data-ttu-id="edb50-178">곱하기(이진 식)</span><span class="sxs-lookup"><span data-stu-id="edb50-178">Multiply (binary expression)</span></span>
3. <span data-ttu-id="edb50-179">조건식(?</span><span class="sxs-lookup"><span data-stu-id="edb50-179">Conditional (the ?</span></span> <span data-ttu-id="edb50-180">: 식)</span><span class="sxs-lookup"><span data-stu-id="edb50-180">: expression)</span></span>
4. <span data-ttu-id="edb50-181">메서드 호출 식(`Range()` 및 `Aggregate()` 호출)</span><span class="sxs-lookup"><span data-stu-id="edb50-181">Method Call Expression (calling `Range()` and `Aggregate()`)</span></span>

<span data-ttu-id="edb50-182">방문자 알고리즘을 수정하는 한 가지 방법은 해당 알고리즘을 계속 실행하고 `default` 절에 도달할 때마다 노드 형식을 기록하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-182">One way to modify the visitor algorithm is to keep executing it, and write the node type every time you reach your `default` clause.</span></span> <span data-ttu-id="edb50-183">몇 번 반복하면 각각의 잠재적 노드를 확인하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-183">After a few iterations, you'll have seen each of the potential nodes.</span></span> <span data-ttu-id="edb50-184">그러면 다 끝났습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-184">Then, you have all you need.</span></span> <span data-ttu-id="edb50-185">결과는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-185">The result would be something like this:</span></span>

```csharp
public static Visitor CreateFromExpression(Expression node)
{
    switch(node.NodeType)
    {
        case ExpressionType.Constant:
            return new ConstantVisitor((ConstantExpression)node);
        case ExpressionType.Lambda:
            return new LambdaVisitor((LambdaExpression)node);
        case ExpressionType.Parameter:
            return new ParameterVisitor((ParameterExpression)node);
        case ExpressionType.Add:
        case ExpressionType.Equal:
        case ExpressionType.Multiply:
            return new BinaryVisitor((BinaryExpression)node);
        case ExpressionType.Conditional:
            return new ConditionalVisitor((ConditionalExpression)node);
        case ExpressionType.Call:
            return new MethodCallVisitor((MethodCallExpression)node);
        default:
            Console.Error.WriteLine($"Node not processed yet: {node.NodeType}");
            return default(Visitor);
    }
}
```

<span data-ttu-id="edb50-186">ConditionalVisitor 및 MethodCallVisitor는 해당 두 노드를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-186">The ConditionalVisitor and MethodCallVisitor process those two nodes:</span></span>

```csharp
public class ConditionalVisitor : Visitor
{
    private readonly ConditionalExpression node;
    public ConditionalVisitor(ConditionalExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression");
        var testVisitor = Visitor.CreateFromExpression(node.Test);
        Console.WriteLine($"{prefix}The Test for this expression is:");
        testVisitor.Visit(prefix + "\t");
        var trueVisitor = Visitor.CreateFromExpression(node.IfTrue);
        Console.WriteLine($"{prefix}The True clause for this expression is:");
        trueVisitor.Visit(prefix + "\t");
        var falseVisitor = Visitor.CreateFromExpression(node.IfFalse);
        Console.WriteLine($"{prefix}The False clause for this expression is:");
        falseVisitor.Visit(prefix + "\t");
    }
}

public class MethodCallVisitor : Visitor
{
    private readonly MethodCallExpression node;
    public MethodCallVisitor(MethodCallExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression");
        if (node.Object == null)
            Console.WriteLine($"{prefix}This is a static method call");
        else
        {
            Console.WriteLine($"{prefix}The receiver (this) is:");
            var receiverVisitor = Visitor.CreateFromExpression(node.Object);
            receiverVisitor.Visit(prefix + "\t");
        }

        var methodInfo = node.Method;
        Console.WriteLine($"{prefix}The method name is {methodInfo.DeclaringType}.{methodInfo.Name}");
        // There is more here, like generic arguments, and so on.
        Console.WriteLine($"{prefix}The Arguments are:");
        foreach(var arg in node.Arguments)
        {
            var argVisitor = Visitor.CreateFromExpression(arg);
            argVisitor.Visit(prefix + "\t");
        }
    }
}
```

<span data-ttu-id="edb50-187">식 트리에 대한 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-187">And the output for the expression tree would be:</span></span>

```
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 1 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: n, ByRef: False
The expression body is:
        This expression is a Conditional expression
        The Test for this expression is:
                This binary expression is a Equal expression
                The Left argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: n, ByRef: False
                The Right argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 0
        The True clause for this expression is:
                This is an Constant expression type
                The type of the constant value is System.Int32
                The value of the constant value is 1
        The False clause for this expression is:
                This expression is a Call expression
                This is a static method call
                The method name is System.Linq.Enumerable.Aggregate
                The Arguments are:
                        This expression is a Call expression
                        This is a static method call
                        The method name is System.Linq.Enumerable.Range
                        The Arguments are:
                                This is an Constant expression type
                                The type of the constant value is System.Int32
                                The value of the constant value is 1
                                This is an Parameter expression type
                                Type: System.Int32, Name: n, ByRef: False
                        This expression is a Lambda expression type
                        The name of the lambda is <null>
                        The return type is System.Int32
                        The expression has 2 arguments. They are:
                                This is an Parameter expression type
                                Type: System.Int32, Name: product, ByRef: False
                                This is an Parameter expression type
                                Type: System.Int32, Name: factor, ByRef: False
                        The expression body is:
                                This binary expression is a Multiply expression
                                The Left argument is:
                                        This is an Parameter expression type
                                        Type: System.Int32, Name: product, ByRef: False
                                The Right argument is:
                                        This is an Parameter expression type
                                        Type: System.Int32, Name: factor, ByRef: False
```

## <a name="extending-the-sample-library"></a><span data-ttu-id="edb50-188">샘플 라이브러리 확장</span><span class="sxs-lookup"><span data-stu-id="edb50-188">Extending the Sample Library</span></span>

<span data-ttu-id="edb50-189">이 섹션의 샘플은 식 트리의 노드를 방문하여 검사하는 핵심 기술을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-189">The samples in this section show the core techniques to visit and examine nodes in an expression tree.</span></span> <span data-ttu-id="edb50-190">식 트리의 노드를 방문하고 액세스하는 핵심 작업에 집중하기 위해 필요할 수 있는 많은 작업에 주석을 달았습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-190">I glossed over many actions you might need in order to concentrate on the core tasks of visiting and accessing nodes in an expression tree.</span></span> 

<span data-ttu-id="edb50-191">첫째, 방문자는 정수인 상수만 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-191">First, the visitors only handle constants that are integers.</span></span> <span data-ttu-id="edb50-192">상수 값은 다른 모든 숫자 형식이 될 수 있으며 C# 언어는 해당 형식 간의 변환 및 승격을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-192">Constant values could be any other numeric type, and the C# language supports conversions and promotions between those types.</span></span> <span data-ttu-id="edb50-193">이 코드의 보다 강력한 버전은 이러한 모든 기능을 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-193">A more robust version of this code would mirror all those capabilities.</span></span>

<span data-ttu-id="edb50-194">마지막 예제도 가능한 노드 형식의 하위 집합을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-194">Even the last example recognizes a subset of the possible node types.</span></span>
<span data-ttu-id="edb50-195">이 예제가 실패하도록 하는 많은 식을 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-195">You can still feed it many expressions that will cause it to fail.</span></span>
<span data-ttu-id="edb50-196">전체 구현은 [ExpressionVisitor](/dotnet/core/api/System.Linq.Expressions.ExpressionVisitor)라는 이름으로 .NET Standard에 포함되며 가능한 노드 형식을 모두 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-196">A full implementation is included in the .NET Standard under the name [ExpressionVisitor](/dotnet/core/api/System.Linq.Expressions.ExpressionVisitor) and can handle all the possible node types.</span></span>

<span data-ttu-id="edb50-197">마지막으로 이 문서에서 사용된 라이브러리는 데모 및 학습용으로 작성되었으며,</span><span class="sxs-lookup"><span data-stu-id="edb50-197">Finally, the library I used in this article was built for demonstration and learning.</span></span> <span data-ttu-id="edb50-198">최적화되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-198">It's not optimized.</span></span> <span data-ttu-id="edb50-199">사용된 구조를 매우 명확하게 하고 노드를 방문하여 포함된 항목을 분석하는 데 사용된 기술을 강조하기 위해 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-199">I wrote it to make the structures used very clear, and to highlight the techniques used to visit the nodes and analyze what's there.</span></span> <span data-ttu-id="edb50-200">프로덕션 구현에서는 지금까지보다 성능에 더 많은 주의를 기울입니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-200">A production implementation would pay more attention to performance than I have.</span></span>

<span data-ttu-id="edb50-201">이러한 제한 사항에도 불구하고 식 트리를 읽고 이해하는 알고리즘 작성을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb50-201">Even with those limitations, you should be well on your way to writing algorithms that read and understand expression trees.</span></span>

[<span data-ttu-id="edb50-202">다음 -- 식 작성</span><span class="sxs-lookup"><span data-stu-id="edb50-202">Next -- Building Expressions</span></span>](expression-trees-building.md)
