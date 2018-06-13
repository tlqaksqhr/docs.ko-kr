---
title: 비동기 작업을 종료하여 응용 프로그램 실행 차단
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
author: rpetrusha
ms.author: ronpet
dev_langs:
- csharp
- vb
ms.openlocfilehash: db46025ca1169f2f93a5b8eabb62a06ccc4bb95e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567421"
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="f7291-102">비동기 작업을 종료하여 응용 프로그램 실행 차단</span><span class="sxs-lookup"><span data-stu-id="f7291-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="f7291-103">비동기 작업의 결과를 기다리는 동안 다른 작업을 계속 수행할 수 없는 응용 프로그램은 작업이 완료될 때까지 차단되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7291-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="f7291-104">다음 옵션 중 하나를 사용하여 비동기 작업이 완료될 때까지 대기하는 동안 응용 프로그램의 기본 스레드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="f7291-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="f7291-105">비동기 작업 **End***OperationName* 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f7291-105">Call the asynchronous operations **End***OperationName* method.</span></span> <span data-ttu-id="f7291-106">이 항목에서 이 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7291-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="f7291-107">비동기 작업의 **Begin***OperationName* 메서드에 의해 반환된 <xref:System.IAsyncResult>의 <xref:System.IAsyncResult.AsyncWaitHandle%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7291-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin***OperationName* method.</span></span> <span data-ttu-id="f7291-108">이 방법을 설명하는 예제는 [AsyncWaitHandle을 사용하는 응용 프로그램 실행 블로킹](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7291-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="f7291-109">비동기 작업이 완료될 때까지 **End***OperationName* 메서드를 사용하여 차단되는 응용 프로그램은 일반적으로 **Begin***OperationName* 메서드를 호출하고 작업 결과 없이 완료할 수 있는 작업을 수행한 다음, **End***OperationName*을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f7291-109">Applications that use the **End***OperationName* method to block until an asynchronous operation is complete will typically call the **Begin***OperationName* method, perform any work that can be done without the results of the operation, and then call **End***OperationName*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7291-110">예</span><span class="sxs-lookup"><span data-stu-id="f7291-110">Example</span></span>  
 <span data-ttu-id="f7291-111">다음 코드 예제는 <xref:System.Net.Dns> 클래스에서 비동기 메서드를 사용하여 사용자가 지정한 컴퓨터의 Domain Name System 정보를 검색하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f7291-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="f7291-112">이 방법을 사용할 경우 이러한 인수가 필요하지 않기 때문에 <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` 및 `stateObject` 매개 변수에 대해 `null`(Visual Basic의 `Nothing`)이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7291-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f7291-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7291-113">See Also</span></span>  
 [<span data-ttu-id="f7291-114">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="f7291-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="f7291-115">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="f7291-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
