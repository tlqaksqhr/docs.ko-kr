---
title: "람다 식"
description: "인수로 전달할 수 있는 실행 코드 블록인 람다 식 사용 방법을 알아봅니다."
keywords: ".NET, .NET Core, 람다 식, 람다, 대리자"
ms-author: ronpet
author: rpetrusha
ms.date: 11/22/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: b6a0539a-8ce5-4da7-adcf-44be345a2714
ms.openlocfilehash: 1a97d830c675c8e3980eddae78f3face279ec6dc
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2017
---
# <a name="lambda-expressions"></a><span data-ttu-id="51b34-104">람다 식</span><span class="sxs-lookup"><span data-stu-id="51b34-104">Lambda expressions</span></span> #

<span data-ttu-id="51b34-105">*람다 식*은 개체로 처리되는 코드 블록(식 또는 문 블록)입니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-105">A *lambda expression* is a block of code (an expression or a statement block) that is treated as an object.</span></span> <span data-ttu-id="51b34-106">이 식은 인수로 메서드에 전달할 수 있으며 메서드 호출에서 반환될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-106">It can be passed as an argument to methods, and it can also be returned by method calls.</span></span> <span data-ttu-id="51b34-107">람다 식은 다음과 같은 경우에 광범위하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-107">Lambda expressions are used extensively for:</span></span>

- <span data-ttu-id="51b34-108">와 같은 비동기 메서드를 실행 하는 코드를 전달 <xref:System.Threading.Tasks.Task.Run(System.Action)>합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-108">Passing the code that is to be executed to asynchronous methods, such as <xref:System.Threading.Tasks.Task.Run(System.Action)>.</span></span>

- <span data-ttu-id="51b34-109">[LINQ 쿼리 식](linq/index.md) 작성.</span><span class="sxs-lookup"><span data-stu-id="51b34-109">Writing [LINQ query expressions](linq/index.md).</span></span>

- <span data-ttu-id="51b34-110">[식 트리](expression-trees-building.md) 만들기.</span><span class="sxs-lookup"><span data-stu-id="51b34-110">Creating [expression trees](expression-trees-building.md).</span></span>

<span data-ttu-id="51b34-111">람다 식은 대리자로 나타내거나 대리자로 컴파일되는 식 트리로 나타낼 수 있는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-111">Lambda expressions are code that can be represented either as a delegate, or as an expression tree that compiles to a delegate.</span></span> <span data-ttu-id="51b34-112">람다 식의 특정 대리자 형식은 해당 매개 변수 및 반환 값에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-112">The specific delegate type of a lambda expression depends on its parameters and return value.</span></span> <span data-ttu-id="51b34-113">값을 반환하지 않는 람다 식은 해당 매개 변수의 개수에 따라 특정 `Action` 대리자에 해당하고,</span><span class="sxs-lookup"><span data-stu-id="51b34-113">Lambda expressions that don't return a value correspond to a specific `Action` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="51b34-114">값을 반환하는 람다 식은 해당 매개 변수의 개수에 따라 특정 `Func` 대리자에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-114">Lambda expressions that return a value correspond to a specific `Func` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="51b34-115">2 개의 매개 변수가 있지만 아무 값도 반환 하는 람다 식에 해당 하는 예를 들어 한 <xref:System.Action%602> 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-115">For example, a lambda expression that has two parameters but returns no value corresponds to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="51b34-116">에 해당 하는 하나의 매개 변수가 있으며 값을 반환 하는 람다 식을 <xref:System.Func%602> 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-116">A lambda expression that has one parameter and returns a value corresponds to <xref:System.Func%602> delegate.</span></span>

