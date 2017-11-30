---
title: "AsyncCallback 대리자를 사용하여 비동기 작업 종료"
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
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bbe170588776daa97fec4c736d4b1bdd871de518
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a><span data-ttu-id="5ff19-102">AsyncCallback 대리자를 사용하여 비동기 작업 종료</span><span class="sxs-lookup"><span data-stu-id="5ff19-102">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>
<span data-ttu-id="5ff19-103">비동기 작업의 결과 기다리는 동안 다른 작업을 수행할 수 있는 응용 프로그램은 작업이 완료 될 때까지 대기 하는 것을 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff19-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="5ff19-104">다음 옵션 중 하나를 사용 하 여 비동기 작업이 완료 되기를 기다리는 동안 명령을 계속 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff19-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="5ff19-105">사용 하 여 프로그램 <xref:System.AsyncCallback> 별도의 스레드에서 비동기 작업의 결과 처리 하는 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="5ff19-105">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="5ff19-106">이 방법은이 항목에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff19-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="5ff19-107">사용 하 여는 <xref:System.IAsyncResult.IsCompleted%2A> 의 속성은 <xref:System.IAsyncResult> 비동기 작업에서 반환 **시작** *OperationName* 작업이 완료 되었는지 여부를 확인 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="5ff19-107">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method to determine whether the operation has completed.</span></span> <span data-ttu-id="5ff19-108">이 방법을 보여 주는 예제를 보려면 [비동기 작업의 상태에 대 한 폴링](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff19-108">For an example that demonstrates this approach, see [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ff19-109">예제</span><span class="sxs-lookup"><span data-stu-id="5ff19-109">Example</span></span>  
 <span data-ttu-id="5ff19-110">다음 코드 예제에서는의 비동기 메서드를 사용 하 여는 <xref:System.Net.Dns> 사용자가 지정한 컴퓨터에 대 한 DNS 도메인 이름 () 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ff19-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="5ff19-111">이 예제에서는 만듭니다는 <xref:System.AsyncCallback> 참조 하는 대리자는 `ProcessDnsInformation` 메서드.</span><span class="sxs-lookup"><span data-stu-id="5ff19-111">This example creates an <xref:System.AsyncCallback> delegate that references the `ProcessDnsInformation` method.</span></span> <span data-ttu-id="5ff19-112">이 메서드는 DNS 정보에 대 한 각 비동기 요청에 대해 한 번씩 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ff19-112">This method is called once for each asynchronous request for DNS information.</span></span>  
  
 <span data-ttu-id="5ff19-113">사용자 지정 호스트에 전달 되는 참고는 <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5ff19-113">Note that the user-specified host is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> parameter.</span></span> <span data-ttu-id="5ff19-114">정의 하 고 더 복잡 한 상태 개체를 사용 하 여 보여 주는 예제를 보려면 [AsyncCallback 대리자 및 상태 개체를 사용 하 여](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ff19-114">For an example that demonstrates defining and using a more complex state object, see [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).</span></span>  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="5ff19-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ff19-115">See Also</span></span>  
 [<span data-ttu-id="5ff19-116">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="5ff19-116">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="5ff19-117">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="5ff19-117">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="5ff19-118">IAsyncResult를 사용하는 비동기 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="5ff19-118">Calling Asynchronous Methods Using IAsyncResult</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [<span data-ttu-id="5ff19-119">AsyncCallback 대리자 및 상태 개체 사용</span><span class="sxs-lookup"><span data-stu-id="5ff19-119">Using an AsyncCallback Delegate and State Object</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
