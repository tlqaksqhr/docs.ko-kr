---
title: "How to: Implement a Partitioner for Static Partitioning | Microsoft Docs"
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
  - "tasks, how to create a static partitioner"
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# How to: Implement a Partitioner for Static Partitioning
다음 예제에서는 정적 분할을 수행하는 PLINQ에 대한 간단한 사용자 지정 파티셔너를 구현하는 한 가지 방법을 보여 줍니다.  이 파티셔너는 동적 파티션을 지원하지 않기 때문에 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>에서 사용할 수 없습니다.  이 파티셔너는 각 요소의 처리에 많은 시간이 소요되는 데이터 소스에 대해 기본 범위 파티셔너보다 빠른 속도를 제공합니다.  
  
## 예제  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 이 예제의 파티션은 각 요소에 대한 처리 시간이 선형적으로 증가한다는 가정을 기반으로 합니다.  실제로는 처리 시간을 이러한 방식으로 예측하기 어려울 수 있습니다.  정적 파티셔너를 특정 데이터 소스와 함께 사용할 경우에는 해당 소스에 대한 분할 형식을 최적화하고 부하 분산 논리를 추가거나 [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)에서 설명된 청크 분할 방법을 사용할 수 있습니다.  
  
## 참고 항목  
 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)