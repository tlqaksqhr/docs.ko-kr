---
title: "비동기 프로그래밍"
description: ".NET Core에서 제공하는 C# 언어 수준 비동기 프로그래밍 모델에 대해 알아봅니다."
keywords: .NET, .NET Core
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.openlocfilehash: 35038b3dae80958071a9615f7f131fca73513077
ms.sourcegitcommit: d095094e942eedf09530ea5636fbaf9029853027
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2017
---
# <a name="asynchronous-programming"></a><span data-ttu-id="39c5b-104">비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="39c5b-104">Asynchronous programming</span></span>

<span data-ttu-id="39c5b-105">네트워크에서 데이터를 요청하거나 데이터베이스에 액세스하는 것과 같이 I/O 바인딩해야 할 경우 비동기 프로그래밍을 사용하고 싶을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-105">If you have any I/O-bound needs (such as requesting data from a network or accessing a database), you'll want to utilize asynchronous programming.</span></span>  <span data-ttu-id="39c5b-106">부담이 큰 계산을 수행하는 것과 같이 CPU 바인딩된 코드가 있을 수도 있으며 이는 비동기 코드 작성의 좋은 시나리오이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-106">You could also have CPU-bound code, such as performing an expensive calculation, which is also a good scenario for writing async code.</span></span>

<span data-ttu-id="39c5b-107">C#에는 콜백을 조작하거나 비동기를 지원하는 라이브러리를 따를 필요 없이 비동기 코드를 쉽게 작성할 수 있는 언어 수준 비동기 프로그래밍 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-107">C# has a language-level asynchronous programming model which allows for easily writing asynchronous code without having to juggle callbacks or conform to a library which supports asynchrony.</span></span> <span data-ttu-id="39c5b-108">이 모델은 [TAP(작업 기반 비동기 패턴)](https://msdn.microsoft.com/library/hh873175.aspx)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-108">It follows what is known as the [Task-based Asynchronous Pattern (TAP)](https://msdn.microsoft.com/library/hh873175.aspx).</span></span>

## <a name="basic-overview-of-the-asynchronous-model"></a><span data-ttu-id="39c5b-109">비동기 모델의 기본 개요</span><span class="sxs-lookup"><span data-stu-id="39c5b-109">Basic Overview of the Asynchronous Model</span></span>

<span data-ttu-id="39c5b-110">비동기 프로그래밍의 핵심은 비동기 작업을 모델링하는 `Task` 및 `Task<T>` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-110">The core of async programming are the `Task` and `Task<T>` objects, which model asynchronous operations.</span></span>  <span data-ttu-id="39c5b-111">이러한 개체는 `async` 및 `await` 키워드를 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-111">They are supported by the `async` and `await` keywords.</span></span>  <span data-ttu-id="39c5b-112">대부분의 경우 모델은 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-112">The model is fairly simple in most cases:</span></span> 

<span data-ttu-id="39c5b-113">I/O 바인딩된 코드에서는 `async` 메서드의 내부에 `Task` 또는 `Task<T>`를 `await`합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-113">For I/O-bound code, you `await` an operation which returns a `Task` or `Task<T>` inside of an `async` method.</span></span>

<span data-ttu-id="39c5b-114">CPU 바인딩된 코드에서는 `Task.Run` 메서드와 함께 백그라운드 스레드에서 시작되는 작업을 `await`합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-114">For CPU-bound code, you `await` an operation which is started on a background thread with the `Task.Run` method.</span></span>

<span data-ttu-id="39c5b-115">`await` 키워드가 마법이 일어나는 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-115">The `await` keyword is where the magic happens.</span></span> <span data-ttu-id="39c5b-116">`await`를 수행한 메서드의 호출자에게 제어를 넘기고, 궁극적으로 UI가 응답하거나 서비스가 탄력적일 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-116">It yields control to the caller of the method that performed `await`, and it ultimately allows a UI to be responsive or a service to be elastic.</span></span>

