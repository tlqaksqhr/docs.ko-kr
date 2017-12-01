---
title: CountdownEvent
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
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a>CountdownEvent
<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>신호를 특정 횟수를 지정한 후에 대기 중인 스레드를 차단 해제 하는 동기화 기본 형식입니다. <xref:System.Threading.CountdownEvent>있는 그렇지 않은 경우 사용 해야 하는 시나리오를 위한는 <xref:System.Threading.ManualResetEvent> 또는 <xref:System.Threading.ManualResetEventSlim> 및 이벤트 신호를 보내기 전에 변수를 수동으로 감소 합니다. 예를 들어 분기/조인 시나리오에서 만들 수 있습니다만 <xref:System.Threading.CountdownEvent> 신호 수가 5, 있고 스레드에서 시작 5 개 작업 항목 풀 및 각 작업 항목 통화는 다음 <xref:System.Threading.CountdownEvent.Signal%2A> 완료 될 때입니다. 호출할 때마다 <xref:System.Threading.CountdownEvent.Signal%2A> 신호 카운트가 1 씩 감소 시킵니다. 주 스레드에서 호출 <xref:System.Threading.CountdownEvent.Wait%2A> 신호 0이 될 때까지 차단 됩니다.  
  
> [!NOTE]
>  .NET Framework 동기화 레거시 Api와 상호 작용할 수 없는 코드를 사용 하는 것이 좋습니다 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 개체 또는 <xref:System.Threading.Tasks.Parallel.Invoke%2A> 분기-조인 병렬 처리 표현 하는 보다 편리 하 게 방식에 대 한 메서드.  
  
 <xref:System.Threading.CountdownEvent>이러한 추가 기능에 있습니다.  
  
-   취소 토큰을 사용 하 여 대기 작업을 취소할 수 있습니다.  
  
-   인스턴스가 만들어진 후에 신호 수가 증가할 수 있습니다.  
  
-   후 인스턴스를 다시 사용할 수 <xref:System.Threading.CountdownEvent.Wait%2A> 가 호출 하 여 반환 되는 <xref:System.Threading.CountdownEvent.Reset%2A> 메서드.  
  
-   인스턴스를 노출 한 <xref:System.Threading.WaitHandle> 다른.NET Framework 동기화 Api와의 통합에 대 한 같은 <xref:System.Threading.WaitHandle.WaitAll%2A>합니다.  
  
## <a name="basic-usage"></a>기본 사용  
 다음 예제에서는 사용 하는 <xref:System.Threading.CountdownEvent> 와 <xref:System.Threading.ThreadPool> 작업 항목.  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a>취소를 지 원하는 CountdownEvent  
 다음 예제에서 대기 작업을 취소 하는 방법을 보여 줍니다 <xref:System.Threading.CountdownEvent> 취소 토큰을 사용 하 여 합니다. 기본 패턴에서 도입 된 통합 된 취소에 대 한 모델을 따르며 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]합니다. 자세한 내용은 참조 [관리 되는 스레드의 취소](../../../docs/standard/threading/cancellation-in-managed-threads.md)합니다.  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 참고 대기 작업 신호를 보내는 하는 스레드의 취소 되지 않습니다. 일반적으로 취소 논리 연산에 적용 되 고 대기 하는 이벤트 뿐만 아니라 대기를 동기화 하는 모든 작업 항목에 포함할 수 있는 합니다. 이 예제에서는 취소 요청에 응답할 수 있도록 각 작업 항목에서 동일한 취소 토큰 복사본에 전달 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
