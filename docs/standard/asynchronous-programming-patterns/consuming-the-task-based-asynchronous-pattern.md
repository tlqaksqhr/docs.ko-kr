---
title: "작업 기반 비동기 패턴 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90b2a36f0e6bf06b0fefe2191d5b17c9c07d1588
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="consuming-the-task-based-asynchronous-pattern"></a><span data-ttu-id="208a9-102">작업 기반 비동기 패턴 사용</span><span class="sxs-lookup"><span data-stu-id="208a9-102">Consuming the Task-based Asynchronous Pattern</span></span>
<span data-ttu-id="208a9-103">TAP(작업 기반 비동기 패턴)을 사용하여 비동기 작업을 수행할 경우 콜백을 사용하면 차단 없이 대기를 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-103">When you use the Task-based Asynchronous Pattern (TAP) to work with asynchronous operations, you can use callbacks to achieve waiting without blocking.</span></span>  <span data-ttu-id="208a9-104">작업의 경우 이렇게 메서드를 통해 같은 <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-104">For tasks, this is achieved through methods such as <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="208a9-105">언어 기반 비동기 지원은 정상적인 제어 흐름 내에서 비동기 작업이 대기할 수 있도록 함으로써 콜백 숨김을 지원하고, 컴파일러에서 생성된 코드는 이와 동일한 API 수준 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-105">Language-based asynchronous support hides callbacks by allowing asynchronous operations to be awaited within normal control flow, and compiler-generated code provides this same API-level support.</span></span>  
  
## <a name="suspending-execution-with-await"></a><span data-ttu-id="208a9-106">Await로 실행 일시 중지</span><span class="sxs-lookup"><span data-stu-id="208a9-106">Suspending Execution with Await</span></span>  
 <span data-ttu-id="208a9-107">부터는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 사용할 수 있습니다는 [await](~/docs/csharp/language-reference/keywords/await.md) C# 키워드 및 [Await 연산자](~/docs/visual-basic/language-reference/operators/await-operator.md) 를 비동기적으로 기다리는 Visual Basic의 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-107">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], you can use the [await](~/docs/csharp/language-reference/keywords/await.md) keyword in C# and the [Await Operator](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic to asynchronously await <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> objects.</span></span> <span data-ttu-id="208a9-108">대기 하는 경우는 <xref:System.Threading.Tasks.Task>, `await` 식이 형식이 `void`합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-108">When you're awaiting a <xref:System.Threading.Tasks.Task>, the `await` expression is of type `void`.</span></span> <span data-ttu-id="208a9-109">대기 하는 경우는 <xref:System.Threading.Tasks.Task%601>, `await` 식이 형식이 `TResult`합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-109">When you're awaiting a <xref:System.Threading.Tasks.Task%601>, the `await` expression is of type `TResult`.</span></span> <span data-ttu-id="208a9-110">`await` 식은 비동기 메서드의 본문 내에서 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-110">An `await` expression must occur inside the body of an asynchronous method.</span></span> <span data-ttu-id="208a9-111">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]의 C# 및 Visual Basic 언어 지원에 대한 자세한 내용은 C# 및 Visual Basic 언어 사양을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="208a9-111">For more information about C# and Visual Basic language support in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], see the C# and Visual Basic language specifications.</span></span>  
  
 <span data-ttu-id="208a9-112">내부적으로 await 기능은 연속을 사용해서 작업에 콜백을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-112">Under the covers, the await functionality installs a callback on the task by using a continuation.</span></span>  <span data-ttu-id="208a9-113">이 콜백은 일시 중지 시점에서 비동기 메서드를 재개합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-113">This callback resumes the asynchronous method at the point of suspension.</span></span> <span data-ttu-id="208a9-114">대기 중인된 작업이 완료 되었으며 경우, 비동기 메서드가 다시 시작 되는 <xref:System.Threading.Tasks.Task%601>, 해당 `TResult` 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-114">When the asynchronous method is resumed, if the awaited operation completed successfully and was a <xref:System.Threading.Tasks.Task%601>, its `TResult` is returned.</span></span>  <span data-ttu-id="208a9-115">경우는 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601> 에 끝났고 하 던는 <xref:System.Threading.Tasks.TaskStatus.Canceled> 상태는 <xref:System.OperationCanceledException> 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-115">If the <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> that was awaited ended in the <xref:System.Threading.Tasks.TaskStatus.Canceled> state, an <xref:System.OperationCanceledException> exception is thrown.</span></span>  <span data-ttu-id="208a9-116">경우는 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601> 에 끝났고 하 던는 <xref:System.Threading.Tasks.TaskStatus.Faulted> 상태 이면 오류를 일으킨 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-116">If the <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> that was awaited ended in the <xref:System.Threading.Tasks.TaskStatus.Faulted> state, the exception that caused it to fault is thrown.</span></span> <span data-ttu-id="208a9-117">`Task`에서는 여러 식의 결과로 오류가 발생할 수 있지만 이러한 예외 중 하나만 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-117">A `Task` can fault as a result of multiple exceptions, but only one of these exceptions is propagated.</span></span> <span data-ttu-id="208a9-118">그러나는 <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> 속성에서 반환 된 <xref:System.AggregateException> 모든 오류를 포함 하는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-118">However, the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property returns an <xref:System.AggregateException> exception that contains all the errors.</span></span>  
  
 <span data-ttu-id="208a9-119">경우 동기화 컨텍스트 (<xref:System.Threading.SynchronizationContext> 개체) 실행 중이 던 비동기 메서드가 일시 중단 시 스레드에 연결 된 (경우에 예를 들어는 <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> 속성은 `null`), 그에 다시 시작 비동기 메서드 컨텍스트를 사용 하 여 동기화 컨텍스트를 동일한 <xref:System.Threading.SynchronizationContext.Post%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="208a9-119">If a synchronization context (<xref:System.Threading.SynchronizationContext> object) is associated with the thread that was executing the asynchronous method at the time of suspension (for example, if the <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> property is not `null`), the asynchronous method resumes on that same synchronization context by using the context’s <xref:System.Threading.SynchronizationContext.Post%2A> method.</span></span> <span data-ttu-id="208a9-120">작업 스케줄러에 의존 하므로 이렇게 하지 않으면 (<xref:System.Threading.Tasks.TaskScheduler> 개체)를 일시 중단 시 현재이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-120">Otherwise, it relies on the task scheduler (<xref:System.Threading.Tasks.TaskScheduler> object) that was current at the time of suspension.</span></span> <span data-ttu-id="208a9-121">일반적으로이 기본 작업 스케줄러 (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), 스레드 풀을 대상으로입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-121">Typically, this is the default task scheduler (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), which targets the thread pool.</span></span> <span data-ttu-id="208a9-122">이 작업 스케줄러는 대기 중이던 비동기 작업이 완료된 위치에서 다시 시작되어야 하는지 또는 재개를 예약해야 하는지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-122">This task scheduler determines whether the awaited asynchronous operation should resume where it completed or whether the resumption should be scheduled.</span></span> <span data-ttu-id="208a9-123">기본 스케줄러는 일반적으로 대기 중이던 작업이 완료된 스레드에서 실행이 계속되도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-123">The default scheduler typically allows the continuation to run on the thread that the awaited operation completed.</span></span>  
  
 <span data-ttu-id="208a9-124">비동기 메서드가 호출되면 아직 완료되지 않은 대기 가능 인스턴스에 대한 첫 번째 대기 식이 나올 때까지, 즉 호출이 호출자에게 반환될 때까지 함수 본문을 동기적으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-124">When an asynchronous method is called, it synchronously executes the body of the function up until the first await expression on an awaitable instance that has not yet completed, at which point the invocation returns to the caller.</span></span> <span data-ttu-id="208a9-125">에서는 비동기 메서드에서 반환 하지 않는 경우 `void`, <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601> 진행 중인 계산을 나타내는 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-125">If the asynchronous method does not return `void`, a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> object is returned to represent the ongoing computation.</span></span> <span data-ttu-id="208a9-126">Void가 아닌 비동기 메서드의 반환 문이 또는 메서드 본문의 끝에 도달 하는 경우 작업 완료에 <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> 최종 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-126">In a non-void asynchronous method, if a return statement is encountered or the end of the method body is reached, the task is completed in the <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> final state.</span></span> <span data-ttu-id="208a9-127">작업에 종료 처리 되지 않은 예외로 인해 컨트롤을 비동기 메서드의 본문을 벗어날 경우는 <xref:System.Threading.Tasks.TaskStatus.Faulted> 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-127">If an unhandled exception causes control to leave the body of the asynchronous method, the task ends in the <xref:System.Threading.Tasks.TaskStatus.Faulted> state.</span></span> <span data-ttu-id="208a9-128">해당 예외는 경우는 <xref:System.OperationCanceledException>, 끝나는 대신 작업의 <xref:System.Threading.Tasks.TaskStatus.Canceled> 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-128">If that exception is an <xref:System.OperationCanceledException>, the task instead ends in the <xref:System.Threading.Tasks.TaskStatus.Canceled> state.</span></span> <span data-ttu-id="208a9-129">이러한 방식으로 결과 또는 예외가 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-129">In this manner, the result or exception is eventually published.</span></span>  
  
 <span data-ttu-id="208a9-130">이 동작은 몇 가지 중요한 형태로 변형되어 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-130">There are several important variations of this behavior.</span></span>  <span data-ttu-id="208a9-131">성능상의 이유로 작업이 대기될 때 이미 거의 완료되었으면 제어가 일시 중단되지 않고 함수는 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-131">For performance reasons, if a task has already completed by the time the task is awaited, control is not yielded, and the function continues to execute.</span></span>  <span data-ttu-id="208a9-132">또한 원래 컨텍스트로 돌아간다고 해서 항상 원하는 동작을 얻을 수 있는 것은 아니며 변경될 수 있습니다. 이 내용에 대해서는 다음 섹션에서 좀 더 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-132">Additionally, returning to the original context isn't always the desired behavior and can be changed; this is described in more detail in the next section.</span></span>  
  
