---
title: "How to: Use SpinWait to Implement a Two-Phase Wait Operation | Microsoft Docs"
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
  - "SpinWait, how to synchronize two-phase wait"
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Use SpinWait to Implement a Two-Phase Wait Operation
다음 예제에서는 <xref:System.Threading.SpinWait?displayProperty=fullName> 개체를 사용하여 2단계 대기 작업을 구현하는 방법을 보여 줍니다.  첫 번째 단계에서는 동기화 개체인 `Latch`가 잠금을 사용할 수 있게 되었는지 여부를 확인하는 동안 몇 차례 회전합니다.  두 번째 단계에서는 잠금을 사용할 수 있으면 `Wait` 메서드가 <xref:System.Threading.ManualResetEvent?displayProperty=fullName>를 사용하여 대기를 수행하지 않은 채 반환되고, 그렇지 않으면 `Wait`가 대기를 수행합니다.  
  
## 예제  
 이 예제에서는 래치 동기화 기본 형식의 기본 구현을 보여 줍니다.  대기 시간이 매우 짧을 것으로 예상될 경우 이 데이터 구조를 사용할 수 있습니다.  이 예제는 예시 목적으로만 제공됩니다.  프로그램에 래치 형식 기능이 필요하면 <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>을 사용할 수 있습니다.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 래치는 `SpinOnce`에 대한 다음 호출에 의해 <xref:System.Threading.SpinWait>가 스레드의 시간 간격을 계산할 때까지만 <xref:System.Threading.SpinWait> 개체를 사용하여 제자리에서 회전합니다.  이때 래치는 <xref:System.Threading.ManualResetEvent>에 대해 <xref:System.Threading.WaitHandle.WaitOne%2A>을 호출하고 제한 시간 값의 남아 있는 시간에 전달하여 컨텍스트 전환이 수행되도록 합니다.  
  
 로깅 결과에서는 래치가 <xref:System.Threading.ManualResetEvent>를 사용하지 않고도 얼마나 자주 잠금을 획득하여 성능을 향상시킬 수 있었는지를 보여 줍니다.  
  
## 참고 항목  
 [SpinWait](../../../docs/standard/threading/spinwait.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)