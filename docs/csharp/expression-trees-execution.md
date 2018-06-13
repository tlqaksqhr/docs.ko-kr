---
title: 식 트리 실행
description: 식 트리를 실행 가능한 중간 언어(IL) 명령으로 변환하여 실행하는 방법을 알아봅니다.
ms.date: 06/20/2016
ms.assetid: 109e0ac5-2a9c-48b4-ac68-9b6219cdbccf
ms.openlocfilehash: 54706cd5d8ebe60bb893bc82f05aecddae370602
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218165"
---
# <a name="executing-expression-trees"></a><span data-ttu-id="d8cc3-103">식 트리 실행</span><span class="sxs-lookup"><span data-stu-id="d8cc3-103">Executing Expression Trees</span></span>

[<span data-ttu-id="d8cc3-104">이전 -- 식 트리를 지원하는 프레임워크 형식</span><span class="sxs-lookup"><span data-stu-id="d8cc3-104">Previous -- Framework Types Supporting Expression Trees</span></span>](expression-classes.md)

<span data-ttu-id="d8cc3-105">*식 트리*는 일부 코드를 나타내는 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-105">An *expression tree* is a data structure that represents some code.</span></span>
<span data-ttu-id="d8cc3-106">컴파일되고 실행 가능한 코드가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-106">It is not compiled and executable code.</span></span> <span data-ttu-id="d8cc3-107">식 트리로 표시되는 .NET 코드를 실행하려면 실행 가능한 IL 명령으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-107">If you want to execute the .NET code that is represented by an expression tree, you must convert it into executable IL instructions.</span></span> 
## <a name="lambda-expressions-to-functions"></a><span data-ttu-id="d8cc3-108">람다 식을 함수로 변환</span><span class="sxs-lookup"><span data-stu-id="d8cc3-108">Lambda Expressions to Functions</span></span>
<span data-ttu-id="d8cc3-109">모든 LambdaExpression 또는 LambdaExpression에서 파생된 모든 형식을 실행 가능한 IL로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-109">You can convert any LambdaExpression, or any type derived from LambdaExpression into executable IL.</span></span> <span data-ttu-id="d8cc3-110">다른 식 형식은 코드로 직접 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-110">Other expression types cannot be directly converted into code.</span></span> <span data-ttu-id="d8cc3-111">실제로 이 제한은 거의 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-111">This restriction has little effect in practice.</span></span> <span data-ttu-id="d8cc3-112">람다 식은 실행 가능한 IL(중간 언어)로 변환하여 실행하려는 식의 유일한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-112">Lambda expressions are the only types of expressions that you would want to execute by converting to executable intermediate language (IL).</span></span> <span data-ttu-id="d8cc3-113">`ConstantExpression`을 직접 실행하는 것의 의미를 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-113">(Think about what it would mean to directly execute a `ConstantExpression`.</span></span> <span data-ttu-id="d8cc3-114">유용한 의미가 있나요? `LamdbaExpression`이거나 `LambdaExpression`에서 파생된 형식인 모든 식 트리는 IL로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-114">Would it mean anything useful?) Any expression tree that is a `LamdbaExpression`, or a type derived from `LambdaExpression` can be converted to IL.</span></span>
<span data-ttu-id="d8cc3-115">식 형식 `Expression<TDelegate>` 는 .NET Core 라이브러리에서 유일하게 구체적인 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-115">The expression type `Expression<TDelegate>` is the only concrete example in the .NET Core libraries.</span></span> <span data-ttu-id="d8cc3-116">이 형식은 모든 대리자 형식에 매핑되는 식을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-116">It's used to represent an expression that maps to any delegate type.</span></span> <span data-ttu-id="d8cc3-117">이 형식은 대리자 형식에 매핑되므로 .NET에서 식을 검사하고 람다 식의 시그니처와 일치하는 적절한 대리자에 대해 IL을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-117">Because this type maps to a delegate type, .NET can examine the expression, and generate IL for an appropriate delegate that matches the signature of the lambda expression.</span></span> 

<span data-ttu-id="d8cc3-118">대부분의 경우 식과 해당 대리자 간에 간단한 매핑이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-118">In most cases, this creates a simple mapping between an expression, and its corresponding delegate.</span></span> <span data-ttu-id="d8cc3-119">예를 들어 `Expression<Func<int>>`로 표시되는 식 트리는 `Func<int>` 형식의 대리자로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-119">For example, an expression tree that is represented by `Expression<Func<int>>` would be converted to a delegate of the type `Func<int>`.</span></span> <span data-ttu-id="d8cc3-120">반환 형식 및 인수 목록을 사용하는 람다 식의 경우 람다 식으로 표시된 실행 코드의 대상 형식인 대리자 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-120">For a lambda expression with any return type and argument list, there exists a delegate type that is the target type for the executable code represented by that lamdba expression.</span></span>

