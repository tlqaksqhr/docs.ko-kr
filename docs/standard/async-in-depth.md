---
title: "비동기에 대한 자세한 설명"
description: ".NET 작업 기반 비동기 모델을 사용하여 간단하게 I/O 및 CPU 바인딩된 비동기 코드를 작성하는 방법을 알아봅니다."
keywords: ".NET, .NET Core, .NET 표준"
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 1e38f9d9-8f84-46ee-a15f-199aec4f2e34
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b01aa5d0fade29d04313a9db2e44517b6512166b
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="async-in-depth"></a><span data-ttu-id="72e47-104">비동기에 대한 자세한 설명</span><span class="sxs-lookup"><span data-stu-id="72e47-104">Async in depth</span></span>

<span data-ttu-id="72e47-105">.NET 태스크 기반 비동기 모델을 사용하면 I/O 및 CPU 바인딩된 비동기 코드를 간단하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-105">Writing I/O- and CPU-bound asynchronous code is straightforward using the .NET Task-based async model.</span></span> <span data-ttu-id="72e47-106">모델은 C# 및 Visual Basic에서 `Task` 및 `Task<T>` 형식과 `async` 및 `await` 키워드로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-106">The model is exposed by the `Task` and `Task<T>` types and the `async` and `await` keywords in C# and Visual Basic.</span></span> <span data-ttu-id="72e47-107">(언어 관련 리소스는 [참고 항목](#see-also) 섹션에 있습니다.) 이 문서에서는 .NET 비동기를 사용하는 방법을 설명하고 백그라운드에서 사용되는 비동기 프레임워크에 대한 통찰을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-107">(Language-specific resources are found in the [See also](#see-also) section.) This article explains how to use .NET async and provides insight into the async framework used under the covers.</span></span>

## <a name="task-and-tasklttgt"></a><span data-ttu-id="72e47-108">Task 및 Task&lt;T&gt;</span><span class="sxs-lookup"><span data-stu-id="72e47-108">Task and Task&lt;T&gt;</span></span>

