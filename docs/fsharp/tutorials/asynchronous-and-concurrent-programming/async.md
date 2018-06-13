---
title: 'F #에서 비동기 프로그래밍'
description: '언어 수준 프로그래밍 모델을 사용 하기 편리 하며 자연 언어를 통해 F # 비동기 프로그래밍은 수행 하는 방법을 알아봅니다.'
ms.date: 06/20/2016
ms.openlocfilehash: 93ecd05efc493489435214dcd7ae78fffcccec1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566875"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="c961a-103">F #에서 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="c961a-103">Async Programming in F#</span></span> #

> [!NOTE]
> <span data-ttu-id="c961a-104">이 문서에 일부 잘못 된 검색 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-104">Some inaccuracies have been discovered in this article.</span></span>  <span data-ttu-id="c961a-105">다시 작성 되 고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-105">It is being rewritten.</span></span>  <span data-ttu-id="c961a-106">참조 [문제 #666](https://github.com/dotnet/docs/issues/666) 변경 내용에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-106">See [Issue #666](https://github.com/dotnet/docs/issues/666) to learn about the changes.</span></span>

<span data-ttu-id="c961a-107">비동기 프로그래밍의 F #을 사용 하기 편리 하며 언어에 자연 스러운 되도록 설계 언어 수준 프로그래밍 모델을 통해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-107">Async programming in F# can be accomplished through a language-level programming model designed to be easy to use and natural to the language.</span></span>

<span data-ttu-id="c961a-108">F #에서 비동기 프로그래밍의 핵심은 `Async<'T>`, 백그라운드에서 실행 되도록 트리거될 수 있는 작업의 표현을 여기서 `'T` 은 특수를 통해 반환 되는 형식 중 하나 `return` 키워드 또는 `unit` 비동기 워크플로 없는 경우 반환할 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-108">The core of async programming in F# is `Async<'T>`, a representation of work that can be triggered to run in the background, where `'T` is either the type returned via the special `return` keyword or `unit` if the async workflow has no result to return.</span></span>

<span data-ttu-id="c961a-109">주요 개념 이해 하는 비동기 식의 형식이 된다는 점입니다 `Async<'T>`,이 단순히 _사양_ 비동기 컨텍스트에서 수행 하는 작업의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-109">The key concept to understand is that an async expression’s type is `Async<'T>`, which is merely a _specification_ of work to be done in an asynchronous context.</span></span> <span data-ttu-id="c961a-110">명시적으로 시작 하는 기능 중 하나를 시작 하기 전 까지는 실행 되지 않습니다 (예: `Async.RunSynchronously`).</span><span class="sxs-lookup"><span data-stu-id="c961a-110">It is not executed until you explicitly start it with one of the starting functions (such as `Async.RunSynchronously`).</span></span> <span data-ttu-id="c961a-111">작업을 수행 하는 방법에 대 한 다른 방법 이지만 실제로 매우 간단 되 고을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-111">Although this is a different way of thinking about doing work, it ends up being quite simple in practice.</span></span>

<span data-ttu-id="c961a-112">예를 들어 주 스레드를 차단 하지 않고 HTML dotnetfoundation.org에서 다운로드 하 려 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-112">For example, say you wanted to download the HTML from dotnetfoundation.org without blocking the main thread.</span></span> <span data-ttu-id="c961a-113">다음과 같이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-113">You can accomplish it like this:</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()

        // Execution of fetchHtmlAsync won't continue until the result
        // of AsyncDownloadString is bound.
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

<span data-ttu-id="c961a-114">이제 끝났습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-114">And that’s it!</span></span> <span data-ttu-id="c961a-115">사용을 제외 `async`, `let!`, 및 `return`, 방금 일반 F # 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-115">Aside from the use of `async`, `let!`, and `return`, this is just normal F# code.</span></span>

<span data-ttu-id="c961a-116">주목할 만한 있는 몇 가지 구문을 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-116">There are a few syntactical constructs which are worth noting:</span></span>

*   <span data-ttu-id="c961a-117">`let!` (다른 컨텍스트에서 실행)이 표시 되는 비동기 식의 결과 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-117">`let!` binds the result of an async expression (which runs on another context).</span></span>
*   <span data-ttu-id="c961a-118">`use!` 동일 하 게 작동 `let!`, 하지만 범위를 벗어날 때 바인딩된 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-118">`use!` works just like `let!`, but disposes its bound resources when it goes out of scope.</span></span>
*   <span data-ttu-id="c961a-119">`do!` 아무 것도 반환 하지 않는 비동기 워크플로 await 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-119">`do!` will await an async workflow which doesn’t return anything.</span></span>
*   <span data-ttu-id="c961a-120">`return` 단순히 비동기 식에서 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-120">`return` simply returns a result from an async expression.</span></span>
*   <span data-ttu-id="c961a-121">`return!` 다른 비동기 워크플로 실행 하 고 해당 반환 값을 결과로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-121">`return!` executes another async workflow and returns its return value as a result.</span></span>

<span data-ttu-id="c961a-122">또한 일반 `let`, `use`, 및 `do` 키워드는 일반 기능에서와 마찬가지로 비동기 버전과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-122">Additionally, normal `let`, `use`, and `do` keywords can be used alongside the async versions just as they would in a normal function.</span></span>

## <a name="how-to-start-async-code-in-f"></a><span data-ttu-id="c961a-123">F #에서 비동기 코드를 시작 하는 방법</span><span class="sxs-lookup"><span data-stu-id="c961a-123">How to start Async Code in F#</span></span> #

<span data-ttu-id="c961a-124">앞서 언급 했 듯이 비동기 코드는 명시적으로 시작 하는 다른 컨텍스트에서 수행 하는 작업에 대 한 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-124">As mentioned earlier, async code is a specification of work to be done in another context which needs to be explicitly started.</span></span> <span data-ttu-id="c961a-125">이렇게 하려면 두 가지 기본 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-125">Here are two primary ways to accomplish this:</span></span>

1.  <span data-ttu-id="c961a-126">`Async.RunSynchronously` 다른 스레드에서 비동기 워크플로 시작 하 고 그 결과 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-126">`Async.RunSynchronously` will start an async workflow on another thread and await its result.</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

 // Execution will pause until fetchHtmlAsync finishes
 let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2.  <span data-ttu-id="c961a-127">`Async.Start` 다른 스레드에서 비동기 워크플로 시작 되며 됩니다 **하지** 그 결과 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-127">`Async.Start` will start an async workflow on another thread, and will **not** await its result.</span></span>

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

<span data-ttu-id="c961a-128">다른 방법 보다 구체적인 시나리오에 사용할 수 있는 비동기 워크플로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-128">There are other ways to start an async workflow available for more specific scenarios.</span></span> <span data-ttu-id="c961a-129">자세히 [비동기 참조에서](https://msdn.microsoft.com/library/ee370232.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-129">They are detailed [in the Async reference](https://msdn.microsoft.com/library/ee370232.aspx).</span></span>

### <a name="a-note-on-threads"></a><span data-ttu-id="c961a-130">스레드에 대 한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="c961a-130">A Note on Threads</span></span>

<span data-ttu-id="c961a-131">"다른 스레드에서" 라는 구를 위에서 언급 한 있다는 점에 주의 해야 하지만 **비동기 워크플로 외관 하는 것이 아니며 다중 스레딩**합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-131">The phrase "on another thread" is mentioned above, but it is important to know that **this does not mean that async workflows are a facade for multithreading**.</span></span> <span data-ttu-id="c961a-132">워크플로 실제로 "이동"으로 적은 양의 유용한 작업을 수행 하는 시간에 대 한 대출 스레드 간에 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-132">The workflow actually "jumps" between threads, borrowing them for a small amount of time to do useful work.</span></span> <span data-ttu-id="c961a-133">대기 하는 경우 비동기 워크플로 효과적 으로"" (예: 결과를 반환 하는 네트워크 호출에 대 한 대기 중), 시간에 연결 된 모든 스레드에서 다른 작업에 유용한 작업을 이동 do까지 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-133">When an async workflow is effectively "waiting" (for example, waiting for a network call to return something), any thread it was borrowing at the time is freed up to go do useful work on something else.</span></span> <span data-ttu-id="c961a-134">이 통해 비동기 워크플로에 최대한 효율적으로 실행 하는 시스템을 활용 하 여 특히 대규모 I/O 시나리오에 대 한 강력한 끌고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-134">This allows async workflows to utilize the system they run on as effectively as possible, and makes them especially strong for high-volume I/O scenarios.</span></span>

## <a name="how-to-add-parallelism-to-async-code"></a><span data-ttu-id="c961a-135">비동기 코드를 병렬 처리를 추가 하는 방법</span><span class="sxs-lookup"><span data-stu-id="c961a-135">How to Add Parallelism to Async Code</span></span>

<span data-ttu-id="c961a-136">경우에 따라 수 있습니다 병렬로 여러 비동기 작업을 수행의 결과 수집 및 하 어떤 식으로든에서이 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-136">Sometimes you may need to perform multiple asynchronous jobs in parallel, collect their results, and interpret them in some way.</span></span> <span data-ttu-id="c961a-137">`Async.Parallel` 포함 하도록 강제 지정 하는 작업 병렬 라이브러리를 사용할 필요 없이이 작업을 수행할 수 있습니다 `Task<'T>` 및 `Async<'T>` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-137">`Async.Parallel` allows you to do this without needing to use the Task Parallel Library, which would involve needing to coerce `Task<'T>` and `Async<'T>` types.</span></span>

<span data-ttu-id="c961a-138">다음 예제에서는 ´ ֲ `Async.Parallel` HTML를 동시에 4 개의 인기 있는 사이트에서 다운로드를 완료 하는 데 해당 작업에 대 한 기다린 다음 다운로드 한를 HTML을 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-138">The following example will use `Async.Parallel` to download the HTML from four popular sites in parallel, wait for those tasks to complete, and then print the HTML which was downloaded.</span></span>

```fsharp
open System
open System.Net

let urlList = 
    [ "https://www.microsoft.com"
      "https://www.google.com"
      "https://www.amazon.com"
      "https://www.facebook.com" ]

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let getHtmlList urls =
    urls
    |> Seq.map fetchHtmlAsync   // Build an Async<'T> for each site
    |> Async.Parallel           // Returns an Async<'T []>
    |> Async.RunSynchronously   // Wait for the result of the parallel work

let htmlList = getHtmlList urlList

// We now have the downloaded HTML for each site!
for html in htmlList do
    printfn "%s" html
```

## <a name="important-info-and-advice"></a><span data-ttu-id="c961a-139">중요한 정보 및 조언</span><span class="sxs-lookup"><span data-stu-id="c961a-139">Important Info and Advice</span></span>

*   <span data-ttu-id="c961a-140">사용할 수 있도록 모든 함수의 끝에 "Async"를 추가</span><span class="sxs-lookup"><span data-stu-id="c961a-140">Append "Async" to the end of any functions you’ll consume</span></span>

 <span data-ttu-id="c961a-141">명명 규칙 뿐 이지만, API 검색 기능 등을 쉽게 수행할지 않습니다 것 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-141">Although this is just a naming convention, it does make things like API discoverability easier.</span></span> <span data-ttu-id="c961a-142">동일한 루틴의 동기 및 비동기 버전이 없을 경우에 특히 명시적으로 지정 되는 이름을 통해 비동기 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-142">Particularly if there are synchronous and asynchronous versions of the same routine, it’s a good idea to explicitly state which is asynchronous via the name.</span></span>

*   <span data-ttu-id="c961a-143">컴파일러에 수신!</span><span class="sxs-lookup"><span data-stu-id="c961a-143">Listen to the compiler!</span></span>

 <span data-ttu-id="c961a-144">F #의 컴파일러는 매우 엄격한 거의 없는 작업을 수행할 수 있도록 "async" 코드를 동기적으로 실행 같은 솔 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-144">F#’s compiler is very strict, making it nearly impossible to do something troubling like run "async" code synchronously.</span></span> <span data-ttu-id="c961a-145">경고를 발견할 경우 코드 않습니다 됩니다 생각 방법을 실행 하는 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-145">If you come across a warning, that’s a sign that the code won’t execute how you think it will.</span></span> <span data-ttu-id="c961a-146">만족도 매우 컴파일러를 만들 수 있습니다, 예상 대로 코드를 실행할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-146">If you can make the compiler happy, your code will most likely execute as expected.</span></span>

## <a name="for-the-cvb-programmer-looking-into-f"></a><span data-ttu-id="c961a-147">F #으로 C# /VB 프로그래머에 대 한</span><span class="sxs-lookup"><span data-stu-id="c961a-147">For the C#/VB Programmer Looking Into F#</span></span> #

<span data-ttu-id="c961a-148">이 섹션에서는 C#에서 비동기 모델에 익숙한 가정 / VB.</span><span class="sxs-lookup"><span data-stu-id="c961a-148">This section assumes you’re familiar with the async model in C#/VB.</span></span> <span data-ttu-id="c961a-149">없는 경우, [C#에서 비동기 프로그래밍](../../../csharp/async.md) 출발점입니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-149">If you are not, [Async Programming in C#](../../../csharp/async.md) is a starting point.</span></span>

<span data-ttu-id="c961a-150">C# /VB 비동기 모델 및 F # 비동기 모델 간에 근본적인 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-150">There is a fundamental difference between the C#/VB async model and the F# async model.</span></span>

<span data-ttu-id="c961a-151">반환 하는 함수를 호출 하는 경우는 `Task` 또는 `Task<'T>`, 해당 작업이 이미 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-151">When you call a function which returns a `Task` or `Task<'T>`, that job has already begun execution.</span></span> <span data-ttu-id="c961a-152">반환 된 핸들이 이미 실행 중인 비동기 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-152">The handle returned represents an already-running asynchronous job.</span></span> <span data-ttu-id="c961a-153">반면, 호출 하는 경우 비동기 함수에서 F #는 `Async<'a>` 반환 될 작업을 나타냅니다 **생성** 특정 시점에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-153">In contrast, when you call an async function in F#, the `Async<'a>` returned represents a job which will be **generated** at some point.</span></span> <span data-ttu-id="c961a-154">이 모델 이해은 F #에서 비동기 작업을 함께 연결 될 수 있기 때문에 강력한 더 쉽게 조건에 따라 수행 하 고 컨트롤의 상세한을 사용 하 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-154">Understanding this model is powerful, because it allows for asynchronous jobs in F# to be chained together easier, performed conditionally, and be started with a finer grain of control.</span></span>

<span data-ttu-id="c961a-155">다른 몇 가지 유사점 및 차이점 주목할 만한 가치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-155">There are a few other similarities and differences worth noting.</span></span>

### <a name="similarities"></a><span data-ttu-id="c961a-156">유사성</span><span class="sxs-lookup"><span data-stu-id="c961a-156">Similarities</span></span>

*   <span data-ttu-id="c961a-157">`let!``use!`, 및 `do!` 유사 `await` 내에서 비동기 작업을 호출 하는 경우는 `async{ }` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-157">`let!`, `use!`, and `do!` are analogous to `await` when calling an async job from within an `async{ }` block.</span></span>

 <span data-ttu-id="c961a-158">키워드 세 개 내 에서만 사용할 수는 `async { }` 블록 방법과 유사 `await` 내 에서만 호출할 수는 `async` 메서드.</span><span class="sxs-lookup"><span data-stu-id="c961a-158">The three keywords can only be used within an `async { }` block, similar to how `await` can only be invoked inside an `async` method.</span></span> <span data-ttu-id="c961a-159">즉, `let!` 캡처하고 결과 사용 하려는 경우에 `use!` 는 동일 하지만 해당 리소스를 사용 하는 후 정리 해야 항목은 및 `do!` 끝나기를 값을 반환 하지 않고는 async 워크플로에 대해 기다려야 하는 경우에 대 한 것 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-159">In short, `let!` is for when you want to capture and use a result, `use!` is the same but for something whose resources should get cleaned after it’s used, and `do!` is for when you want to wait for an async workflow with no return value to finish before moving on.</span></span>

*   <span data-ttu-id="c961a-160">F # 비슷한 방법으로 데이터 병렬 처리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-160">F# supports data-parallelism in a similar way.</span></span>

 <span data-ttu-id="c961a-161">매우 다른 방식으로 작동 하기는 하지만 `Async.Parallel` 에 해당 `Task.WhenAll` 모두 완료 하는 경우 비동기 작업 집합의 결과 원하는의 시나리오에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-161">Although it operates very differently, `Async.Parallel` corresponds to `Task.WhenAll` for the scenario of wanting the results of a set of async jobs when they all complete.</span></span>

### <a name="differences"></a><span data-ttu-id="c961a-162">차이점</span><span class="sxs-lookup"><span data-stu-id="c961a-162">Differences</span></span>

*   <span data-ttu-id="c961a-163">중첩 된 `let!` 허용, 달리 중첩은 `await`</span><span class="sxs-lookup"><span data-stu-id="c961a-163">Nested `let!` is not allowed, unlike nested `await`</span></span>

 <span data-ttu-id="c961a-164">와 달리 `await`를 무기한으로 중첩 될 수 있는 `let!` 수 없으며 다른 내부에서 사용 하기 전에 바인딩된 결과 있어야 `let!`, `do!`, 또는 `use!`합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-164">Unlike `await`, which can be nested indefinitely, `let!` cannot and must have its result bound before using it inside of another `let!`, `do!`, or `use!`.</span></span>

*   <span data-ttu-id="c961a-165">취소 지원은 F # 보다 C#에서 간단한 / VB.</span><span class="sxs-lookup"><span data-stu-id="c961a-165">Cancellation support is simpler in F# than in C#/VB.</span></span>

 <span data-ttu-id="c961a-166">C# /VB에서의 실행을 통해 작업 중간의 취소를 지 원하는 검사 해야는 `IsCancellationRequested` 속성 또는 호출 `ThrowIfCancellationRequested()` 에 `CancellationToken` 비동기 메서드에 전달 되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-166">Supporting cancellation of a task midway through its execution in C#/VB requires checking the `IsCancellationRequested` property or calling `ThrowIfCancellationRequested()` on a `CancellationToken` object that’s passed into the async method.</span></span>

<span data-ttu-id="c961a-167">반면, F # 비동기 워크플로 더 자연스럽 게 취소할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-167">In contrast, F# async workflows are more naturally cancellable.</span></span> <span data-ttu-id="c961a-168">취소는 간단한 3 단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-168">Cancellation is a simple three-step process.</span></span>

1.  <span data-ttu-id="c961a-169">새 `CancellationTokenSource`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-169">Create a new `CancellationTokenSource`.</span></span>
2.  <span data-ttu-id="c961a-170">시작을 함수로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-170">Pass it into a starting function.</span></span>
3.  <span data-ttu-id="c961a-171">호출 `Cancel` 토큰에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-171">Call `Cancel` on the token.</span></span>

<span data-ttu-id="c961a-172">예제:</span><span class="sxs-lookup"><span data-stu-id="c961a-172">Example:</span></span>

```fsharp
open System
open System.Net

let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

let token = new CancellationTokenSource()
Async.Start (workflow, token)

// Immediately cancel uploadDataAsync after it's been started.
token.Cancel()
```

<span data-ttu-id="c961a-173">이제 끝났습니다.</span><span class="sxs-lookup"><span data-stu-id="c961a-173">And that’s it!</span></span>

## <a name="further-resources"></a><span data-ttu-id="c961a-174">추가 리소스:</span><span class="sxs-lookup"><span data-stu-id="c961a-174">Further resources:</span></span>

*   [<span data-ttu-id="c961a-175">MSDN에서 비동기 워크플로</span><span class="sxs-lookup"><span data-stu-id="c961a-175">Async Workflows on MSDN</span></span>](https://msdn.microsoft.com/library/dd233250.aspx)
*   [<span data-ttu-id="c961a-176">F #에 대 한 비동기 시퀀스</span><span class="sxs-lookup"><span data-stu-id="c961a-176">Asynchronous Sequences for F#</span></span>](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [<span data-ttu-id="c961a-177">F # 데이터 HTTP 유틸리티</span><span class="sxs-lookup"><span data-stu-id="c961a-177">F# Data HTTP Utilities</span></span>](https://fsharp.github.io/FSharp.Data/library/Http.html)
