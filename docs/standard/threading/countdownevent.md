---
title: "CountdownEvent | Microsoft Docs"
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
  - "synchronization primitives, CountdownEvent"
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# CountdownEvent
<xref:System.Threading.CountdownEvent?displayProperty=fullName>는 특정 횟수만큼 신호를 받은 후에 대기 중인 스레드를 차단 해제하는 동기화 기본 형식입니다.  <xref:System.Threading.CountdownEvent>는 <xref:System.Threading.ManualResetEvent> 또는 <xref:System.Threading.ManualResetEventSlim>을 사용해야 하고 이벤트에 신호를 보내기 전에 수동으로 변수를 감소시켜야 하는 시나리오에서 대안으로 사용하도록 설계되어 있습니다.  예를 들어, 분기\/조인 시나리오에서 신호 카운트가 5인 <xref:System.Threading.CountdownEvent>를 만든 다음 스레드 풀의 작업 항목 5개를 시작하고 각 작업 항목이 완료될 때 작업 항목에서 <xref:System.Threading.CountdownEvent.Signal%2A>을 호출하도록 하면 됩니다.  <xref:System.Threading.CountdownEvent.Signal%2A>를 호출할 때마다 신호 카운트가 1씩 감소합니다.  주 스레드에서 <xref:System.Threading.CountdownEvent.Wait%2A>에 대한 호출은 신호 카운트가 0이 될 때까지 차단됩니다.  
  
> [!NOTE]
>  레거시 .NET Framework 동기화 API와 상호 작용할 필요가 없는 코드의 경우 포크\-참가 병렬 처리를 훨씬 더 쉽게 표현하기 위하여 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 개체 또는 <xref:System.Threading.Tasks.Parallel.Invoke%2A> 메서드를 사용하는 것이 좋습니다.  
  
 <xref:System.Threading.CountdownEvent>에는 다음과 같은 추가 기능이 있습니다.  
  
-   대기 작업은 취소 토큰을 사용하여 취소할 수 있습니다.  
  
-   신호 카운트는 인스턴스가 만들어진 후 증가할 수 있습니다.  
  
-   <xref:System.Threading.CountdownEvent.Wait%2A>에서 반환한 이후 <xref:System.Threading.CountdownEvent.Reset%2A> 메서드를 호출하여 인스턴스를 다시 사용할 수 있습니다.  
  
-   인스턴스는 다른 .NET Framework 동기화 API와의 통합을 위해 <xref:System.Threading.WaitHandle.WaitAll%2A>과 같은 <xref:System.Threading.WaitHandle>을 노출합니다.  
  
## 기본 사용법  
 다음 예제에서는 <xref:System.Threading.CountdownEvent>를 <xref:System.Threading.ThreadPool> 작업 항목과 함께 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## CountdownEvent 취소  
 다음 예제에서는 취소 토큰을 사용하여 <xref:System.Threading.CountdownEvent>에 대한 대기 작업을 취소하는 방법을 보여 줍니다.  기본 패턴은 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서 도입된 통합 취소 모델을 따릅니다.  자세한 내용은 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)을 참조하십시오.  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 대기 작업에 신호를 보내는 스레드는 해당 대기 작업에 의해 취소되지 않습니다.  일반적으로 취소는 논리적 작업에 적용되고, 이러한 작업에는 이벤트에 대한 대기 및 대기를 통해 동기화되고 있는 모든 작업 항목이 포함될 수 있습니다.  이 예제에서는 동일한 취소 토큰의 복사본이 각 작업 항목에 전달되므로 해당 작업 항목에서 취소 요청에 응답할 수 있습니다.  
  
## 참고 항목  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)