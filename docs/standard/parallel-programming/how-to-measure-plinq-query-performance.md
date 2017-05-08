---
title: "How to: Measure PLINQ Query Performance | Microsoft Docs"
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
  - "PLINQ queries, how to measure performance"
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Measure PLINQ Query Performance
이 예제에서는 <xref:System.Diagnostics.Stopwatch> 클래스를 사용하여 PLINQ 쿼리를 실행하는 데 소요되는 시간을 측정하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 빈 `foreach` 루프\(Visual Basic의 경우 `For Each`\)를 사용하여 쿼리를 실행하는 데 소요되는 시간을 측정합니다.  실제 코드에서는 일반적으로 루프에 추가 처리 단계가 포함되므로 총 쿼리 실행 시간이 늘어납니다.  루프 바로 전, 즉 쿼리 실행이 시작되기 전까지는 스톱워치가 시작되지 않습니다.  보다 세밀한 측정이 필요한 경우에는 `ElapsedMilliseconds` 대신 `ElapsedTicks` 속성을 사용할 수 있습니다.  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 총 실행 시간은 쿼리 구현을 시험하는 데 유용한 메트릭이지만 이것만으로는 전반적인 성능을 알 수 없는 경우도 있습니다.  쿼리 스레드 간의 상호 작용 및 쿼리 스레드와 실행 중인 다른 프로세스의 상호 작용을 깊이 있고 자세하게 보려면 동시성 시각화 도우미를 사용합니다.  자세한 내용은 [동시성 시각화 도우미](../Topic/Concurrency%20Visualizer.md)을 참조하십시오.  
  
## 참고 항목  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)