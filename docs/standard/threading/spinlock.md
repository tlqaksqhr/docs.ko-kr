---
title: "SpinLock | Microsoft Docs"
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
  - "synchronization primitives, SpinLock"
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# SpinLock
<xref:System.Threading.SpinLock> 구조는 잠금 확보 대기 중에 스핀되는 낮은 수준의 상호 제외 동기화 기본 형식입니다.  다중 코어 컴퓨터에서 대기 시간이 짧을 것으로 예상되고 경합이 적으면 다른 종류의 잠금보다 <xref:System.Threading.SpinLock>을 수행하는 것이 효과적입니다.  그러나 <xref:System.Threading.SpinLock>은 <xref:System.Threading.Monitor?displayProperty=fullName> 메서드 또는 <xref:System.Threading.Interlocked> 메서드로 인해 프로그램 성능이 크게 떨어진다는 점이 프로파일링을 통해 확인될 때만 사용하는 것이 좋습니다.  
  
 <xref:System.Threading.SpinLock>은 아직 잠금을 확보하지 않은 경우에도 스레드의 시간 간격을 계산할 수 있습니다.  이는 스레드 우선 순위 반전을 방지하고 가비지 수집기가 작업을 진행할 수 있도록 하기 위한 것입니다.  <xref:System.Threading.SpinLock>을 사용할 때는 모든 스레드가 아주 짧은 시간 범위 동안만 잠금을 유지할 수 있도록 하고, 잠금을 유지하는 동안에는 스레드가 잠금을 차단할 수 없도록 해야 합니다.  
  
 SpinLock은 값 형식이므로 두 복사본에서 같은 잠금을 참조하도록 하려면 참조를 통해 이를 명시적으로 전달해야 합니다.  
  
 이 형식을 사용하는 방법에 대한 자세한 내용은 <xref:System.Threading.SpinLock?displayProperty=fullName>을 참조하십시오.  예제를 보려면 [How to: Use SpinLock for Low\-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)를 참조하십시오.  
  
 <xref:System.Threading.SpinLock>은 지정된 시간에 잠금을 유지하는 스레드를 추적하기 위해 개발 단계 중에 사용할 수 있는 *스레드*\-*추적* 모드를 지원합니다.  스레드\-추적 모드는 디버깅 시 매우 유용하지만 성능을 저하시킬 수 있으므로 프로그램의 릴리스 버전에서는 해제하는 것이 좋습니다.  자세한 내용은 [How to: Enable Thread\-Tracking Mode in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md)을 참조하십시오.  
  
## 참고 항목  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)