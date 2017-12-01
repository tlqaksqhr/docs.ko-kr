---
title: "방법: 동적 파티션 구현"
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
helpviewer_keywords: tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1e5dc93997918e0f7da29fa1f94c434a556f19f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-dynamic-partitions"></a>방법: 동적 파티션 구현
다음 예제에서는 사용자 지정을 구현 하는 방법을 보여 줍니다. <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> 동적 분할을 구현 하 고 특정 오버 로드에서 사용할 수 있는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 및 PLINQ 합니다.  
  
## <a name="example"></a>예제  
 파티션을 호출할 때마다 <xref:System.Collections.IEnumerator.MoveNext%2A> 파티션을 목록 요소를 하나 열거자에 열거자를 제공 합니다. PLINQ의 경우 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A>, 파티션이 <xref:System.Threading.Tasks.Task> 인스턴스. 요청에서 발생 하 고 동시에 여러 스레드를 때문에 현재 인덱스에 대 한 액세스 동기화 됩니다.  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 이것이 청크 하나의 요소로 구성 되어 각 청크를 사용 하 여 분할의 예입니다. 더 많은 요소를 한 번에 제공 하 여 잠금을 통해 경합을 줄이려면 고 이론적으로 더 빠른 성능을 얻을 수 있습니다. 그러나 일부 시점에서는 더 큰 청크로 구성 필요할 수 있습니다 부하 분산 하는 추가 논리 작업을 모두 완료 될 때까지 모든 스레드를 사용 중 상태로 유지 하기 위해.  
  
## <a name="see-also"></a>참고 항목  
 [PLINQ 및 TPL에 대한 사용자 지정 파티셔너](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [방법: 정적 분할을 위한 파티셔너 구현](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
