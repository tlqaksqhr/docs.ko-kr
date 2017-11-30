---
title: "ManualResetEvent 및 ManualResetEventSlim"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f663dd17b063f77e2f9ce6bd4bbd0f8859ba4116
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent 및 ManualResetEventSlim
<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> 신호를 보낸 후 수동으로 재설정 해야 하는 로컬 대기 핸들 이벤트 클래스를 나타냅니다. 이 클래스는 기본 클래스의 특수 한 경우를 나타냅니다. <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>합니다. 수동 재설정 이벤트의 사용 및 기능은 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 개념 설명서를 참조하세요.  
  
 A <xref:System.Threading.ManualResetEvent> 개체 유지 될 때까지 신호를 받은 해당 <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> 메서드를 호출 합니다. 대기 스레드 또는 신호를 받은 후 이벤트를 기다리는 스레드 수는 제한 없이 개체의 상태가 신호를 받는 동안 해제될 수 있습니다. <xref:System.Threading.ManualResetEvent>해당 하는 Win32 `CreateEvent` 지정 함으로써 호출 `true` 에 대 한는 `bManualReset` 인수입니다.  
  
 에 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]를 사용할 수 있습니다는 <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> 시점과 이벤트 프로세스 경계를 교차 하지 않으며 대기 시간이 매우 짧은 것으로 예상 되는 성능 향상을 위해 클래스입니다. <xref:System.Threading.ManualResetEventSlim>에서는 이벤트에 신호가 전달되기를 기다리는 짧은 시간 동안 고속 회전을 사용합니다. 대기 시간이 짧은 경우 대기 핸들을 사용하여 기다리는 것보다 회전하는 것이 비용이 적게 들 수 있습니다. 그러나 특정 기간 내 이벤트 신호 되지 않는 경우, <xref:System.Threading.ManualResetEventSlim> 일반적인 이벤트 핸들 대기도 다시 정렬 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레딩](../../../docs/standard/threading/index.md)  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)  
 [대기 핸들](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 [스핀 대기](../../../docs/standard/threading/spinwait.md)  
 [세마포 및 SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
