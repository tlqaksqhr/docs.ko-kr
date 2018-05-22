---
title: AsyncWaitHandle을 사용하는 응용 프로그램 실행 블로킹
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a1f9c7a5c1e083500ccf88d7a165e109238e875
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a><span data-ttu-id="6f17c-102">AsyncWaitHandle을 사용하는 응용 프로그램 실행 블로킹</span><span class="sxs-lookup"><span data-stu-id="6f17c-102">Blocking Application Execution Using an AsyncWaitHandle</span></span>
<span data-ttu-id="6f17c-103">비동기 작업의 결과를 기다리는 동안 다른 작업을 계속 수행할 수 없는 응용 프로그램은 작업이 완료될 때까지 차단되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f17c-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="6f17c-104">다음 옵션 중 하나를 사용하여 비동기 작업이 완료될 때까지 대기하는 동안 응용 프로그램의 기본 스레드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="6f17c-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="6f17c-105">비동기 작업의 **Begin***OperationName* 메서드에 의해 반환된 <xref:System.IAsyncResult>의 <xref:System.IAsyncResult.AsyncWaitHandle%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f17c-105">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin***OperationName* method.</span></span> <span data-ttu-id="6f17c-106">이 항목에서 이 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f17c-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="6f17c-107">비동기 작업의 **End***OperationName* 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6f17c-107">Call the asynchronous operation's **End***OperationName* method.</span></span> <span data-ttu-id="6f17c-108">이 방법을 설명하는 예제는 [비동기 작업을 종료하여 응용 프로그램 실행 블로킹](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f17c-108">For an example that demonstrates this approach, see [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
 <span data-ttu-id="6f17c-109">비동기 작업이 완료될 때까지 하나 이상의 <xref:System.Threading.WaitHandle> 개체를 사용하여 차단하는 응용 프로그램은 일반적으로 **Begin***OperationName* 메서드를 호출하고 작업의 결과 없이 완료할 수 있는 작업을 수행한 다음, 비동기 작업이 완료될 때까지 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="6f17c-109">Applications that use one or more <xref:System.Threading.WaitHandle> objects to block until an asynchronous operation is complete will typically call the **Begin***OperationName* method, perform any work that can be done without the results of the operation, and then block until the asynchronous operation(s) completes.</span></span> <span data-ttu-id="6f17c-110">응용 프로그램은 <xref:System.IAsyncResult.AsyncWaitHandle%2A>를 사용하는 <xref:System.Threading.WaitHandle.WaitOne%2A> 메서드 중 하나를 호출하여 단일 작업을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f17c-110">An application can block on a single operation by calling one of the <xref:System.Threading.WaitHandle.WaitOne%2A> methods using the <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span></span> <span data-ttu-id="6f17c-111">비동기 작업 집합이 완료될 때까지 대기하는 동안 차단하려면 연관된 <xref:System.IAsyncResult.AsyncWaitHandle%2A> 개체를 배열에 저장하고 <xref:System.Threading.WaitHandle.WaitAll%2A> 메서드 중 하나를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6f17c-111">To block while waiting for a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAll%2A> methods.</span></span> <span data-ttu-id="6f17c-112">일련의 비동기 작업 중 하나가 완료될 때까지 대기하는 동안 차단하려면 연관된 <xref:System.IAsyncResult.AsyncWaitHandle%2A> 개체를 배열에 저장하고 <xref:System.Threading.WaitHandle.WaitAny%2A> 메서드 중 하나를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6f17c-112">To block while waiting for any one of a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAny%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f17c-113">예제</span><span class="sxs-lookup"><span data-stu-id="6f17c-113">Example</span></span>  
 <span data-ttu-id="6f17c-114">다음 코드 예제는 DNS 클래스에서 비동기 메서드를 사용하여 사용자가 지정한 컴퓨터의 Domain Name System 정보를 검색하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f17c-114">The following code example demonstrates using asynchronous methods in the DNS class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="6f17c-115">이 예제는 비동기 작업과 연결된 <xref:System.Threading.WaitHandle>을 사용하여 차단하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f17c-115">The example demonstrates blocking using the <xref:System.Threading.WaitHandle> associated with the asynchronous operation.</span></span> <span data-ttu-id="6f17c-116">이 방법을 사용할 경우 이러한 항목이 필요하지 않기 때문에 <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` 및 `stateObject` 매개 변수에 대해 `null`(Visual Basic의 `Nothing`)이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f17c-116">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6f17c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f17c-117">See Also</span></span>  
 [<span data-ttu-id="6f17c-118">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="6f17c-118">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="6f17c-119">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="6f17c-119">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
