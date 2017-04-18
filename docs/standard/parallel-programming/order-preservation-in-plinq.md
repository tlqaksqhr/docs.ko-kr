---
title: "Order Preservation in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, order preservation"
ms.assetid: 10d202bc-19e1-4b5c-bbf1-9a977322a9ca
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Order Preservation in PLINQ
PLINQ에서는 성능을 최대화하면서 정확성을 유지하는 것이 목적입니다.  쿼리는 가능한 한 빠르게 실행되면서도 올바른 결과를 생성해야 합니다.  정확성을 유지하기 위해 소스 시퀀스의 순서를 유지해야 하는 경우도 있지만 순서를 유지하는 경우 많은 계산 과정이 필요할 수 있습니다.  따라서 PLINQ에서는 기본적으로 소스 시퀀스의 순서가 유지되지 않습니다.  이런 점에서 PLINQ는 [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)]과 유사하지만 순서가 유지되는 LINQ to Objects와는 다릅니다.  
  
 기본 동작을 재정의하려면 소스 시퀀스에 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 연산자를 사용하여 순서 유지 기능을 설정합니다.  그런 다음 쿼리의 뒷부분에서 <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> 메서드를 사용하여 순서 유지 기능을 해제할 수 있습니다.  두 메서드를 사용할 때 모두 쿼리를 병렬로 실행할지 순차적으로 실행할지 결정하는 휴리스틱을 기반으로 쿼리가 처리됩니다.  자세한 내용은 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)을 참조하십시오.  
  
 다음 예제에서는 어떤 방식으로도 결과의 순서를 지정하지 않고 조건과 일치하는 모든 요소를 필터링하는 순서가 지정되지 않은 병렬 쿼리를 보여 줍니다.  
  
 [!code-csharp[PLINQ#8](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#8)]
 [!code-vb[PLINQ#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#8)]  
  
 이 쿼리는 반드시 소스 시퀀스의 도시 중 조건을 만족하는 처음 1000개의 도시를 생성하는 것이 아니라 조건을 만족하는 1000개의 도시가 포함된 임의의 집합을 생성합니다.  PLINQ 쿼리 연산자는 소스 시퀀스를 동시 작업으로 처리되는 여러 개의 하위 시퀀스로 분할합니다.  순서 유지 기능을 지정하지 않은 경우 각 파티션의 결과는 임의의 순서로 쿼리의 다음 단계에 전달됩니다.  또한 한 파티션에서 나머지 요소에 대한 처리를 계속하기 전에 결과의 하위 집합이 생성될 수 있습니다.  결과 순서는 매번 달라질 수 있습니다.  결과 순서는 운영 체제에서 스레드를 예약하는 방식에 따라 달라지므로 응용 프로그램에서는 이 순서를 제어할 수 없습니다.  
  
 다음 예제에서는 소스 시퀀스에 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 연산자를 사용하여 기본 동작을 재정의합니다.  이것은 소스 시퀸스에서 조건을 만족시키는 처음 10개 도시를 반환하는 <xref:System.Linq.ParallelEnumerable.Take%2A> 메서드를 보장합니다.  
  
 [!code-csharp[PLINQ#9](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#9)]
 [!code-vb[PLINQ#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#9)]  
  
 그러나 이 쿼리는 전체 파티션에서 원래 순서를 추적해야 하고 병합 시 순서가 일관되도록 해야 하므로 순서가 지정되지 않은 쿼리만큼 빠르게 실행되지 않을 수 있습니다.  따라서 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>는 필요할 때 이 연산자가 필요한 쿼리 부분에만 사용하는 것이 좋습니다.  더 이상 순서를 유지할 필요가 없으면 <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>를 사용하여 순서 유지 기능을 해제합니다.  다음 예제에서는 이를 위해 두 개의 쿼리를 작성합니다.  
  
 [!code-csharp[PLINQ#6](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#6)]
 [!code-vb[PLINQ#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#6)]  
  
 PLINQ에서는 순서 적용 연산자에 의해 생성된 시퀀스의 순서가 쿼리의 나머지 부분에 대해서도 유지됩니다.  즉, <xref:System.Linq.ParallelEnumerable.OrderBy%2A> 및 <xref:System.Linq.ParallelEnumerable.ThenBy%2A> 등의 연산자는 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>가 호출되기 전에 호출된 것처럼 처리됩니다.  
  
## 쿼리 연산자 및 순서  
 다음 쿼리 연산자는 순서 유지 기능을 쿼리의 모든 후속 작업에 적용하거나 <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>가 호출될 때까지 적용합니다.  
  
-   <xref:System.Linq.ParallelEnumerable.OrderBy%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.ThenBy%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>  
  
 다음 PLINQ 쿼리 연산자는 경우에 따라 소스 시퀀스의 순서가 지정되어야 올바른 결과를 생성할 수 있습니다.  
  
-   <xref:System.Linq.ParallelEnumerable.Reverse%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.TakeWhile%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.SkipWhile%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.Zip%2A>  
  
 일부 PLINQ 쿼리 연산자는 소스 시퀀스의 순서가 지정되었는지 여부에 따라 다르게 동작합니다.  다음 표에서는 이러한 연산자를 보여 줍니다.  
  
|연산자|소스 시퀀스의 순서가 지정된 경우의 결과|소스 시퀀스의 순서가 지정되지 않은 경우의 결과|  
|---------|----------------------------|--------------------------------|  
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A>|비결합적 또는 비가환적 작업의 경우 불명확한 결과가 출력됩니다.|비결합적 또는 비가환적 작업의 경우 불명확한 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.All%2A>|해당 없음|해당 없음|  
|<xref:System.Linq.ParallelEnumerable.Any%2A>|해당 없음|해당 없음|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|해당 없음|해당 없음|  
|<xref:System.Linq.ParallelEnumerable.Average%2A>|비결합적 또는 비가환적 작업의 경우 불명확한 결과가 출력됩니다.|비결합적 또는 비가환적 작업의 경우 불명확한 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Count%2A>|해당 없음|해당 없음|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|해당 없음|해당 없음|  
|<xref:System.Linq.ParallelEnumerable.Distinct%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.ElementAt%2A>|지정된 요소가 반환됩니다.|임의의 요소가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.ElementAtOrDefault%2A>|지정된 요소가 반환됩니다.|임의의 요소가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Except%2A>|순서가 지정되지 않은 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.First%2A>|지정된 요소가 반환됩니다.|임의의 요소가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.FirstOrDefault%2A>|지정된 요소가 반환됩니다.|임의의 요소가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|병렬로 불명확하게 실행됩니다.|병렬로 불명확하게 실행됩니다.|  
|<xref:System.Linq.ParallelEnumerable.GroupBy%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.GroupJoin%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Intersect%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Join%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Last%2A>|지정된 요소가 반환됩니다.|임의의 요소가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.LastOrDefault%2A>|지정된 요소가 반환됩니다.|임의의 요소가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.LongCount%2A>|해당 없음|해당 없음|  
|<xref:System.Linq.ParallelEnumerable.Min%2A>|해당 없음|해당 없음|  
|<xref:System.Linq.ParallelEnumerable.OrderBy%2A>|시퀀스의 순서가 다시 지정됩니다.|순서가 지정된 새 섹션이 시작됩니다.|  
|<xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>|시퀀스의 순서가 다시 지정됩니다.|순서가 지정된 새 섹션이 시작됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Range%2A>|해당 사항 없음\(<xref:System.Linq.ParallelEnumerable.AsParallel%2A>과 동일한 기본값\)|해당 없음|  
|<xref:System.Linq.ParallelEnumerable.Repeat%2A>|해당 사항 없음\(<xref:System.Linq.ParallelEnumerable.AsParallel%2A>과 동일한 기본값\)|해당 없음|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|반전됩니다.|아무 작업도 수행되지 않습니다.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>\(인덱싱됨\)|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>\(인덱싱됨\)|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>|순서가 지정된 비교가 출력됩니다.|순서가 지정되지 않은 비교가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Single%2A>|해당 없음|해당 없음|  
|<xref:System.Linq.ParallelEnumerable.SingleOrDefault%2A>|해당 없음|해당 없음|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|처음 *n* 개의 요소가 생략됩니다.|임의의 *n* 개 요소가 생략됩니다.|  
|<xref:System.Linq.ParallelEnumerable.SkipWhile%2A>|순서가 지정된 결과가 출력됩니다.|불명확합니다.  현재의 임의 순서로 SkipWhile이 수행됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Sum%2A>|비결합적 또는 비가환적 작업의 경우 불명확한 결과가 출력됩니다.|비결합적 또는 비가환적 작업의 경우 불명확한 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|처음 `n`개의 요소가 사용됩니다.|임의의 `n`개 요소가 사용됩니다.|  
|<xref:System.Linq.ParallelEnumerable.TakeWhile%2A>|순서가 지정된 결과가 출력됩니다.|불명확합니다.  현재의 임의 순서로 TakeWhile이 수행됩니다.|  
|<xref:System.Linq.ParallelEnumerable.ThenBy%2A>|`OrderBy`를 보완합니다.|`OrderBy`를 보완합니다.|  
|<xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>|`OrderBy`를 보완합니다.|`OrderBy`를 보완합니다.|  
|<xref:System.Linq.ParallelEnumerable.ToArray%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.ToDictionary%2A>|해당 없음|해당 없음|  
|<xref:System.Linq.ParallelEnumerable.ToList%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.ToLookup%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Union%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>\(인덱싱됨\)|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
|<xref:System.Linq.ParallelEnumerable.Zip%2A>|순서가 지정된 결과가 출력됩니다.|순서가 지정되지 않은 결과가 출력됩니다.|  
  
 순서가 지정되지 않은 결과는 적극적으로 섞이지 않으며 이 결과에 적용되는 특수 정렬 논리는 없습니다.  순서가 지정되지 않은 쿼리에 소스 시퀀스의 순서가 유지되는 경우도 있습니다.  인덱싱된 Select 연산자를 사용하는 쿼리에 대해 PLINQ는 출력 요소가 증가하는 인덱스 순서로 나타나도록 하지만 어떤 요소에 어떤 인덱스를 할당할지에 대해서는 보장하지 않습니다.  
  
## 참고 항목  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)