---
title: "How to: Cancel a Task and Its Children | Microsoft Docs"
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
  - "tasks, how to cancel"
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# How to: Cancel a Task and Its Children
이 예제에서는 다음과 같은 작업을 수행하는 방법을 보여 줍니다.  
  
1.  취소할 수 있는 작업을 만들고 시작합니다.  
  
2.  사용자 대리자 및 작업 인스턴스\(선택적\)에 취소 토큰을 전달합니다.  
  
3.  사용자 대리자에서 취소 요청을 인식하고 이에 응답합니다.  
  
4.  필요한 경우 호출 스레드에 작업이 취소되었음을 알립니다.  
  
 호출 스레드에서는 작업을 강제로 종료하는 것이 아니라 취소가 요청되었음을 알리기만 합니다.  작업이 이미 실행 중인 경우에는 사용자 대리자에서 해당 요청을 인식하고 적절하게 응답합니다.  작업이 실행되기 전에 취소가 요청된 경우에는 사용자 대리자가 실행되지 않으며 작업 개체는 Canceled 상태로 전환됩니다.  
  
## 예제  
 이 예제에서는 취소 요청에 대한 응답으로 <xref:System.Threading.Tasks.Task>와 해당 자식 작업을 종료하는 방법을 보여 줍니다.  또한 <xref:System.Threading.Tasks.TaskCanceledException>을 throw하여 사용자 대리자가 종료될 때 호출 스레드에서 필요에 따라 <xref:System.Threading.Tasks.Task.Wait%2A> 메서드나 <xref:System.Threading.Tasks.Task.WaitAll%2A> 메서드를 사용하여 작업이 종료될 때까지 대기할 수 있음을 보여 줍니다.  이 경우 `try/catch` 블록을 사용하여 호출 스레드에서 예외를 처리해야 합니다.  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 클래스는 <xref:System.Threading.CancellationTokenSource?displayProperty=fullName> 및 <xref:System.Threading.CancellationToken?displayProperty=fullName> 형식을 기반으로 하는 취소 모델과 완전하게 통합됩니다.  자세한 내용은 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md) 및 [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Threading.CancellationTokenSource?displayProperty=fullName>   
 <xref:System.Threading.CancellationToken?displayProperty=fullName>   
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 <xref:System.Threading.Tasks.Task%601?displayProperty=fullName>   
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)   
 [Attached and Detached Child Tasks](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)