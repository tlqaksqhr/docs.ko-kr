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
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a>AsyncCallback 대리자를 사용하여 비동기 작업 종료
비동기 작업의 결과 기다리는 동안 다른 작업을 수행할 수 있는 응용 프로그램은 작업이 완료 될 때까지 대기 하는 것을 차단 하지 않아야 합니다. 다음 옵션 중 하나를 사용 하 여 비동기 작업이 완료 되기를 기다리는 동안 명령을 계속 실행 합니다.  
  
-   사용 하 여 프로그램 <xref:System.AsyncCallback> 별도의 스레드에서 비동기 작업의 결과 처리 하는 대리자입니다. 이 방법은이 항목에 나와 있습니다.  
  
-   사용 하 여는 <xref:System.IAsyncResult.IsCompleted%2A> 의 속성은 <xref:System.IAsyncResult> 비동기 작업에서 반환 **시작** *OperationName* 작업이 완료 되었는지 여부를 확인 하는 메서드. 이 방법을 보여 주는 예제를 보려면 [비동기 작업의 상태에 대 한 폴링](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는의 비동기 메서드를 사용 하 여는 <xref:System.Net.Dns> 사용자가 지정한 컴퓨터에 대 한 DNS 도메인 이름 () 정보를 검색할 수 있습니다. 이 예제에서는 만듭니다는 <xref:System.AsyncCallback> 참조 하는 대리자는 `ProcessDnsInformation` 메서드. 이 메서드는 DNS 정보에 대 한 각 비동기 요청에 대해 한 번씩 호출 됩니다.  
  
 사용자 지정 호스트에 전달 되는 참고는 <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object> 매개 변수입니다. 정의 하 고 더 복잡 한 상태 개체를 사용 하 여 보여 주는 예제를 보려면 [AsyncCallback 대리자 및 상태 개체를 사용 하 여](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)합니다.  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a>참고 항목  
 [EAP(이벤트 기반 비동기 패턴)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [IAsyncResult를 사용하는 비동기 메서드 호출](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [AsyncCallback 대리자 및 상태 개체 사용](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
