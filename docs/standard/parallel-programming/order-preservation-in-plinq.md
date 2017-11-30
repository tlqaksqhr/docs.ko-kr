---
title: "PLINQ에서 순서 유지"
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
helpviewer_keywords: PLINQ queries, order preservation
ms.assetid: 10d202bc-19e1-4b5c-bbf1-9a977322a9ca
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 060459cf8f408e40ddc394fbcda6a022ec6379de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="order-preservation-in-plinq"></a>PLINQ에서 순서 유지
PLINQ의 목표는 정확성을 유지 하면서 성능을 극대화할 수입니다. 쿼리 가능한 한 빠르게 실행 되지만 여전히 올바른 결과 생성 해야 합니다. 경우에 따라 정확성 필요 소스 시퀀스의 순서를 보존 해야 합니다. 그러나 순서 계산이 수 있습니다. 따라서 기본적으로 PLINQ 유지 하지 않습니다는 소스 시퀀스의 순서. 이런 점에서 PLINQ 유사한 [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)], 하지만 순서는 유지 하는 LINQ to Objects와 다릅니다.  
  
 기본 동작을 재정의 하려면 켤 수 있습니다 순서 유지를 사용 하 여는 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 소스 시퀀스에는 연산자입니다. 사용 하 여 나중에 쿼리에서 순서 유지 해제 한 다음는 <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> 메서드. 두 가지 방법, 쿼리는 쿼리를 병렬로 실행할 것인지를 결정 하는 추론에 따라 또는 순차적으로 처리 됩니다. 자세한 내용은 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)를 참조하세요.  
  
 다음 예제에서는 어떤 방식으로든에서 결과 정렬 하려고 하지 않고도 조건을 일치 하는 모든 요소에 대해 필터링 하는 순서가 지정 되지 않은 병렬 쿼리를 보여 줍니다.  
  
 [!code-csharp[PLINQ#8](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#8)]
 [!code-vb[PLINQ#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#8)]  
  
 이 쿼리를 제외한 아니라 몇 가지 조건을 충족 시키는 1000 도시 조건을 만족 하는 소스 시퀀스의 처음 1000 개의 도시를 반드시 생성 하지 않습니다. PLINQ 쿼리 연산자에는 동시 작업으로 처리 하는 여러 개의 하위 시퀀스로 소스 시퀀스를 분할 합니다. 순서 유지를 지정 하지 않은 경우의 결과를 각 파티션에 임의의 순서로 쿼리의 다음 단계로 전달 됩니다. 또한 파티션 처리는 나머지 요소를 계속 하기 전에 결과의 하위 집합을 얻을 수도 있습니다. 결과 순서 될 때마다 다 수 있습니다. 응용 프로그램 운영 체제 스레드를 예약 하는 방법에 따라 달라 지므로이 제어할 수 없습니다.  
  
 다음 예제를 사용 하 여 기본 동작 재정의 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 소스 시퀀스에는 연산자입니다. 이렇게 하면 <xref:System.Linq.ParallelEnumerable.Take%2A> 메서드가 소스 시퀀스에서 조건을 충족하는 처음 1000개의 도시를 반환합니다.  
  
 [!code-csharp[PLINQ#9](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#9)]
 [!code-vb[PLINQ#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#9)]  
  
 그러나이 쿼리 아마도 실행 되지 않습니다 순서가 지정 되지 않은 버전으로 빠른 전체 파티션에서 원래 순서 지정 한 추적 하 고 병합 시 순서 지정이 일치 하는지 확인 해야 하기 때문에. 사용 하는 권장 따라서 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 필요한 경우에 하 고 필요로 하는 쿼리 부분에 대해서만 합니다. 순서 유지는 더 이상 필요를 사용 하 여 <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> 을 해제 합니다. 다음 예제에서는 두 개의 쿼리를 작성 하 여 이것을 달성 합니다.  
  
 [!code-csharp[PLINQ#6](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#6)]
 [!code-vb[PLINQ#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#6)]  
  
 PLINQ 쿼리의 다른 부분에 대 한 주문 부과 연산자에서 생성 되는 시퀀스의 순서 유지 됨을 참고 합니다. 즉, 같은 연산자 <xref:System.Linq.ParallelEnumerable.OrderBy%2A> 및 <xref:System.Linq.ParallelEnumerable.ThenBy%2A> 를 호출 하 여 호출 된 것 처럼 처리 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>합니다.  
  
## <a name="query-operators-and-ordering"></a>쿼리 연산자 및 순서 지정  
 다음 쿼리 연산자 소개 순서 유지 될 때까지 또는 쿼리에서 모든 후속 작업으로 <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> 호출 됩니다.  
  
-   <xref:System.Linq.ParallelEnumerable.OrderBy%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.ThenBy%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>  
  
 다음 PLINQ 쿼리 연산자 경우에 따라 해야 올바른 결과 생성 하기 위해 정렬 된 소스 시퀀스:  
  
-   <xref:System.Linq.ParallelEnumerable.Reverse%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.TakeWhile%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.SkipWhile%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.Zip%2A>  
  
 일부 PLINQ 쿼리 연산자는 소스 시퀀스의 정렬 또는 순서가 지정 되지 않은 여부에 따라 다르게 동작 합니다. 다음 표에서 이러한 연산자를 나열합니다.  
  
|연산자|소스 시퀀스 정렬 되는 경우의 결과|소스 시퀀스 정렬 되지 않은 경우의 결과|  
|--------------|------------------------------------------------|--------------------------------------------------|  
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A>|결합성 없음 또는 비가 작업에 대 한 비결 정적 출력|결합성 없음 또는 비가 작업에 대 한 비결 정적 출력|  
|<xref:System.Linq.ParallelEnumerable.All%2A>|적용할 수 없음|적용할 수 없음|  
|<xref:System.Linq.ParallelEnumerable.Any%2A>|적용할 수 없음|적용할 수 없음|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|적용할 수 없음|적용할 수 없음|  
|<xref:System.Linq.ParallelEnumerable.Average%2A>|결합성 없음 또는 비가 작업에 대 한 비결 정적 출력|결합성 없음 또는 비가 작업에 대 한 비결 정적 출력|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.Count%2A>|적용할 수 없음|적용할 수 없음|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|적용할 수 없음|적용할 수 없음|  
|<xref:System.Linq.ParallelEnumerable.Distinct%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.ElementAt%2A>|지정 된 요소를 반환 합니다.|임의 요소|  
|<xref:System.Linq.ParallelEnumerable.ElementAtOrDefault%2A>|지정 된 요소를 반환 합니다.|임의 요소|  
|<xref:System.Linq.ParallelEnumerable.Except%2A>|순서가 지정 되지 않은 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.First%2A>|지정 된 요소를 반환 합니다.|임의 요소|  
|<xref:System.Linq.ParallelEnumerable.FirstOrDefault%2A>|지정 된 요소를 반환 합니다.|임의 요소|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|병렬에서 불명확 하 게 실행|병렬에서 불명확 하 게 실행|  
|<xref:System.Linq.ParallelEnumerable.GroupBy%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.GroupJoin%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.Intersect%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.Join%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.Last%2A>|지정 된 요소를 반환 합니다.|임의 요소|  
|<xref:System.Linq.ParallelEnumerable.LastOrDefault%2A>|지정 된 요소를 반환 합니다.|임의 요소|  
|<xref:System.Linq.ParallelEnumerable.LongCount%2A>|적용할 수 없음|적용할 수 없음|  
|<xref:System.Linq.ParallelEnumerable.Min%2A>|적용할 수 없음|적용할 수 없음|  
|<xref:System.Linq.ParallelEnumerable.OrderBy%2A>|시퀀스 순서를 재정렬 합니다.|새 섹션 정렬 시작|  
|<xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>|시퀀스 순서를 재정렬 합니다.|새 섹션 정렬 시작|  
|<xref:System.Linq.ParallelEnumerable.Range%2A>|해당 사항 없음 (과 동일한 기본값 <xref:System.Linq.ParallelEnumerable.AsParallel%2A> )|적용할 수 없음|  
|<xref:System.Linq.ParallelEnumerable.Repeat%2A>|해당 사항 없음 (과 동일한 기본값 <xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|적용할 수 없음|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|역순으로|아무 작업도 수행하지 않습니다.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>(인덱스)|정렬 된 결과|순서가 지정 되지 않은 결과입니다.|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|정렬 된 결과입니다.|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>(인덱스)|정렬 된 결과입니다.|순서가 지정 되지 않은 결과입니다.|  
|<xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>|순서가 지정 된 비교|순서가 지정 되지 않은 비교|  
|<xref:System.Linq.ParallelEnumerable.Single%2A>|적용할 수 없음|적용할 수 없음|  
|<xref:System.Linq.ParallelEnumerable.SingleOrDefault%2A>|적용할 수 없음|적용할 수 없음|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|먼저 건너뜁니다  *n*  요소|모든 건너뜁니다  *n*  요소|  
|<xref:System.Linq.ParallelEnumerable.SkipWhile%2A>|정렬 된 결과입니다.|비결 정적입니다. SkipWhile 현재 임의 순서에 수행합니다.|  
|<xref:System.Linq.ParallelEnumerable.Sum%2A>|결합성 없음 또는 비가 작업에 대 한 비결 정적 출력|결합성 없음 또는 비가 작업에 대 한 비결 정적 출력|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|첫 번째는 `n` 요소|사용 `n` 요소|  
|<xref:System.Linq.ParallelEnumerable.TakeWhile%2A>|정렬 된 결과|비결 정적입니다. TakeWhile 현재 임의 순서에 수행합니다.|  
|<xref:System.Linq.ParallelEnumerable.ThenBy%2A>|조항`OrderBy`|조항`OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>|조항`OrderBy`|조항`OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ToArray%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.ToDictionary%2A>|적용할 수 없음|적용할 수 없음|  
|<xref:System.Linq.ParallelEnumerable.ToList%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.ToLookup%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.Union%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>(인덱스)|정렬 된 결과|순서가 지정 되지 않은 결과|  
|<xref:System.Linq.ParallelEnumerable.Zip%2A>|정렬 된 결과|순서가 지정 되지 않은 결과|  
  
 순서가 지정 되지 않은 결과 적극적으로 섞 습니다 되지 않습니다. 단순히 없는에 적용 된 특별 한 정렬 논리입니다. 경우에 따라 순서가 지정 되지 않은 쿼리는 소스 시퀀스의 순서을 유지할 수 있습니다. 인덱스는 Select 연산자를 사용 하는 쿼리에 대 한 출력 요소 증가 시켜 인덱스, 하지만 어떤 인덱스에 대 한 보장은 없습니다 요소에 할당 될 순서 대로 상황이 개선 됩니다는 PLINQ 보장 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [병렬 프로그래밍](../../../docs/standard/parallel-programming/index.md)
