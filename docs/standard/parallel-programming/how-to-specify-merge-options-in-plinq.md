---
title: "How to: Specify Merge Options in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, how to use merge options"
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Specify Merge Options in PLINQ
이 예제에서는 PLINQ 쿼리의 모든 후속 연산자에 적용할 병합 옵션을 지정하는 방법을 보여 줍니다.  병합 옵션을 명시적으로 설정할 필요는 없지만 이렇게 하면 성능이 향상될 수 있습니다.  병합 옵션에 대한 자세한 내용은 [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)을 참조하십시오.  
  
> [!WARNING]
>  이 예제는 사용법을 보여 주기 위한 것이며, 이에 상응하는 순차 LINQ to Objects 쿼리보다 실행 속도가 느릴 수 있습니다.  속도 향상에 대한 자세한 내용은 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 소스의 순서가 지정되지 않고 모든 요소에 부담이 큰 함수가 적용되는 기본적인 경우의 병합 옵션 동작을 보여 줍니다.  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 <xref:System.Linq.ParallelMergeOptions> 옵션을 사용할 경우 첫 번째 요소가 생성될 때까지 원하지 않는 지연이 발생한다면 <xref:System.Linq.ParallelMergeOptions> 옵션을 사용하여 결과 요소를 더 빠르고 원활하게 생성할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Linq.ParallelMergeOptions>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)