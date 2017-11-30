---
title: "비동기 워크플로(F#)"
description: "배울 F # 프로그래밍 계산을 비동기적으로 수행 하는 것에 대 한 언어 지원에 대 한 다른 작업의 실행을 차단 하지 않고 실행 합니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ee2bb9bf-e04a-4fbe-bf58-46d07229e981
ms.openlocfilehash: 425dbcbce06f183c81acb90993978c6dd9523de9
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2017
---
# <a name="asynchronous-workflows"></a>비동기 워크플로

> [!NOTE]
API 참조 링크를 통해 MSDN으로 이동됩니다.  docs.microsoft.com API 참조가 완전하지 않습니다.

이 항목에서는 계산 수행 비동기적으로, 즉, 다른 작업의 실행을 차단 하지 않고에 대 한 F #에서 지원을 설명 합니다. 예를 들어 비동기 계산 응용 프로그램이 다른 작업을 수행 하는 대로 사용자에 게 응답을 유지 하는 동안 Ui가 응용 프로그램을 쓰는 데 사용할 수 있습니다.

## <a name="syntax"></a>구문

```fsharp
async { expression }
```

## <a name="remarks"></a>설명

위 구문에서 계산으로 표시 `expression` 비동기적으로 비동기 대기 작업, I/O 및 기타 비동기 작업을 수행할 때 현재 계산 스레드를 차단 하지 않고, 즉 실행 하도록 설정 되어 있습니다. 현재 스레드의 실행이 계속 하는 동안 백그라운드 스레드에서 비동기 계산 시작 종종 됩니다. 식의 형식이 `Async<'T>`여기서 `'T` 식에서 반환 되는 형식 때는 `return` 키워드를 사용 합니다. 이와 같은 식에 코드 라고는 *비동기 블록*, 또는 *비동기 블록*합니다.

다양 한 방법으로 비동기적으로 프로그래밍 및 [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7) 클래스 몇 가지 시나리오를 지 원하는 메서드를 제공 합니다. 일반적인 방법은 만들려는 `Async` 트리거 함수 중 하나를 사용 하 여 이러한 계산을 시작한 다음 계산 또는 비동기적으로 실행 하려면 계산을 나타내는 개체입니다. 트리거 함수 비동기 계산 실행의 여러 가지 방법을 제공 하 고 현재 스레드, 백그라운드 스레드, 또는.NET Framework 작업 개체를 사용을 여부에 따라 사용 하는 방법도 및 계산이 완료 될 때 실행 되어야 하는 함수입니다. 예를 들어 현재 스레드에서 비동기 계산을 시작 하는 데 [ `Async.StartImmediate` ](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3)합니다. UI 스레드에서 비동기 계산을 시작 하는 경우 응용 프로그램 응답 가능한 상태로 유지 되므로 키 입력 및 마우스 활동, 같은 사용자 동작을 처리 하는 기본 이벤트 루프를 차단 하지 않습니다.

## <a name="asynchronous-binding-by-using-let"></a>Let를 사용 하 여 비동기 바인딩을!

비동기 워크플로 식과 작업은 동기화 버전을 비동기적으로 결과 반환 하도록 설계 된 긴 계산 합니다. 비동기적으로 일반 대신 메서드를 호출 하는 경우 `let` 사용 바인딩, `let!`합니다. 효과 `let!` 계산을 수행 하는 다른 계산 이나 스레드가 계속 실행을 활성화 하는 것입니다. 오른쪽 후는 `let!` 바인딩 실행을 다시 시작 비동기 워크플로의 나머지를 반환 합니다.

다음 코드 차이 보여 줍니다. `let` 및 `let!`합니다. 사용 하는 코드의 줄 `let` 비동기 계산 예를 들어를 사용 하 여 나중에 실행할 수 있는 개체를 만들기만 `Async.StartImmediate` 또는 [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)합니다. 사용 하는 코드의 줄 `let!` 계산을 시작 하 고 결과에 어떤 지점 실행이 계속 있을 때까지 스레드가 일시 중단 된 후입니다.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

