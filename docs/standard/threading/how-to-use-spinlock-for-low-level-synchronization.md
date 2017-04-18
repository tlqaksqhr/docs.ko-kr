---
title: "How to: Use SpinLock for Low-Level Synchronization | Microsoft Docs"
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
  - "SpinLock, how to use"
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# How to: Use SpinLock for Low-Level Synchronization
다음 예제에서는 <xref:System.Threading.SpinLock>을 사용하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서 임계 섹션은 최소량의 작업을 수행하므로 <xref:System.Threading.SpinLock>의 후보가 되기에 적합합니다.  작업량을 조금 늘리면 표준 잠금에 비해 <xref:System.Threading.SpinLock>의 성능이 향상됩니다.  그러나 일정 수준을 넘어서면 SpinLock의 효율성이 표준 잠금보다 더 떨어지기 시작합니다.  프로파일링 도구에서 동시성 프로파일링 기능을 사용하면 프로그램의 성능을 향상시키는 데 어떤 유형의 잠금이 더 적합한지 판단할 수 있습니다.  자세한 내용은 [동시성 시각화 도우미](../Topic/Concurrency%20Visualizer.md)을 참조하십시오.  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <xref:System.Threading.SpinLock>은 공유 리소스에 대한 잠금을 오래 유지할 필요가 없을 때 유용합니다.  이와 같은 경우 다중 코어 컴퓨터에서는 잠금이 해제될 때까지 차단된 스레드를 몇 차례 더 회전하는 것이 효율적일 수 있습니다.  스레드를 회전하면 스레드가 차단되지 않지만 이는 CPU 성능을 많이 필요로 하는 프로세스입니다.  <xref:System.Threading.SpinLock>은 특정 상황에서 회전을 중지하여 Hyper\-Threading 기술을 통해 논리적 프로세서가 고갈되거나 시스템에 대한 우선 순위가 뒤바뀌는 경우를 방지합니다.  
  
 이 예제에는 다중 스레드 액세스를 위한 사용자 동기화를 필요로 하는 <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> 클래스가 사용됩니다.  .NET Framework 버전 4를 대상으로 하는 응용 프로그램에는 어떠한 사용자 잠금도 필요로 하지 않는 <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>이라는 다른 옵션이 사용됩니다.  
  
 <xref:System.Threading.SpinLock.Exit%2A> 호출에 사용되는 `false`\(Visual Basic의 경우 `False`\)에 주목할 필요가 있습니다.  이렇게 하면 최상의 성능을 얻을 수 있습니다.  IA64 아키텍처에서는 메모리 펜스를 사용하도록 `true`\(`True`\)를 지정합니다. 이렇게 하면 쓰기 버퍼를 플러시하여 다른 스레드를 끝내는 데 잠금을 사용할 수 있습니다.  
  
## 참고 항목  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)