<span data-ttu-id="51b34-117">람다 식은 [람다 선언 연산자](language-reference/operators/lambda-operator.md) `=>`을 사용하여 람다의 매개 변수 목록을 실행 코드와 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-117">A lambda expression uses `=>`, the [lambda declaration operator](language-reference/operators/lambda-operator.md), to separate the lambda's parameter list from its executable code.</span></span> <span data-ttu-id="51b34-118">람다 식을 만들려면 람다 연산자 왼쪽에 입력 매개 변수(있는 경우)를 지정하고 다른 쪽에 식이나 문 블록을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-118">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator, and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="51b34-119">예를 들어 한 줄 람다 식 `x => x * x`는 이름이 `x`인 매개 변수를 지정하고 `x` 제곱 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-119">For example, the single-line lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="51b34-120">다음 예제와 같이 대리자 형식에 이 식을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-120">You can assign this expression to a delegate type, as the following example shows:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/lambda1.cs#1)]

<span data-ttu-id="51b34-121">또는 메서드 인수로 직접 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-121">Or you can pass it directly as a method argument:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/lambda2.cs#2)]

## <a name="expression-lambdas"></a><span data-ttu-id="51b34-122">식 람다</span><span class="sxs-lookup"><span data-stu-id="51b34-122">Expression lambdas</span></span> ##

 <span data-ttu-id="51b34-123">=> 연산자의 오른쪽에 식이 있는 람다 식을 *식 람다*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-123">A lambda expression with an expression on the right side of the => operator is called an *expression lambda*.</span></span> <span data-ttu-id="51b34-124">식 람다는 [식 트리](expression-trees.md)를 만드는 데 광범위하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-124">Expression lambdas are used extensively in the construction of [expression trees](expression-trees.md).</span></span> <span data-ttu-id="51b34-125">식 람다는 식의 결과를 반환하며 기본 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-125">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input parameters) => expression
