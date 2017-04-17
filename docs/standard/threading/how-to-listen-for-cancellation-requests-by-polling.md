---
title: "How to: Listen for Cancellation Requests by Polling | Microsoft Docs"
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
  - "cancellation, how to poll for requests"
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Listen for Cancellation Requests by Polling
다음 예제에서는 호출 스레드에서 취소가 요청되었는지 여부를 확인하기 위해 사용자 코드를 사용하여 취소 토큰을 일정한 간격으로 폴링할 수 있는 한 가지 방법을 보여 줍니다.  이 예제에서는 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 형식을 사용하지만 동일한 패턴이 <xref:System.Threading.ThreadPool?displayProperty=fullName> 형식 또는 <xref:System.Threading.Thread?displayProperty=fullName> 형식을 통해 직접 만든 비동기 작업에도 적용됩니다.  
  
## 예제  
 폴링에는 부울 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성의 값을 주기적으로 읽을 수 있는 특정 종류의 루프 또는 재귀 코드가 필요합니다.  <xref:System.Threading.Tasks.Task?displayProperty=fullName> 형식을 사용하고 있고 호출 스레드에서 작업이 완료되기를 기다리는 경우 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> 메서드를 사용하여 속성을 확인하고 예외를 throw할 수 있습니다.  이 메서드를 사용하면 요청에 대한 응답으로 올바른 예외가 throw되도록 할 수 있습니다.  <xref:System.Threading.Tasks.Task>를 사용하는 경우 수동으로 <xref:System.OperationCanceledException>을 throw하는 것보다 이 메서드를 호출하는 것이 좋습니다.  예외를 throw하지 않아도 되는 경우에는 속성을 확인하고 속성이 `true`이면 이 메서드에서 반환할 수 있습니다.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> 호출은 매우 빠르게 수행되기 때문에 루프의 오버헤드가 크게 증가하지 않습니다.  
  
 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>를 호출하는 경우 취소에 대한 응답으로 예외 throw 이외의 다른 작업을 수행해야 하면 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성을 명시적으로 확인하기만 하면 됩니다.  이 예제에서는 실제로 코드에서 명시적 액세스와 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>를 통해 속성에 두 번 액세스하는 것을 확인할 수 있습니다.  그러나 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성을 읽는 동작에는 액세스당 하나의 volatile 읽기 명령만 사용되므로 이러한 이중 액세스는 성능 측면에서 별다른 도움이 되지 않습니다.  수동으로 <xref:System.OperationCanceledException>을 throw하는 것보다 이 메서드를 호출하는 것이 좋습니다.  
  
## 참고 항목  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)