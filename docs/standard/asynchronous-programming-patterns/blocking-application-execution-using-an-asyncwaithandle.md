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
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a>AsyncWaitHandle을 사용하는 응용 프로그램 실행 블로킹
계속 비동기 작업의 결과 기다리는 동안 다른 작업을 수행할 수 없는 응용 프로그램은 작업이 완료 될 때까지 차단 되어야 합니다. 다음 옵션 중 하나를 사용 하 여 비동기 작업이 완료 되기를 기다리는 동안 응용 프로그램의 주 스레드를 차단 합니다.  
  
-   사용 하 여는 <xref:System.IAsyncResult.AsyncWaitHandle%2A> 의 속성은 <xref:System.IAsyncResult> 비동기 작업에서 반환 된 **시작** *OperationName* 메서드. 이 방법은이 항목에 나와 있습니다.  
  
-   비동기 작업의 호출 **끝** *OperationName* 메서드. 이 방법을 보여 주는 예제를 보려면 [비동기 작업을 종료 하 여 응용 프로그램 실행 블로킹](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)합니다.  
  
 하나 이상을 사용 하는 응용 프로그램 <xref:System.Threading.WaitHandle> 비동기 작업이 완료 될 때까지 차단 하는 개체는 일반적으로 호출 된 **시작** *OperationName* 메서드를 수행할 수 있는 작업을 수행 결과 작업 및 다음 비동기 작업이 될 때까지 차단 하지 않고 완료합니다. 응용 프로그램 중 하나를 호출 하 여 단일 작업에 차단할 수는 <xref:System.Threading.WaitHandle.WaitOne%2A> 메서드를 사용 하는 <xref:System.IAsyncResult.AsyncWaitHandle%2A>합니다. 집합의 비동기 작업이 완료 될 때까지 기다리는 동안 차단, 하려면 연결 된 저장 <xref:System.IAsyncResult.AsyncWaitHandle%2A> 개체를 배열 중 하나를 호출에는 <xref:System.Threading.WaitHandle.WaitAll%2A> 메서드. 을 완료 하는 비동기 작업의 집합 중 하나를 기다리는 동안 차단 하려면 연결 된 저장 <xref:System.IAsyncResult.AsyncWaitHandle%2A> 개체를 배열 중 하나를 호출에는 <xref:System.Threading.WaitHandle.WaitAny%2A> 메서드.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 DNS 클래스에서 비동기 메서드를 사용 하 여 사용자가 지정한 컴퓨터에 대 한 도메인 이름 시스템 정보를 검색 하는 방법을 보여 줍니다. 예제에 사용 하 여 차단는 <xref:System.Threading.WaitHandle> 비동기 작업과 연결 합니다. `null` (`Nothing` Visual Basic의)에 대 한 전달 되는 <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` 및 `stateObject` 매개 변수가 필요 하지 않으므로이 방법을 사용할 때는 합니다.  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 [EAP(이벤트 기반 비동기 패턴)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
