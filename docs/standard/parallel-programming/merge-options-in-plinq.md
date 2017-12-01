---
title: "PLINQ의 병합 옵션"
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
helpviewer_keywords: PLINQ queries, merge options
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e9bf586c1805fc5b5f1cc5f96f4e6b08d80c199a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="merge-options-in-plinq"></a>PLINQ의 병합 옵션
쿼리 실행 될 때, PLINQ 파티션으로 소스 시퀀스 여러 스레드에서 작업할 수 있도록 다른 부분에서 동시에 일반적으로 별도 스레드에서 합니다. 결과 하나의 스레드에서 사용할 수 있도록 하는 경우의 예를 들어 한 `foreach` (`For Each` 에 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 루프의 모든 스레드의 결과 단일 시퀀스로 다시 병합 해야 합니다. PLINQ 수행 하는 병합의 종류는 쿼리에 있는 연산자에 따라 달라 집니다. 예를 들어 결과에 새로운 순서를 적용 하는 연산자는 모든 스레드에서 모든 요소를 버퍼링 해야 합니다. 소비 스레드로 (해당 하는 또한 응용 프로그램 사용자)의 관점에서 전체적으로 버퍼링된 쿼리는 첫 번째 결과 생성 하기 전의 시간을 크게 기간 동안 실행 될 수 있습니다. 다른 연산자를 기본적으로 부분적으로 버퍼링 됩니다. 일괄 처리의 결과 생성 합니다. 연산자가 <xref:System.Linq.ParallelEnumerable.ForAll%2A> 기본적으로 버퍼링 되지 않습니다. 생성 요소를 모두에서 모든 스레드가 즉시 합니다.  
  
 사용 하 여는 <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> 메서드를 다음 예에서 같이 있습니다 힌트를 제공할 수 plinq 수행 하려면 병합 종류를 나타내는입니다.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 전체 예제를 참조 하십시오. [하는 방법: PLINQ에서 병합 옵션 지정](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)합니다.  
  
 특정 쿼리 요청된 된 옵션을 지원할 수 없는 경우에 옵션만 무시 됩니다. 대부분의 경우 PLINQ 쿼리에 대 한 병합 옵션을 지정할 필요가 없습니다. 그러나 경우에 따라 테스트 하 고 기본이 아닌 모드에서 쿼리는 최적으로 실행 하는 알 수 있습니다. 이 옵션의 일반적인 용도 응답성 사용자 인터페이스를 제공 하기 위해 그 결과 스트리밍하려면 청크 병합 연산자를 적용 하는 것입니다.  
  
## <a name="parallelmergeoptions"></a>ParallelMergeOptions  
 <xref:System.Linq.ParallelMergeOptions> 열거형을 지정 하는 지원 되는 쿼리 셰이프는 결과 하나의 스레드에서 사용 하는 경우 쿼리의 최종 출력이 생성 하는 방법을 다음 옵션을 포함 합니다.  
  
-   `Not Buffered`  
  
     <xref:System.Linq.ParallelMergeOptions.NotBuffered> 옵션을 사용 하면 처리 된 각 요소 생성 되는 즉시 각 스레드에서 반환할 수 있습니다. 이 동작은 출력 "스트리밍"와 비슷합니다. 경우는 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 연산자는 쿼리에 `NotBuffered` 소스 요소의 순서를 유지 합니다. 하지만 `NotBuffered` 사용할 수는 즉시 결과 생성 하기 시작, 모든 결과 유지 될 수 있습니다를 생성 하기 위한 총 시간은 다른 병합 옵션 중 하나를 사용 하 여 보다 길 수 있습니다.  
  
-   `Auto Buffered`  
  
     <xref:System.Linq.ParallelMergeOptions.AutoBuffered> 옵션을 사용하면 쿼리에서는 요소를 버퍼에 수집한 다음 정기적으로 버퍼 내용을 모두 한꺼번에 소비 스레드로 내보냅니다. "스트리밍" 동작을 사용 하는 대신 "청크"에 원본 데이터를 생성 합니다. 이것은 `NotBuffered`합니다. `AutoBuffered`보다 오래 걸릴 수 `NotBuffered` 소비 스레드에서 첫 번째 요소에서 사용할 수 있도록 합니다. 정확한 생성 동작 및 버퍼의 크기 구성 가능 하지 않으며 쿼리와 관련 된 다양 한 요인에 따라 달라질 수 있습니다.  
  
-   `FullyBuffered`  
  
     <xref:System.Linq.ParallelMergeOptions.FullyBuffered> 옵션을 사용 하면 전체 쿼리 요소가 생성 되기 때문 전에 버퍼링 할를 출력 합니다. 이 옵션을 사용 하면 느려질 수 있습니다 첫 번째 요소를 소비 스레드에서 사용할 수 있지만 완전 한 결과 생성 될 수 전에 다른 옵션을 사용 하 여 보다 더 빠릅니다.  
  
## <a name="query-operators-that-support-merge-options"></a>병합 옵션을 지 원하는 쿼리 연산자  
 다음 표에서 지정 된 제한에 따라 모든 병합 옵션 모드를 지 원하는 연산자를 나열 합니다.  
  
|연산자|제한|  
|--------------|------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|배열 또는 목록 원본만 사용 하는 순서가 지정 되지 않은 쿼리가 있습니다.|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|배열 또는 목록 원본만 사용 하는 순서가 지정 되지 않은 쿼리가 있습니다.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|없음|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|없음|  
  
 다른 모든 PLINQ 쿼리 연산자는 사용자가 제공한 병합 옵션을 무시 수도 있습니다. 예를 들어 일부 쿼리 연산자 <xref:System.Linq.ParallelEnumerable.Reverse%2A> 및 <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, 모든 생성 되어 순서가 변경 될 때까지 모든 요소를 생성할 수 없습니다. 따라서, <xref:System.Linq.ParallelMergeOptions> 도 같은 연산자를 포함 하는 쿼리에 사용 되는 <xref:System.Linq.ParallelEnumerable.Reverse%2A>, 해당 연산자에서 그 결과 발생 한 후 병합 동작 될 때까지 쿼리에 적용 되지 것입니다.  
  
 병합 옵션을 처리 하는 기능이 일부 연산자의 소스 시퀀스의 형식에 따라 달라 집니다 여부와 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 연산자가 이전에 쿼리에서 사용 합니다. <xref:System.Linq.ParallelEnumerable.ForAll%2A>항상 <xref:System.Linq.ParallelMergeOptions.NotBuffered> ; 요소 즉시 반환 합니다. <xref:System.Linq.ParallelEnumerable.OrderBy%2A>항상 <xref:System.Linq.ParallelMergeOptions.FullyBuffered>; 반환 하기 전에 전체 목록이 대로 정렬 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [방법: PLINQ에서 병합 옵션 지정](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)
