---
title: SpinWait
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
helpviewer_keywords: synchronization primitives, SpinWait
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfaf85c0fe1de3be89618ae540e9c183b66a11eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="spinwait"></a>SpinWait
<xref:System.Threading.SpinWait?displayProperty=nameWithType>비용이 많이 드는 컨텍스트 전환 및 커널 이벤트에 필요한 커널 전환을 방지 하기 위해 하위 수준 시나리오에서 사용할 수 있는 간단한 동기화 형식이입니다. 다중 코어 컴퓨터에서 것 오랜 시간 동안 유지 되어야 하는 리소스를 사용할 수 없습니다 경우 몇 가지 수십 또는 백 사이클에서는 사용자 모드에서 시작 하 고 리소스 확보 한 다음 다시 시도를 대기 중인 스레드에 대 한 더 효율적일 수 있습니다. 회전 후 사용 가능한 리소스가 경우 천 몇 회의 주기를 저장 했습니다 합니다. 리소스가 여전히 사용할 수 없으면 다음 몇 차례만 투자 했으며 커널 기반 대기를 입력할 수 있습니다. 이 회전 다음 대기 조합은 때때로 이라고는 *2 단계 대기 작업*합니다.  
  
 <xref:System.Threading.SpinWait>와 같은 커널 이벤트를 래핑하는.NET Framework 형식 함께에서 사용 하도록 설계 <xref:System.Threading.ManualResetEvent>합니다. <xref:System.Threading.SpinWait>사용할 수도 있습니다 자체적으로 하나의 프로그램에서 기본 회전 기능에 대 한 합니다.  
  
 <xref:System.Threading.SpinWait>빈 루프 보다 더입니다. 일반적인 경우에 대 한 올바른 회전 동작을 제공 하도록 구현 신중 하 게 되 고 시작 합니다 컨텍스트 전환 만큼 회전 하는 경우 (대략 커널 전환에 필요한 시간의 길이). 단일 코어 컴퓨터에서 예를 들어 <xref:System.Threading.SpinWait> 스레드 시간 조각 생성 회전 블록이 앞으로 모든 스레드에서 진행 때문에 즉시 합니다. <xref:System.Threading.SpinWait>대기 스레드가 우선 순위가 높은 스레드에서 얼마 또는 가비지 수집기를 차단 하지 않도록 하려면 다중 코어 컴퓨터에도 보여 줍니다. 따라서 사용 하는 경우는 <xref:System.Threading.SpinWait> 2 단계 대기 작업의 호출 하기 전에 커널 대기 하는 권장는 <xref:System.Threading.SpinWait> 컨텍스트 스위치 시작 합니다. <xref:System.Threading.SpinWait>제공 된 <xref:System.Threading.SpinWait.NextSpinWillYield%2A> 를 호출 하기 전에 확인할 수 있는 속성 <xref:System.Threading.SpinWait.SpinOnce%2A>합니다. 속성이 반환 하는 경우 `true`, 사용자 고유의 대기 작업을 시작 합니다. 예를 들어 참조 [하는 방법: 2 단계 대기 작업을 구현 하는 사용 하 여 SpinWait](../../../docs/standard/threading/how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md)합니다.  
  
 2 단계 대기 작업을 수행 하지 않고 있으며 해도 일부 조건이 true가 될 때까지 단순히 회전 하는 경우 설정할 수 있습니다 <xref:System.Threading.SpinWait> 해당 컨텍스트를 수행 하려면 Windows 운영 체제 환경에서 제대로 작동 되도록 전환 합니다. 다음 기본 예제에서는 한 <xref:System.Threading.SpinWait> 잠금 없는 스택의 합니다. 고성능, 스레드로부터 안전한 스택, 필요한 경우에 사용 하 여 고려 <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>합니다.  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Thread.SpinWait%2A>  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)
