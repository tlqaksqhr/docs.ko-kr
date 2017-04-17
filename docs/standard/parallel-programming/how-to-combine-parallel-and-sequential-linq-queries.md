---
title: "How to: Combine Parallel and Sequential LINQ Queries | Microsoft Docs"
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
  - "parallel queries, combine parallel and sequential"
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Combine Parallel and Sequential LINQ Queries
이 예제에서는 <xref:System.Linq.ParallelEnumerable.AsSequential%2A> 메서드를 사용하여 PLINQ에서 쿼리의 모든 후속 연산자가 순차적으로 처리되도록 지정하는 방법을 보여 줍니다.  순차적 처리는 대개 병렬 처리보다 느리지만 올바른 결과를 생성하기 위해 순차적 처리가 필요한 경우도 있습니다.  
  
> [!WARNING]
>  이 예제는 사용법을 보여 주기 위한 것이며, 이에 상응하는 순차 LINQ to Objects 쿼리보다 실행 속도가 느릴 수 있습니다.  속도 향상에 대한 자세한 내용은 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>이 필요한 경우, 즉 쿼리의 이전 절에서 설정된 순서를 유지해야 하는 경우를 보여 줍니다.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## 코드 컴파일  
 이 코드를 컴파일하고 실행하려면 이를 [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) 프로젝트에 붙여넣고 `Main`에서 메서드를 호출하는 줄을 추가한 다음 F5 키를 누릅니다.  
  
## 참고 항목  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)