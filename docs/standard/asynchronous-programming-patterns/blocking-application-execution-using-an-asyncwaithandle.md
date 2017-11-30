---
title: "AsyncWaitHandle을 사용하는 응용 프로그램 실행 블로킹"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- blocks, asynchronous operations
- ending asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming, blocking applications
- stopping asynchronous operations
- blocking application execution
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2660b3cbf7e8ee43a22edbfb66a4262684983b87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a><span data-ttu-id="9e792-102">AsyncWaitHandle을 사용하는 응용 프로그램 실행 블로킹</span><span class="sxs-lookup"><span data-stu-id="9e792-102">Blocking Application Execution Using an AsyncWaitHandle</span></span>
<span data-ttu-id="9e792-103">계속 비동기 작업의 결과 기다리는 동안 다른 작업을 수행할 수 없는 응용 프로그램은 작업이 완료 될 때까지 차단 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e792-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="9e792-104">다음 옵션 중 하나를 사용 하 여 비동기 작업이 완료 되기를 기다리는 동안 응용 프로그램의 주 스레드를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e792-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="9e792-105">사용 하 여는 <xref:System.IAsyncResult.AsyncWaitHandle%2A> 의 속성은 <xref:System.IAsyncResult> 비동기 작업에서 반환 된 **시작** *OperationName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="9e792-105">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method.</span></span> <span data-ttu-id="9e792-106">이 방법은이 항목에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e792-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="9e792-107">비동기 작업의 호출 **끝** *OperationName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="9e792-107">Call the asynchronous operation's **End** *OperationName* method.</span></span> <span data-ttu-id="9e792-108">이 방법을 보여 주는 예제를 보려면 [비동기 작업을 종료 하 여 응용 프로그램 실행 블로킹](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e792-108">For an example that demonstrates this approach, see [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
 <span data-ttu-id="9e792-109">하나 이상을 사용 하는 응용 프로그램 <xref:System.Threading.WaitHandle> 비동기 작업이 완료 될 때까지 차단 하는 개체는 일반적으로 호출 된 **시작** *OperationName* 메서드를 수행할 수 있는 작업을 수행 결과 작업 및 다음 비동기 작업이 될 때까지 차단 하지 않고 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="9e792-109">Applications that use one or more <xref:System.Threading.WaitHandle> objects to block until an asynchronous operation is complete will typically call the **Begin** *OperationName* method, perform any work that can be done without the results of the operation, and then block until the asynchronous operation(s) completes.</span></span> <span data-ttu-id="9e792-110">응용 프로그램 중 하나를 호출 하 여 단일 작업에 차단할 수는 <xref:System.Threading.WaitHandle.WaitOne%2A> 메서드를 사용 하는 <xref:System.IAsyncResult.AsyncWaitHandle%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="9e792-110">An application can block on a single operation by calling one of the <xref:System.Threading.WaitHandle.WaitOne%2A> methods using the <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span></span> <span data-ttu-id="9e792-111">집합의 비동기 작업이 완료 될 때까지 기다리는 동안 차단, 하려면 연결 된 저장 <xref:System.IAsyncResult.AsyncWaitHandle%2A> 개체를 배열 중 하나를 호출에는 <xref:System.Threading.WaitHandle.WaitAll%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9e792-111">To block while waiting for a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAll%2A> methods.</span></span> <span data-ttu-id="9e792-112">을 완료 하는 비동기 작업의 집합 중 하나를 기다리는 동안 차단 하려면 연결 된 저장 <xref:System.IAsyncResult.AsyncWaitHandle%2A> 개체를 배열 중 하나를 호출에는 <xref:System.Threading.WaitHandle.WaitAny%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9e792-112">To block while waiting for any one of a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAny%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e792-113">예제</span><span class="sxs-lookup"><span data-stu-id="9e792-113">Example</span></span>  
 <span data-ttu-id="9e792-114">다음 코드 예제에서는 DNS 클래스에서 비동기 메서드를 사용 하 여 사용자가 지정한 컴퓨터에 대 한 도메인 이름 시스템 정보를 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e792-114">The following code example demonstrates using asynchronous methods in the DNS class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="9e792-115">예제에 사용 하 여 차단는 <xref:System.Threading.WaitHandle> 비동기 작업과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e792-115">The example demonstrates blocking using the <xref:System.Threading.WaitHandle> associated with the asynchronous operation.</span></span> <span data-ttu-id="9e792-116">`null` (`Nothing` Visual Basic의)에 대 한 전달 되는 <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` 및 `stateObject` 매개 변수가 필요 하지 않으므로이 방법을 사용할 때는 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e792-116">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9e792-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e792-117">See Also</span></span>  
 [<span data-ttu-id="9e792-118">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="9e792-118">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="9e792-119">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="9e792-119">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
