---
title: "How to: Speed Up Small Loop Bodies | Microsoft Docs"
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
  - "parallel loops, how to speed up"
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# How to: Speed Up Small Loop Bodies
<xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> 루프에 작은 본문이 있는 경우 C\#의 [for](../Topic/for%20\(C%23%20Reference\).md) 루프 및 Visual Basic의 [For](http://msdn.microsoft.com/ko-kr/c470a263-9b49-4308-8fd6-8592b84a7980) 루프와 같은 동등한 순차 루프보다 성능이 느려질 수 있습니다.  성능 저하는 데이터 분할과 관련된 오버헤드 및 각 루프 반복에서 대리자를 호출하는 비용으로 인해 발생합니다.  이러한 시나리오를 처리하기 위해 <xref:System.Collections.Concurrent.Partitioner> 클래스는 <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=fullName> 메서드를 제공합니다. 이 메서드를 통해 대리자가 반복당 한 번이 아니라 파티션당 한 번만 호출되도록 대리자 본문에 대한 순차 루프를 제공할 수 있습니다.  자세한 내용은 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)를 참조하세요.  
  
## 예제  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 이 예제에서 설명하는 접근 방식은 루프가 최소한의 작업을 수행하는 경우에 유용합니다.  작업이 많은 계산을 포함하게 되면 기본 파티셔너와 함께 <xref:System.Threading.Tasks.Parallel.For%2A> 또는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프를 사용하여 동일하거나 더 나은 성능을 얻을 수 있습니다.  
  
## 참고 항목  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)   
 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)