### <a name="configuring-suspension-and-resumption-with-yield-and-configureawait"></a><span data-ttu-id="208a9-133">Yield 및 ConfigureAwait를 사용하여 일시 중단 및 재개 구성</span><span class="sxs-lookup"><span data-stu-id="208a9-133">Configuring Suspension and Resumption with Yield and ConfigureAwait</span></span>  
 <span data-ttu-id="208a9-134">몇 가지 메서드는 비동기 메서드 실행을 좀 더 강력하게 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-134">Several methods provide more control over an asynchronous method’s execution.</span></span> <span data-ttu-id="208a9-135">예를 들어, 사용할 수는 <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> 메서드를 비동기 메서드로 점을 소개:</span><span class="sxs-lookup"><span data-stu-id="208a9-135">For example, you can use the <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> method to introduce a yield point into the asynchronous method:</span></span>  
  
```csharp  
public class Task : …  
{  
    public static YieldAwaitable Yield();  
    …  
}  
```  
  
 <span data-ttu-id="208a9-136">이 작업은 비동기적으로 원래 컨텍스트에 다시 게시하거나 원래 컨텍스트를 예약하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-136">This is equivalent to asynchronously posting or scheduling back to the current context.</span></span>  
  
```csharp  
Task.Run(async delegate  
{  
    for(int i=0; i<1000000; i++)  
    {  
        await Task.Yield(); // fork the continuation into a separate work item  
        ...  
    }  
});  
```  
  
 <span data-ttu-id="208a9-137">사용할 수도 있습니다는 <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> 메서드를 일시 중단 했다가 비동기 메서드가 보다 효율적으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-137">You can also use the <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> method for better control over suspension and resumption in an asynchronous method.</span></span>  <span data-ttu-id="208a9-138">앞서 언급했듯이 기본적으로 비동기 메서드가 일시 중단되었던 당시의 현재 컨텍스트가 캡처되며 캡처된 해당 컨텍스트는 다시 시작할 때 비동기 메서드의 연속을 호출하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-138">As mentioned previously, by default, the current context is captured at the time an asynchronous  method is suspended, and that captured context is used to invoke the asynchronous  method’s continuation upon resumption.</span></span>  <span data-ttu-id="208a9-139">대부분의 경우에서 사용자가 원하는 정확한 행동이 바로 이것일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-139">In many cases, this is the exact behavior you want.</span></span>  <span data-ttu-id="208a9-140">연속 컨텍스트를 별로 중요하게 생각하지 않을 수도 있고 원래 컨텍스트로의 다시 게시를 피함으로써 더 나은 성능을 얻을 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-140">In other cases, you may not care about the continuation context, and you can achieve better performance by avoiding such posts back to the original context.</span></span>  <span data-ttu-id="208a9-141">이 위해 사용 하 여는 <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> 캡처하고에 컨텍스트를 다시 시작 않고 실행을 계속가 대기 중인 비동기 작업이 완료 하는 경우 await 작업을 알리는 메서드:</span><span class="sxs-lookup"><span data-stu-id="208a9-141">To enable this, use the <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> method to inform the await operation not to capture and resume on the context, but to continue execution wherever the asynchronous operation that was being awaited completed:</span></span>  
  
```csharp  
await someTask.ConfigureAwait(continueOnCapturedContext:false);  
```  
  
## <a name="canceling-an-asynchronous-operation"></a><span data-ttu-id="208a9-142">비동기 작업 취소</span><span class="sxs-lookup"><span data-stu-id="208a9-142">Canceling an Asynchronous Operation</span></span>  
 <span data-ttu-id="208a9-143">부터는 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], 취소를 지원 TAP 메서드는 취소 토큰을 허용 하는 하나 이상의 오버 로드를 제공 (<xref:System.Threading.CancellationToken> 개체).</span><span class="sxs-lookup"><span data-stu-id="208a9-143">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], TAP methods that support cancellation provide at least one overload that accepts a cancellation token (<xref:System.Threading.CancellationToken> object).</span></span>  
  
 <span data-ttu-id="208a9-144">취소 토큰이 취소 토큰 소스를 통해 생성 됩니다 (<xref:System.Threading.CancellationTokenSource> 개체).</span><span class="sxs-lookup"><span data-stu-id="208a9-144">A cancellation token is created through a cancellation token source (<xref:System.Threading.CancellationTokenSource> object).</span></span>  <span data-ttu-id="208a9-145">원본의 <xref:System.Threading.CancellationTokenSource.Token%2A> 신호를 받는 취소 토큰을 반환 하는 속성 때 원본의 <xref:System.Threading.CancellationTokenSource.Cancel%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-145">The source’s <xref:System.Threading.CancellationTokenSource.Token%2A> property returns the cancellation token that will be signaled when the source’s <xref:System.Threading.CancellationTokenSource.Cancel%2A> method is called.</span></span>  <span data-ttu-id="208a9-146">예를 들어 하나의 웹 페이지를 다운로드 하 고 작업을 취소할 수 있게 되기를 원하는 경우 만들면는 <xref:System.Threading.CancellationTokenSource> 개체 하 고, TAP 메서드를 해당 토큰이 전달,는 소스를 호출 하 <xref:System.Threading.CancellationTokenSource.Cancel%2A> 작업을 취소 준비가 되었습니다. 메서드:</span><span class="sxs-lookup"><span data-stu-id="208a9-146">For example, if you want to download a single webpage and you want to be able to cancel the operation, you create a <xref:System.Threading.CancellationTokenSource> object, pass its token to the TAP method, and then call the source’s <xref:System.Threading.CancellationTokenSource.Cancel%2A> method when you're ready to cancel the operation:</span></span>  
  
```csharp  
var cts = new CancellationTokenSource();  
string result = await DownloadStringAsync(url, cts.Token);  
… // at some point later, potentially on another thread  
cts.Cancel();  
```  
  
 <span data-ttu-id="208a9-147">여러 비동기 호출을 취소하려면 모든 호출에 동일한 토큰을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-147">To cancel multiple asynchronous invocations, you can pass the same token to all invocations:</span></span>  
  
```csharp  
var cts = new CancellationTokenSource();  
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));  
    // at some point later, potentially on another thread  
    …  
    cts.Cancel();  
```  
  
 <span data-ttu-id="208a9-148">또는 작업의 선택적 하위 집합에 동일한 토큰을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-148">Or, you can pass the same token to a selective subset of operations:</span></span>  
  
```csharp  
var cts = new CancellationTokenSource();  
    byte [] data = await DownloadDataAsync(url, cts.Token);  
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);  
    … // at some point later, potentially on another thread  
    cts.Cancel();  
```  
  
 <span data-ttu-id="208a9-149">어떤 스레드에서도 취소 요청이 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-149">Cancellation requests may be initiated from any thread.</span></span>  
  
 <span data-ttu-id="208a9-150">전달할 수는 <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> 취소 요청 되지 했음을 나타내기 위해 취소 토큰을 허용 하는 모든 메서드에 값입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-150">You can pass the <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> value to any method that accepts a cancellation token to indicate that cancellation will never be requested.</span></span>  <span data-ttu-id="208a9-151">이 인해는 <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> 반환할 속성 `false`, 고 호출된 된 메서드가 적절 하 게 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-151">This causes the <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> property to return `false`, and the called method can optimize accordingly.</span></span>  <span data-ttu-id="208a9-152">테스트를 위해 토큰이 이미 취소된 상태 또는 취소 불가능 상태로 시작되어야 하는지를 나타내는 부울 값을 수락하는 생성자를 사용하여 인스턴스화된 미리 취소된 취소 토큰을 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-152">For testing purposes, you can also pass in a pre-canceled cancellation token that is instantiated by using the constructor that accepts a Boolean value to indicate whether the token should start in an already-canceled or not-cancelable state.</span></span>  
  
 <span data-ttu-id="208a9-153">이러한 취소 방법에는 다음과 같은 여러 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-153">This approach to cancellation has several advantages:</span></span>  
  
-   <span data-ttu-id="208a9-154">제한 없는 수의 비동기 및 동기 작업에 동일한 취소 토큰을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-154">You can pass the same cancellation token to any number of asynchronous and synchronous operations.</span></span>  
  