<span data-ttu-id="39c5b-117">위에 연결된 TAP에 간단히 설명된 `async` 및 `await` 이외의 비동기 코드에 접근하는 다른 방법이 있지만, 이 문서에서는 이 지점부터 앞으로 언어 수준 구문에 초점을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-117">There are other ways to approach async code than `async` and `await` outlined in the TAP article linked above, but this document will focus on the language-level constructs from this point forward.</span></span>

### <a name="io-bound-example-downloading-data-from-a-web-service"></a><span data-ttu-id="39c5b-118">I/O 바인딩된 예제: 웹 서비스에서 데이터 다운로드</span><span class="sxs-lookup"><span data-stu-id="39c5b-118">I/O-Bound Example: Downloading data from a web service</span></span>

<span data-ttu-id="39c5b-119">단추가 눌릴 때 웹 서비스에서 일부 데이터를 다운로드해야 할 수 있지만 UI 스레드를 차단하지 않으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-119">You may need to download some data from a web service when a button is pressed, but don’t want to block the UI thread.</span></span> <span data-ttu-id="39c5b-120">이 작업은 간단히 다음과 같이 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-120">It can be accomplished simply like this:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

downloadButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI as the request
    // from the web service is happening.
    //
    // The UI thread is now free to perform other work.
    var stringData = await _httpClient.GetStringAsync(URL);
    DoSomethingWithData(stringData);
};
```

<span data-ttu-id="39c5b-121">이제 끝났습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-121">And that’s it!</span></span> <span data-ttu-id="39c5b-122">이 코드는 Task 개체 조작 시 위험에 빠지지 않고 의도(일부 데이터를 비동기식으로 다운로드)를 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-122">The code expresses the intent (downloading some data asynchronously) without getting bogged down in interacting with Task objects.</span></span>

### <a name="cpu-bound-example-performing-a-calculation-for-a-game"></a><span data-ttu-id="39c5b-123">CPU 바인딩된 예제: 게임에 대한 계산 수행</span><span class="sxs-lookup"><span data-stu-id="39c5b-123">CPU-bound Example: Performing a Calculation for a Game</span></span>

<span data-ttu-id="39c5b-124">단추를 누르면 화면의 많은 적에게 손상을 입힐 수 있는 모바일 게임을 작성한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-124">Say you're writing a mobile game where pressing a button can inflict damage on many enemies on the screen.</span></span>  <span data-ttu-id="39c5b-125">손상 계산을 수행하는 것은 부담이 클 수 있고 UI 스레드에서 이 작업을 수행하면 계산이 수행될 때 게임이 일시 중지되는 것처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-125">Performing the damage calculation can be expensive, and doing it on the UI thread would make the game appear to pause as the calculation is performed!</span></span>

<span data-ttu-id="39c5b-126">이 작업을 처리하는 가장 좋은 방법은 `Task.Run`을 사용하여 작업을 수행하는 백그라운드 스레드를 시작하고 결과를 `await`하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-126">The best way to handle this is to start a background thread which does the work using `Task.Run`, and `await` its result.</span></span>  <span data-ttu-id="39c5b-127">이렇게 하면 작업이 수행되고 있을 때 UI가 부드럽게 느껴질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-127">This will allow the UI to feel smooth as the work is being done.</span></span>

```csharp
private DamageResult CalculateDamageDone()
{
    // Code omitted:
    //
    // Does an expensive calculation and returns
    // the result of that calculation.
}


calculateButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI while CalculateDamageDone()
    // performs its work.  The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

<span data-ttu-id="39c5b-128">됐습니다!</span><span class="sxs-lookup"><span data-stu-id="39c5b-128">And that's it!</span></span>  <span data-ttu-id="39c5b-129">이 코드는 단추 클릭 이벤트의 의도를 표현하고, 백그라운드 스레드를 수동으로 관리할 필요가 없고, 비차단 방식으로 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-129">This code cleanly expresses the intent of the button's click event, it doesn't require managing a background thread manually, and it does so in a non-blocking way.</span></span>

