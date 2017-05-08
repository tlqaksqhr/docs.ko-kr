---
title: "Parallel LINQ (PLINQ) | Microsoft Docs"
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
  - "PLINQ, overview"
ms.assetid: 3d4d0cd3-bde4-490b-99e7-f4e41be96455
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Parallel LINQ (PLINQ)
PLINQ\(병렬 LINQ\)는 LINQ to Objects의 병렬 구현입니다.  PLINQ는 LINQ 표준 쿼리 연산자의 전체 집합을 T:System.Linq 네임스페이스에 대한 확장 메서드로 구현하며 병렬 작업을 위한 추가 연산자를 포함합니다.  PLINQ는 LINQ 구문의 편의성 및 가독성과 강력한 병렬 프로그래밍 기능을 결합한 것입니다.  작업 병렬 라이브러리를 대상으로 하는 코드와 마찬가지로 PLINQ 쿼리의 동시성 수준은 호스트 컴퓨터의 용량에 따라 결정됩니다.  
  
 대부분의 경우 PLINQ를 사용하면 호스트 컴퓨터의 사용 가능한 모든 코어를 보다 효율적으로 사용하여 LINQ to Objects 쿼리를 사용할 때보다 속도를 상당히 높일 수 있습니다.  이렇게 향상된 쿼리 성능은 데스크톱의 계산 성능도 향상시켜 줍니다.  
  
## 단원 내용  
 [Introduction to PLINQ](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
  
 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)  
  
 [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)  
  
 [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)  
  
 [How to: Create and Execute a Simple PLINQ Query](../../../docs/standard/parallel-programming/how-to-create-and-execute-a-simple-plinq-query.md)  
  
 [How to: Control Ordering in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md)  
  
 [How to: Combine Parallel and Sequential LINQ Queries](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)  
  
 [How to: Handle Exceptions in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)  
  
 [How to: Cancel a PLINQ Query](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)  
  
 [How to: Write a Custom PLINQ Aggregate Function](../../../docs/standard/parallel-programming/how-to-write-a-custom-plinq-aggregate-function.md)  
  
 [How to: Specify the Execution Mode in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)  
  
 [How to: Specify Merge Options in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)  
  
 [How to: Iterate File Directories with PLINQ](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)  
  
 [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)  
  
 [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md)  
  
## 참고 항목  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)