<span data-ttu-id="d8cc3-121">`LamdbaExpression` 형식에는 식 트리를 실행 코드로 변환하는 데 사용되는 `Compile` 및 `CompileToMethod` 멤버가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-121">The `LamdbaExpression` type contains `Compile` and `CompileToMethod` members that you would use to convert an expression tree to executable code.</span></span> <span data-ttu-id="d8cc3-122">`Compile` 메서드는 대리자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-122">The `Compile` method creates a delegate.</span></span> <span data-ttu-id="d8cc3-123">`CompileToMethod` 메서드는 식 트리의 컴파일된 출력을 나타내는 IL로 `MethodBuilder` 개체를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-123">The `CompileToMethod` method updates a `MethodBuilder` object with the IL that represents the compiled output of the expression tree.</span></span> <span data-ttu-id="d8cc3-124">`CompileToMethod`는 .NET Core 프레임워크가 아니라 전체 데스크톱 프레임워크에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-124">Note that `CompileToMethod` is only available on the full desktop framework, not on the .NET Core framework.</span></span>

<span data-ttu-id="d8cc3-125">필요에 따라 생성된 대리자 개체에 대한 기호 디버깅 정보를 수신하는 `DebugInfoGenerator`를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-125">Optionally, you can also provide a `DebugInfoGenerator` that will receive the symbol debugging information for the generated delegate object.</span></span> <span data-ttu-id="d8cc3-126">그러면 식 트리를 대리자 개체로 변환하고 생성된 대리자에 대한 전체 디버깅 정보를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-126">This enables you to convert the expression tree into a delegate object, and have full debugging information about the generated delegate.</span></span>

<span data-ttu-id="d8cc3-127">다음 코드를 사용하여 식을 대리자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-127">You would convert an expression into a delegate using the following code:</span></span>

```csharp
Expression<Func<int>> add = () => 1 + 2;
var func = add.Compile(); // Create Delegate
var answer = func(); // Invoke Delegate
Console.WriteLine(answer);
```

<span data-ttu-id="d8cc3-128">대리자 형식은 식 형식을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-128">Notice that the delegate type is based on the expression type.</span></span> <span data-ttu-id="d8cc3-129">강력한 형식의 방식으로 대리자 개체를 사용하려면 반환 형식 및 인수 목록을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-129">You must know the return type and the argument list if you want to use the delegate object in a strongly typed manner.</span></span> <span data-ttu-id="d8cc3-130">`LambdaExpression.Compile()` 메서드는 `Delegate` 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-130">The `LambdaExpression.Compile()` method returns the `Delegate` type.</span></span> <span data-ttu-id="d8cc3-131">컴파일 시간 도구에서 반환 형식의 인수 목록을 확인할 수 있도록 하려면 올바른 대리자 형식으로 캐스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-131">You will have to cast it to the correct delegate type to have any compile-time tools check the argument list of return type.</span></span>

## <a name="execution-and-lifetimes"></a><span data-ttu-id="d8cc3-132">실행 및 수명</span><span class="sxs-lookup"><span data-stu-id="d8cc3-132">Execution and Lifetimes</span></span>

<span data-ttu-id="d8cc3-133">`LamdbaExpression.Compile()`을 호출할 때 만든 대리자를 호출하여 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-133">You execute the code by invoking the delegate created when you called `LamdbaExpression.Compile()`.</span></span> <span data-ttu-id="d8cc3-134">위의 `add.Compile()`이 대리자를 반환하는 위치에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-134">You can see this above where `add.Compile()` returns a delegate.</span></span> <span data-ttu-id="d8cc3-135">해당 대리자를 호출하고 `func()`를 호출하면 코드가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-135">Invoking that delegate, by calling `func()` executes the code.</span></span>

<span data-ttu-id="d8cc3-136">이 대리자는 식 트리의 코드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-136">That delegate represents the code in the expression tree.</span></span> <span data-ttu-id="d8cc3-137">해당 대리자에 대한 핸들을 유지하고 나중에 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-137">You can retain the handle to that delegate and invoke it later.</span></span> <span data-ttu-id="d8cc3-138">식 트리가 나타내는 코드를 실행할 때마다 식 트리를 컴파일할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-138">You don't need to compile the expression tree each time you want to execute the code it represents.</span></span> <span data-ttu-id="d8cc3-139">식 트리는 변경할 수 없으며 나중에 동일한 식 트리를 컴파일하면 동일한 코드를 실행하는 대리자가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-139">(Remember that expression trees are immutable, and compiling the same expression tree later will create a delegate that executes the same code.)</span></span>

