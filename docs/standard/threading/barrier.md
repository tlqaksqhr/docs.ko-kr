---
title: "장벽(.NET Framework)"
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
helpviewer_keywords: synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a8111cc9f2798ff96be8b128f22a75d21b441178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="barrier-net-framework"></a>장벽(.NET Framework)
A *장벽* 은 여러 스레드가 사용자 정의 동기화 기본 형식 (라고 *참가자*) 단계에는 알고리즘에서 동시에 작동 하도록 합니다. 각 참가자는 코드의 장벽 지점에 도달할 때까지 실행됩니다. 장벽은 한 작업 단계의 끝을 나타냅니다. 참가자가 장벽에 도달하면 모든 참가자가 동일한 장벽에 도달할 때까지 차단됩니다. 모든 참가자가 장벽에 도달한 후 사후 단계 작업을 필요에 따라 호출할 수 있습니다. 이 사후 단계 작업을 사용하여 다른 모든 스레드는 여전히 차단하는 동시에 단일 스레드에서 작업을 수행할 수 있습니다. 작업이 실행된 후 모든 참가자가 차단 취소됩니다.  
  
 다음 코드 조각에서는 기본 장벽 패턴을 보여 줍니다.  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 전체 예제를 참조 하십시오. [하는 방법: 동시 작업을 장벽과 동기화](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)합니다.  
  
## <a name="adding-and-removing-participants"></a>참가자 추가 및 제거  
 <xref:System.Threading.Barrier>를 만들 때 참가자 수를 지정합니다. 언제든지 참가자를 동적으로 추가 또는 제거할 수도 있습니다. 예를 들어 한 참가자가 문제의 해당 부분을 해결 되 면 결과, 실행을 중지 해당 스레드에서 호출 저장할 수 <xref:System.Threading.Barrier.RemoveParticipant%2A> 장벽의 참가자 수를 감소 시키기 위해. <xref:System.Threading.Barrier.AddParticipant%2A>를 호출하여 참가자를 추가하는 경우 반환 값은 새 참가자의 작업을 초기화하는 데 유용할 수 있는 현재 단계 번호를 지정합니다.  
  
## <a name="broken-barriers"></a>손상된 장벽  
 한 참가자가 장벽에 도달하지 못할 경우 교착 상태가 발생할 수 있습니다. 이러한 교착 상태를 방지하려면 <xref:System.Threading.Barrier.SignalAndWait%2A> 메서드의 오버로드를 사용하여 시간 제한 기간 및 취소 토큰을 지정합니다. 이러한 오버로드는 다음 단계로 넘어가기 전에 각 참가자가 확인할 수 있는 부울 값을 반환합니다.  
  
## <a name="post-phase-exceptions"></a>사후 단계 예외  
 사후 단계 대리자에서 예외가 발생하는 경우 <xref:System.Threading.BarrierPostPhaseException> 개체에 래핑된 다음 모든 참가자에게 전파됩니다.  
  
## <a name="barrier-versus-continuewhenall"></a>장벽과 ContinueWhenAll 비교  
 장벽은 스레드가 루프로 여러 단계를 수행할 때 특히 유용합니다. 코드에 한두 개의 작업 단계만 필요한 경우 다음을 포함하여 임의 종류의 암시적 조인과 함께 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 개체를 사용할지 여부를 고려합니다.  
  
-   <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.Invoke%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.ForEach%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.For%2A>  
  
 자세한 내용은 [연속 작업을 사용하여 작업 연결](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)  
 [방법: 동시 작업을 배리어와 동기화](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)