-   <span data-ttu-id="208a9-155">동일한 취소 요청을 제한 없는 수의 수신기에 확산시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-155">The same cancellation request may be proliferated to any number of listeners.</span></span>  
  
-   <span data-ttu-id="208a9-156">비동기 API의 개발자는 취소를 요청할 수 있는지 여부 및 적용되는 시기 등을 완전히 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-156">The developer of the asynchronous API is in complete control of whether cancellation may be requested and when it may take effect.</span></span>  
  
-   <span data-ttu-id="208a9-157">API를 사용하는 코드는 취소 요청이 전파되는 비동기 호출을 선택적으로 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-157">The code that consumes the API may selectively determine the asynchronous invocations that cancellation requests will be propagated to.</span></span>  
  
## <a name="monitoring-progress"></a><span data-ttu-id="208a9-158">진행률 모니터링</span><span class="sxs-lookup"><span data-stu-id="208a9-158">Monitoring Progress</span></span>  
 <span data-ttu-id="208a9-159">일부 비동기 메서드는 비동기 메서드에 전달된 진행률 인터페이스를 통해 진행 상황을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-159">Some asynchronous methods expose progress through a progress interface passed into the asynchronous method.</span></span>  <span data-ttu-id="208a9-160">예를 들어 텍스트 문자열을 비동기적으로 다운로드하고 지금까지 완료된 다운로드의 비율을 포함하는 진행률 업데이트를 야기하는 함수를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="208a9-160">For example, consider a function which asynchronously downloads a string of text, and along the way raises progress updates that include the percentage of the download that has completed thus far.</span></span>  <span data-ttu-id="208a9-161">이러한 메서드는 다음과 같이 WPF(Windows Presentation Foundation) 응용 프로그램에서 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-161">Such a method could be consumed in a Windows Presentation Foundation (WPF) application as follows:</span></span>  
  
```csharp  
private async void btnDownload_Click(object sender, RoutedEventArgs e)    
{  
    btnDownload.IsEnabled = false;  
    try  
    {  
        txtResult.Text = await DownloadStringAsync(txtUrl.Text,   
            new Progress<int>(p => pbDownloadProgress.Value = p));  
    }  
    finally { btnDownload.IsEnabled = true; }  
}  
```  
  
<a name="combinators"></a>   
## <a name="using-the-built-in-task-based-combinators"></a><span data-ttu-id="208a9-162">기본 제공 작업 기반 조합기 사용</span><span class="sxs-lookup"><span data-stu-id="208a9-162">Using the Built-in Task-based Combinators</span></span>  
 <span data-ttu-id="208a9-163"><xref:System.Threading.Tasks> 네임 스페이스는 작성 하 고 작업을 사용 하기 위한 몇 가지 메서드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-163">The <xref:System.Threading.Tasks> namespace includes several methods for composing and working with tasks.</span></span>  
  
### <a name="taskrun"></a><span data-ttu-id="208a9-164">Task.Run</span><span class="sxs-lookup"><span data-stu-id="208a9-164">Task.Run</span></span>  
 <span data-ttu-id="208a9-165"><xref:System.Threading.Tasks.Task> 클래스에 몇 <xref:System.Threading.Tasks.Task.Run%2A> 쉽게 수 있는 메서드를 기준으로 오프 로드는 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601> 예를 들어 스레드 풀에:</span><span class="sxs-lookup"><span data-stu-id="208a9-165">The <xref:System.Threading.Tasks.Task> class includes several <xref:System.Threading.Tasks.Task.Run%2A> methods that let you easily offload work as a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> to the thread pool, for example:</span></span>  
  
```csharp  
public async void button1_Click(object sender, EventArgs e)  
{  
    textBox1.Text = await Task.Run(() =>  
    {  
        // … do compute-bound work here  
        return answer;  
    });  
}  
```  
  
 <span data-ttu-id="208a9-166">이 중 일부를 <xref:System.Threading.Tasks.Task.Run%2A> 메서드 같은 <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> 오버 로드, 하기 위한 줄임 속성으로 존재는 <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="208a9-166">Some of these <xref:System.Threading.Tasks.Task.Run%2A> methods, such as the <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> overload, exist as shorthand for the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> method.</span></span>  <span data-ttu-id="208a9-167">와 같은 다른 overloads <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, 예를 들어 오프 로드 된 작업 내에서 await를 사용 하 여 사용:</span><span class="sxs-lookup"><span data-stu-id="208a9-167">Other overloads, such as <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, enable you to use await within the offloaded work, for example:</span></span>  
  
```csharp  
public async void button1_Click(object sender, EventArgs e)  
{  
    pictureBox1.Image = await Task.Run(async() =>  
    {  
        using(Bitmap bmp1 = await DownloadFirstImageAsync())  
        using(Bitmap bmp2 = await DownloadSecondImageAsync())  
        return Mashup(bmp1, bmp2);  
    });  
}  
```  
  
 <span data-ttu-id="208a9-168">이러한 오버 로드를 사용 하 여 논리적으로 동일는 <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> 메서드와 함께 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 작업 병렬 라이브러리의 확장 메서드.</span><span class="sxs-lookup"><span data-stu-id="208a9-168">Such overloads are logically equivalent to using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> method in conjunction with the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension method in the Task Parallel Library.</span></span>  
  
### <a name="taskfromresult"></a><span data-ttu-id="208a9-169">Task.FromResult</span><span class="sxs-lookup"><span data-stu-id="208a9-169">Task.FromResult</span></span>  
 <span data-ttu-id="208a9-170">사용 하 여 <xref:System.Threading.Tasks.Task.FromResult%2A> 에 적용 되지 않습니다. 작업 반환 메서드에서 반환 될 데이터 사용 가능 하 고 정당한 수 이미 있습니다 시나리오에서 메서드에 필요한는 <xref:System.Threading.Tasks.Task%601>:</span><span class="sxs-lookup"><span data-stu-id="208a9-170">Use the <xref:System.Threading.Tasks.Task.FromResult%2A> method in scenarios where data may already be available and just needs to be returned from a task-returning method lifted into a <xref:System.Threading.Tasks.Task%601>:</span></span>  
  
```csharp  
public Task<int> GetValueAsync(string key)  
{  
    int cachedValue;  
    return TryGetCachedValue(out cachedValue) ?  
        Task.FromResult(cachedValue) :  
        GetValueAsyncInternal();  
}  
  
private async Task<int> GetValueAsyncInternal(string key)  
{  
    …  
}  
```  
  
### <a name="taskwhenall"></a><span data-ttu-id="208a9-171">Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="208a9-171">Task.WhenAll</span></span>  
 <span data-ttu-id="208a9-172">사용 된 <xref:System.Threading.Tasks.Task.WhenAll%2A> 메서드를 비동기적으로 작업으로 표현 되는 여러 개의 비동기 작업에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-172">Use the <xref:System.Threading.Tasks.Task.WhenAll%2A> method to asynchronously wait on multiple asynchronous operations that are represented as tasks.</span></span>  <span data-ttu-id="208a9-173">이 메서드에는 비일반 작업 집합 또는 균일하지 않은 일반 작업 집합을 지원하는 오버로드(예: 여러 void 반환 작업을 비동기적으로 대기하거나 각 값이 다른 형식을 가질 수 있는 여러 값 반환 메서드를 비동기적으로 대기) 및 균일한 일반 작업 집합을 지원하는 오버로드(여러 `TResult` 반환 메서드를 비동기적으로 대기)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-173">The method has multiple overloads that support a set of non-generic tasks or a non-uniform set of generic tasks (for example, asynchronously waiting for multiple void-returning operations, or asynchronously waiting for multiple value-returning methods where each value may have a different type) and to support a uniform set of generic tasks (such as asynchronously waiting for multiple `TResult`-returning methods).</span></span>  
  
 <span data-ttu-id="208a9-174">여러 고객에게 전자 메일 메시지를 전송하려는 경우를 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-174">Let's say you want to send email messages to several customers.</span></span> <span data-ttu-id="208a9-175">한 메시지가 완료될 때까지 기다렸다가 다음 메시지를 전송하지 않도록 메시지 전송을 겹칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-175">You can overlap sending the messages so you're not waiting for one message to complete before sending the next.</span></span> <span data-ttu-id="208a9-176">또한 보내기 작업이 완료될 때와 오류가 발생했는지 여부도 확인할 수 있습니다.또</span><span class="sxs-lookup"><span data-stu-id="208a9-176">You can also find out when the send operations have completed and whether any errors have occurred:</span></span>  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
