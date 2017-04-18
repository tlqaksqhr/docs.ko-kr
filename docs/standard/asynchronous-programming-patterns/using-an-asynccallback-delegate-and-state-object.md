---
title: "Using an AsyncCallback Delegate and State Object | Microsoft Docs"
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
  - "asynchronous programming, delegates"
  - "AsyncCallback delegate, samples"
  - "asynchronous programming, state objects"
  - "IAsyncResult interface, samples"
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Using an AsyncCallback Delegate and State Object
<xref:System.AsyncCallback> 대리자를 사용하여 별도 스레드에서 비동기 작업의 결과를 처리하는 경우 콜백 간에 정보를 전달하고 최종 결과를 가져오도록 상태 개체를 사용할 수 있습니다.  이 항목은 [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)의 예제를 확장하는 과정을 보여줍니다.  
  
## 예제  
 다음 코드 예제에는 <xref:System.Net.Dns> 클래스의 비동기 메서드를 사용하여 사용자 지정 컴퓨터에 대한 DNS\(Domain Name System\) 정보를 검색하는 방법을 보여 줍니다.  이 예제에서는 `HostRequest` 클래스를 정의하고 사용하여 상태 정보를 저장합니다.  `HostRequest` 개체는 사용자가 입력한 각 컴퓨터 이름마다 작성됩니다.  이 개체는 <xref:System.Net.Dns.BeginGetHostByName%2A> 메서드에 전달됩니다.  `ProcessDnsInformation` 메서드는 요청이 완료될 때마다 호출됩니다.  `HostRequest` 개체는 <xref:System.IAsyncResult.AsyncState%2A> 속성을 사용하여 검색합니다.  `ProcessDnsInformation` 메서드는 `HostRequest` 개체를 사용하여 요청자가 반환한 <xref:System.Net.IPHostEntry> 또는 요청자가 throw한 <xref:System.Net.Sockets.SocketException>을 저장합니다.  모든 요청이 완료될 때 응용 프로그램에서는 `HostRequest` 개체를 반복하고 DNS 정보 또는 <xref:System.Net.Sockets.SocketException> 오류 메시지를 표시합니다.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## 참고 항목  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)