### <a name="what-happens-under-the-covers"></a><span data-ttu-id="39c5b-130">백그라운드에서 수행되는 작업</span><span class="sxs-lookup"><span data-stu-id="39c5b-130">What happens under the covers</span></span>

<span data-ttu-id="39c5b-131">비동기 작업이 관련된 많은 조각 이동이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-131">There's a lot of moving pieces where asynchronous operations are concerned.</span></span>  <span data-ttu-id="39c5b-132">`Task` 및 `Task<T>`의 백그라운드에서 수행되는 작업이 궁금하면 [세부 비동기](../standard/async-in-depth.md) 문서를 체크 아웃하여 자세한 내용을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="39c5b-132">If you're curious about what's happening underneath the covers of `Task` and `Task<T>`, checkout the [Async in-depth](../standard/async-in-depth.md) article for more information.</span></span>

<span data-ttu-id="39c5b-133">C#에서는 컴파일러가 해당 코드를, `await`에 도달할 때 실행을 양도하고 백그라운드 작업이 완료될 때 실행을 다시 시작하는 것과 같은 작업을 추적하는 상태 시스템으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-133">On the C# side of things, the compiler transforms your code into a state machine which keeps track of things like yielding execution when an `await` is reached and resuming execution when a background job has finished.</span></span>

