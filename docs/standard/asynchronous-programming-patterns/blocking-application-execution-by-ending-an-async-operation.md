---
title: "비동기 작업을 종료하여 응용 프로그램 실행 차단"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
dev_langs:
- csharp
- vb
ms.openlocfilehash: ccca6e1e4f6b5cdf098018b59426fb2262e2b346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="73bfb-102">비동기 작업을 종료하여 응용 프로그램 실행 차단</span><span class="sxs-lookup"><span data-stu-id="73bfb-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="73bfb-103">계속 비동기 작업의 결과 기다리는 동안 다른 작업을 수행할 수 없는 응용 프로그램은 작업이 완료 될 때까지 차단 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73bfb-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="73bfb-104">다음 옵션 중 하나를 사용 하 여 비동기 작업이 완료 되기를 기다리는 동안 응용 프로그램의 주 스레드를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="73bfb-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="73bfb-105">비동기 작업을 호출 **끝** *OperationName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="73bfb-105">Call the asynchronous operations **End** *OperationName* method.</span></span> <span data-ttu-id="73bfb-106">이 방법은이 항목에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73bfb-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="73bfb-107">사용 하 여는 <xref:System.IAsyncResult.AsyncWaitHandle%2A> 의 속성은 <xref:System.IAsyncResult> 비동기 작업에서 반환 된 **시작** *OperationName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="73bfb-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method.</span></span> <span data-ttu-id="73bfb-108">이 방법을 보여 주는 예제를 보려면 [AsyncWaitHandle를 사용한 응용 프로그램 실행 블로킹](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73bfb-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="73bfb-109">사용 하는 응용 프로그램의 **끝** *OperationName* 메서드는 비동기 작업이 완료 될 때까지 차단 하려면 일반적으로 호출 됩니다는 **시작**  *OperationName* 메서드는 작업의 결과 없이 수행할 수 있습니다 하 고 호출 하는 작업을 수행 **끝** *OperationName*합니다.</span><span class="sxs-lookup"><span data-stu-id="73bfb-109">Applications that use the **End** *OperationName* method to block until an asynchronous operation is complete will typically call the **Begin** *OperationName* method, perform any work that can be done without the results of the operation, and then call **End** *OperationName*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73bfb-110">예제</span><span class="sxs-lookup"><span data-stu-id="73bfb-110">Example</span></span>  
 <span data-ttu-id="73bfb-111">다음 코드 예제에서는의 비동기 메서드를 사용 하 여는 <xref:System.Net.Dns> 사용자가 지정한 컴퓨터에 대 한 도메인 이름 시스템 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73bfb-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="73bfb-112">`null` (`Nothing` Visual Basic의)에 대 한 전달 되는 <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` 및 `stateObject` 매개 변수가이 방법을 사용할 때는이 인수를 필요 하지 않으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="73bfb-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="73bfb-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73bfb-113">See Also</span></span>  
 [<span data-ttu-id="73bfb-114">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="73bfb-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="73bfb-115">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="73bfb-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
