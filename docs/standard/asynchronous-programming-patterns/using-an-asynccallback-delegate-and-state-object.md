---
title: "AsyncCallback 대리자 및 상태 개체 사용"
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
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e8793a78289e9b58407038f41cc9d403ff9f9940
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="8a23c-102">AsyncCallback 대리자 및 상태 개체 사용</span><span class="sxs-lookup"><span data-stu-id="8a23c-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="8a23c-103">사용 하는 경우는 <xref:System.AsyncCallback> 별도의 스레드에서 비동기 작업의 결과 처리할 대리자를 콜백 간에 정보를 전달 하 고 최종 결과 검색 하는 상태 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a23c-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="8a23c-104">이 항목의 예제를 확장 하 여 해당 사례를 보여 줍니다. [AsyncCallback 대리자를 사용 하 여 비동기 작업을 종료 하도록](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a23c-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a23c-105">예제</span><span class="sxs-lookup"><span data-stu-id="8a23c-105">Example</span></span>  
 <span data-ttu-id="8a23c-106">다음 코드 예제에서는의 비동기 메서드를 사용 하 여는 <xref:System.Net.Dns> 사용자가 지정한 컴퓨터에 대 한 DNS 도메인 이름 () 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a23c-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="8a23c-107">이 예제에서는 정의 하 고 사용 하 여는 `HostRequest` 클래스 상태 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a23c-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="8a23c-108">A `HostRequest` 개체에 대 한 사용자가 입력 한 각 컴퓨터 이름을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a23c-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="8a23c-109">이 개체에 전달 되는 <xref:System.Net.Dns.BeginGetHostByName%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="8a23c-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="8a23c-110">`ProcessDnsInformation` 메서드가 요청 완료 될 때마다 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a23c-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="8a23c-111">`HostRequest` 개체를 사용 하 여 검색할는 <xref:System.IAsyncResult.AsyncState%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8a23c-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="8a23c-112">`ProcessDnsInformation` 메서드는 `HostRequest` 저장할 개체입니다는 <xref:System.Net.IPHostEntry> 요청이 반환 또는 <xref:System.Net.Sockets.SocketException> 요청에 의해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a23c-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="8a23c-113">응용 프로그램에 대해 반복 모든 요청이 완료 되 면는 `HostRequest` 개체 및 DNS 정보를 표시 또는 <xref:System.Net.Sockets.SocketException> 오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="8a23c-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="8a23c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a23c-114">See Also</span></span>  
 [<span data-ttu-id="8a23c-115">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="8a23c-115">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="8a23c-116">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="8a23c-116">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="8a23c-117">AsyncCallback 대리자를 사용하여 비동기 작업 종료</span><span class="sxs-lookup"><span data-stu-id="8a23c-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