await Task.WhenAll(asyncOps);  
```  
  
 <span data-ttu-id="208a9-177">이 코드 발생할 수 있지만 전파 예외 수 있게 예외를 명시적으로 처리 하지 않습니다는 `await` 에서 결과 작업에서 <xref:System.Threading.Tasks.Task.WhenAll%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-177">This code doesn't explicitly handle exceptions that may occur, but lets exceptions propagate out of the `await` on the resulting task from <xref:System.Threading.Tasks.Task.WhenAll%2A>.</span></span>  <span data-ttu-id="208a9-178">예외를 처리하려면 다음과 같은 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-178">To handle the exceptions, you can use code such as the following:</span></span>  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
try  
{  
    await Task.WhenAll(asyncOps);  
}  
catch(Exception exc)  
{  
    ...  
}  
```  
  
 <span data-ttu-id="208a9-179">이 경우 비동기 작업이 실패 하면, 모든 예외는에 통합 되도록는 <xref:System.AggregateException> 에 저장 되는 예외는 <xref:System.Threading.Tasks.Task> 에서 반환 되는 <xref:System.Threading.Tasks.Task.WhenAll%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="208a9-179">In this case, if any asynchronous operation fails, all the exceptions will be consolidated in an <xref:System.AggregateException> exception, which is stored in the <xref:System.Threading.Tasks.Task> that is returned from the <xref:System.Threading.Tasks.Task.WhenAll%2A> method.</span></span>  <span data-ttu-id="208a9-180">그러나 이러한 예외 중 하나만 `await` 키워드에 의해 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-180">However, only one of those exceptions is propagated by the `await` keyword.</span></span>  <span data-ttu-id="208a9-181">모든 예외를 검사하려는 경우 앞의 코드를 다음과 같이 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-181">If you want to examine all the exceptions, you can rewrite the previous code as follows:</span></span>  
  
```csharp  
Task [] asyncOps = (from addr in addrs select SendMailAsync(addr)).ToArray();  
try  
{  
    await Task.WhenAll(asyncOps);  
}  
catch(Exception exc)  
{  
    foreach(Task faulted in asyncOps.Where(t => t.IsFaulted))  
    {  
        … // work with faulted and faulted.Exception  
    }  
}  
```  
  
 <span data-ttu-id="208a9-182">웹에서 비동기적으로 여러 파일을 다운로드하는 예를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-182">Let's consider an example of downloading multiple files from the web asynchronously.</span></span>  <span data-ttu-id="208a9-183">이 경우 모든 비동기 작업이 동일한 결과 형식을 가지며 결과에 액세스하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-183">In this case, all the asynchronous operations have homogeneous result types, and it's easy to access the results:</span></span>  
  
```csharp  
string [] pages = await Task.WhenAll(  
    from url in urls select DownloadStringAsync(url));  
```  
  
 <span data-ttu-id="208a9-184">이전의 void 반환 시나리오에서 설명한 것과 동일한 예외 처리 기술을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-184">You can use the same exception-handling techniques we discussed in the previous void-returning scenario:</span></span>  
  
```csharp  
Task [] asyncOps =   
    (from url in urls select DownloadStringAsync(url)).ToArray();  
try  
{  
    string [] pages = await Task.WhenAll(asyncOps);  
    ...  
}  
catch(Exception exc)  
{  
    foreach(Task<string> faulted in asyncOps.Where(t => t.IsFaulted))  
    {  
        … // work with faulted and faulted.Exception  
    }  
}  
```  
  
### <a name="taskwhenany"></a><span data-ttu-id="208a9-185">Task.WhenAny</span><span class="sxs-lookup"><span data-stu-id="208a9-185">Task.WhenAny</span></span>  
 <span data-ttu-id="208a9-186">사용할 수는 <xref:System.Threading.Tasks.Task.WhenAny%2A> 메서드를 비동기적으로 기다리는 여러 비동기 작업 중 하나를 완료 하려면 작업으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-186">You can use the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to asynchronously wait for just one of multiple asynchronous operations represented as tasks to complete.</span></span>  <span data-ttu-id="208a9-187">이 메서드는 다음 네 가지 기본 사용 사례를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-187">This method serves four primary use cases:</span></span>  
  
-   <span data-ttu-id="208a9-188">중복: 작업을 여러 번 수행하고 먼저 완료되는 작업을 선택합니다(예를 들어, 단일의 결과를 생성하는 여러 주식 시세 웹 서비스에 연결하고 가장 빨리 완료되는 결과를 선택).</span><span class="sxs-lookup"><span data-stu-id="208a9-188">Redundancy:  Performing an operation multiple times and selecting the one that completes first (for example, contacting multiple stock quote web services that will produce a single result and selecting the one that completes the fastest).</span></span>  
  
-   <span data-ttu-id="208a9-189">인터리브: 여러 작업을 시작하고 모두 완료해야 하지만 완료되었을 때 작업을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-189">Interleaving:  Launching multiple operations and waiting for all of them to complete, but processing them as they complete.</span></span>  
  
-   <span data-ttu-id="208a9-190">스로틀: 다른 작업이 완료되면 추가 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-190">Throttling:  Allowing additional operations to begin as others complete.</span></span>  <span data-ttu-id="208a9-191">이것은 인터리브 시나리오의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-191">This is an extension of the interleaving scenario.</span></span>  
  
-   <span data-ttu-id="208a9-192">초기 재귀 한도: 예를 들어, 작업 t1으로 표시되는 작업은 다른 작업 t2를 사용하여 <xref:System.Threading.Tasks.Task.WhenAny%2A> 작업에서 그룹화할 수 있으며 <xref:System.Threading.Tasks.Task.WhenAny%2A> 작업에서 대기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-192">Early bailout:  For example, an operation represented by task t1 can be grouped in a <xref:System.Threading.Tasks.Task.WhenAny%2A> task with another task t2, and you can wait on the <xref:System.Threading.Tasks.Task.WhenAny%2A> task.</span></span> <span data-ttu-id="208a9-193">시간 제한 또는 취소 또는 일부 다른 신호를 발생 시키는 작업 t 2를 나타낼 수는 <xref:System.Threading.Tasks.Task.WhenAny%2A> t1 완료 되기 전에 완료할 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-193">Task t2 could represent a time-out, or cancellation, or some other signal that causes the <xref:System.Threading.Tasks.Task.WhenAny%2A> task to complete before t1 completes.</span></span>  
  
#### <a name="redundancy"></a><span data-ttu-id="208a9-194">중복성</span><span class="sxs-lookup"><span data-stu-id="208a9-194">Redundancy</span></span>  
 <span data-ttu-id="208a9-195">주식 구매 여부를 결정하려는 경우를 고려해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-195">Consider a case where you want to make a decision about whether to buy a stock.</span></span>  <span data-ttu-id="208a9-196">신뢰할 수 있는 일부 주식 권장 웹 서비스가 있지만 매일의 부하에 따라 각 서비스가 서로 다른 시간에 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-196">There are several stock recommendation web services that you trust, but depending on daily load, each service can end up being slow at different times.</span></span>  <span data-ttu-id="208a9-197">사용할 수는 <xref:System.Threading.Tasks.Task.WhenAny%2A> 모든 작업이 완료 될 때 알림을 받기 메서드:</span><span class="sxs-lookup"><span data-stu-id="208a9-197">You can use the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to receive a notification when any operation completes:</span></span>  
  
```csharp  
var recommendations = new List<Task<bool>>()   
{   
    GetBuyRecommendation1Async(symbol),   
    GetBuyRecommendation2Async(symbol),  
    GetBuyRecommendation3Async(symbol)  
};  
Task<bool> recommendation = await Task.WhenAny(recommendations);  
if (await recommendation) BuyStock(symbol);  
```  
  
 <span data-ttu-id="208a9-198">와 달리 <xref:System.Threading.Tasks.Task.WhenAll%2A>, 성공적으로 완료 되는 모든 작업의 래핑 해제 된 결과 반환 하는 <xref:System.Threading.Tasks.Task.WhenAny%2A> 완료 하는 작업을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-198">Unlike <xref:System.Threading.Tasks.Task.WhenAll%2A>, which returns the unwrapped results of all tasks that completed successfully, <xref:System.Threading.Tasks.Task.WhenAny%2A> returns the task that completed.</span></span> <span data-ttu-id="208a9-199">작업이 실패하면 해당 작업이 실패했다는 사실을 알아야 하고, 작업이 성공하면 해당 반환 값과 연결된 작업이 어떤 작업인지 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-199">If a task fails, it’s important to know that it failed, and if a task succeeds, it’s important to know which task the return value is associated with.</span></span>  <span data-ttu-id="208a9-200">따라서 반환된 작업의 결과에 액세스하거나 이 예제에 나타난 대로 더 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-200">Therefore, you need to access the result of the returned task, or further await it, as  this example shows.</span></span>  
  
 <span data-ttu-id="208a9-201">와 마찬가지로 <xref:System.Threading.Tasks.Task.WhenAll%2A>, 예외를 수용 하기 위해 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-201">As with <xref:System.Threading.Tasks.Task.WhenAll%2A>, you have to be able to accommodate exceptions.</span></span>  <span data-ttu-id="208a9-202">완료된 작업이 다시 수신되므로 반환된 작업이 오류를 전파하고 적절히 `try/catch`할 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-202">Because you receive the completed task back, you can await the returned task to have errors propagated, and `try/catch` them appropriately; for example:</span></span>  
  
