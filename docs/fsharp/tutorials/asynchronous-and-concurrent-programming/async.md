---
title: 'F #에서 비동기 프로그래밍'
description: '언어 수준 프로그래밍 모델을 사용 하기 편리 하며 자연 언어를 통해 F # 비동기 프로그래밍은 수행 하는 방법을 알아봅니다.'
keywords: .NET, .NET Core
author: cartermp
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f9196bfc-b8a8-4d33-8b53-0dcbd58a69d8
ms.openlocfilehash: c3fde46e804b7acac78d3ce5454a3c6f806e24e7
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="async-programming-in-f"></a>F #에서 비동기 프로그래밍 #

> [!NOTE]
> 이 문서에 일부 잘못 된 검색 된 합니다.  다시 작성 되 고 됩니다.  참조 [문제 #666](https://github.com/dotnet/docs/issues/666) 변경 내용에 대 한 자세한 내용은 합니다.

비동기 프로그래밍의 F #을 사용 하기 편리 하며 언어에 자연 스러운 되도록 설계 언어 수준 프로그래밍 모델을 통해 수행할 수 있습니다.

F #에서 비동기 프로그래밍의 핵심은 `Async<'T>`, 백그라운드에서 실행 되도록 트리거될 수 있는 작업의 표현을 여기서 `'T` 은 특수를 통해 반환 되는 형식 중 하나 `return` 키워드 또는 `unit` 비동기 워크플로 없는 경우 반환할 결과입니다.

주요 개념 이해 하는 비동기 식의 형식이 된다는 점입니다 `Async<'T>`,이 단순히 _사양_ 비동기 컨텍스트에서 수행 하는 작업의 합니다. 명시적으로 시작 하는 기능 중 하나를 시작 하기 전 까지는 실행 되지 않습니다 (예: `Async.RunSynchronously`). 작업을 수행 하는 방법에 대 한 다른 방법 이지만 실제로 매우 간단 되 고을 종료 합니다.

예를 들어 주 스레드를 차단 하지 않고 HTML dotnetfoundation.org에서 다운로드 하 려 합니다. 다음과 같이 수행할 수 있습니다.

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

이제 끝났습니다. 사용을 제외 `async`, `let!`, 및 `return`, 방금 일반 F # 코드입니다.

주목할 만한 있는 몇 가지 구문을 가지가 있습니다.

*   `let!` (다른 컨텍스트에서 실행)이 표시 되는 비동기 식의 결과 바인딩합니다.
*   `use!` 동일 하 게 작동 `let!`, 하지만 범위를 벗어날 때 바인딩된 리소스를 삭제 합니다.
*   `do!` 아무 것도 반환 하지 않는 비동기 워크플로 await 됩니다.
*   `return` 단순히 비동기 식에서 결과 반환 합니다.
*   `return!` 다른 비동기 워크플로 실행 하 고 해당 반환 값을 결과로 반환 합니다.

또한 일반 `let`, `use`, 및 `do` 키워드는 일반 기능에서와 마찬가지로 비동기 버전과 함께 사용할 수 있습니다.

## <a name="how-to-start-async-code-in-f"></a>F #에서 비동기 코드를 시작 하는 방법 #

앞서 언급 했 듯이 비동기 코드는 명시적으로 시작 하는 다른 컨텍스트에서 수행 하는 작업에 대 한 사양입니다. 이렇게 하려면 두 가지 기본 방법은 다음과 같습니다.

1.  `Async.RunSynchronously` 다른 스레드에서 비동기 워크플로 시작 하 고 그 결과 기다립니다.

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

2.  `Async.Start` 다른 스레드에서 비동기 워크플로 시작 되며 됩니다 **하지** 그 결과 기다립니다.

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

다른 방법 보다 구체적인 시나리오에 사용할 수 있는 비동기 워크플로 시작할 수 있습니다. 자세히 [비동기 참조에서](https://msdn.microsoft.com/library/ee370232.aspx)합니다.

### <a name="a-note-on-threads"></a>스레드에 대 한 참고 사항

"다른 스레드에서" 라는 구를 위에서 언급 한 있다는 점에 주의 해야 하지만 **비동기 워크플로 외관 하는 것이 아니며 다중 스레딩**합니다. 워크플로 실제로 "이동"으로 적은 양의 유용한 작업을 수행 하는 시간에 대 한 대출 스레드 간에 됩니다. 대기 하는 경우 비동기 워크플로 효과적 으로"" (예: 결과를 반환 하는 네트워크 호출에 대 한 대기 중), 시간에 연결 된 모든 스레드에서 다른 작업에 유용한 작업을 이동 do까지 해제 됩니다. 이 통해 비동기 워크플로에 최대한 효율적으로 실행 하는 시스템을 활용 하 여 특히 대규모 I/O 시나리오에 대 한 강력한 끌고 있습니다.

## <a name="how-to-add-parallelism-to-async-code"></a>비동기 코드를 병렬 처리를 추가 하는 방법

경우에 따라 수 있습니다 병렬로 여러 비동기 작업을 수행의 결과 수집 및 하 어떤 식으로든에서이 해석 합니다. `Async.Parallel` 포함 하도록 강제 지정 하는 작업 병렬 라이브러리를 사용할 필요 없이이 작업을 수행할 수 있습니다 `Task<'T>` 및 `Async<'T>` 형식입니다.

다음 예제에서는 ´ ֲ `Async.Parallel` HTML를 동시에 4 개의 인기 있는 사이트에서 다운로드를 완료 하는 데 해당 작업에 대 한 기다린 다음 다운로드 한를 HTML을 인쇄 합니다.

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

## <a name="important-info-and-advice"></a>중요한 정보 및 조언

*   사용할 수 있도록 모든 함수의 끝에 "Async"를 추가

 명명 규칙 뿐 이지만, API 검색 기능 등을 쉽게 수행할지 않습니다 것 있습니다. 동일한 루틴의 동기 및 비동기 버전이 없을 경우에 특히 명시적으로 지정 되는 이름을 통해 비동기 것이 좋습니다.

*   컴파일러에 수신!

 F #의 컴파일러는 매우 엄격한 거의 없는 작업을 수행할 수 있도록 "async" 코드를 동기적으로 실행 같은 솔 합니다. 경고를 발견할 경우 코드 않습니다 됩니다 생각 방법을 실행 하는 기호입니다. 만족도 매우 컴파일러를 만들 수 있습니다, 예상 대로 코드를 실행할 가능성이 높습니다.

## <a name="for-the-cvb-programmer-looking-into-f"></a>F #으로 C# /VB 프로그래머에 대 한 #

이 섹션에서는 C#에서 비동기 모델에 익숙한 가정 / VB. 없는 경우, [C#에서 비동기 프로그래밍](../../../csharp/async.md) 출발점입니다.

C# /VB 비동기 모델 및 F # 비동기 모델 간에 근본적인 차이가 있습니다.

반환 하는 함수를 호출 하는 경우는 `Task` 또는 `Task<'T>`, 해당 작업이 이미 실행을 시작 합니다. 반환 된 핸들이 이미 실행 중인 비동기 작업을 나타냅니다. 반면, 호출 하는 경우 비동기 함수에서 F #는 `Async<'a>` 반환 될 작업을 나타냅니다 **생성** 특정 시점에 있습니다. 이 모델 이해은 F #에서 비동기 작업을 함께 연결 될 수 있기 때문에 강력한 더 쉽게 조건에 따라 수행 하 고 컨트롤의 상세한을 사용 하 여 시작 합니다.

다른 몇 가지 유사점 및 차이점 주목할 만한 가치가 있습니다.

### <a name="similarities"></a>유사성

*   `let!``use!`, 및 `do!` 유사 `await` 내에서 비동기 작업을 호출 하는 경우는 `async{ }` 블록입니다.

 키워드 세 개 내 에서만 사용할 수는 `async { }` 블록 방법과 유사 `await` 내 에서만 호출할 수는 `async` 메서드. 즉, `let!` 캡처하고 결과 사용 하려는 경우에 `use!` 는 동일 하지만 해당 리소스를 사용 하는 후 정리 해야 항목은 및 `do!` 끝나기를 값을 반환 하지 않고는 async 워크플로에 대해 기다려야 하는 경우에 대 한 것 이동 합니다.

*   F # 비슷한 방법으로 데이터 병렬 처리를 지원합니다.

 매우 다른 방식으로 작동 하기는 하지만 `Async.Parallel` 에 해당 `Task.WhenAll` 모두 완료 하는 경우 비동기 작업 집합의 결과 원하는의 시나리오에 대 한 합니다.

### <a name="differences"></a>차이점

*   중첩 된 `let!` 허용, 달리 중첩은 `await`

 와 달리 `await`를 무기한으로 중첩 될 수 있는 `let!` 수 없으며 다른 내부에서 사용 하기 전에 바인딩된 결과 있어야 `let!`, `do!`, 또는 `use!`합니다.

*   취소 지원은 F # 보다 C#에서 간단한 / VB.

 C# /VB에서의 실행을 통해 작업 중간의 취소를 지 원하는 검사 해야는 `IsCancellationRequested` 속성 또는 호출 `ThrowIfCancellationRequested()` 에 `CancellationToken` 비동기 메서드에 전달 되는 개체입니다.

반면, F # 비동기 워크플로 더 자연스럽 게 취소할 수 없습니다. 취소는 간단한 3 단계 프로세스입니다.

1.  새 `CancellationTokenSource`를 만듭니다.
2.  시작을 함수로 전달 합니다.
3.  호출 `Cancel` 토큰에 있습니다.

예제:

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

이제 끝났습니다.

## <a name="further-resources"></a>추가 리소스:

*   [MSDN에서 비동기 워크플로](https://msdn.microsoft.com/library/dd233250.aspx)
*   [F #에 대 한 비동기 시퀀스](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [F # 데이터 HTTP 유틸리티](https://fsharp.github.io/FSharp.Data/library/Http.html)
