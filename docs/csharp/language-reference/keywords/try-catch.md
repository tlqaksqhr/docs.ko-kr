---
title: "try-catch(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
caps.latest.revision: "45"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 753beb554796ad0aa2c5e15c715240453de9a3e1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="try-catch-c-reference"></a><span data-ttu-id="87b1a-102">try-catch(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="87b1a-102">try-catch (C# Reference)</span></span>
<span data-ttu-id="87b1a-103">try-catch 문은 `try` 블록에 이어 서로 다른 예외에 대한 처리기를 지정하는 하나 이상의 `catch` 절로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-103">The try-catch statement consists of a `try` block followed by one or more `catch` clauses, which specify handlers for different exceptions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87b1a-104">주의</span><span class="sxs-lookup"><span data-stu-id="87b1a-104">Remarks</span></span>  
 <span data-ttu-id="87b1a-105">예외가 throw되면 CLR(공용 언어 런타임)에서는 이 예외를 처리하는 `catch` 문을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-105">When an exception is thrown, the common language runtime (CLR) looks for the `catch` statement that handles this exception.</span></span> <span data-ttu-id="87b1a-106">현재 실행 중인 메서드에 `catch` 블록이 포함되지 않으면 CLR에서는 현재 메서드를 호출한 메서드 등에서 호출 스택까지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-106">If the currently executing method does not contain such a `catch` block, the CLR looks at the method that called the current method, and so on up the call stack.</span></span> <span data-ttu-id="87b1a-107">`catch` 블록을 찾을 수 없으면 CLR에서는 처리되지 않은 예외 메시지를 사용자에게 표시하고 프로그램의 예외를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-107">If no `catch` block is found, then the CLR displays an unhandled exception message to the user and stops execution of the program.</span></span>  
  
 <span data-ttu-id="87b1a-108">`try` 블록에는 예외를 가져올 수 있는 보호된 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-108">The `try` block contains the guarded code that may cause the exception.</span></span> <span data-ttu-id="87b1a-109">블록은 예외가 throw되거나 성공적으로 완료될 때까지 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-109">The block is executed until an exception is thrown or it is completed successfully.</span></span> <span data-ttu-id="87b1a-110">예를 들어 `null` 개체를 캐스팅하는 다음 시도에서 <xref:System.NullReferenceException> 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-110">For example, the following attempt to cast a `null` object raises the <xref:System.NullReferenceException> exception:</span></span>  
  
```csharp  
object o2 = null;  
try  
{  
    int i2 = (int)o2;   // Error  
}  
```  
  
 <span data-ttu-id="87b1a-111">`catch` 절은 예외 형식을 catch하는 인수 없이 사용할 수 있지만 이 사용은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-111">Although the `catch` clause can be used without arguments to catch any type of exception, this usage is not recommended.</span></span> <span data-ttu-id="87b1a-112">일반적으로 복구하는 방법을 알고 있는 예외만 catch해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-112">In general, you should only catch those exceptions that you know how to recover from.</span></span> <span data-ttu-id="87b1a-113">따라서 항상 <xref:System.Exception?displayProperty=nameWithType>에서 파생된 개체 인수를 지정해야 합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-113">Therefore, you should always specify an object argument derived from <xref:System.Exception?displayProperty=nameWithType> For example:</span></span>  
  
```csharp  
catch (InvalidCastException e)   
{  
}  
```  
  
 <span data-ttu-id="87b1a-114">같은 try-catch 문에서 특정 `catch` 절을 두 개 이상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-114">It is possible to use more than one specific `catch` clause in the same try-catch statement.</span></span> <span data-ttu-id="87b1a-115">이 경우 `catch` 절은 순서대로 검사되므로 `catch` 절의 순서가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-115">In this case, the order of the `catch` clauses is important because the `catch` clauses are examined in order.</span></span> <span data-ttu-id="87b1a-116">더 구체적인 예외를 덜 구체적인 예외보다 먼저 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-116">Catch the more specific exceptions before the less specific ones.</span></span> <span data-ttu-id="87b1a-117">나중에 나타나는 블록에 도달할 수 없도록 catch 블록 순서를 지정하면 컴파일러에서 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-117">The compiler produces an error if you order your catch blocks so that a later block can never be reached.</span></span>  
  
 <span data-ttu-id="87b1a-118">`catch` 인수를 사용하여 처리할 예외를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-118">Using `catch` arguments is one way to filter for the exceptions you want to handle.</span></span>  <span data-ttu-id="87b1a-119">예외를 추가로 검사하는 조건자 식을 사용하여 예외를 처리할지 결정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-119">You can also use a predicate expression that further examines the exception to decide whether to handle it.</span></span>  <span data-ttu-id="87b1a-120">조건자 식에서 false를 반환하면 처리기 검색이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-120">If the predicate expression returns false, then the search for a handler continues.</span></span>  
  
```csharp  
catch (ArgumentException e) when (e.ParamName == "…")  
{  
}  
```  
  
 <span data-ttu-id="87b1a-121">필터 덕분에 스택이 손상되지 않으므로 예외 필터는 catch하고 다시 throw하는 것이 좋습니다(아래 내용 참조).</span><span class="sxs-lookup"><span data-stu-id="87b1a-121">Exception filters are preferable to catching and rethrowing (explained below) because filters leave the stack unharmed.</span></span>  <span data-ttu-id="87b1a-122">나중에 나타나는 처리기가 스택을 덤프하면 예외가 다시 throw된 마지막 위치가 아니라 예외가 원래 발생한 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-122">If a later handler dumps the stack, you can see where the exception originally came from, rather than just the last place it was rethrown.</span></span>  <span data-ttu-id="87b1a-123">예외 필터 식의 일반적으로 사용법은 로깅입니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-123">A common use of exception filter expressions is logging.</span></span>  <span data-ttu-id="87b1a-124">로그에도 출력되는 항상 false를 반환하는 조건자 함수를 만들 수 있고, 예외를 처리하고 다시 throw할 필요 없이 진행되는 대로 예외를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-124">You can create a predicate function that always returns false that also outputs to a log, you can log exceptions as they go by without having to handle them and rethrow.</span></span>  
  
 <span data-ttu-id="87b1a-125">[throw](../../../csharp/language-reference/keywords/throw.md) 문을 `catch` 블록에서 사용하여 `catch` 문에 의해 catch된 예외를 다시 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-125">A [throw](../../../csharp/language-reference/keywords/throw.md) statement can be used in a `catch` block to re-throw the exception that is caught by the `catch` statement.</span></span> <span data-ttu-id="87b1a-126">다음 예제에서는 <xref:System.IO.IOException> 예외에서 소스 정보를 추출하고 예외를 부모 메서드에 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-126">The following example extracts source information from an <xref:System.IO.IOException> exception, and then throws the exception to the parent method.</span></span>  
  
```csharp  
catch (FileNotFoundException e)  
{  
    // FileNotFoundExceptions are handled here.  
}  
catch (IOException e)  
{  
    // Extract some information from this exception, and then   
    // throw it to the parent method.  
    if (e.Source != null)  
        Console.WriteLine("IOException source: {0}", e.Source);  
    throw;  
}  
```  
  
 <span data-ttu-id="87b1a-127">하나의 예외를 catch하고 다른 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-127">You can catch one exception and throw a different exception.</span></span> <span data-ttu-id="87b1a-128">이 작업을 할 때 다음 예제와 같이 내부 예외로 catch한 예외를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-128">When you do this, specify the exception that you caught as the inner exception, as shown in the following example.</span></span>  
  
```csharp  
catch (InvalidCastException e)   
{  
    // Perform some action here, and then throw a new exception.  
    throw new YourCustomException("Put your error message here.", e);  
}  
```  
  
 <span data-ttu-id="87b1a-129">다음 예제와 같이 지정된 조건이 true이면 예외를 다시 throw할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-129">You can also re-throw an exception when a specified condition is true, as shown in the following example.</span></span>  
  
```csharp  
catch (InvalidCastException e)  
{  
    if (e.Data == null)  
    {  
        throw;  
    }  
    else  
    {  
        // Take some action.  
    }  
 }  
```  
  
 <span data-ttu-id="87b1a-130">`try` 블록 내부에서 선언된 변수만 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-130">From inside a `try` block, initialize only variables that are declared therein.</span></span> <span data-ttu-id="87b1a-131">그렇지 않으면 블록의 예외가 완료되기 전에 다른 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-131">Otherwise, an exception can occur before the execution of the block is completed.</span></span> <span data-ttu-id="87b1a-132">예를 들어 다음 코드 예제에서 `n` 변수는 `try` 블록 내부에서 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-132">For example, in the following code example, the variable `n` is initialized inside the `try` block.</span></span> <span data-ttu-id="87b1a-133">`Write(n)` 문의 `try` 블록 외부에서 이 변수를 사용하려고 하면 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-133">An attempt to use this variable outside the `try` block in the `Write(n)` statement will generate a compiler error.</span></span>  
  
```csharp  
static void Main()   
{  
    int n;  
    try   
    {  
        // Do not initialize this variable here.  
        n = 123;  
    }  
    catch  
    {  
    }  
    // Error: Use of unassigned local variable 'n'.  
    Console.Write(n);  
}  
```  
  
 <span data-ttu-id="87b1a-134">catch에 대한 자세한 내용은 [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87b1a-134">For more information about catch, see [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span></span>  
  
## <a name="exceptions-in-async-methods"></a><span data-ttu-id="87b1a-135">비동기 메서드의 예외</span><span class="sxs-lookup"><span data-stu-id="87b1a-135">Exceptions in Async Methods</span></span>  
 <span data-ttu-id="87b1a-136">비동기 메서드는 [async](../../../csharp/language-reference/keywords/async.md) 한정자를 통해 표시되고 대개 하나 이상의 await 식 및 문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-136">An async method is marked  by an  [async](../../../csharp/language-reference/keywords/async.md) modifier and usually contains one or more await expressions or statements.</span></span> <span data-ttu-id="87b1a-137">await 식은 [await](../../../csharp/language-reference/keywords/await.md) 연산자를 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-137">An await expression applies the [await](../../../csharp/language-reference/keywords/await.md) operator to a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="87b1a-138">컨트롤이 비동기 메서드의 `await`에 도달하면 대기 중인 작업이 완료될 때까지 메서드의 진행이 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-138">When control reaches an `await` in the async method, progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="87b1a-139">작업이 완료되면 메서드가 실행이 다시 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-139">When the task  is complete, execution can resume in the method.</span></span> <span data-ttu-id="87b1a-140">자세한 내용은 [async 및 await를 사용한 비동기 프로그래밍](../../../csharp/programming-guide/concepts/async/index.md) 및 [비동기 프로그램의 제어 흐름](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87b1a-140">For more information, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md) and [Control Flow in Async Programs](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
 <span data-ttu-id="87b1a-141">`await`가 적용되는 완료된 작업은 작업을 반환하는 메서드의 처리되지 않은 예외로 인해 오류 상태에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-141">The completed task to which `await` is applied might be in a faulted state because of an unhandled exception in the method that returns the task.</span></span> <span data-ttu-id="87b1a-142">작업을 기다리면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-142">Awaiting the task throws an exception.</span></span> <span data-ttu-id="87b1a-143">작업을 반환하는 비동기 프로세스가 취소되면 작업이 취소됨 상태로 종료될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-143">A task can also end up in a canceled state if the asynchronous process that returns it is canceled.</span></span> <span data-ttu-id="87b1a-144">취소된 작업을 기다리면 `OperationCanceledException`이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-144">Awaiting a canceled task throws  an `OperationCanceledException`.</span></span> <span data-ttu-id="87b1a-145">비동기 프로세스를 취소하는 방법에 대한 자세한 내용은 [Async 응용 프로그램 미세 조정](../../programming-guide/concepts/async/fine-tuning-your-async-application.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87b1a-145">For more information about how to cancel an asynchronous process, see [Fine-Tuning Your Async Application](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>  
  
 <span data-ttu-id="87b1a-146">예외를 catch하려면 `try` 블록에서 작업을 기다리고 연결된 `catch` 블록에서 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-146">To catch the exception, await the task in a `try` block, and catch the exception in the associated `catch` block.</span></span> <span data-ttu-id="87b1a-147">예제에 대해서는 "예제" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87b1a-147">For an example, see the "Example" section.</span></span>  
  
 <span data-ttu-id="87b1a-148">대기 중인 비동기 메서드에서 여러 예외가 발생했기 때문에 작업이 오류 상태에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-148">A task can be in a faulted state because multiple exceptions occurred in the awaited async method.</span></span> <span data-ttu-id="87b1a-149">예를 들어 작업은 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 호출의 결과일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-149">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="87b1a-150">작업을 기다릴 때 예외 중 하나만 catch되고 catch될 예외를 예상할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-150">When you await such a task, only one of the exceptions is caught, and you can't predict which exception will be caught.</span></span> <span data-ttu-id="87b1a-151">예제에 대해서는 "예제" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87b1a-151">For an example, see the "Example" section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87b1a-152">예제</span><span class="sxs-lookup"><span data-stu-id="87b1a-152">Example</span></span>  
 <span data-ttu-id="87b1a-153">다음 예제에서 `try` 블록에는 예외를 가져올 수 있는 `ProcessString` 메서드에 대한 호출이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-153">In the following example, the `try` block contains a call to the `ProcessString` method that may cause an exception.</span></span> <span data-ttu-id="87b1a-154">`catch` 절에는 화면에 메시지만 표시하는 예외 처리기가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-154">The `catch` clause contains the exception handler that just displays a message on the screen.</span></span> <span data-ttu-id="87b1a-155">`throw` 문이 `MyMethod` 내부에서 호출되면 시스템에서는 `catch` 문을 검색하고 메시지 `Exception caught`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-155">When the `throw` statement is called from inside `MyMethod`, the system looks for the `catch` statement and displays the message `Exception caught`.</span></span>  
  
 [!code-csharp[csrefKeywordsExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="87b1a-156">예제</span><span class="sxs-lookup"><span data-stu-id="87b1a-156">Example</span></span>  
 <span data-ttu-id="87b1a-157">다음 예제에서는 두 catch 블록이 사용되고 먼저 나오는 가장 구체적인 예외가 catch됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-157">In the following example, two catch blocks are used, and the most specific exception, which comes first, is caught.</span></span>  
  
 <span data-ttu-id="87b1a-158">가장 덜 구체적인 예외를 catch하려면 `ProcessString`의 throw 문을 `throw new Exception()` 문으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-158">To catch the least specific exception, you can replace the throw statement in `ProcessString` with the following statement: `throw new Exception()`.</span></span>  
  
 <span data-ttu-id="87b1a-159">가장 덜 구체적인 catch 블록을 예제에 첫 번째로 배치하면 다음 오류 메시지가 표시됩니다. `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span><span class="sxs-lookup"><span data-stu-id="87b1a-159">If you place the least-specific catch block first in the example, the following  error message appears: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span></span>  
  
 [!code-csharp[csrefKeywordsExceptions#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="87b1a-160">예제</span><span class="sxs-lookup"><span data-stu-id="87b1a-160">Example</span></span>  
 <span data-ttu-id="87b1a-161">다음 예제에서는 비동기 메서드에 대한 예외 처리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-161">The following example illustrates exception handling for async methods.</span></span> <span data-ttu-id="87b1a-162">비동기 작업에서 throw하는 예외를 catch하려면 `try` 블록에 `await` 식을 배치하고 `catch` 블록에서 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-162">To catch an exception that an async task throws, place the `await` expression in a `try` block, and catch the exception in a `catch` block.</span></span>  
  
 <span data-ttu-id="87b1a-163">예제에서 `throw new Exception` 줄의 주석 처리를 제거하여 예외 처리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-163">Uncomment the `throw new Exception` line in the example to demonstrate exception handling.</span></span> <span data-ttu-id="87b1a-164">작업의 `IsFaulted` 속성이 `True`로 설정되고, 작업의 `Exception.InnerException` 속성이 예외로 설정되고, 예외가 `catch` 블록에서 catch됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-164">The task's `IsFaulted` property is set to `True`, the task's `Exception.InnerException` property is set to the exception, and the exception is caught in the `catch` block.</span></span>  
  
 <span data-ttu-id="87b1a-165">`throw new OperationCancelledException` 줄의 주석 처리를 제거하여 비동기 프로세스를 취소할 수 있을 때 발생하는 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-165">Uncomment the `throw new OperationCancelledException` line to demonstrate what happens when you cancel an asynchronous process.</span></span> <span data-ttu-id="87b1a-166">작업의 `IsCanceled` 속성이 `true`로 설정되고, 예외가 `catch` 블록에서 catch됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-166">The task's `IsCanceled` property is set to `true`, and the exception is caught in the `catch` block.</span></span> <span data-ttu-id="87b1a-167">이 예제에 적용되지 않는 몇몇 조건에서는 작업의 `IsFaulted` 속성이 `true`로 설정되고 `IsCanceled`가 `false`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-167">Under some conditions that don't apply to this example, the task's `IsFaulted` property is set to `true` and `IsCanceled` is set to `false`.</span></span>  
  
 [!code-csharp[csAsyncExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="87b1a-168">예제</span><span class="sxs-lookup"><span data-stu-id="87b1a-168">Example</span></span>  
 <span data-ttu-id="87b1a-169">다음 예제에서는 여러 작업에서 여러 예외가 발생할 수 있는 경우 예외 처리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-169">The following example illustrates exception handling where multiple tasks can result in multiple exceptions.</span></span> <span data-ttu-id="87b1a-170">`try` 블록은 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>에 대한 호출에서 반환된 작업을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-170">The `try` block awaits the task that's returned by a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="87b1a-171">WhenAll이 적용된 작업 세 개가 완료되면 작업이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-171">The task is complete when the three tasks to which WhenAll is applied are complete.</span></span>  
  
 <span data-ttu-id="87b1a-172">세 작업에서 각각 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-172">Each of the three tasks causes an exception.</span></span> <span data-ttu-id="87b1a-173">`catch` 블록은 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>에서 반환된 작업의 `Exception.InnerExceptions` 속성에 있는 예외를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="87b1a-173">The `catch` block iterates through the exceptions, which are found in the `Exception.InnerExceptions` property of the task that was returned by <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[csAsyncExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="87b1a-174">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="87b1a-174">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="87b1a-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87b1a-175">See Also</span></span>  
 [<span data-ttu-id="87b1a-176">C# 참조</span><span class="sxs-lookup"><span data-stu-id="87b1a-176">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="87b1a-177">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="87b1a-177">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="87b1a-178">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="87b1a-178">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="87b1a-179">try, throw 및 catch 문(C++)</span><span class="sxs-lookup"><span data-stu-id="87b1a-179">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)  
 [<span data-ttu-id="87b1a-180">예외 처리 문</span><span class="sxs-lookup"><span data-stu-id="87b1a-180">Exception Handling Statements</span></span>](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
 [<span data-ttu-id="87b1a-181">throw</span><span class="sxs-lookup"><span data-stu-id="87b1a-181">throw</span></span>](../../../csharp/language-reference/keywords/throw.md)  
 [<span data-ttu-id="87b1a-182">try-finally</span><span class="sxs-lookup"><span data-stu-id="87b1a-182">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)  
 [<span data-ttu-id="87b1a-183">방법: 명시적으로 예외 Throw</span><span class="sxs-lookup"><span data-stu-id="87b1a-183">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