<span data-ttu-id="72e47-109">태스크는 [동시성 약속 모델](https://en.wikipedia.org/wiki/Futures_and_promises)을 구현하는 데 사용되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-109">Tasks are constructs used to implement what is known as the [Promise Model of Concurrency](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>  <span data-ttu-id="72e47-110">간단히 말해서, 나중에 작업이 완료될 것이라는 "약속"을 제공하여 클린 API로 약속을 조정할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-110">In short, they offer you a "promise" that work will be completed at a later point, letting you coordinate with the promise with a clean API.</span></span>

*   <span data-ttu-id="72e47-111">`Task` - 값을 반환하지 않는 작업 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-111">`Task` represents a single operation which does not return a value.</span></span>
*   <span data-ttu-id="72e47-112">`Task<T>` - `T` 형식의 값을 반환하는 작업 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-112">`Task<T>` represents a single operation which returns a value of type `T`.</span></span>

<span data-ttu-id="72e47-113">스레딩에 대한 추상화가 *아니라* 비동기적으로 수행되는 작업의 추상화로 태스크에 대해 추론하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-113">It’s important to reason about tasks as abstractions of work happening asynchronously, and *not* an abstraction over threading.</span></span> <span data-ttu-id="72e47-114">기본적으로 태스크는 현재 스레드에 대해 실행되며 해당하는 경우 운영 체제에 작업을 위임합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-114">By default, tasks execute on the current thread and delegate work to the Operating System, as appropriate.</span></span> <span data-ttu-id="72e47-115">필요에 따라 `Task.Run` API를 통해 별도 스레드에서 실행되도록 태스크를 명시적으로 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-115">Optionally, tasks can be explicitly requested to run on a separate thread via the `Task.Run` API.</span></span>

<span data-ttu-id="72e47-116">태스크는 태스크의 결과 값(`Task<T>`의 경우)을 모니터링, 대기 및 액세스하기 위한 API 프로토콜을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-116">Tasks expose an API protocol for monitoring, waiting upon and accessing the result value (in the case of `Task<T>`) of a task.</span></span> <span data-ttu-id="72e47-117">`await` 키워드가 있는 언어 통합에서는 태스크 사용을 위한 상위 수준 추상화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-117">Language integration, with the `await` keyword, provides a higher-level abstraction for using tasks.</span></span> 

<span data-ttu-id="72e47-118">`await`를 사용하면 태스크가 완료될 때까지 해당 호출자에게 제어가 양도되므로 태스크가 실행되는 동안 응용 프로그램 또는 서비스에서 유용한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-118">Using `await` allows your application or service to perform useful work while a task is running by yielding control to its caller until the task is done.</span></span> <span data-ttu-id="72e47-119">태스크가 완료된 후에는 코드에서 콜백 또는 이벤트를 사용하여 실행을 계속할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-119">Your code does not need to rely on callbacks or events to continue execution after the task has been completed.</span></span> <span data-ttu-id="72e47-120">언어 및 태스크 API 통합에서 해당 작업을 자동으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-120">The language and task API integration does that for you.</span></span> <span data-ttu-id="72e47-121">`Task<T>`를 사용하는 경우 `await` 키워드는 작업이 완료될 때 반환되는 값을 추가로 “래핑 해제”합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-121">If you’re using `Task<T>`, the `await` keyword will additionally "unwrap" the value returned when the Task is complete.</span></span>  <span data-ttu-id="72e47-122">작동 방식에 대한 자세한 내용은 아래에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-122">The details of how this works are explained further below.</span></span>

<span data-ttu-id="72e47-123">[TAP(작업 기반 비동기 패턴)](~/docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) 항목에서 작업 및 작업을 조작하는 다양한 방법에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-123">You can learn more about tasks and the different ways to interact with them in the [Task-based Asynchronous Pattern (TAP)](~/docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) topic.</span></span>

## <a name="deeper-dive-into-tasks-for-an-io-bound-operation"></a><span data-ttu-id="72e47-124">I/O 바인딩된 작업에 대한 태스크 심층 분석</span><span class="sxs-lookup"><span data-stu-id="72e47-124">Deeper Dive into Tasks for an I/O-Bound Operation</span></span>

<span data-ttu-id="72e47-125">다음 섹션에서는 일반적인 비동기 I/O 호출에서 발생하는 결과에 대해 대략적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-125">The following section describes a 10,000 foot view of what happens with a typical async I/O call.</span></span> <span data-ttu-id="72e47-126">몇 가지 예부터 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-126">Let's start with a couple examples.</span></span>

<span data-ttu-id="72e47-127">첫 번째 예제에서는 비동기 메서드를 호출하고 아직 완료되지 않았을 가능성이 큰 활성 태스크를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-127">The first example calls an async method and returns an active task, likely yet to complete.</span></span>

```csharp
public Task<string> GetHtmlAsync()
{
    // Execution is synchronous here
    var client = new HttpClient();
    
    return client.GetStringAsync("http://www.dotnetfoundation.org");
}
```

<span data-ttu-id="72e47-128">두 번째 예제에서는 작업에 적용할 `async` 및 `await` 키워드 사용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-128">The second example adds the use of the `async` and `await` keywords to operate on the task.</span></span>

```csharp
public async Task<string> GetFirstCharactersCountAsync(string url, int count)
{
    // Execution is synchronous here
    var client = new HttpClient();
    
    // Execution of GetFirstCharactersCountAsync() is yielded to the caller here
    // GetStringAsync returns a Task<string>, which is *awaited*
    var page = await client.GetStringAsync("http://www.dotnetfoundation.org");
    
    // Execution resumes when the client.GetStringAsync task completes,
    // becoming synchronous again.
    
    if (count > page.Length)
    {
        return page;
    }
    else
    {
        return page.Substring(0, count);
    }
}
```

<span data-ttu-id="72e47-129">`GetStringAsync()` 호출은 네이티브 네트워킹 라이브러리에 대한 P/Invoke interop 호출에 도달할 때까지 하위 수준 .NET 라이브러리를 호출(다른 비동기 메서드 호출)합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-129">The call to `GetStringAsync()` calls through lower-level .NET libraries (perhaps calling other async methods) until it reaches a P/Invoke interop call into a native networking library.</span></span> <span data-ttu-id="72e47-130">이후에 네이티브 라이브러리는 시스템 API 호출(예: Linux의 소켓에 대한 `write()`)을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-130">The native library may subsequently call into a System API call (such as `write()` to a socket on Linux).</span></span> <span data-ttu-id="72e47-131">[TaskCompletionSource](xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult(%600))를 사용하여 네이티브/관리 경계에 태스크 개체가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-131">A task object will be created at the native/managed boundary, possibly using [TaskCompletionSource](xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult(%600)).</span></span> <span data-ttu-id="72e47-132">태스크 개체가 계층을 통해 위로 전달되며, 초기 호출자에게 반환될 때까지 작업되거나 바로 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-132">The task object will be passed up through the layers, possibly operated on or directly returned, eventually returned to the initial caller.</span></span> 

<span data-ttu-id="72e47-133">위의 두 번째 예제에서는 `Task<T>` 개체가 `GetStringAsync`에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-133">In the second example above, a `Task<T>` object will be returned from `GetStringAsync`.</span></span> <span data-ttu-id="72e47-134">`await` 키워드를 사용하면 메서드가 새로 만든 태스크 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-134">The use of the `await` keyword causes the method to return a newly created task object.</span></span> <span data-ttu-id="72e47-135">`GetFirstCharactersCountAsync` 메서드의 이 위치에서 호출자에게 제어가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-135">Control returns to the caller from this location in the `GetFirstCharactersCountAsync` method.</span></span> <span data-ttu-id="72e47-136">[Task&lt;T&gt;](xref:System.Threading.Tasks.Task%601) 개체의 메서드 및 속성을 사용하면 GetFirstCharactersCountAsync의 나머지 코드가 실행될 때 완료되는 태스크의 진행률을 호출자가 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-136">The methods and properties of the [Task&lt;T&gt;](xref:System.Threading.Tasks.Task%601) object enable callers to monitor the progress of the task, which will complete when the remaining code in GetFirstCharactersCountAsync has executed.</span></span>

<span data-ttu-id="72e47-137">시스템 API 호출 후에 요청은 이제 커널 공간에 있으며, OS의 네트워킹 하위 시스템(예: Linux 커널의 `/net`)로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-137">After the System API call, the request is now in kernel space, making its way to the networking subsystem of the OS (such as `/net` in the Linux Kernel).</span></span>  <span data-ttu-id="72e47-138">여기서 OS는 네트워킹 요청을 *비동기적으로* 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-138">Here the OS will handle the networking request *asynchronously*.</span></span>  <span data-ttu-id="72e47-139">세부 정보는 사용하는 OS에 따라 다를 수 있지만(장치 드라이버 호출을 런타임으로 다시 전송되는 신호로 예약하거나 장치 드라이버를 호출한 *다음* 신호가 다시 전송될 수 있음) 결국 런타임에서 네트워킹 요청이 진행 중이라는 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-139">Details may be different depending on the OS used (the device driver call may be scheduled as a signal sent back to the runtime, or a device driver call may be made and *then* a signal sent back), but eventually the runtime will be informed that the networking request is in progress.</span></span>  <span data-ttu-id="72e47-140">이번에는 장치 드라이버에 대한 작업이 예약되거나, 진행 중이거나, 이미 완료(요청이 이미 "네트워크"를 통해 전송됨)되었지만 이 모든 작업이 비동기적으로 수행되므로 장치 드라이버에서 다른 작업을 즉시 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-140">At this time, the work for the device driver will either be scheduled, in-progress, or already finished (the request is already out "over the wire") - but because this is all happening asynchronously, the device driver is able to immediately handle something else!</span></span>

<span data-ttu-id="72e47-141">예를 들어 Windows에서 OS 스레드는 네트워크 장치 드라이버를 호출하고 작업을 나타내는 IRP(인터럽트 요청 패킷)를 통해 네트워킹 작업을 수행하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-141">For example, in Windows an OS thread makes a call to the network device driver and asks it to perform the networking operation via an Interrupt Request Packet (IRP) which represents the operation.</span></span>  <span data-ttu-id="72e47-142">장치 드라이버는 IRP를 수신하고 네트워크를 호출한 다음 IRP를 "보류 중"으로 표시하고 OS에 다시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-142">The device driver receives the IRP, makes the call to the network, marks the IRP as "pending", and returns back to the OS.</span></span>  <span data-ttu-id="72e47-143">이제 OS 스레드에서 IRP가 "보류 중"임을 알고 있으므로 이 작업에 대해 수행할 작업이 없으며 다른 작업을 수행하는 데 사용될 수 있도록 다시 "반환"됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-143">Because the OS thread now knows that the IRP is "pending", it doesn't have any more work to do for this job and "returns" back so that it can be used to perform other work.</span></span>

<span data-ttu-id="72e47-144">요청이 수행되고 장치 드라이버를 통해 데이터가 반환되면 인터럽트를 통해 수신된 새 데이터를 CPU에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-144">When the request is fulfilled and data comes back through the device driver, it notifies the CPU of new data received via an interrupt.</span></span>  <span data-ttu-id="72e47-145">이 인터럽트의 처리 방법은 OS에 따라 다르지만 결국 데이터가 시스템 interop 호출에 도달할 때까지 OS를 통해 전달됩니다. 예를 들어 Linux에서는 인터럽트 처리기가 OS를 통해 비동기적으로 데이터를 위로 전달하기 위해 IRQ의 아래쪽 절반을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-145">How this interrupt gets handled will vary depending on the OS, but eventually the data will be passed through the OS until it reaches a system interop call (for example, in Linux an interrupt handler will schedule the bottom half of the IRQ to pass the data up through the OS asynchronously).</span></span>  <span data-ttu-id="72e47-146">이 작업도 *역시* 비동기적으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-146">Note that this *also* happens asynchronously!</span></span>  <span data-ttu-id="72e47-147">다음 사용 가능한 스레드가 비동기 메서드를 실행하고 완료된 태스크의 결과를 "래핑 해제"할 수 있을 때까지 결과가 큐에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-147">The result is queued up until the next available thread is able execute the async method and "unwrap" the result of the completed task.</span></span>

<span data-ttu-id="72e47-148">이 전체 프로세스의 요점은 **태스크 실행 전용 스레드가 없다**는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-148">Throughout this entire process, a key takeaway is that **no thread is dedicated to running the task**.</span></span>  <span data-ttu-id="72e47-149">일부 컨텍스트에서 작업이 실행되기는 하지만(즉, OS에서 데이터를 장치 드라이버로 전달하고 인터럽트에 응답해야 함) 요청에서 데이터가 반환될 때까지 *대기*하는 전용 스레드는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-149">Although work is executed in some context (that is, the OS does have to pass data to a device driver and respond to an interrupt), there is no thread dedicated to *waiting* for data from the request to come back.</span></span>  <span data-ttu-id="72e47-150">이렇게 하면 시스템에서 일부 I/O 호출이 완료될 때까지 대기하는 것보다 훨씬 더 많은 작업량을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-150">This allows the system to handle a much larger volume of work rather than waiting for some I/O call to finish.</span></span>

<span data-ttu-id="72e47-151">위의 프로세스를 위해 수행할 작업이 많아 보일 수도 있지만 벽시계 시간으로 측정할 때 실제 I/O 작업을 수행하는 데 걸리는 시간보다 훨씬 짧습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-151">Although the above may seem like a lot of work to be done, when measured in terms of wall clock time, it’s miniscule compared to the time it takes to do the actual I/O work.</span></span> <span data-ttu-id="72e47-152">정확하지는 않지만 이러한 호출의 잠재적인 타임라인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-152">Although not at all precise, a potential timeline for such a call would look like this:</span></span>

<span data-ttu-id="72e47-153">0-1————————————————————————————————————————————————–2-3</span><span class="sxs-lookup"><span data-stu-id="72e47-153">0-1————————————————————————————————————————————————–2-3</span></span>

*   <span data-ttu-id="72e47-154">`0` 지점에서 `1` 지점 사이의 소요 시간은 비동기 메서드가 호출자에 제어를 양도할 때까지 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-154">Time spent from points `0` to `1` is everything up until an async method yields control to its caller.</span></span>
*   <span data-ttu-id="72e47-155">`1` 지점에서 `2` 지점 사이의 소요 시간은 CPU 비용 없이 I/O에 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-155">Time spent from points `1` to `2` is the time spent on I/O, with no CPU cost.</span></span>
*   <span data-ttu-id="72e47-156">마지막으로, `2` 지점에서 `3` 지점 사이의 소요 시간은 제어(및 잠재적으로 값)가 비동기 메서드로 다시 전달되는 시간으로, 이때 메서드가 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-156">Finally, time spent from points `2` to `3` is passing control back (and potentially a value) to the async method, at which point it is executing again.</span></span>

### <a name="what-does-this-mean-for-a-server-scenario"></a><span data-ttu-id="72e47-157">서버 시나리오에서는 어떤 의미가 있을까요?</span><span class="sxs-lookup"><span data-stu-id="72e47-157">What does this mean for a server scenario?</span></span>

<span data-ttu-id="72e47-158">이 모델은 일반적인 서버 시나리오 작업에도 잘 맞습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-158">This model works well with a typical server scenario workload.</span></span>  <span data-ttu-id="72e47-159">완료되지 않은 태스크를 차단하는 전용 스레드가 없기 때문에 서버 스레드 풀이 훨씬 더 많은 웹 요청을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-159">Because there are no threads dedicated to blocking on unfinished tasks, the server threadpool can service a much higher volume of web requests.</span></span>

<span data-ttu-id="72e47-160">비동기 코드를 실행하는 서버와 비동기 코드를 실행하지 않는 서버가 있다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="72e47-160">Consider two servers: one that runs async code, and one that does not.</span></span>  <span data-ttu-id="72e47-161">이 예제를 위해 각 서버에서 서비스 요청에 사용할 수 있는 스레드가 5개뿐이라고 가정해봅시다.</span><span class="sxs-lookup"><span data-stu-id="72e47-161">For the purpose of this example, each server only has 5 threads available to service requests.</span></span>  <span data-ttu-id="72e47-162">이러한 개수는 비현실적으로 적은 개수이며 데모 컨텍스트에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-162">Note that these numbers are imaginarily small and serve only in a demonstrative context.</span></span>

<span data-ttu-id="72e47-163">두 서버가 모두 6개의 동시 요청을 받는다고 가정해봅시다.</span><span class="sxs-lookup"><span data-stu-id="72e47-163">Assume both servers receive 6 concurrent requests.</span></span> <span data-ttu-id="72e47-164">각 요청에서 I/O 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-164">Each request performs an I/O operation.</span></span>  <span data-ttu-id="72e47-165">비동기 코드가 *없는* 서버는 5개의 스레드 중 하나가 I/O 바인딩된 작업을 완료하고 응답을 쓸 때까지 6번째 요청을 큐에 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-165">The server *without* async code has to queue up the 6th request until one of the 5 threads have finished the I/O-bound work and written a response.</span></span> <span data-ttu-id="72e47-166">20번째 요청이 도달할 때쯤에는 큐가 너무 길어져서 서버 속도가 저하되기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-166">At the point that the 20th request comes in, the server might start to slow down, because the queue is getting too long.</span></span>

<span data-ttu-id="72e47-167">비동기 코드가 실행되고 *있는* 서버도 여섯 번째 요청을 큐에 유지하지만 `async` 및 `await`를 사용하기 때문에 I/O 바인딩된 작업이 완료될 때가 아니라 시작될 때 해당 스레드가 각각 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-167">The server *with* async code running on it still queues up the 6th request, but because it uses `async` and `await`, each of its threads are freed up when the I/O-bound work starts, rather than when it finishes.</span></span>  <span data-ttu-id="72e47-168">20번째 요청이 도달할 때쯤에는 들어오는 요청의 큐가 훨씬 더 적으며(큐에 요청이 있는 경우에도) 서버 속도가 저하되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-168">By the time the 20th request comes in, the queue for incoming requests will be far smaller (if it has anything in it at all), and the server won't slow down.</span></span>

<span data-ttu-id="72e47-169">가상의 예제이지만 실제 환경에서도 매우 유사한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-169">Although this is a contrived example, it works in a very similar fashion in the real world.</span></span>  <span data-ttu-id="72e47-170">실제로 서버가 `async` 및 `await`를 사용할 경우 받는 각 요청에 전용 스레드를 사용하는 경우에 비해 훨씬 더 많은 요청을 처리할 것을 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-170">In fact, you can expect a server to be able to handle an order of magnitude more requests using `async` and `await` than if it were dedicating a thread for each request it receives.</span></span>

### <a name="what-does-this-mean-for-client-scenario"></a><span data-ttu-id="72e47-171">클라이언트 시나리오에서는 어떤 의미가 있을까요?</span><span class="sxs-lookup"><span data-stu-id="72e47-171">What does this mean for client scenario?</span></span>

<span data-ttu-id="72e47-172">클라이언트 앱에 `async` 및 `await`를 사용할 경우의 가장 큰 이점은 응답성 증가입니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-172">The biggest gain for using `async` and `await` for a client app is an increase in responsiveness.</span></span>  <span data-ttu-id="72e47-173">스레드를 수동으로 생성하여 앱의 응답성을 개선할 수도 있지만 스레드 생성 작업은 `async` 및 `await`를 사용하는 것보다 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-173">Although you can make an app responsive by spawning threads manually, the act of spawning a thread is an expensive operation relative to just using `async` and `await`.</span></span>  <span data-ttu-id="72e47-174">특히 모바일 게임 등의 경우 I/O와 관련된 UI 스레드에 대한 영향을 최소화하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-174">Especially for something like a mobile game, impacting the UI thread as little as possible where I/O is concerned is crucial.</span></span>

<span data-ttu-id="72e47-175">무엇보다도, I/O 바인딩된 작업은 CPU 시간이 거의 필요하지 않으므로 유용하지 않은 작업에 전체 CPU 스레드를 전용으로 지정할 경우 리소스를 잘못 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-175">More importantly, because I/O-bound work spends virtually no time on the CPU, dedicating an entire CPU thread to perform barely any useful work would be a poor use of resources.</span></span>

<span data-ttu-id="72e47-176">또한 UI 스레드에 작업을 디스패치하는 경우(예: UI 업데이트) `async` 메서드를 사용하면 간단하며 추가 작업(예: 스레드로부터 안전한 대리자 호출)이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-176">Additionally, dispatching work to the UI thread (such as updating a UI) is very simple with `async` methods, and does not require extra work (such as calling a thread-safe delegate).</span></span>

## <a name="deeper-dive-into-task-and-taskt-for-a-cpu-bound-operation"></a><span data-ttu-id="72e47-177">CPU 바인딩된 작업에 대한 Task 및 Task<T> 심층 분석</span><span class="sxs-lookup"><span data-stu-id="72e47-177">Deeper Dive into Task and Task<T> for a CPU-Bound Operation</span></span>

<span data-ttu-id="72e47-178">CPU 바인딩된 `async` 코드는 I/O 바인딩된 `async` 코드와 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-178">CPU-bound `async` code is a bit different than I/O-bound `async` code.</span></span>  <span data-ttu-id="72e47-179">CPU에서 작업이 수행되기 때문에 스레드를 계산 전용으로 지정할 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-179">Because the work is done on the CPU, there's no way to get around dedicating a thread to the computation.</span></span>  <span data-ttu-id="72e47-180">`async` 및 `await`를 사용하면 깔끔하게 백그라운드 스레드를 조작하고 비동기 메서드 호출자를 응답 가능한 상태로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-180">The use of `async` and `await` provides you with a clean way to interact with a background thread and keep the caller of the async method responsive.</span></span>  <span data-ttu-id="72e47-181">이 경우 공유 데이터는 보호되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-181">Note that this does not provide any protection for shared data.</span></span>  <span data-ttu-id="72e47-182">공유 데이터를 사용하는 경우 적절한 동기화 전략을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-182">If you are using shared data, you will still need to apply an appropriate synchronization strategy.</span></span>

<span data-ttu-id="72e47-183">CPU 바인딩된 비동기 호출에 대한 개략적인 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-183">Here's a 10,000 foot view of a CPU-bound async call:</span></span>

```csharp
public async Task<int> CalculateResult(InputData data)
{
    // This queues up the work on the threadpool.
    var expensiveResultTask = Task.Run(() => DoExpensiveCalculation(data));
    
    // Note that at this point, you can do some other work concurrently,
    // as CalculateResult() is still executing!
    
    // Execution of CalculateResult is yielded here!
    var result = await expensiveResultTask;
    
    return result;
}
```

<span data-ttu-id="72e47-184">`CalculateResult()`가 호출된 스레드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-184">`CalculateResult()` executes on the thread it was called on.</span></span>  <span data-ttu-id="72e47-185">`Task.Run`을 호출할 때 비용이 많이 드는 CPU 바인딩된 작업 `DoExpensiveCalculation()`을 스레드 풀의 큐에 넣고 `Task<int>` 핸들을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-185">When it calls `Task.Run`, it queues the expensive CPU-bound operation, `DoExpensiveCalculation()`, on the thread pool and receives a `Task<int>` handle.</span></span>  <span data-ttu-id="72e47-186">`DoExpensiveCalculation()`이 결국 다른 CPU 코어에 있을 가능성이 큰 다음 사용 가능한 스레드에서 동시에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-186">`DoExpensiveCalculation()` is eventually run concurrently on the next available thread, likely on another CPU core.</span></span>  <span data-ttu-id="72e47-187">`CalculateResult()`를 호출한 스레드가 여전히 실행되고 있으므로 `DoExpensiveCalculation()`이 다른 스레드에서 진행 중인 동안 동시 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-187">It's possible to do concurrent work while `DoExpensiveCalculation()` is busy on another thread, because the thread which called `CalculateResult()` is still executing.</span></span>

<span data-ttu-id="72e47-188">`await`가 발생하면 `CalculateResult()` 실행이 해당 호출자에게 양도되어 `DoExpensiveCalculation()`이 결과를 생성하는 동안 현재 스레드에서 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-188">Once `await` is encountered, the execution of `CalculateResult()` is yielded to its caller, allowing other work to be done with the current thread while `DoExpensiveCalculation()` is churning out a result.</span></span>  <span data-ttu-id="72e47-189">완료되면 결과가 주 스레드에서 실행하기 위해 큐에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-189">Once it has finished, the result is queued up to run on the main thread.</span></span>  <span data-ttu-id="72e47-190">결국 주 스레드가 `CalculateResult()` 실행으로 돌아가고, 이때 `DoExpensiveCalculation()` 결과를 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-190">Eventually, the main thread will return to executing `CalculateResult()`, at which point it will have the result of `DoExpensiveCalculation()`.</span></span>

### <a name="why-does-async-help-here"></a><span data-ttu-id="72e47-191">이때 비동기가 왜 도움이 될까요?</span><span class="sxs-lookup"><span data-stu-id="72e47-191">Why does async help here?</span></span>

<span data-ttu-id="72e47-192">`async` 및 `await`는 응답성이 필요할 때 CPU 바인딩된 작업을 관리하는 모범 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-192">`async` and `await` are the best practice managing CPU-bound work when you need responsiveness.</span></span> <span data-ttu-id="72e47-193">CPU 바인딩된 작업에 비동기를 사용하는 여러 가지 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-193">There are multiple patterns for using async with CPU-bound work.</span></span> <span data-ttu-id="72e47-194">비동기 사용 시 작은 비용이 발생하며 타이트 루프에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-194">It's important to note that there is a small cost to using async and it's not recommended for tight loops.</span></span>  <span data-ttu-id="72e47-195">이 새로운 기능과 관련된 코드 작성 방법은 사용자가 결정할 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="72e47-195">It's up to you to determine how you write your code around this new capability.</span></span>

## <a name="see-also"></a><span data-ttu-id="72e47-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72e47-196">See also</span></span>

<span data-ttu-id="72e47-197">[C#의 비동기 프로그래밍](~/docs/csharp/async.md) </span><span class="sxs-lookup"><span data-stu-id="72e47-197">[Asynchronous programming in C#](~/docs/csharp/async.md) </span></span>  
[<span data-ttu-id="72e47-198">async 및 await를 사용한 비동기 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="72e47-198">Asynchronous programming with async and await (C#)</span></span>](../csharp/programming-guide/concepts/async/index.md)  
<span data-ttu-id="72e47-199">[Async Programming in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) (F#의 비동기 프로그래밍)</span><span class="sxs-lookup"><span data-stu-id="72e47-199">[Async Programming in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span></span>  
[<span data-ttu-id="72e47-200">Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72e47-200">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)