```

<span data-ttu-id="51b34-126">괄호는 람다 식에 입력 매개 변수가 하나뿐인 경우에만 생략할 수 있고 그렇지 않으면 생략할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-126">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span> <span data-ttu-id="51b34-127">입력 매개 변수가 0개이면 다음과 같이 빈 괄호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-127">Specify zero input parameters with empty parentheses:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/expression3.cs#1)]

<span data-ttu-id="51b34-128">둘 이상의 입력 매개 변수는 다음과 같이 괄호로 묶고 쉼표로 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-128">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/expression3.cs#2)]

<span data-ttu-id="51b34-129">일반적으로 컴파일러는 매개 변수 형식을 확인하는 데 형식 유추를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-129">Ordinarily, the compiler uses type inference in determining parameter types.</span></span> <span data-ttu-id="51b34-130">그러나 컴파일러에서 입력 형식을 유추하기 어렵거나 유추할 수 없는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-130">However, sometimes it is difficult or impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="51b34-131">이런 경우 다음 예제와 같이 형식을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-131">When this occurs, you can specify the types explicitly, as in the following example:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/expression3.cs#3)]

<span data-ttu-id="51b34-132">위의 예제에서 식 람다의 본문은 메서드 호출로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-132">Note in the previous example that the body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="51b34-133">그러나 SQL Server 또는 EF(Entity Framework)와 같이 .NET Framework 외부에서 평가되는 식 트리를 만드는 경우 .NET 구현 컨텍스트 외부에서는 메서드가 의미가 없을 수 있으므로 람다 식에서 메서드 호출을 사용할 수 없도록 방지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-133">However, if you are creating expression trees that are evaluated outside of the .NET Framework, such as in SQL Server or Entity Framework (EF), you should refrain from using method calls in lambda expressions, since the methods may have no meaning outside the context of the .NET implementation.</span></span> <span data-ttu-id="51b34-134">이 경우 메서드 호출을 사용하도록 선택하면 메서드 호출을 철저히 테스트하여 성공적으로 해결할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-134">If you do choose to use method calls in this case, be sure to test them thoroughly to ensure that the method calls can be successfuly resolved.</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="51b34-135">문 람다</span><span class="sxs-lookup"><span data-stu-id="51b34-135">Statement lambdas</span></span> ##

<span data-ttu-id="51b34-136">문 람다는 다음과 같이 중괄호 안에 문을 지정한다는 점을 제외하면 식 람다와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-136">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>

```csharp
(input parameters) => { statement; }
```

<span data-ttu-id="51b34-137">문 람다의 본문에 지정할 수 있는 문의 개수에는 제한이 없지만 일반적으로 2-3개 정도만 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-137">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/statement1.cs#1)]

<span data-ttu-id="51b34-138">무명 메서드와 마찬가지로 문 람다는 식 트리를 만드는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-138">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="51b34-139">비동기 람다</span><span class="sxs-lookup"><span data-stu-id="51b34-139">Async lambdas</span></span> ##

<span data-ttu-id="51b34-140">[async](language-reference/keywords/async.md) 및 [await](language-reference/keywords/await.md) 키워드를 사용하여 비동기 처리를 통합하는 람다 식과 문을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-140">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](language-reference/keywords/async.md) and [await](language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="51b34-141">예를 들어 예제에서는 비동기적으로 실행되는 `ShowSquares` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-141">For example, the example calls a `ShowSquares` method that executes asynchronously.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/async1.cs#1)]

<span data-ttu-id="51b34-142">비동기 메서드를 만들고 사용하는 방법에 대한 자세한 내용은 [Async 및 Await를 사용한 비동기 프로그래밍](programming-guide/concepts/async/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51b34-142">For more information about how to create and use async methods, see [Asynchronous programming with async and await](programming-guide/concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="51b34-143">람다 식 및 튜플</span><span class="sxs-lookup"><span data-stu-id="51b34-143">Lambda expressions and tuples</span></span> ##

<span data-ttu-id="51b34-144">C# 7.0부터 C# 언어에서 튜플을 기본적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-144">Starting with C# 7.0, the C# language provides built-in support for tuples.</span></span> <span data-ttu-id="51b34-145">람다 식에 인수로 튜플을 제공할 수 있으며 람다 식에서 튜플을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-145">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="51b34-146">경우에 따라 C# 컴파일러는 형식 유추를 사용하여 튜플 구성 요소의 형식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-146">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span> 

<span data-ttu-id="51b34-147">쉼표로 구분된 해당 구성 요소 목록을 괄호로 묶어 튜플을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-147">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="51b34-148">다음 예제에서는 5개 구성 요소가 있는 튜플을 사용하여 숫자 시퀀스를 람다 식에 전달하고 각 값을 두 배로 늘린 후 곱하기의 결과가 포함된, 5개 구성 요소가 있는 튜플을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-148">The following example uses tuple with 5 components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with 5 components that contains the result of the multiplications.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/tuples1.cs#1)]

<span data-ttu-id="51b34-149">일반적으로 튜플 필드의 이름은 `Item1`, `Item2` 등입니다. 그러나 다음 예제에서처럼 명명된 구성 요소가 있는 튜플을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-149">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/tuples2.cs#1)]

<span data-ttu-id="51b34-150">C#의 튜플 지원에 대한 자세한 내용은 [C# 튜플 형식](tuples.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51b34-150">For more information on support for tuples in C#, see [C# Tuple types](tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="51b34-151">표준 쿼리 연산자와 람다 식</span><span class="sxs-lookup"><span data-stu-id="51b34-151">Lambdas with the standard query operators</span></span> ##

<span data-ttu-id="51b34-152">다른 구현 간에 개체에 대 한 LINQ 하나는 형식의 입력된 매개 변수는의 <xref:System.Func%601> 제네릭 대리자의 제품군입니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-152">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="51b34-153">이러한 대리자는 형식 매개 변수를 사용하여 입력 매개 변수의 수와 형식 및 대리자의 반환 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-153">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="51b34-154">`Func` 대리자는 소스 데이터 집합에 있는 각 요소에 적용할 사용자 정의 식을 캡슐화하는 데 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-154">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="51b34-155">예를 들어는 <xref:System.Func%601> 인 구문은 대리자:</span><span class="sxs-lookup"><span data-stu-id="51b34-155">For example, consider the <xref:System.Func%601> delegate, whose syntax is:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#1)]

<span data-ttu-id="51b34-156">다음과 같은 코드로 대리자를 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-156">The delegate can be instantiated with code like the following</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#2)]

<span data-ttu-id="51b34-157">여기서 `int`는 입력 매개 변수이고 `bool`은 반환 값입니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-157">where `int` is an input parameter, and `bool` is the return value.</span></span> <span data-ttu-id="51b34-158">반환 값은 항상 마지막 형식 매개 변수에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-158">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="51b34-159">다음 `Func` 대리자를 호출하면 입력 매개 변수가 5인지 여부를 나타내는 true 또는 false가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-159">When the following `Func` delegate is invoked, it returns true or false to indicate whether the input parameter is equal to 5:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#3)]

<span data-ttu-id="51b34-160">인수 형식이 람다 식을 제공할 수도 있습니다는 <xref:System.Linq.Expressions.Expression%601>에 정의 되어 있는 표준 쿼리 연산자는 <xref:System.Linq.Queryable> 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-160">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="51b34-161">지정 하는 경우는 <xref:System.Linq.Expressions.Expression%601> 인수를 람다는 식 트리로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-161">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span> <span data-ttu-id="51b34-162">다음 예제에서는 [System.Linq.Enumerable.Count](xref:System.Linq.Enumerable.Count%60%601(System.Collections.Generic.IEnumerable{%60%600})) 표준 쿼리 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-162">The following example uses the [System.Linq.Enumerable.Count](xref:System.Linq.Enumerable.Count%60%601(System.Collections.Generic.IEnumerable{%60%600})) standard query operator.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#4)]

<span data-ttu-id="51b34-163">컴파일러에서 입력 매개 변수의 형식을 유추하거나 사용자가 형식을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-163">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="51b34-164">이 람다 식은 2로 나누었을 때 나머지가 1인 정수(`n`)의 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-164">This particular lambda expression counts those integers (`n`) that, when divided by two, have a remainder of 1.</span></span>

<span data-ttu-id="51b34-165">다음 예제에서는 숫자 시퀀스에서 조건을 만족하지 않는 첫 번째 숫자가 "9"이기 때문에 `numbers` 배열에서 "9" 앞에 오는 모든 요소가 포함된 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-165">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#5)]

<span data-ttu-id="51b34-166">다음 예제에서는 입력 매개 변수를 괄호로 묶어 여러 개 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-166">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="51b34-167">이 메서드는 값이 배열의 서수 위치보다 작은 숫자가 나타날 때까지 숫자 배열의 모든 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-167">The method returns all the elements in the numbers array until it encounters a number whose value is less than its ordinal position in the array.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/query1.cs#6)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="51b34-168">람다 식에서의 형식 유추</span><span class="sxs-lookup"><span data-stu-id="51b34-168">Type inference in lambda expressions</span></span> ##

<span data-ttu-id="51b34-169">컴파일러에서는 람다 식 본문, 매개 변수 형식 및 C# 언어 사양에 설명되어 있는 기타 요소를 기준으로 형식을 유추할 수 있기 때문에 대부분의 경우에는 람다 식을 작성할 때 입력 매개 변수의 형식을 지정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-169">When writing lambdas, you often do not have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors, as described in the C# Language Specification.</span></span> <span data-ttu-id="51b34-170">대부분의 표준 쿼리 연산자에서 첫 번째 입력 형식은 소스 시퀀스 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-170">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="51b34-171">`IEnumerable<Customer>`를 쿼리할 경우 입력 변수가 `Customer` 개체로 유추됩니다. 이는 이 개체의 메서드와 속성에 액세스할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-171">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/infer1.cs#1)]

<span data-ttu-id="51b34-172">람다 식의 형식 유추에 대한 일반적인 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-172">The general rules for type inference for lambdas are:</span></span>

- <span data-ttu-id="51b34-173">람다 식과 대리자 형식에 포함된 매개 변수 수가 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-173">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="51b34-174">람다 식의 각 입력 인수는 해당되는 대리자 매개 변수로 암시적으로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-174">Each input argument in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="51b34-175">람다 식의 반환 값(있는 경우)은 대리자의 반환 형식으로 암시적으로 변환될 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-175">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>

<span data-ttu-id="51b34-176">공용 형식 시스템에는 "람다 식"이라는 개념이 기본적으로 포함되어 있지 않기 때문에 람다 식 자체에는 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-176">Note that lambda expressions in themselves do not have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="51b34-177">그러나 람다 식의 "형식"을 비공식적으로 언급해야 할 경우도 있는데</span><span class="sxs-lookup"><span data-stu-id="51b34-177">However, it is sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="51b34-178">이 경우 형식은 대리자 형식 또는 람다 식이 변환되는 <xref:System.Linq.Expressions.Expression> 형식을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-178">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="51b34-179">람다 식의 변수 범위</span><span class="sxs-lookup"><span data-stu-id="51b34-179">Variable Scope in Lambda Expressions</span></span> ##

<span data-ttu-id="51b34-180">람다 식은 람다 함수를 정의하는 메서드 범위 내에 있거나 람다 식을 포함하는 형식 범위 내에 있는 *외부 변수*([무명 메서드](programming-guide/statements-expressions-operators/anonymous-methods.md) 참조)를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-180">Lambdas can refer to *outer variables* (see [Anonymous methods](programming-guide/statements-expressions-operators/anonymous-methods.md)) that are in scope in the method that defines the lambda function, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="51b34-181">이러한 방식으로 캡처되는 변수는 변수가 범위를 벗어나 가비지 수집되는 경우에도 람다 식에 사용할 수 있도록 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-181">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="51b34-182">외부 변수는 명확하게 할당해야만 람다 식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-182">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="51b34-183">다음 예제에서는 이러한 규칙을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-183">The following example demonstrates these rules.</span></span>

[!code-csharp[csSnippets.Lambdas](../../samples/snippets/csharp/concepts/lambda-expressions/scope.cs#1)]

 <span data-ttu-id="51b34-184">람다 식의 변수 범위에는 다음과 같은 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-184">The following rules apply to variable scope in lambda expressions:</span></span>

- <span data-ttu-id="51b34-185">캡처된 변수는 해당 변수를 참조하는 대리자가 가비지 수집 대상이 될 때까지 가비지 수집되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-185">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="51b34-186">람다 식에 사용된 변수는 외부 메서드에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-186">Variables introduced within a lambda expression are not visible in the outer method.</span></span>

- <span data-ttu-id="51b34-187">람다 식은 바깥쪽 메서드에서 `ref` 또는 `out` 매개 변수를 직접 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-187">A lambda expression cannot directly capture a `ref` or `out` parameter from an enclosing method.</span></span>

- <span data-ttu-id="51b34-188">람다 식의 return 문에 의해서는 바깥쪽 메서드가 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-188">A return statement in a lambda expression does not cause the enclosing method to return.</span></span>

- <span data-ttu-id="51b34-189">점프문의 대상이 블록 외부에 있는 경우 람다 식에 람다 함수 내에 있는 `goto` 문, `break` 문 또는 `continue` 문을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-189">A lambda expression cannot contain a `goto` statement, `break` statement, or `continue` statement that is inside the lambda function if the jump statement’s target is outside the block.</span></span> <span data-ttu-id="51b34-190">대상이 블록 내에 있는 경우 람다 함수 블록 외부에 점프문을 사용해도 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51b34-190">It is also an error to have a jump statement outside the lambda function block if the target is inside the block.</span></span>

## <a name="see-also"></a><span data-ttu-id="51b34-191">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51b34-191">See also</span></span> ##

<span data-ttu-id="51b34-192">[LINQ(Language-Integrated Query)](../standard/using-linq.md) </span><span class="sxs-lookup"><span data-stu-id="51b34-192">[LINQ (Language-Integrated Query)](../standard/using-linq.md) </span></span>  
<span data-ttu-id="51b34-193">[무명 메서드](programming-guide/statements-expressions-operators/anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="51b34-193">[Anonymous methods](programming-guide/statements-expressions-operators/anonymous-methods.md) </span></span>  
[<span data-ttu-id="51b34-194">식 트리</span><span class="sxs-lookup"><span data-stu-id="51b34-194">Expression trees</span></span>](expression-trees.md)