```csharp  
Task<bool> [] recommendations = …;  
while(recommendations.Count > 0)  
{   
    Task<bool> recommendation = await Task.WhenAny(recommendations);      
    try  
    {  
        if (await recommendation) BuyStock(symbol);  
        break;  
    }  
    catch(WebException exc)  
    {  
        recommendations.Remove(recommendation);  
    }  
}  
```  
  
 <span data-ttu-id="208a9-203">또한 첫 번째 작업이 성공적으로 완료되더라도 후속 작업은 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-203">Additionally, even if a first task completes successfully, subsequent tasks may fail.</span></span>  <span data-ttu-id="208a9-204">이 시점에서 예외를 처리할 수 있는 여러 옵션이 있습니다. <xref:System.Threading.Tasks.Task.WhenAll%2A> 메서드를 사용할 수 있는 경우 시작된 모든 작업이 완료될 때까지 기다릴 수도 있고 또는 모든 예외가 중요하며 로그온해야 한다고 결정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-204">At this point, you have several options for dealing with exceptions:  You can wait until all the launched tasks have completed, in which case you can use the <xref:System.Threading.Tasks.Task.WhenAll%2A> method, or you can decide that all exceptions are important and must be logged.</span></span>  <span data-ttu-id="208a9-205">이를 위해 연속 작업을 사용하여 작업이 비동기적으로 완료되었을 때 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-205">For this, you can use continuations to receive a notification when tasks have completed asynchronously:</span></span>  
  
```csharp  
foreach(Task recommendation in recommendations)  
{  
    var ignored = recommendation.ContinueWith(  
        t => { if (t.IsFaulted) Log(t.Exception); });  
}  
```  
  
 <span data-ttu-id="208a9-206">또는</span><span class="sxs-lookup"><span data-stu-id="208a9-206">or:</span></span>  
  
```csharp  
foreach(Task recommendation in recommendations)  
{  
    var ignored = recommendation.ContinueWith(  
        t => Log(t.Exception), TaskContinuationOptions.OnlyOnFaulted);  
}  
```  
  
 <span data-ttu-id="208a9-207">다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-207">or even:</span></span>  
  
```  
private static async void LogCompletionIfFailed(IEnumerable<Task> tasks)  
{  
    foreach(var task in tasks)  
    {  
        try { await task; }  
        catch(Exception exc) { Log(exc); }  
    }  
}  
…  
LogCompletionIfFailed(recommendations);  
```  
  
 <span data-ttu-id="208a9-208">마지막으로 남은 모든 작업을 취소하려고 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-208">Finally, you may want to cancel all the remaining operations:</span></span>  
  
```csharp  
var cts = new CancellationTokenSource();  
var recommendations = new List<Task<bool>>()   
{   
    GetBuyRecommendation1Async(symbol, cts.Token),   
    GetBuyRecommendation2Async(symbol, cts.Token),  
    GetBuyRecommendation3Async(symbol, cts.Token)  
};  
  
Task<bool> recommendation = await Task.WhenAny(recommendations);  
cts.Cancel();  
if (await recommendation) BuyStock(symbol);  
```  
  
#### <a name="interleaving"></a><span data-ttu-id="208a9-209">인터리브</span><span class="sxs-lookup"><span data-stu-id="208a9-209">Interleaving</span></span>  
 <span data-ttu-id="208a9-210">웹에서 이미지를 다운로드하고 각 이미지를 처리하는 것을 고려해 봅니다(예: UI 컨트롤에 이미지 추가).</span><span class="sxs-lookup"><span data-stu-id="208a9-210">Consider a case where you're downloading images from the web and processing each image (for example, adding the image to a UI control).</span></span>  <span data-ttu-id="208a9-211">UI 스레드에서 순차적으로 처리를 수행해야 하지만 가능한 동시에 이미지를 다운로드하려고 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-211">You have to do the processing sequentially on the UI thread, but you want to download the images as concurrently as possible.</span></span> <span data-ttu-id="208a9-212">또한 이미지가 모두 다운로드될 때까지 UI에 이미지를 추가하는 작업을 보류하지 않고 완료되는 대로 추가하려고 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-212">Also, you don’t want to hold up adding the images to the UI until they’re all downloaded—you want to add them as they complete:</span></span>  
  
```csharp  
List<Task<Bitmap>> imageTasks =   
    (from imageUrl in urls select GetBitmapAsync(imageUrl)).ToList();  
while(imageTasks.Count > 0)  
{  
    try  
    {  
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);  
        imageTasks.Remove(imageTask);  
  
        Bitmap image = await imageTask;  
        panel.AddImage(image);  
    }  
    catch{}  
}  
```  
  
 <span data-ttu-id="208a9-213">인터리빙에 복잡 한 계산 처리와 관련 된 시나리오에 적용할 수 있습니다는 <xref:System.Threading.ThreadPool> 다운로드 한 이미지의 예:</span><span class="sxs-lookup"><span data-stu-id="208a9-213">You can also apply interleaving to a scenario that involves computationally intensive processing on the <xref:System.Threading.ThreadPool> of the downloaded images; for example:</span></span>  
  
```csharp  
List<Task<Bitmap>> imageTasks =   
    (from imageUrl in urls select GetBitmapAsync(imageUrl)  
         .ContinueWith(t => ConvertImage(t.Result)).ToList();  
while(imageTasks.Count > 0)  
{  
    try  
    {  
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);  
        imageTasks.Remove(imageTask);  
  
        Bitmap image = await imageTask;  
        panel.AddImage(image);  
    }  
    catch{}  
}  
```  
  
#### <a name="throttling"></a><span data-ttu-id="208a9-214">스로틀</span><span class="sxs-lookup"><span data-stu-id="208a9-214">Throttling</span></span>  
 <span data-ttu-id="208a9-215">사용자가 너무 많은 이미지를 다운로드하여 다운로드를 조절해야 하는 경우를 제외하고, 인터리브 예제를 고려해 보세요. 예를 들어 특정 횟수의 다운로드만 동시에 발생하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-215">Consider the interleaving example, except that the user is downloading so many images that the downloads have to be throttled; for example, you want only a specific number of downloads to happen concurrently.</span></span> <span data-ttu-id="208a9-216">이를 위해 비동기 작업 일부를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-216">To achieve this, you can start a subset of the asynchronous operations.</span></span>  <span data-ttu-id="208a9-217">작업이 완료되면 추가 작업을 추가해서 시작되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-217">As operations complete, you can start additional operations to take their place:</span></span>  
  
```csharp  
const int CONCURRENCY_LEVEL = 15;  
Uri [] urls = …;  
int nextIndex = 0;  
var imageTasks = new List<Task<Bitmap>>();  
while(nextIndex < CONCURRENCY_LEVEL && nextIndex < urls.Length)  
{  
    imageTasks.Add(GetBitmapAsync(urls[nextIndex]));  
    nextIndex++;  
}  
  
while(imageTasks.Count > 0)  
{  
    try  
    {  
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);  
        imageTasks.Remove(imageTask);  
  
        Bitmap image = await imageTask;  
        panel.AddImage(image);  
    }  
    catch(Exception exc) { Log(exc); }  
  
    if (nextIndex < urls.Length)  
    {  
        imageTasks.Add(GetBitmapAsync(urls[nextIndex]));  
        nextIndex++;  
    }  
}  
```  
  
#### <a name="early-bailout"></a><span data-ttu-id="208a9-218">초기 재귀 한도 초과</span><span class="sxs-lookup"><span data-stu-id="208a9-218">Early Bailout</span></span>  
 <span data-ttu-id="208a9-219">사용자의 취소 요청에 동시에 응답하면서 작업이 완료되기를 비동기적으로 기다리는 경우를 고려해 봅니다(예: 사용자가 취소 단추를 클릭한 경우).</span><span class="sxs-lookup"><span data-stu-id="208a9-219">Consider that you're waiting asynchronously for an operation to complete while simultaneously responding to a user’s cancellation request (for example, the user clicked a cancel button).</span></span> <span data-ttu-id="208a9-220">다음 코드에서는 이 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-220">The following code illustrates this scenario:</span></span>  
  
```csharp  
private CancellationTokenSource m_cts;   
  
public void btnCancel_Click(object sender, EventArgs e)  
{  
    if (m_cts != null) m_cts.Cancel();  
}  
  
public async void btnRun_Click(object sender, EventArgs e)  
{  
    m_cts = new CancellationTokenSource();  
    btnRun.Enabled = false;  
    try  
    {  
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text);   
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);  
        if (imageDownload.IsCompleted)  
        {  
            Bitmap image = await imageDownload;  
            panel.AddImage(image);  
        }  
        else imageDownload.ContinueWith(t => Log(t));  
    }  
    finally { btnRun.Enabled = true; }  
}  
  
private static async Task UntilCompletionOrCancellation(  
    Task asyncOp, CancellationToken ct)  
{  
    var tcs = new TaskCompletionSource<bool>();  
    using(ct.Register(() => tcs.TrySetResult(true)))  
        await Task.WhenAny(asyncOp, tcs.Task);  
    return asyncOp;  
}  
```  
  
 <span data-ttu-id="208a9-221">이 구현은 재귀 한도가 초과되었다고 결정하는 즉시 사용자 인터페이스를 다시 사용하도록 설정하지만 기본 비동기 작업을 취소하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-221">This implementation re-enables the user interface as soon as you decide to bail out, but doesn't cancel the underlying asynchronous operations.</span></span>  <span data-ttu-id="208a9-222">또 다른 방법은 재귀 한도가 초과되었다고 결정할 때 보류 중인 작업을 취소하지만, 취소 요청으로 인해 일찍 종료될 수 있으므로 작업이 실제로 완료될 때까지 사용자 인터페이스를 다시 설정하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-222">Another alternative would be to cancel the pending operations when you decide to bail out, but not reestablish the user interface until the operations actually complete, potentially due to ending early due to the cancellation request:</span></span>  
  
