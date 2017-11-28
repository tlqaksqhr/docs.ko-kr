---
title: "관리되는 스레드 상태"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: threading [.NET Framework], states
ms.assetid: 63890d5e-6025-4a7c-aaf0-d8bfd54b455f
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 073fb19ef34ba32ccb5d5664413718a436563770
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="managed-thread-states"></a>관리되는 스레드 상태
<xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> 속성은 스레드의 현재 상태를 나타내는 비트 마스크를 제공합니다. 스레드는 항상 <xref:System.Threading.ThreadState> 열거형의 가능한 상태 중 하나 이상이며 동시에 여러 상태일 수 있습니다.  
  
> [!IMPORTANT]
>  스레드 상태는 일부 디버깅 시나리오에서만 중요합니다. 코드에서 스레드 상태를 사용하여 스레드 활동을 동기화하면 안 됩니다.  
  
 관리되는 스레드를 만드는 경우 <xref:System.Threading.ThreadState.Unstarted> 상태입니다. 스레드는 운영 체제에서 시작됨 상태로 이동할 때까지 <xref:System.Threading.ThreadState.Unstarted> 상태로 유지됩니다. <xref:System.Threading.Thread.Start%2A> 를 호출하면 운영 체제에서 스레드를 시작할 수 있음을 알게 됩니다. 스레드의 상태를 변경하지 않습니다.  
  
 관리되는 환경으로 들어가는 관리되지 않는 스레드는 이미 시작됨 상태입니다. 스레드가 시작됨 상태이면 다양한 작업에 의해 스레드 상태가 변경될 수 있습니다. 다음 표에서는 상태 변경이 발생하는 작업 및 해당 새 상태를 보여 줍니다.  
  
|작업|새 상태|  
|------------|-------------------------|  
|<xref:System.Threading.Thread> 클래스의 생성자가 호출됩니다.|<xref:System.Threading.ThreadState.Unstarted>|  
|다른 스레드가 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>를 호출합니다.|<xref:System.Threading.ThreadState.Unstarted>|  
|스레드가 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>에 응답하고 실행을 시작합니다.|<xref:System.Threading.ThreadState.Running>|  
|스레드가 <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>를 호출합니다.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|스레드가 다른 개체에서 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>를 호출합니다.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|스레드가 다른 스레드에서 <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>를 호출합니다.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|다른 스레드가 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>를 호출합니다.|<xref:System.Threading.ThreadState.SuspendRequested>|  
|스레드가 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> 요청에 응답합니다.|<xref:System.Threading.ThreadState.Suspended>|  
|다른 스레드가 <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>를 호출합니다.|<xref:System.Threading.ThreadState.Running>|  
|다른 스레드가 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>를 호출합니다.|<xref:System.Threading.ThreadState.AbortRequested>|  
|스레드가 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>에 응답합니다.|<xref:System.Threading.ThreadState.Aborted>, <xref:System.Threading.ThreadState.Stopped>|  
  
 <xref:System.Threading.ThreadState.Running> 상태는 값이 0이므로 비트 테스트를 통해 이 상태를 검색할 수 없습니다. 대신, 의사 코드에서 다음 테스트를 사용할 수 있습니다.  
  
```  
if ((state & (Unstarted | Stopped)) == 0)   // implies Running     
```  
  
 스레드가 지정된 시간에 둘 이상의 상태인 경우도 있습니다. 예를 들어 한 스레드가 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> 호출에서 차단되고 다른 스레드가 동일한 스레드에서 <xref:System.Threading.Thread.Abort%2A>를 호출할 경우 스레드는 동시에 <xref:System.Threading.ThreadState.WaitSleepJoin> 및 <xref:System.Threading.ThreadState.AbortRequested> 상태를 갖게 됩니다. 이 경우 스레드가 <xref:System.Threading.Monitor.Wait%2A> 호출에서 반환되거나 중단되는 즉시 <xref:System.Threading.ThreadAbortException>이 수신됩니다.  
  
 <xref:System.Threading.ThreadState.Unstarted> 호출의 결과로 스레드가 <xref:System.Threading.Thread.Start%2A>상태를 벗어난 후에는 <xref:System.Threading.ThreadState.Unstarted> 상태로 돌아갈 수 없습니다. 스레드는 <xref:System.Threading.ThreadState.Stopped> 상태를 벗어날 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadState>  
 [스레딩](../../../docs/standard/threading/index.md)
