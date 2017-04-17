---
title: "How to: Synchronize Concurrent Operations with a Barrier | Microsoft Docs"
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
  - "Barrier, how to use"
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Synchronize Concurrent Operations with a Barrier
다음 예제에서는 <xref:System.Threading.Barrier>를 사용하여 동시 작업을 동기화하는 방법을 보여 줍니다.  
  
## 예제  
 다음 프로그램의 목적은 무작위 선택 알고리즘으로 단어를 뒤섞은 후 두 스레드가 각각 동일한 단계에서 해의 절반을 각각 찾아내는 데 필요한 반복\(또는 단계\) 횟수를 구하는 데 있습니다.  각 스레드에서 해당 단어를 뒤섞은 후 배리어 사후 단계 작업으로 두 결과를 비교하여 완전한 문장이 올바른 단어 순서대로 렌더링되었는지 확인합니다.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <xref:System.Threading.Barrier>는 병렬로 실행되는 작업이 모두 장벽에 도달할 때까지 개별 작업이 계속 실행되고 있지 않도록 방지하는 개체입니다.  이는 병렬 작업이 단계별로 이루어지고 각 단계에서 작업 사이에 동기화가 필요한 경우 유용합니다.  이 예제에서는 작업이 두 단계로 진행됩니다.  첫째 단계에서는 각 작업을 통해 해당 버퍼 섹션을 데이터로 채웁니다.  각 작업에서 해당 섹션을 채우고 나면 다음 단계를 계속 진행할 준비가 되었다는 신호가 장벽에 보내지고 작업은 대기 상태로 들어갑니다.  모든 작업에서 장벽에 신호를 보내고 나면 대기 상태이던 작업의 차단이 해제되고 둘째 단계가 시작됩니다.  둘째 단계에서는 각 작업을 통해 현재 시점까지 생성된 모든 데이터에 액세스해야 하므로 두 단계를 구분하는 이와 같은 장벽이 필요합니다.  장벽이 없으면 먼저 완료된 작업에서 아직 다른 작업을 통해 미처 채우지 못한 버퍼의 데이터를 읽으려고 시도할 수 있습니다.  이와 같은 방식으로 동기화할 수 있는 단계의 수에는 제한이 없습니다.  
  
## 참고 항목  
 [Data Structures for Parallel Programming](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)