```csharp  
private CancellationTokenSource m_cts;  
  
public async void btnRun_Click(object sender, EventArgs e)  
{  
    m_cts = new CancellationTokenSource();  
  
    btnRun.Enabled = false;  
    try  
    {  
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text, m_cts.Token);   
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);  
        Bitmap image = await imageDownload;  
        panel.AddImage(image);  
    }  
    catch(OperationCanceledException) {}  
    finally { btnRun.Enabled = true; }  
}  
```  
  
 <span data-ttu-id="208a9-223">초기 재귀 한도의 또 다른 예를 사용 하는 <xref:System.Threading.Tasks.Task.WhenAny%2A> 메서드와 함께 <xref:System.Threading.Tasks.Task.Delay%2A> 메서드를 다음 섹션에서 설명 했 듯이 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-223">Another example of early bailout involves using the <xref:System.Threading.Tasks.Task.WhenAny%2A> method in conjunction with the <xref:System.Threading.Tasks.Task.Delay%2A> method, as discussed in the next section.</span></span>  
  
### <a name="taskdelay"></a><span data-ttu-id="208a9-224">Task.Delay</span><span class="sxs-lookup"><span data-stu-id="208a9-224">Task.Delay</span></span>  
 <span data-ttu-id="208a9-225">사용할 수는 <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> 소개 하기 위한 메서드는 비동기 메서드 실행을 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-225">You can use the <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> method to introduce pauses into an asynchronous method’s execution.</span></span>  <span data-ttu-id="208a9-226">이것은 폴링 루프 작성 및 미리 결정된 기간 동안 사용자 입력 처리 지연 등의 다양한 기능에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-226">This is useful for many kinds of functionality, including building polling loops and delaying the handling of user input for a predetermined period of time.</span></span>  <span data-ttu-id="208a9-227"><xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> 메서드도 유용할 수 있습니다 함께에서 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> 대기 제한 시간에 구현에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-227">The <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> method can also be useful in combination with <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> for implementing time-outs on awaits.</span></span>  
  
 <span data-ttu-id="208a9-228">더 큰 비동기 작업(예: ASP.NET 웹 서비스)에 속하는 작업(task)이 완료하는 데 너무 오래 걸리는 경우 전체 작업에 문제가 발생하며, 완료가 실패하는 경우에는 더 큰 문제가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-228">If a task that’s part of a larger asynchronous operation (for example, an ASP.NET web service) takes too long to complete, the overall operation could suffer, especially if it fails to ever complete.</span></span>  <span data-ttu-id="208a9-229">이러한 이유로 비동기 작업을 대기하는 경우 시간이 초과되도록 할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-229">For this reason, it’s important to be able to time out when waiting on an asynchronous operation.</span></span>  <span data-ttu-id="208a9-230">동기 <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>, 및 <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> 방법 사용할 수 있지만 해당 시간 제한 값을 <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> / <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> 앞에서 언급 한 및 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> / <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>다릅니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-230">The synchronous <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> methods accept time-out values, but the corresponding <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> and the previously mentioned <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> methods do not.</span></span>  <span data-ttu-id="208a9-231">대신 사용할 수 있습니다 <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> 제한 시간을 구현 하는 조합에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-231">Instead, you can use <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> in combination to implement a time-out.</span></span>  
  
 <span data-ttu-id="208a9-232">예를 들어 UI 응용 프로그램에서 이미지를 다운로드하려고 하며 이미지를 다운로드하는 동안에 UI를 사용하지 않도록 설정하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-232">For example, in your UI application, let's say that you want to download an image and disable the UI while the image is downloading.</span></span> <span data-ttu-id="208a9-233">그러나 다운로드가 너무 오래 걸리는 경우 UI를 다시 사용하도록 설정하고 다운로드를 취소하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-233">However, if the download takes too long, you want to re-enable the UI and discard the download:</span></span>  
  
```csharp  
public async void btnDownload_Click(object sender, EventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap> download = GetBitmapAsync(url);  
        if (download == await Task.WhenAny(download, Task.Delay(3000)))  
        {  
            Bitmap bmp = await download;  
            pictureBox.Image = bmp;  
            status.Text = "Downloaded";  
        }  
        else  
        {  
            pictureBox.Image = null;  
            status.Text = "Timed out";  
            var ignored = download.ContinueWith(  
                t => Trace("Task finally completed"));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
```  
  
 <span data-ttu-id="208a9-234">마찬가지 여러 다운로드 하기 때문에 <xref:System.Threading.Tasks.Task.WhenAll%2A> 는 작업을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-234">The same applies to multiple downloads, because <xref:System.Threading.Tasks.Task.WhenAll%2A> returns a task:</span></span>  
  
```csharp  
public async void btnDownload_Click(object sender, RoutedEventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap[]> downloads =   
            Task.WhenAll(from url in urls select GetBitmapAsync(url));  
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))  
        {  
            foreach(var bmp in downloads) panel.AddImage(bmp);  
            status.Text = "Downloaded";  
        }  
        else  
        {  
            status.Text = "Timed out";  
            downloads.ContinueWith(t => Log(t));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
```  
  
## <a name="building-task-based-combinators"></a><span data-ttu-id="208a9-235">작업 기반 조합기 구축</span><span class="sxs-lookup"><span data-stu-id="208a9-235">Building Task-based Combinators</span></span>  
 <span data-ttu-id="208a9-236">작업(task)이 완전히 비동기 작업을 나타내고 작업에 조인, 결과 가져오기 등을 위한 동기 및 비동기 기능을 제공할 수 있으므로 작업을 구성하여 더 큰 패턴을 구축하는 유용한 조합기 라이브러리를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-236">Because a task is able to completely represent an asynchronous operation and provide synchronous and asynchronous capabilities for joining with the operation, retrieving its results, and so on, you can build useful libraries of combinators that compose tasks to build larger patterns.</span></span>  <span data-ttu-id="208a9-237">이전 섹션에서 설명한 것처럼 .NET Framework에는 몇 가지 기본 제공 조합기가 포함되어 있으나 직접 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-237">As discussed in the previous section, the .NET Framework includes several built-in combinators, but you can also build your own.</span></span> <span data-ttu-id="208a9-238">다음 섹션에서는 잠재적인 조합기 메서드 및 형식의 몇 가지 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-238">The following sections provide several examples of potential combinator methods and types.</span></span>  
  
### <a name="retryonfault"></a><span data-ttu-id="208a9-239">RetryOnFault</span><span class="sxs-lookup"><span data-stu-id="208a9-239">RetryOnFault</span></span>  
 <span data-ttu-id="208a9-240">대부분의 경우 이전 시도가 실패하면 작업을 다시 시도하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-240">In many situations, you may want to retry an operation if a previous attempt fails.</span></span>  <span data-ttu-id="208a9-241">동기 코드의 경우 이를 위해 다음 예제의 `RetryOnFault`와 같은 도우미 메서드를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-241">For synchronous code, you might build a helper method such as `RetryOnFault` in the following example to accomplish this:</span></span>  
  
```csharp  
public static T RetryOnFault<T>(  
    Func<T> function, int maxTries)  
{  
    for(int i=0; i<maxTries; i++)  
    {  
        try { return function(); }  
        catch { if (i == maxTries-1) throw; }  
    }  
    return default(T);  
}  
```  
  
 <span data-ttu-id="208a9-242">TAP으로 구현되므로 작업(task)을 반환하는 비동기 작업에 대해서도 거의 동일한 도우미 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-242">You can build an almost identical helper method for asynchronous operations that are implemented with TAP and thus return tasks:</span></span>  
  
```csharp  
public static async Task<T> RetryOnFault<T>(  
    Func<Task<T>> function, int maxTries)  
{  
    for(int i=0; i<maxTries; i++)  
    {  
        try { return await function().ConfigureAwait(false); }  
        catch { if (i == maxTries-1) throw; }  
    }  
    return default(T);  
}  
```  
  
 <span data-ttu-id="208a9-243">이 조합기를 사용하여 응용 프로그램의 논리에 다시 시도를 인코딩할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-243">You can then use this combinator to encode retries into the application’s logic; for example:</span></span>  
  
```csharp  
// Download the URL, trying up to three times in case of failure  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3);  
```  
  
 <span data-ttu-id="208a9-244">`RetryOnFault` 함수를 추가로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-244">You could extend the `RetryOnFault` function further.</span></span> <span data-ttu-id="208a9-245">예를 들어 이 함수는 다시 시도 중간에 호출되는 다른 `Func<Task>`를 수락하여 작업을 다시 시도해야 하는 시기를 결정할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-245">For example, the function could accept another `Func<Task>` that will be invoked between retries to determine when to try the operation again; for example:</span></span>  
  
