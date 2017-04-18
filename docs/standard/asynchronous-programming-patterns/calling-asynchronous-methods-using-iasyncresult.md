---
title: "Calling Asynchronous Methods Using IAsyncResult | Microsoft Docs"
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
  - "waiting for asynchronous operations"
  - "asynchronous method calling"
  - "calling asynchronous methods"
  - "asynchronous programming, calling asynchronous methods"
  - "IAsyncResult interface, calling asynchronous methods"
  - "stopping asynchronous operations"
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Calling Asynchronous Methods Using IAsyncResult
.NET Framework 및 타사 클래스 라이브러리에 포함된 형식은 주 응용 프로그램 스레드 이외의 스레드에서 비동기 작업을 수행하는 동안 응용 프로그램이 계속 실행될 수 있도록 하는 메서드를 제공할 수 있습니다.  다음 단원에서는 <xref:System.IAsyncResult> 디자인 패턴을 사용하는 비동기 메서드를 호출할 수 있는 다양한 방법을 보여 주는 코드 예제 및 관련 설명을 제공합니다.  
  
-   [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
-   [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
-   [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
-   [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## 참고 항목  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)