<span data-ttu-id="d8cc3-140">필요 없는 컴파일 호출을 방지하여 성능을 향상시키려면 보다 정교한 캐싱 메커니즘을 만들려고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-140">I will caution you against trying to create any more sophisticated caching mechanisms to increase performance by avoiding unnecessary compile calls.</span></span> <span data-ttu-id="d8cc3-141">임의의 식 트리 두 개를 비교하여 동일한 알고리즘을 나타내는지 확인하는 경우에도 실행하는 데 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-141">Comparing two arbitrary expression trees to determine if they represent the same algorithm will also be time consuming to execute.</span></span> <span data-ttu-id="d8cc3-142">`LambdaExpression.Compile()`의 추가 호출을 방지하여 절약한 계산 시간이 동일한 실행 코드에서 서로 다른 두 식 트리 결과를 확인하는 코드 실행 시간을 초과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-142">You'll likely find that the compute time you save avoiding any extra calls to `LambdaExpression.Compile()` will be more than consumed by the time executing code that determines of two different expression trees result in the same executable code.</span></span>

## <a name="caveats"></a><span data-ttu-id="d8cc3-143">주의 사항</span><span class="sxs-lookup"><span data-stu-id="d8cc3-143">Caveats</span></span>

<span data-ttu-id="d8cc3-144">람다 식을 대리자로 컴파일하고 해당 대리자를 호출하는 것은 식 트리로 수행할 수 있는 가장 간단한 작업 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-144">Compiling a lambda expression to a delegate and invoking that delegate is one of the simplest operations you can perform with an expression tree.</span></span> <span data-ttu-id="d8cc3-145">그러나 이 간단한 작업에서도 주의해야 할 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-145">However, even with this simple operation, there are caveats you must be aware of.</span></span> 

<span data-ttu-id="d8cc3-146">람다 식은 식에서 참조되는 모든 지역 변수에 대해 클로저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-146">Lambda Expressions create closures over any local variables that are referenced in the expression.</span></span> <span data-ttu-id="d8cc3-147">대리자의 일부가 되는 모든 변수는 `Compile`을 호출하는 위치 및 결과 대리자를 실행할 때 사용할 수 있도록 보장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-147">You must guarantee that any variables that would be part of the delegate are usable at the location where you call `Compile`, and when you execute the resulting delegate.</span></span>

<span data-ttu-id="d8cc3-148">일반적으로 컴파일러는 이렇게 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-148">In general, the compiler will ensure that this is true.</span></span> <span data-ttu-id="d8cc3-149">그러나 식이 `IDisposable`을 구현하는 변수에 액세스하는 경우 코드는 식 트리에서 보유한 개체를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-149">However, if your expression accesses a variable that implements `IDisposable`, it's possible that your code might dispose of the object while it is still held by the expression tree.</span></span>

<span data-ttu-id="d8cc3-150">예를 들어 다음 코드는 `int`가 `IDisposable`을 구현하지 않기 때문에 제대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-150">For example, this code works fine, because `int` does not implement `IDisposable`:</span></span>

```csharp
private static Func<int, int> CreateBoundFunc()
{
    var constant = 5; // constant is captured by the expression tree
    Expression<Func<int, int>> expression = (b) => constant + b;
    var rVal = expression.Compile();
    return rVal;
}
```

<span data-ttu-id="d8cc3-151">대리자가 지역 변수 `constant`에 대한 참조를 캡처했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-151">The delegate has captured a reference to the local variable `constant`.</span></span>
<span data-ttu-id="d8cc3-152">해당 변수는 나중에 `CreateBoundFunc`에서 반환한 함수가 실행될 때 언제든지 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-152">That variable is accessed at any time later, when the function returned by `CreateBoundFunc` executes.</span></span>

<span data-ttu-id="d8cc3-153">그러나 `IDisposable`을 구현하는 다음(다소 인위적임) 클래스를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-153">However, consider this (rather contrived) class that implements `IDisposable`:</span></span>

```csharp
public class Resource : IDisposable
{
    private bool isDisposed = false;
    public int Argument
    {
        get
        {
            if (!isDisposed)
                return 5;
            else throw new ObjectDisposedException("Resource");
        }
    }

    public void Dispose()
    {
        isDisposed = true;
    }
}
```