```csharp  
public static async Task<T> RetryOnFault<T>(  
    Func<Task<T>> function, int maxTries, Func<Task> retryWhen)  
{  
    for(int i=0; i<maxTries; i++)  
    {  
        try { return await function().ConfigureAwait(false); }  
        catch { if (i == maxTries-1) throw; }  
        await retryWhen().ConfigureAwait(false);  
    }  
    return default(T);  
}  
```  
  
 <span data-ttu-id="208a9-246">그런 후 다음과 같은 함수를 사용하여 작업을 다시 시도하기 전에 잠시 대기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-246">You could then use the function as follows to wait for a second before retrying the operation:</span></span>  
  
```csharp  
// Download the URL, trying up to three times in case of failure,  
// and delaying for a second between retries  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));  
```  
  
### <a name="needonlyone"></a><span data-ttu-id="208a9-247">NeedOnlyOne</span><span class="sxs-lookup"><span data-stu-id="208a9-247">NeedOnlyOne</span></span>  
 <span data-ttu-id="208a9-248">경우에 따라 작업의 대기 시간 및 성공 가능성을 개선하기 위해 중복성을 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-248">Sometimes, you can take advantage of redundancy to improve an operation’s latency and chances for success.</span></span>  <span data-ttu-id="208a9-249">주식 시세를 제공하는 여러 웹 서비스가 있으나 각 서비스는 하루 중 다른 시간에 다른 수준의 품질 및 응답 시간을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-249">Consider multiple web services that provide stock quotes, but at various times of the day, each service may provide different levels of quality and response times.</span></span>  <span data-ttu-id="208a9-250">이러한 변동을 처리하려면 모든 웹 서비스로 요청을 보내고 응답을 받는 즉시 나머지 요청을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-250">To deal with these fluctuations, you may issue requests to all the web services, and as soon as you get a response from one, cancel the remaining requests.</span></span>  <span data-ttu-id="208a9-251">도우미 함수를 구현하면 여러 작업을 시작하고, 하나가 완료되기를 기다린 후 나머지는 취소하는 이러한 일반적인 패턴을 보다 쉽게 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-251">You can implement a helper function to make it easier to implement this common pattern of launching multiple operations, waiting for any, and then canceling the rest.</span></span> <span data-ttu-id="208a9-252">다음 예제의 `NeedOnlyOne` 함수는 이 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-252">The `NeedOnlyOne` function in the following example illustrates this scenario:</span></span>  
  
```csharp  
public static async Task<T> NeedOnlyOne(  
    params Func<CancellationToken,Task<T>> [] functions)  
{  
    var cts = new CancellationTokenSource();  
    var tasks = (from function in functions  
                 select function(cts.Token)).ToArray();  
    var completed = await Task.WhenAny(tasks).ConfigureAwait(false);  
    cts.Cancel();  
    foreach(var task in tasks)   
    {  
        var ignored = task.ContinueWith(  
            t => Log(t), TaskContinuationOptions.OnlyOnFaulted);  
    }  
    return completed;  
}  
```  
  
 <span data-ttu-id="208a9-253">그런 후 이 함수를 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-253">You can then use this function as follows:</span></span>  
  
```csharp  
double currentPrice = await NeedOnlyOne(  
    ct => GetCurrentPriceFromServer1Async("msft", ct),  
    ct => GetCurrentPriceFromServer2Async("msft", ct),  
    ct => GetCurrentPriceFromServer3Async("msft", ct));  
```  
  
### <a name="interleaved-operations"></a><span data-ttu-id="208a9-254">인터리브 작업</span><span class="sxs-lookup"><span data-stu-id="208a9-254">Interleaved Operations</span></span>  
 <span data-ttu-id="208a9-255">사용 하 여 잠재적인 성능 문제가 <xref:System.Threading.Tasks.Task.WhenAny%2A> 메서드를 작업의 매우 큰 집합으로 작업 하는 경우에 인터리빙 시나리오를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-255">There is a potential performance problem with using the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to support an interleaving scenario when you're working with very large sets of tasks.</span></span>  <span data-ttu-id="208a9-256">호출할 때마다 <xref:System.Threading.Tasks.Task.WhenAny%2A> 각 작업과 함께 등록 되는 연속 작업에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-256">Every call to <xref:System.Threading.Tasks.Task.WhenAny%2A> results in a continuation being registered with each task.</span></span> <span data-ttu-id="208a9-257">작업 수가 N이면 인터리브 작업의 수명 동안 O(N2) 연속이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-257">For N number of tasks, this results in O(N2) continuations created over the lifetime of the interleaving operation.</span></span>  <span data-ttu-id="208a9-258">큰 작업을 하는 경우에는 성능 문제를 해결하기 위해 (다음 예의 `Interleaved`와 같은) 조합기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-258">If you're working with a large set of tasks, you can use a combinator  (`Interleaved` in the following example) to address the performance issue:</span></span>  
  
```csharp  
static IEnumerable<Task<T>> Interleaved<T>(IEnumerable<Task<T>> tasks)  
{  
    var inputTasks = tasks.ToList();  
    var sources = (from _ in Enumerable.Range(0, inputTasks.Count)   
                   select new TaskCompletionSource<T>()).ToList();  
    int nextTaskIndex = -1;  
    foreach (var inputTask in inputTasks)  
    {  
        inputTask.ContinueWith(completed =>  
        {  
            var source = sources[Interlocked.Increment(ref nextTaskIndex)];  
            if (completed.IsFaulted)   
                source.TrySetException(completed.Exception.InnerExceptions);  
            else if (completed.IsCanceled)   
                source.TrySetCanceled();  
            else   
                source.TrySetResult(completed.Result);  
        }, CancellationToken.None,   
           TaskContinuationOptions.ExecuteSynchronously,   
           TaskScheduler.Default);  
    }  
    return from source in sources   
           select source.Task;  
}  
```  
  
 <span data-ttu-id="208a9-259">그런 다음 조합기를 사용하여 완료된 작업의 결과를 처리할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-259">You can then use the combinator to process the results of tasks as they complete; for example:</span></span>  
  
```csharp  
IEnumerable<Task<int>> tasks = ...;  
foreach(var task in Interleaved(tasks))  
{  
    int result = await task;  
    …  
}  
```  
  
### <a name="whenallorfirstexception"></a><span data-ttu-id="208a9-260">WhenAllOrFirstException</span><span class="sxs-lookup"><span data-stu-id="208a9-260">WhenAllOrFirstException</span></span>  
 <span data-ttu-id="208a9-261">특정 분산/수집 시나리오에서 집합의 작업 하나가 실패하지 않는 한, 모든 작업이 완료되기를 기다리며, 실패하는 작업이 있으면 예외가 발생하는 즉시 대기를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-261">In certain scatter/gather scenarios, you might want to wait for all tasks in a set, unless one of them faults, in which case you want to stop waiting as soon as the exception occurs.</span></span>  <span data-ttu-id="208a9-262">다음 예제의 `WhenAllOrFirstException`과 같은 조합기 메서드로 이러한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-262">You can accomplish that with a combinator method such as `WhenAllOrFirstException` in the following example:</span></span>  
  
```csharp  
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)  
{  
    var inputs = tasks.ToList();  
    var ce = new CountdownEvent(inputs.Count);  
    var tcs = new TaskCompletionSource<T[]>();  
  
    Action<Task> onCompleted = (Task completed) =>  
    {  
        if (completed.IsFaulted)   
            tcs.TrySetException(completed.Exception.InnerExceptions);  
        if (ce.Signal() && !tcs.Task.IsCompleted)  
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());  
    };  
  
    foreach (var t in inputs) t.ContinueWith(onCompleted);  
    return tcs.Task;  
}  
```  
  
## <a name="building-task-based-data-structures"></a><span data-ttu-id="208a9-263">작업 기반 데이터 구조 구축</span><span class="sxs-lookup"><span data-stu-id="208a9-263">Building Task-based Data Structures</span></span>  
 <span data-ttu-id="208a9-264">사용자 지정 작업 기반 조합 기를 구축 하는 기능, 이외에 데이터 구조에 포함 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601> 함께 조인 하는 데 필요한 동기화를 사용 하면 매우 강력한을 비동기 작업의 결과 나타내고 비동기 시나리오에 사용할 사용자 지정 데이터 구조를 구축할 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-264">In addition to the ability to build custom task-based combinators, having a data structure in <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> that represents both the results of an asynchronous operation and the necessary synchronization to join with it makes it a very powerful type on which to build custom data structures to be used in asynchronous scenarios.</span></span>  
  
