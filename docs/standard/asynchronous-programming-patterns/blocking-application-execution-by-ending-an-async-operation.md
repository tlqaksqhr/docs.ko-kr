---
title: "Blocking Application Execution by Ending an Async Operation | Microsoft Docs"
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
  - "blocks, asynchronous operations"
  - "AsyncWaitHandle property"
  - "asynchronous programming, blocking applications"
  - "blocking application execution"
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Blocking Application Execution by Ending an Async Operation
비동기 작업의 결과를 기다리는 동안 다른 작업을 계속 수행할 수 없는 응용 프로그램은 해당 작업이 완료될 때까지 블로킹되어야 합니다.  비동기 작업 완료를 기다리는 동안 다음 옵션 중 하나를 사용하여 응용 프로그램의 주 스레드를 블로킹합니다.  
  
-   비동기 작업 **End** *OperationName* 메서드를 호출합니다.  이 방법에 대해서는 이 항목에서 설명합니다.  
  
-   비동기 작업의**Begin** *OperationName* 메서드에 의해 반환된 <xref:System.IAsyncResult> 의  <xref:System.IAsyncResult.AsyncWaitHandle%2A>속성을 사용합니다.  이 방법을 보여 주는 예제를 보려면 [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)을 참조하십시오.  
  
 비동기 작업이 완료될 때까지 **End** *OperationName* 메서드를 사용하여 블로킹하는 응용 프로그램은 일반적으로 **Begin** *OperationName* 메서드를 호출하고 해당 작업의 결과에 관계없이 완료될 수 있는 작업을 수행한 다음 **End** *OperationName*을 호출합니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Net.Dns> 클래스의 비동기 메서드를 사용하여 사용자 지정 컴퓨터에 대한 Domain Name System 정보를 검색하는 방법을 보여 줍니다.  이 방법을 사용할 때는 이러한 인수가 필요하지 않으므로 <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` 및 `stateObject` 매개 변수에 대해 `null`\(Visual Basic에서는 `Nothing`\)이 전달됩니다.  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## 참고 항목  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)