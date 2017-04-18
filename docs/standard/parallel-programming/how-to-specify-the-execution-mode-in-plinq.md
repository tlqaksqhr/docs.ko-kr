---
title: "How to: Specify the Execution Mode in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, how to use execution mode"
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Specify the Execution Mode in PLINQ
이 예제에서는 PLINQ에서 기본 휴리스틱을 무시하고 쿼리의 형태에 관계없이 쿼리를 병렬화하도록 지정하는 방법을 보여 줍니다.  
  
> [!WARNING]
>  이 예제는 사용법을 보여 주기 위한 것이며, 이에 상응하는 순차 LINQ to Objects 쿼리보다 실행 속도가 느릴 수 있습니다.  속도 향상에 대한 자세한 내용은 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)를 참조하십시오.  
  
## 예제  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ는 가능할 때마다 병렬화를 활용할 수 있도록 만들어졌습니다.  그러나 일부 쿼리는 병렬로 실행해도 이점이 없습니다.  예를 들어 매우 적은 양의 작업만 수행하는 단일 사용자 대리자가 포함된 쿼리는 대개 순차적으로 실행하는 것이 더 빠릅니다.  개선되는 속도에 비해 실행을 병렬화하는 데 필요한 오버헤드가 너무 크기 때문입니다.  따라서 PLINQ에서는 모든 쿼리를 자동으로 병렬화하는 것이 아니라,  먼저 쿼리의 형태와 쿼리를 구성하는 다양한 연산자를 확인합니다.  기본 실행 모드의 PLINQ에서는 이 분석 결과에 따라 쿼리의 일부 또는 모든 부분을 순차적으로 실행하도록 결정할 수 있습니다.  그러나 일부 경우에는 쿼리와 관련하여 PLINQ에서 분석을 통해 확인할 수 있는 것보다 사용자가 알고 있는 정보가 더 많을 수도 있습니다.  예를 들어 대리자의 부담이 크며 쿼리를 병렬화함으로써 얻을 수 있는 이점은 한정적일 것으로 판단되는 경우가 있습니다.  이 경우 <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> 메서드를 사용하고 <xref:System.Linq.ParallelExecutionMode> 값을 지정하여 PLINQ에서 항상 쿼리를 병렬로 실행하도록 지정할 수 있습니다.  
  
## 코드 컴파일  
 이 코드를 복사하여 [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md)에 붙여넣고 `Main`에서 해당 메서드를 호출합니다.  
  
## 참고 항목  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)