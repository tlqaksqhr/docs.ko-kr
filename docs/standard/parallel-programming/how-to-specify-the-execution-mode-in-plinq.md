---
title: "방법: PLINQ에 실행 모드 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 745ceae9832582c7b66a56075d128f9cf1c8ff69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a>방법: PLINQ에 실행 모드 지정
이 예의 기본 휴리스틱 무시 하 고 쿼리의 형태에 관계 없이 쿼리를 병렬화는 PLINQ 하는 방법을 보여 줍니다.  
  
> [!WARNING]
>  이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다. 속도 대 한 자세한 내용은 참조 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ는 병렬화에 대 한 기회를 이용 하도록 설계 되었습니다. 그러나 일부 쿼리 병렬 실행의 이점을 얻을 수 있습니다. 예를 들어 매우 적은 양의 작업을 수행 하는 단일 사용자 대리자, 포함 된 쿼리는 일반적으로 더 빠르게 순차적으로 실행 합니다. 즉, 병렬화 실행에 관련 된 오버 헤드는 지금까지 가져온 보다 더 비쌉니다. 따라서 PLINQ는 자동으로 모든 쿼리를 병렬화 되지 않습니다. 먼저 쿼리 및 구성 하는 다양 한 연산자의 셰이프를 검사 합니다. 이 분석에 따라, 기본 실행 모드에서 PLINQ 쿼리의 일부 또는 전부를 순차적으로 실행을 결정할 수 있습니다. 그러나 경우에 따라 알고 있습니다 더는 쿼리에 대 한 PLINQ에서 분석을 통해 확인할 수 있는 것 보다. 예를 들어 대리자 매우 상당히 소모 되며 쿼리에 평행에서 확실 하 게 이점이 있는지 알고 있습니다. 이러한 경우에 사용할 수 있습니다는 <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> 메서드를 지정 하 고는 <xref:System.Linq.ParallelExecutionMode.ForceParallelism> plinq 항상를 병렬로 쿼리를 실행 하도록 하는 값입니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 잘라내기 및 붙여넣기에이 코드는 [PLINQ 데이터 샘플](../../../docs/standard/parallel-programming/plinq-data-sample.md) 에서 메서드를 호출 하 고 `Main`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>  
 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
