---
title: "Polling for the Status of an Asynchronous Operation | Microsoft Docs"
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
  - "asynchronous programming, status polling"
  - "polling asynchronous operation status"
  - "status information [.NET Framework], asynchronous operations"
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Polling for the Status of an Asynchronous Operation
비동기 작업 결과를 기다리는 동안 다른 작업을 수행할 수 있는 응용 프로그램은 해당 작업이 완료될 때까지 기다리는 동안 블로킹되지 않아야 합니다.  다음 옵션 중 하나를 사용하여 비동기 작업이 완료될 때까지 기다리는 동안 명령을 계속 실행합니다.  
  
-   비동기 작업의 **Begin** *OperationName* 메서드에서 반환한<xref:System.IAsyncResult> 의 <xref:System.IAsyncResult.IsCompleted%2A>속성을 사용하여 해당 작업이 완료되었는지 여부를 확인합니다.  폴링이라고 하는 방법에 대해서는 이 항목에서 설명합니다.  
  
-   <xref:System.AsyncCallback> 대리자를 사용하여 비동기 작업 결과를 별도의 스레드에서 처리합니다.  이 방법을 보여 주는 예제를 보려면 [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)를 참조하십시오.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Net.Dns> 클래스의 비동기 메서드를 사용하여 사용자 지정 컴퓨터에 대한 Domain Name System 정보를 검색하는 방법을 보여 줍니다.  이 예제에서는 비동기 작업을 시작한 다음 작업이 완료 때까지 콘솔에 마침표\("."\)를 인쇄합니다.  이 방법을 사용할 때 <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> 및 <xref:System.Object> 매개 변수가 필요하지 않으므로 이 인수에 **null**\(Visual Basic의 경우 **Nothing**\)이 전달됩니다.  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## 참고 항목  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)