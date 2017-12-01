---
title: "방법: SpinWait을 사용하여 2단계 대기 작업 구현"
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
helpviewer_keywords: SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2717ba2d63e4ecf40638c369b66f2c696e396a5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a>방법: SpinWait을 사용하여 2단계 대기 작업 구현
사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Threading.SpinWait?displayProperty=nameWithType> 2 단계 대기 작업을 구현 하는 개체입니다. 첫 번째 단계에서는 동기화 개체는 `Latch`, 잠금을 사용할 수 있게 되었는지 여부를 확인 하는 동안 몇 차례 회전 합니다. 잠금을 사용할 수 있게 하는 경우 두 번째 단계에서는 다음 `Wait` 메서드를 사용 하지 않고 반환는 <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> 대기 상태; 수행 하려면 그렇지 않으면 `Wait` 대기를 수행 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 기본 래치 동기화를 구현 하는 매우 기본적인를 보여 줍니다. 대기 시간이 매우 짧은 것으로 예상 되는이 데이터 구조를 사용할 수 있습니다. 이 예제는 예시용입니다. 프로그램에서 래치 형식 기능을 필요한 경우에 사용 하 여 고려 <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>합니다.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 래치를 사용 하 여는 <xref:System.Threading.SpinWait> 개체에 대 한 다음 호출 될 때까지 준비에서 회전 하는 데 `SpinOnce` 하면는 <xref:System.Threading.SpinWait> 스레드 시간 간격을 생성 합니다. 래치를 호출 하 여 컨텍스트 전환이 사용 하면 해당 시점에 <xref:System.Threading.WaitHandle.WaitOne%2A> 에 <xref:System.Threading.ManualResetEvent> 시간 제한 값의 나머지 부분에 전달 합니다.  
  
 로깅 출력 표시 얼마나 자주 래치를 사용 하지 않고 잠금을 획득 하 여 성능을 향상 시킬 수는 <xref:System.Threading.ManualResetEvent>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [스핀 대기](../../../docs/standard/threading/spinwait.md)  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)