<span data-ttu-id="d8cc3-154">아래와 같이 식에서 사용하는 경우 `Resource.Argument` 속성에서 참조하는 코드를 실행하면 `ObjectDisposedException`이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-154">If you use it in an expression as shown below, you'll get an `ObjectDisposedException` when you execute the code referenced by the `Resource.Argument` property:</span></span>

```csharp
private static Func<int, int> CreateBoundResource()
{
    using (var constant = new Resource()) // constant is captured by the expression tree
    {
        Expression<Func<int, int>> expression = (b) => constant.Argument + b;
        var rVal = expression.Compile();
        return rVal;
    }
}
```

<span data-ttu-id="d8cc3-155">이 메서드에서 반환된 대리자는 `constant`를 통해 닫히고 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-155">The delegate returned from this method has closed over the `constant` object, which has been disposed of.</span></span> <span data-ttu-id="d8cc3-156">이 대리자는 `using` 문에서 선언되었기 때문에 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-156">(It's been disposed, because it was declared in a `using` statement.)</span></span> 

<span data-ttu-id="d8cc3-157">이제 이 메서드에서 반환된 대리자를 실행하면 실행 시점에 `ObjecctDisposedException`이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-157">Now, when you execute the delegate returned from this method, you'll have a `ObjecctDisposedException` thrown at the point of execution.</span></span>

<span data-ttu-id="d8cc3-158">컴파일 시간 구문을 나타내는 런타임 오류가 발생하면 이상하게 보일 수 있지만 식 트리를 사용하면 이런 환경이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-158">It does seem strange to have a runtime error representing a compile-time construct, but that's the world we enter when we work with expression trees.</span></span>

<span data-ttu-id="d8cc3-159">이 문제에는 많은 순열이 있으므로 이 문제를 방지하는 일반적인 지침을 제공하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-159">There are a lot of permutations of this problem, so it's hard to offer general guidance to avoid it.</span></span> <span data-ttu-id="d8cc3-160">식을 정의하는 경우 지역 변수에 액세스할 때 주의해야 하며 공용 API에서 반환할 수 있는 식 트리를 만드는 경우 현재 개체(`this`로 표시됨)의 상태에 액세스할 때도 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-160">Be careful about accessing local variables when defining expressions, and be careful about accessing state in the current object (represented by `this`) when creating an expression tree that can be returned by a public API.</span></span>

<span data-ttu-id="d8cc3-161">식의 코드는 다른 어셈블리의 메서드나 속성을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-161">The code in your expression may reference methods or properties in other assemblies.</span></span> <span data-ttu-id="d8cc3-162">해당 어셈블리는 식을 정의할 때, 식을 컴파일할 때 및 결과 대리자를 호출할 때 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-162">That assembly must be accessible when the expression is defined, and when it is compiled, and when the resulting delegate is invoked.</span></span> <span data-ttu-id="d8cc3-163">어셈블리가 없는 경우 `ReferencedAssemblyNotFoundException`이 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-163">You'll be met with a `ReferencedAssemblyNotFoundException` in cases where it is not present.</span></span>

## <a name="summary"></a><span data-ttu-id="d8cc3-164">요약</span><span class="sxs-lookup"><span data-stu-id="d8cc3-164">Summary</span></span>

<span data-ttu-id="d8cc3-165">람다 식을 나타내는 식 트리를 컴파일하면 실행할 수 있는 대리자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-165">Expression Trees that represent lambda expressions can be compiled to create a delegate that you can execute.</span></span> <span data-ttu-id="d8cc3-166">그러면 식 트리로 표시되는 코드를 실행하는 메커니즘이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-166">This provides one mechanism to execute the code represented by an expression tree.</span></span>

<span data-ttu-id="d8cc3-167">식 트리는 생성되는 특정 구문에 대해 실행되는 코드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-167">The Expression Tree does represent the code that would execute for any given construct you create.</span></span> <span data-ttu-id="d8cc3-168">코드를 컴파일하고 실행하는 환경이 식을 만드는 환경과 일치하는 경우 모든 작업이 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-168">As long as the environment where you compile and execute the code matches the environment where you create the expression, everything works as expected.</span></span> <span data-ttu-id="d8cc3-169">그렇지 않을 경우 오류를 예측할 수 있으며 식 트리를 사용하여 코드를 처음 테스트할 때 catch됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8cc3-169">When that doesn't happen, the errors are very predictable, and they will be caught in your first tests of any code using the expression trees.</span></span>

[<span data-ttu-id="d8cc3-170">다음 -- 식 해석</span><span class="sxs-lookup"><span data-stu-id="d8cc3-170">Next -- Interpreting Expressions</span></span>](expression-trees-interpreting.md)