<span data-ttu-id="39c5b-134">이론적으로 보면 이 변환은 [비동기 약속 모델](https://en.wikipedia.org/wiki/Futures_and_promises)입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-134">For the theoretically-inclined, this is an implementation of the [Promise Model of asynchrony](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>

## <a name="key-pieces-to-understand"></a><span data-ttu-id="39c5b-135">이해해야 하는 주요 부분</span><span class="sxs-lookup"><span data-stu-id="39c5b-135">Key Pieces to Understand</span></span>

*   <span data-ttu-id="39c5b-136">비동기 코드는 I/O 바인딩된 코드와 CPU 바인딩된 코드에 둘 다 사용할 수 있지만 시나리오마다 다르게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-136">Async code can be used for both I/O-bound and CPU-bound code, but differently for each scenario.</span></span>
*   <span data-ttu-id="39c5b-137">비동기 코드는 백그라운드에서 수행되는 작업을 모델링하는 데 사용되는 구문인 `Task<T>` 및 `Task`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-137">Async code uses `Task<T>` and `Task`, which are constructs used to model work being done in the background.</span></span>
* <span data-ttu-id="39c5b-138">`async` 키워드는 본문에서 `await` 키워드를 사용할 수 있는 비동기 메서드로 메서드를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-138">The `async` keyword turns a method into an async method, which allows you to use the `await` keyword in its body.</span></span>
*   <span data-ttu-id="39c5b-139">`await` 키워드가 적용되면 이 키워드는 호출 메서드를 일시 중단하고 대기 작업이 완료할 때까지 제어 권한을 다시 호출자에게 양도합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-139">When the `await` keyword is applied, it suspends the calling method and yields control back to its caller until the awaited task is complete.</span></span>
*   <span data-ttu-id="39c5b-140">`await`는 비동기 메서드 내부에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-140">`await` can only be used inside an async method.</span></span>

## <a name="recognize-cpu-bound-and-io-bound-work"></a><span data-ttu-id="39c5b-141">CPU 바인딩된 작업 및 I/O 바인딩된 작업 인식</span><span class="sxs-lookup"><span data-stu-id="39c5b-141">Recognize CPU-Bound and I/O-Bound Work</span></span>

<span data-ttu-id="39c5b-142">이 가이드의 처음 두 예제에서는 I/O 바인딩된 작업과 CPU 바인딩된 작업에 `async` 및 `await`를 사용하는 방법을 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-142">The first two examples of this guide showed how you can use `async` and `await` for I/O-bound and CPU-bound work.</span></span>  <span data-ttu-id="39c5b-143">이 방법은 수행해야 하는 작업이 I/O 바인딩된 작업 또는 CPU 바인딩된 작업일 경우 이를 식별할 수 있는 키입니다. 이 방법이 코드 성능에 큰 영향을 미칠 수 있고 잠재적으로 특정 구문을 잘못 사용하게 될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-143">It's key that you can identify when a job you need to do is I/O-bound or CPU-bound, because it can greatly affect the performance of your code and could potentially lead to misusing certain constructs.</span></span>

<span data-ttu-id="39c5b-144">다음은 코드를 작성하기 전에 질문해야 하는 두 가지 질문입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-144">Here are two questions you should ask before you write any code:</span></span>

1. <span data-ttu-id="39c5b-145">코드가 데이터베이스의 데이터와 같은 무엇인가를 “기다리게” 되나요?</span><span class="sxs-lookup"><span data-stu-id="39c5b-145">Will your code be "waiting" for something, such as data from a database?</span></span>

    <span data-ttu-id="39c5b-146">대답이 "예"이면 **I/O 바인딩된** 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-146">If your answer is "yes", then your work is **I/O-bound**.</span></span>

2. <span data-ttu-id="39c5b-147">코드가 매우 부담이 큰 계산을 수행하게 되나요?</span><span class="sxs-lookup"><span data-stu-id="39c5b-147">Will your code be performing a very expensive computation?</span></span>

    <span data-ttu-id="39c5b-148">대답이 "예"이면 **CPU 바인딩된** 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-148">If you answered "yes", then your work is **CPU-bound**.</span></span>
    
<span data-ttu-id="39c5b-149">**I/O 바인딩된** 작업이 있을 경우 `Task.Run` *없이* `async` 및 `await`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-149">If the work you have is **I/O-bound**, use `async` and `await` *without* `Task.Run`.</span></span>  <span data-ttu-id="39c5b-150">작업 병렬 라이브러리를 사용*하면 안 됩니다*.</span><span class="sxs-lookup"><span data-stu-id="39c5b-150">You *should not* use the Task Parallel Library.</span></span>  <span data-ttu-id="39c5b-151">그 이유는 [세부 비동기 문서](../standard/async-in-depth.md)에서 간단히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-151">The reason for this is outlined in the [Async in Depth article](../standard/async-in-depth.md).</span></span>

<span data-ttu-id="39c5b-152">**CPU 바인딩된** 작업이 있고 빠른 응답이 필요할 경우 `async` 및 `await`를 사용하지만 `Task.Run`을 사용하여 또 다른 스레드에서 작업을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-152">If the work you have is **CPU-bound** and you care about responsiveness, use `async` and `await` but spawn the work off on another thread *with* `Task.Run`.</span></span>  <span data-ttu-id="39c5b-153">작업이 동시성 및 병렬 처리에 해당할 경우 작업 병렬 라이브러리를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-153">If the work is appropriate for concurrency and parallelism, you should also consider using the Task Parallel Library.</span></span>

<span data-ttu-id="39c5b-154">또한 항상 코드 실행을 측정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-154">Additionally, you should always measure the execution of your code.</span></span>  <span data-ttu-id="39c5b-155">예를 들어 CPU 바인딩된 작업이 다중 스레딩 시 컨텍스트 전환의 오버헤드에 비해 부담이 크지 않은 상황이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-155">For example, you may find yourself in a situation where your CPU-bound work is not costly enough compared with the overhead of context switches when multithreading.</span></span>  <span data-ttu-id="39c5b-156">모든 선택에는 절충점이 있습니다. 상황에 맞는 올바른 절충점을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-156">Every choice has its tradeoff, and you should pick the correct tradeoff for your situation.</span></span>

## <a name="more-examples"></a><span data-ttu-id="39c5b-157">추가 예제</span><span class="sxs-lookup"><span data-stu-id="39c5b-157">More Examples</span></span>

<span data-ttu-id="39c5b-158">다음 예제에서는 C#에서 비동기 코드를 작성할 수 있는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-158">The following examples demonstrate various ways you can write async code in C#.</span></span>  <span data-ttu-id="39c5b-159">예제에서는 발생할 수 있는 몇 가지 시나리오를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-159">They cover a few different scenarios you may come across.</span></span>

### <a name="extracting-data-from-a-network"></a><span data-ttu-id="39c5b-160">네트워크에서 데이터 추출</span><span class="sxs-lookup"><span data-stu-id="39c5b-160">Extracting Data from a Network</span></span>

<span data-ttu-id="39c5b-161">이 코드 조각은 www.dotnetfoundation.org에서 HTML을 다운로드하고 문자열 ".NET"이 HTML에서 발생하는 횟수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-161">This snippet downloads the HTML from www.dotnetfoundation.org and counts the number of times the string ".NET" occurs in the HTML.</span></span>  <span data-ttu-id="39c5b-162">또한 ASP.NET MVC를 통해 이 작업을 수행하는 웹 컨트롤러 메서드를 정의하여 숫자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-162">It uses ASP.NET MVC to define a web controller method which performs this task, returning the number.</span></span>

> [!NOTE]
> <span data-ttu-id="39c5b-163">프로덕션 코드에서 HTML 구문 분석을 수행하려는 경우 정규식을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="39c5b-163">If you plan on doing HTML parsing in production code, don't use regular expressions.</span></span> <span data-ttu-id="39c5b-164">대신 구문 분석 라이브러리를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="39c5b-164">Use a parsing library instead.</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet]
[Route("DotNetCount")]
public async Task<int> GetDotNetCountAsync()
{
    // Suspends GetDotNetCountAsync() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.DownloadStringAsync("http://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

<span data-ttu-id="39c5b-165">다음은 단추가 눌릴 때 같은 작업을 수행하는 유니버설 Windows 앱용으로 작성된 동일한 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-165">Here's the same scenario written for a Universal Windows App, which performs the same task when a Button is pressed:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void SeeTheDotNets_Click(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("http://www.dotnetfoundation.org");

    // Any other work on the UI thread can be done here, such as enabling a Progress Bar.
    // This is important to do here, before the "await" call, so that the user
    // sees the progress bar before execution of this method is yielded.
    NetworkProgressBar.IsEnabled = true;
    NetworkProgressBar.Visibility = Visibility.Visible;

    // The await operator suspends SeeTheDotNets_Click, returning control to its caller.
    // This is what allows the app to be responsive and not hang on the UI thread.
    var html = await getDotNetFoundationHtmlTask;
    int count = Regex.Matches(html, @"\.NET").Count;

    DotNetCountLabel.Text = $"Number of .NETs on dotnetfoundation.org: {count}";

    NetworkProgressBar.IsEnabled = false;
    NetworkProgressBar.Visibility = Visibility.Collapsed;
}
```

### <a name="waiting-for-multiple-tasks-to-complete"></a><span data-ttu-id="39c5b-166">여러 작업이 완료할 때까지 대기</span><span class="sxs-lookup"><span data-stu-id="39c5b-166">Waiting for Multiple Tasks to Complete</span></span>

<span data-ttu-id="39c5b-167">동시에 데이터의 여러 부분을 검색해야 하는 상황이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-167">You may find yourself in a situation where you need to retrieve multiple pieces of data concurrently.</span></span>  <span data-ttu-id="39c5b-168">`Task` API에는 여러 백그라운드 작업에서 비차단 대기를 수행하는 비동기 코드를 작성할 수 있는 `Task.WhenAll` 및 `Task.WhenAny` 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-168">The `Task` API contains two methods, `Task.WhenAll` and `Task.WhenAny` which allow you to write asynchronous code which performs a non-blocking wait on multiple background jobs.</span></span>

<span data-ttu-id="39c5b-169">이 예제에서는 `userId` 집합에 대한 `User` 데이터를 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-169">This example shows how you might grab `User` data for a set of `userId`s.</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<IEnumerable<User>> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = new List<Task<User>>();
    
    foreach (int userId in userIds)
    {
        getUserTasks.Add(GetUserAsync(userId));
    }
    
    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="39c5b-170">다음은 LINQ를 사용하여 이 코드를 더 간결하게 작성하는 또 다른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-170">Here's another way to write this a bit more succinctly, using LINQ:</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<User[]> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = userIds.Select(id => GetUserAsync(id));
    return await Task.WhenAll(getUserTasks);
}
```
<span data-ttu-id="39c5b-171">코드 양은 더 적지만 LINQ를 비동기 코드와 혼합할 경우 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="39c5b-171">Although it's less code, take care when mixing LINQ with asynchronous code.</span></span>  <span data-ttu-id="39c5b-172">LINQ는 연기된(지연) 실행을 사용하므로, `.ToList()` 또는 `.ToArray()` 호출을 반복하도록 생성된 시퀀스를 적용해야 비동기 호출이 `foreach()` 루프에서 수행되면 즉시 비동기 호출이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-172">Because LINQ uses deferred (lazy) execution, async calls won't happen immediately as they do in a `foreach()` loop unless you force the generated sequence to iterate with a call to `.ToList()` or `.ToArray()`.</span></span>

## <a name="important-info-and-advice"></a><span data-ttu-id="39c5b-173">중요한 정보 및 조언</span><span class="sxs-lookup"><span data-stu-id="39c5b-173">Important Info and Advice</span></span>

<span data-ttu-id="39c5b-174">비동기 프로그래밍이 비교적 직관적이지만 예상치 못한 동작을 방지할 수 있는 몇 가지 세부 정보를 기억해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-174">Although async programming is relatively straightforward, there are some details to keep in mind which can prevent unexpected behavior.</span></span>

*  <span data-ttu-id="39c5b-175">`async` **메서드에는 본문에** `await` **키워드가 있어야 합니다. 키워드가 없으면 양도되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="39c5b-175">`async` **methods need to have an** `await` **keyword in their body or they will never yield!**</span></span>

<span data-ttu-id="39c5b-176">기억해야 할 중요한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-176">This is important to keep in mind.</span></span>  <span data-ttu-id="39c5b-177">`await`가 `async` 메서드의 본문에서 사용되지 않으면 C# 컴파일러가 경고를 생성하지만 코드는 일반 메서드인 것처럼 컴파일 및 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-177">If `await` is not used in the body of an `async` method, the C# compiler will generate a warning, but the code will compile and run as if it were a normal method.</span></span>  <span data-ttu-id="39c5b-178">이 방법은 상당히 비효율적입니다. 비동기 메서드용으로 C# 컴파일러에서 생성된 상태 컴퓨터가 아무 작업도 수행하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-178">Note that this would also be incredibly inefficient, as the state machine generated by the C# compiler for the async method would not be accomplishing anything.</span></span>

*   <span data-ttu-id="39c5b-179">**작성하는 모든 비동기 메서드 이름의 접미사로 "Async"를 추가해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="39c5b-179">**You should add "Async" as the suffix of every async method name you write.**</span></span>

<span data-ttu-id="39c5b-180">이 규칙을 .NET에서 사용하여 동기 및 비동기 메서드를 훨씬 더 쉽게 구별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-180">This is the convention used in .NET to more-easily differentiate synchronous and asynchronous methods.</span></span> <span data-ttu-id="39c5b-181">코드에서 명시적으로 호출되지 않은 특정 메서드(예: 이벤트 처리기 또는 웹 컨트롤러 메서드)가 반드시 적용되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-181">Note that certain methods which aren’t explicitly called by your code (such as event handlers or web controller methods) don’t necessarily apply.</span></span> <span data-ttu-id="39c5b-182">이러한 메서드는 코드에서 명시적으로 호출되지 않으므로 명시적으로 명명하는 것은 별로 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-182">Because these are not explicitly called by your code, being explicit about their naming isn’t as important.</span></span>

*   <span data-ttu-id="39c5b-183">`async void`**는 이벤트 처리기에만 사용해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="39c5b-183">`async void` **should only be used for event handlers.**</span></span>

<span data-ttu-id="39c5b-184">이벤트에는 반환 형식이 없어서 `Task` 및 `Task<T>`를 사용할 수 없으므로 비동기 이벤트 처리기가 작동하도록 허용하는 유일한 방법은 `async void`입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-184">`async void` is the only way to allow asynchronous event handlers to work because events do not have return types (thus cannot make use of `Task` and `Task<T>`).</span></span> <span data-ttu-id="39c5b-185">`async void`의 다른 사용은 TAP 모델을 따르지 않고 다음과 같이 사용이 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-185">Any other use of `async void` does not follow the TAP model and can be challenging to use, such as:</span></span>

  *   <span data-ttu-id="39c5b-186">`async void` 메서드에서 throw된 예외는 해당 메서드 외부에서 catch될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-186">Exceptions thrown in an `async void` method can’t be caught outside of that method.</span></span>
  *   <span data-ttu-id="39c5b-187">`async void` 메서드는 테스트하기 매우 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-187">`async void` methods are very difficult to test.</span></span>
  *   <span data-ttu-id="39c5b-188">호출자가 `async void` 메서드를 비동기로 예상하지 않을 경우 이러한 메서드는 잘못된 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-188">`async void` methods can cause bad side effects if the caller isn’t expecting them to be async.</span></span>

*   <span data-ttu-id="39c5b-189">**LINQ 식에서 비동기 람다를 사용할 경우 신중하게 스레드**</span><span class="sxs-lookup"><span data-stu-id="39c5b-189">**Tread carefully when using async lambdas in LINQ expressions**</span></span>

<span data-ttu-id="39c5b-190">LINQ의 람다 식은 연기된 실행을 사용합니다. 즉, 예상치 않은 시점에 코드 실행이 끝날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-190">Lambda expressions in LINQ use deferred execution, meaning code could end up executing at a time when you’re not expecting it to.</span></span> <span data-ttu-id="39c5b-191">이 코드에 차단 작업을 도입하면 코드가 제대로 작성되지 않은 경우 교착 상태가 쉽게 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-191">The introduction of blocking tasks into this can easily result in a deadlock if not written correctly.</span></span> <span data-ttu-id="39c5b-192">또한 이 코드처럼 비동기 코드를 중첩하면 코드 실행에 대해 추론하기가 훨씬 더 어려울 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-192">Additionally, the nesting of asynchronous code like this can also make it more difficult to reason about the execution of the code.</span></span> <span data-ttu-id="39c5b-193">비동기 및 LINQ는 강력하지만 가능한 한 신중하고 분명하게 함께 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-193">Async and LINQ are powerful, but should be used together as carefully and clearly as possible.</span></span>

*   <span data-ttu-id="39c5b-194">**비차단 방식으로 작업을 기다리는 코드 작성**</span><span class="sxs-lookup"><span data-stu-id="39c5b-194">**Write code that awaits Tasks in a non-blocking manner**</span></span>

<span data-ttu-id="39c5b-195">작업이 완료될 때까지 대기하는 수단으로 현재 스레드를 차단하면 교착 상태가 발생하고 컨텍스트 스레드가 차단될 수 있고 훨씬 더 복잡한 오류 처리가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-195">Blocking the current thread as a means to wait for a Task to complete can result in deadlocks and blocked context threads, and can require significantly more complex error-handling.</span></span> <span data-ttu-id="39c5b-196">다음 표에서는 비차단 방식으로 작업 대기를 처리하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-196">The following table provides guidance on how to deal with waiting for Tasks in a non-blocking way:</span></span>

| <span data-ttu-id="39c5b-197">사용 방법</span><span class="sxs-lookup"><span data-stu-id="39c5b-197">Use this...</span></span> | <span data-ttu-id="39c5b-198">대체 방법</span><span class="sxs-lookup"><span data-stu-id="39c5b-198">Instead of this...</span></span> | <span data-ttu-id="39c5b-199">수행할 작업</span><span class="sxs-lookup"><span data-stu-id="39c5b-199">When wishing to do this</span></span> |
| --- | --- | --- |
| `await` | <span data-ttu-id="39c5b-200">`Task.Wait` 또는 `Task.Result`</span><span class="sxs-lookup"><span data-stu-id="39c5b-200">`Task.Wait` or `Task.Result`</span></span> | <span data-ttu-id="39c5b-201">백그라운드 작업의 결과 검색</span><span class="sxs-lookup"><span data-stu-id="39c5b-201">Retrieving the result of a background task</span></span> |
| `await Task.WhenAny` | `Task.WaitAny` | <span data-ttu-id="39c5b-202">작업이 완료될 때까지 대기</span><span class="sxs-lookup"><span data-stu-id="39c5b-202">Waiting for any task to complete</span></span> |
| `await Task.WhenAll` | `Task.WaitAll` | <span data-ttu-id="39c5b-203">모든 작업이 완료될 때까지 대기</span><span class="sxs-lookup"><span data-stu-id="39c5b-203">Waiting for all tasks to complete</span></span> |
| `await Task.Delay` | `Thread.Sleep` | <span data-ttu-id="39c5b-204">일정 기간 대기</span><span class="sxs-lookup"><span data-stu-id="39c5b-204">Waiting for a period of time</span></span> |

*   <span data-ttu-id="39c5b-205">**상태 저장 코드 작성 분량 감소**</span><span class="sxs-lookup"><span data-stu-id="39c5b-205">**Write less stateful code**</span></span>

<span data-ttu-id="39c5b-206">전역 개체의 상태나 특정 메서드의 실행에 의존하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="39c5b-206">Don’t depend on the state of global objects or the execution of certain methods.</span></span> <span data-ttu-id="39c5b-207">대신, 메서드의 반환 값에만 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-207">Instead, depend only on the return values of methods.</span></span> <span data-ttu-id="39c5b-208">이유</span><span class="sxs-lookup"><span data-stu-id="39c5b-208">Why?</span></span>

  *   <span data-ttu-id="39c5b-209">코드를 더 쉽게 추론할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-209">Code will be easier to reason about.</span></span>
  *   <span data-ttu-id="39c5b-210">코드를 더 쉽게 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-210">Code will be easier to test.</span></span>
  *   <span data-ttu-id="39c5b-211">비동기 및 동기 코드를 훨씬 더 쉽게 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-211">Mixing async and synchronous code is far simpler.</span></span>
  *   <span data-ttu-id="39c5b-212">일반적으로 함께 경합 상태를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-212">Race conditions can typically be avoided altogether.</span></span>
  *   <span data-ttu-id="39c5b-213">반환 값에 의존하면 비동기 코드를 간단히 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-213">Depending on return values makes coordinating async code simple.</span></span>
  *   <span data-ttu-id="39c5b-214">(이점) 이 방법은 실제로 종속성 주입에도 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-214">(Bonus) it works really well with dependency injection.</span></span>

<span data-ttu-id="39c5b-215">권장되는 목적은 코드에서 완전하거나 거의 완전한 [참조 투명성](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29)을 달성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-215">A recommended goal is to achieve complete or near-complete [Referential Transparency](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in your code.</span></span> <span data-ttu-id="39c5b-216">이렇게 하면 확실히 예측 가능하고, 테스트 가능하고, 유지 관리 가능한 코드베이스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-216">Doing so will result in an extremely predictable, testable, and maintainable codebase.</span></span>

## <a name="other-resources"></a><span data-ttu-id="39c5b-217">기타 리소스</span><span class="sxs-lookup"><span data-stu-id="39c5b-217">Other Resources</span></span>

* <span data-ttu-id="39c5b-218">[세부 비동기](../standard/async-in-depth.md)에서는 작업이 어떻게 작동하는지 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-218">[Async in-depth](../standard/async-in-depth.md) provides more information about how Tasks work.</span></span>
* <span data-ttu-id="39c5b-219">Lucian Wischik의 [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async)(비동기에 대한 6가지 필수 팁)는 비동기 프로그래밍에 대한 훌륭한 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="39c5b-219">Lucian Wischik's [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) are a wonderful resource for async programming</span></span>
