---
title: "Using an AsyncCallback Delegate to End an Asynchronous Operation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ending asynchronous operations"
  - "asynchronous programming, ending operations"
  - "AsyncCallback delegate"
  - "stopping asynchronous operations"
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Using an AsyncCallback Delegate to End an Asynchronous Operation
비동기 작업 결과를 기다리는 동안 다른 작업을 수행할 수 있는 응용 프로그램은 해당 작업이 완료될 때까지 기다리는 동안 블로킹되지 않아야 합니다.  다음 옵션 중 하나를 사용하여 비동기 작업이 완료될 때까지 기다리는 동안 명령을 계속 실행합니다.  
  
-   <xref:System.AsyncCallback> 대리자를 사용하여 비동기 작업 결과를 별도의 스레드에서 처리합니다.  이 방법에 대해서는 이 항목에서 설명합니다.  
  
-   비동기 작업의 **Begin** *OperationName*메서드에서 반환한 <xref:System.IAsyncResult>의 <xref:System.IAsyncResult.IsCompleted%2A> 속성을 사용하여 해당 작업이 완료되었는지 여부를 확인합니다.  이 방법을 보여 주는 예제를 보려면 [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)을 참조하십시오.  
  
## 예제  
 다음 코드 예제에는 <xref:System.Net.Dns> 클래스의 비동기 메서드를 사용하여 사용자 지정 컴퓨터에 대한 DNS\(Domain Name System\) 정보를 검색하는 방법을 보여 줍니다.  이 예제에서는 `ProcessDnsInformation` 메서드를 참조하는 <xref:System.AsyncCallback> 대리자를 만듭니다.  이 메서드는 DNS 정보를 비동기적으로 요청할 때마다 한 번씩 호출됩니다.  
  
 사용자 지정한 호스트는 <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object> 매개 변수로 전달됩니다.  보다 복잡한 상태 개체를 정의하고 사용하는 방법을 보여 주는 예제를 보려면 [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)을 참조하십시오.  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## 참고 항목  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [Calling Asynchronous Methods Using IAsyncResult](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)   
 [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)