외에 `let!`를 사용할 수 있습니다 `use!` 비동기 바인딩을 수행 하려면. 차이 `let!` 및 `use!` 간의 차이와 같습니다 `let` 및 `use`합니다. 에 대 한 `use!`, 개체가 현재 범위의 종료할 때 삭제 됩니다. F # 언어의 현재 릴리스에서 유의 `use!` 경우에 null로 초기화할 수 값을 허용 하지 않습니다 `use` 않습니다.

## <a name="asynchronous-primitives"></a>비동기 기본 형식

단일 비동기 작업을 수행 하 고 결과 반환 하는 메서드가 호출 되는 *비동기 기본*, 사용 하도록 특별히 디자인 된 이러한를 `let!`합니다. 여러 비동기 기본 요소는 F # 핵심 라이브러리에 정의 됩니다. 웹 응용 프로그램에 대 한 이러한 두 메서드는 모듈에 정의 되어 [ `Microsoft.FSharp.Control.WebExtensions` ](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003): [ `WebRequest.AsyncGetResponse` ](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c) 및 [ `WebClient.AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a)합니다. 두 기본 URL에 따라 해당 웹 페이지에서 데이터를 다운로드 합니다. `AsyncGetResponse`생성 한 `System.Net.WebResponse` 개체 및 `AsyncDownloadString` 웹 페이지에 대 한 HTML을 나타내는 문자열을 생성 합니다.

비동기 I/O 작업에 대 한 여러 기본 요소에 포함 된는 [ `Microsoft.FSharp.Control.CommonExtensions` ](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396) 모듈입니다. 이러한 확장 메서드는 `System.IO.Stream` 클래스 [ `Stream.AsyncRead` ](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e) 및 [ `Stream.AsyncWrite` ](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618)합니다.

비동기 추가 기본 형식에서 사용할 수 있는 [F # 파워 도구](http://fsprojects.github.io/VisualFSharpPowerTools/)합니다. 또한 전체 본문이 비동기 블록으로 묶어야 하는 함수를 정의 하 여 사용자 지정 비동기 기본 형식을 작성할 수 있습니다.

F #을 반환 하는 함수를 만드는 다른 비동기 모델 F # 비동기 프로그래밍 모델을 위해 디자인 된.NET Framework에서 비동기 메서드를 사용 하려면 `Async` 개체입니다. F # 라이브러리의이을 쉽게 수행할 수 있도록 하는 기능입니다.

비동기 워크플로 사용 하 여의 한 가지 예는 여기; 메서드에 대 한 설명서에도 많은 키워드가 [Async 클래스](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)합니다.

이 예제에서는 비동기 워크플로 사용 하 여 병렬에서 계산을 수행 하는 방법을 보여 줍니다.

다음 코드 예제에서는 함수에서에서 `fetchAsync` 웹 요청에서 반환 된 HTML 텍스트를 가져옵니다. `fetchAsync` 함수는 비동기 코드 블록을 포함 합니다. 때 바인딩은 구성 됩니다는 비동기 기본 결과에 예에서 [ `AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a), let! let 대신 사용 됩니다.

함수를 사용 하면 [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) 비동기 작업을 실행 하는 결과 대 한 대기입니다. 예를 들어, 있습니다 병렬로 실행할 수 있는 비동기 작업을 여러 개를 사용 하 여는 [ `Async.Parallel` ](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4) 와 함께 함수는 `Async.RunSynchronously` 함수입니다. `Async.Parallel` 함수 목록을 가져와서는 `Async` 개체, 코드를 설정 하는 각 `Async` task 개체를 실행 하려면 병렬로 반환에는 `Async` 병렬 계산을 나타내는 개체입니다. 호출 하는 단일 작업의 경우 처럼 `Async.RunSynchronously` 실행을 시작 합니다.

`runAll` 함수는 동시에 세 개의 비동기 워크플로 하 고 모두 완료 될 때까지 대기 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>참고 항목

[F# 언어 참조](index.md)

[계산 식](computation-expressions.md)

[Control.Async 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
