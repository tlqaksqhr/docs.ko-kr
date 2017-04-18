---
title: "How to: Control Ordering in a PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to control ordering"
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Control Ordering in a PLINQ Query
이 예제에서는 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 확장 메서드를 사용하여 PLINQ 쿼리의 순서를 제어하는 방법을 보여 줍니다.  
  
> [!WARNING]
>  이 예제들은 주로 사용법을 보여 주기 위한 것이며, 이에 상응하는 순차 LINQ to Objects 쿼리보다 실행 속도가 느리거나 느리지 않을 수 있습니다.  
  
## 예제  
 다음 예제에서는 소스 시퀀스의 순서를 유지합니다.  일부 쿼리 연산자에서 순서가 지정된 소스 시퀀스를 사용해야 올바른 결과가 생성되는 경우와 같이 소스 시퀀스의 순서를 유지해야 하는 경우가 있습니다.  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## 예제  
 다음 예제에서는 순서가 지정된 소스 시퀀스를 사용해야 할 수 있는 몇 가지 쿼리 연산자를 보여 줍니다.  이러한 연산자는 순서가 지정되지 않은 시퀀스에서도 작동하지만 예기치 않은 결과가 생성될 수 있습니다.  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 이 메서드를 실행하려면 [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) 프로젝트의 PLINQDataSample 클래스에 코드를 붙여넣고 F5 키를 누릅니다.  
  
## 예제  
 다음 예제에서는 쿼리의 첫 번째 부분에 대한 순서를 유지하고, 이 순서를 제거하여 조인 절의 성능을 향상시키고, 최종 결과 시퀀스에 순서를 다시 적용하는 방법을 보여 줍니다.  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 이 메서드를 실행하려면 [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) 프로젝트의 PLINQDataSample 클래스에 코드를 붙여넣고 F5 키를 누릅니다.  
  
## 참고 항목  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)