### <a name="asynccache"></a><span data-ttu-id="208a9-265">AsyncCache</span><span class="sxs-lookup"><span data-stu-id="208a9-265">AsyncCache</span></span>  
 <span data-ttu-id="208a9-266">결과 또는 예외가 해당 작업의 중요 한 측면은는 그 수 게 전달할 수 이들은 모두 수 기다려야 합니다, 레지스터 연속 하는 여러 소비자가 하나 가져오기 (의 경우 <xref:System.Threading.Tasks.Task%601>) 등입니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-266">One important aspect of a task is that it may be handed out to multiple consumers, all of whom may await it, register continuations with it, get its result or exceptions (in the case of <xref:System.Threading.Tasks.Task%601>), and so on.</span></span>  <span data-ttu-id="208a9-267">이렇게 하면 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601> 완벽 하 게 비동기 캐싱 인프라에서 사용할 수에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-267">This makes <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> perfectly suited to be used in an asynchronous caching infrastructure.</span></span>  <span data-ttu-id="208a9-268">사용할 경우 약간의 예로 하지만 강력한 비동기 캐시의 맨 위에 빌드된 <xref:System.Threading.Tasks.Task%601>:</span><span class="sxs-lookup"><span data-stu-id="208a9-268">Here’s an example of a small but powerful asynchronous cache built on top of <xref:System.Threading.Tasks.Task%601>:</span></span>  
  
```csharp  
public class AsyncCache<TKey, TValue>  
{  
    private readonly Func<TKey, Task<TValue>> _valueFactory;  
    private readonly ConcurrentDictionary<TKey, Lazy<Task<TValue>>> _map;  
  
    public AsyncCache(Func<TKey, Task<TValue>> valueFactory)  
    {  
        if (valueFactory == null) throw new ArgumentNullException("loader");  
        _valueFactory = valueFactory;  
        _map = new ConcurrentDictionary<TKey, Lazy<Task<TValue>>>();  
    }  
  
    public Task<TValue> this[TKey key]  
    {  
        get  
        {  
            if (key == null) throw new ArgumentNullException("key");  
            return _map.GetOrAdd(key, toAdd =>   
                new Lazy<Task<TValue>>(() => _valueFactory(toAdd))).Value;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="208a9-269">[AsyncCache\<TKey, TValue >](http://go.microsoft.com/fwlink/p/?LinkId=251941) 클래스는으로 허용 대리자 생성자를 사용 하는 함수는 `TKey` 반환는 <xref:System.Threading.Tasks.Task%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-269">The [AsyncCache\<TKey,TValue>](http://go.microsoft.com/fwlink/p/?LinkId=251941) class accepts as a delegate to its constructor a function that takes a `TKey` and returns a <xref:System.Threading.Tasks.Task%601>.</span></span>  <span data-ttu-id="208a9-270">캐시에서 이전에 액세스했던 값은 내부 사전에 저장되며, 캐시에 동시에 액세스하더라도 `AsyncCache`는 키당 하나의 작업만 생성되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-270">Any previously accessed values from the cache are stored in the internal dictionary, and the `AsyncCache` ensures that only one task is generated per key, even if the cache is accessed concurrently.</span></span>  
  
 <span data-ttu-id="208a9-271">예를 들어 다운로드한 웹 페이지에 대한 캐시를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-271">For example, you can build a cache for downloaded web pages:</span></span>  
  
```csharp  
private AsyncCache<string,string> m_webPages =   
    new AsyncCache<string,string>(DownloadStringAsync);  
```  
  
 <span data-ttu-id="208a9-272">그런 다음 웹 페이지의 콘텐츠가 필요할 때마다 비동기 메서드에서 이 캐시를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-272">You can then use this cache in asynchronous methods whenever you need the contents of a web page.</span></span> <span data-ttu-id="208a9-273">`AsyncCache` 클래스는 가능한 작은 수의 페이지를 다운로드하도록 하고 결과를 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-273">The `AsyncCache` class ensures that you’re downloading as few pages as possible, and caches the results.</span></span>  
  
```csharp  
private async void btnDownload_Click(object sender, RoutedEventArgs e)   
{  
    btnDownload.IsEnabled = false;  
    try  
    {  
        txtContents.Text = await m_webPages["http://www.microsoft.com"];  
    }  
    finally { btnDownload.IsEnabled = true; }  
}  
```  
  
### <a name="asyncproducerconsumercollection"></a><span data-ttu-id="208a9-274">AsyncProducerConsumerCollection</span><span class="sxs-lookup"><span data-stu-id="208a9-274">AsyncProducerConsumerCollection</span></span>  
 <span data-ttu-id="208a9-275">또한 작업을 사용하여 비동기 활동을 조정하기 위한 데이터 구조를 구축할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-275">You can also use tasks to build data structures for coordinating asynchronous activities.</span></span>  <span data-ttu-id="208a9-276">클래식 병렬 디자인인 생산자/소비자 중 하나를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="208a9-276">Consider one of the classic parallel design patterns: producer/consumer.</span></span>  <span data-ttu-id="208a9-277">이 패턴에서 생산자는 소비자가 사용하는 데이터를 생성하고, 생산자와 소비자가 동시에 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-277">In this pattern, producers generate data that is consumed by consumers, and the producers and consumers may run in parallel.</span></span> <span data-ttu-id="208a9-278">예를 들어, 소비자는 항목 2를 생성하고 있는 생산자가 이전에 생성한 항목 1을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-278">For example, the consumer processes item 1, which was previously generated by a producer who is now producing item 2.</span></span>  <span data-ttu-id="208a9-279">생산자/소비자 패턴의 경우 항상 소비자가 새 데이터에 대한 알림을 수신하고 사용 가능할 때 찾을 수 있도록 생산자가 만든 작업을 저장할 일부 데이터 구조가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-279">For the producer/consumer pattern, you invariably need some data structure to store the work created by producers so that the consumers may be notified of new data and find it when available.</span></span>  
  
 <span data-ttu-id="208a9-280">비동기 메서드가 생산자 및 소비자로 사용할 수 있게 해 주는 작업 기반의 간단한 데이터 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-280">Here’s a simple data structure built on top of tasks that enables asynchronous methods to be used as producers and consumers:</span></span>  
  
```csharp  
public class AsyncProducerConsumerCollection<T>  
{  
    private readonly Queue<T> m_collection = new Queue<T>();  
    private readonly Queue<TaskCompletionSource<T>> m_waiting =   
        new Queue<TaskCompletionSource<T>>();  
  
    public void Add(T item)  
    {  
        TaskCompletionSource<T> tcs = null;  
        lock (m_collection)  
        {  
            if (m_waiting.Count > 0) tcs = m_waiting.Dequeue();  
            else m_collection.Enqueue(item);  
        }  
        if (tcs != null) tcs.TrySetResult(item);  
    }  
  
    public Task<T> Take()  
    {  
        lock (m_collection)  
        {  
            if (m_collection.Count > 0)   
            {  
                return Task.FromResult(m_collection.Dequeue());   
            }  
            else   
            {  
                var tcs = new TaskCompletionSource<T>();  
                m_waiting.Enqueue(tcs);  
                return tcs.Task;  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="208a9-281">해당 데이터 구조가 준비되면 다음과 같이 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-281">With that data structure in place, you can write code such as the following:</span></span>  
  
```csharp  
private static AsyncProducerConsumerCollection<int> m_data = …;  
…  
private static async Task ConsumerAsync()  
{  
    while(true)  
    {  
        int nextItem = await m_data.Take();  
        ProcessNextItem(nextItem);  
    }  
}  
…  
private static void Produce(int data)  
{  
    m_data.Add(data);  
}  
```  
  
 <span data-ttu-id="208a9-282"><xref:System.Threading.Tasks.Dataflow> 네임 스페이스는 포함 된 <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> 비슷한 방식 이지만 사용자 지정 컬렉션 유형을 작성할 필요 없이 사용할 수 있는 형식:</span><span class="sxs-lookup"><span data-stu-id="208a9-282">The <xref:System.Threading.Tasks.Dataflow> namespace includes the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> type, which you can use in a similar manner, but without having to build a custom collection type:</span></span>  
  
```csharp  
private static BufferBlock<int> m_data = …;  
…  
private static async Task ConsumerAsync()  
{  
    while(true)  
    {  
        int nextItem = await m_data.ReceiveAsync();  
        ProcessNextItem(nextItem);  
    }  
}  
…  
private static void Produce(int data)  
{  
    m_data.Post(data);  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="208a9-283"><xref:System.Threading.Tasks.Dataflow> 네임 스페이스는에서 사용할 수는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 통해 **NuGet**합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-283">The <xref:System.Threading.Tasks.Dataflow> namespace is available in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] through **NuGet**.</span></span> <span data-ttu-id="208a9-284">포함 된 어셈블리를 설치 하려면는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴를 선택한 다음 Microsoft.Tpl.Dataflow 패키지에 대 한 온라인 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="208a9-284">To install the assembly that contains the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the Microsoft.Tpl.Dataflow package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="208a9-285">참고 항목</span><span class="sxs-lookup"><span data-stu-id="208a9-285">See Also</span></span>  
 [<span data-ttu-id="208a9-286">TAP(작업 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="208a9-286">Task-based Asynchronous Pattern (TAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 [<span data-ttu-id="208a9-287">작업 기반 비동기 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="208a9-287">Implementing the Task-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)  
 [<span data-ttu-id="208a9-288">다른 비동기 패턴 및 형식과의 Interop</span><span class="sxs-lookup"><span data-stu-id="208a9-288">Interop with Other Asynchronous Patterns and Types</span></span>](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)
