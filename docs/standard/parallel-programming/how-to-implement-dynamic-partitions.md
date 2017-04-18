---
title: "How to: Implement Dynamic Partitions | Microsoft Docs"
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
  - "tasks, how to create a dynamic partitioner"
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# How to: Implement Dynamic Partitions
다음 예제에서는 동적 분할을 구현하고 <xref:System.Threading.Tasks.Parallel.ForEach%2A>의 특정 오버로드 및 PLINQ에서 사용할 수 있는 사용자 지정 <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=fullName>을 구현하는 방법을 보여 줍니다.  
  
## 예제  
 파티션에서 <xref:System.Collections.IEnumerator.MoveNext%2A>를 열거자에 대해 호출할 때마다 열거자는 파티션에 목록 요소를 하나 제공합니다.  PLINQ 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A>의 경우 파티션은 <xref:System.Threading.Tasks.Task> 인스턴스입니다.  여러 스레드에서 요청이 동시에 발생하기 때문에 현재 인덱스에 대한 액세스는 동기화됩니다.  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 이는 각 청크가 하나의 요소로 구성되어 있는 청크 분할의 예입니다.  한 번에 보다 많은 요소를 제공하면 잠금에 대한 경합을 줄일 수 있고 이론적으로는 수행 속도를 향상시킬 수 있습니다.  그러나 모든 작업이 수행될 때까지 모든 스레드가 유휴 상태에 있지 않도록 하려면 특정 시점에는 큰 청크 때문에 추가적인 부하 분산 논리가 필요할 수 있습니다.  
  
## 참고 항목  
 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)   
 [How to: Implement a Partitioner for Static Partitioning](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)