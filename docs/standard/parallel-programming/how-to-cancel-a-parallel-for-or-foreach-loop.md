---
title: "How to: Cancel a Parallel.For or ForEach Loop | Microsoft Docs"
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
  - "parallel foreach loop, how to cancel"
  - "parallel for loops, how to cancel"
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Cancel a Parallel.For or ForEach Loop
<xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> 메서드는 취소 토큰을 사용한 취소 기능을 지원합니다.  일반적인 취소에 대한 자세한 내용은 [취소](../../../docs/standard/threading/cancellation-in-managed-threads.md)를 참조하십시오.  병렬 루프에서는 <xref:System.Threading.Tasks.ParallelOptions> 매개 변수로 메서드에 <xref:System.Threading.CancellationToken>을 제공한 다음 병렬 호출을 try\-catch 블록 안에 넣습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>에 대한 호출을 취소하는 방법을 보여 줍니다.  <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> 호출에도 동일한 방법을 적용할 수 있습니다.  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 취소를 알리는 토큰이 <xref:System.Threading.Tasks.ParallelOptions> 인스턴스에 지정된 토큰과 동일한 경우 병렬 루프에서는 취소에 대해 단일 <xref:System.OperationCanceledException>을 throw합니다.  다른 토큰에 의해 취소가 발행한 경우 루프에서는 <xref:System.AggregateException>을 throw하고 <xref:System.OperationCanceledException>을 InnerException으로 throw합니다.  
  
## 참고 항목  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)