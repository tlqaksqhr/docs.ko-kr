---
title: "PLINQ 및 TPL에 대한 사용자 지정 파티셔너"
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
helpviewer_keywords: tasks, partitioners
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12d234b86b0067178d54d2fdcb5d37ceaee6109d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="custom-partitioners-for-plinq-and-tpl"></a>PLINQ 및 TPL에 대한 사용자 지정 파티셔너
에 필수 단계 중 하나는 데이터 원본에 대 한 작업을 병렬화 *파티션* 여러 스레드에서 동시에 액세스할 수 있는 여러 섹션으로 소스입니다. PLINQ 및 TPL 작업 병렬 라이브러리 ()는 병렬 쿼리를 작성 하는 경우 투명 하 게 작동 하는 기본 파티션을 제공 또는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프입니다. 더 고급 시나리오에 대 한 사용자 고유의 파티 셔 너에 연결할 수 있습니다.  
  
## <a name="kinds-of-partitioning"></a>분할의 종류  
 데이터 소스를 분할 하는 방법은 여러 가지가 있습니다. 가장 효율적인 방법은 여러 스레드는 물리적으로 구분 하 여 소스 여러 하위 시퀀스에 아닌 프로세스 원래 소스 시퀀스에 있도록 협력 합니다. 배열 및 다른 인덱스가 소스와 같은 <xref:System.Collections.IList> 컬렉션 길이 사전에 알고 있는 *범위 분할* 분할의 가장 간단한 종류입니다. 모든 스레드가 다른 스레드에 의해 덮어쓰이지 하지 않고 소스 범위를 처리할 수 있도록 고유한 시작 및 끝 인덱스를 받습니다. 범위 분할 관련 된 유일한 오버 헤드는 범위가;의 초기 작업 그 후 없습니다 추가 동기화가 필요 합니다. 따라서 작업 부하를 균등 하 게 분할은으로 보다 나은 성능을 제공할 수 있습니다. 범위 분할의 단점은 한 스레드가 일찍 완료, 다른 스레드의 작업 완료 도움이 되지 것입니다.  
  
 연결 된 목록 또는 길이 알 수 없는 다른 컬렉션에 사용할 수 있습니다 *청크 분할*합니다. 청크 분할에 모든 스레드나 병렬 루프 또는 쿼리 작업의 일정 수의 하나의 소스 요소, 고 추가 요소를 검색 한 다음 다시 작동 합니다. 파티 셔 너 된 요소를 모두 배포 하 고 중복 항목이 없는지 확인 합니다. 청크는 크기에 제한이 될 수 있습니다. 예를 들어 파티 셔 너에 설명 된 [하는 방법: 동적 파티션 구현](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md) 한 요소만 포함 하는 청크를 만듭니다. 청크를 너무 커서 없는 상태로이 종류의 분할은 본질적으로 부하 분산 요소 스레드를 할당 미리 결정 되지 않기 때문에 있습니다. 그러나 파티 셔 너 동기화 오버 헤드로 인해 다른 청크 하는 데 필요한 스레드 때마다 유발 하지는 않습니다. 이러한 경우에 발생 하는 동기화 양은 반비례 청크 크기입니다.  
  
 일반적으로 범위 분할은 더 빠른 경우에 대리자의 실행 시간, 중간의 소스에는 많은 수의 요소 및 각 파티션의 총 작업와 대략 같습니다. 청크 분할 빠릅니다 따라서 일반적으로 대부분의 경우. 적은 수의 요소 또는 대리자에 대 한 실행 시간이 더 오래 된 원본에서 청크 및 범위 분할의 성능을 이면 거의 동일 합니다.  
  
 또한 TPL 파티 셔 너 파티션의 동적 수를 지원합니다. 즉, 예를 들어 파티션을에 즉시를 만들 수 있습니다 때는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프는 새 작업을 생성 합니다. 이 기능에는 파티 셔를 너는 루프 확장할 수 있습니다. 동적 파티 셔 너 본질적으로 부하 분산도 있습니다. 사용자 지정 파티 셔 너를 만들 때 동적 분할에서 사용할 수 있으려면 지원 해야 합니다는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프입니다.  
  
### <a name="configuring-load-balancing-partitioners-for-plinq"></a>부하 분산 PLINQ에 대 한 파티 셔 너 구성  
 오버 로드는 <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> 메서드를 통해 배열에 대 한 파티 셔 너를 만들 수 있습니다 또는 <xref:System.Collections.IList> 소스 하 고 스레드 간에 작업을 균형 있게에 연결할지 여부를 지정 합니다. 파티 셔 너 부하를 분산 하도록 구성 된, 청크 분할을 사용 하 고 요소에 전달 됩니다 작은 청크로의 각 파티션에 요청입니다. 이 방식을 사용 하면 모든 파티션에 있는 전체 루프까지 처리할 요소를 또는 쿼리가 완료 됩니다. 부하 분산 분할을 제공 하는 추가 오버 로드를 사용할 수 <xref:System.Collections.IEnumerable> 소스입니다.  
  
 일반적으로 부하 분산 요소 비교적 자주 요청 된 partitioner에서 파티션이 필요 합니다. 반면, 정적 분할을 수행 하는 파티 셔 너를 할당할 수 요소 각 파티 셔 너에 한 번에 범위 또는 청크 분할을 사용 하 여 합니다. 부하 분산에 비해 오버 헤드 하지만 특정 스레드에서 다른 조건들 보다 훨씬 더 많은 작업을 처리할 경우 실행 하는 데 더 많은 시간이 걸릴 수 있습니다. 기본적으로 IList 또는 배열에 전달 될 때 PLINQ 항상 사용 하 여 로드 균형 조정 없이 범위 분할 합니다. PLINQ의 부하 분산을 사용 하려면는 `Partitioner.Create` 메서드를 다음 예제와 같이 합니다.  
  
 [!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
 [!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]  
  
 되는지 확인 하려면 부하를 사용 하도록 해당된 시나리오에서 분산 대표적인 부하 및 컴퓨터 구성에서 작업 완료에 걸리는 시간을 측정 하는 가장 좋은 방법은 합니다. 예를 들어 정적 분할 상당히 높일 수 있는 몇 가지 코어, 다중 코어 컴퓨터에 있지만 상대적으로 많은 코어를 포함 하는 컴퓨터에서 성능 저하를 발생할 수 있습니다.  
  
 다음 표에서 사용할 수 있는 오버 로드는 <xref:System.Collections.Concurrent.Partitioner.Create%2A> 메서드. 이러한 파티 셔이 너는 plinq를 사용 하도록 제한 되지 않습니다. 또는 <xref:System.Threading.Tasks.Task>합니다. 모든 사용자 지정 하는 병렬 구문으로도 사용할 수 있습니다.  
  
|오버 로드|부하 분산 사용|  
|--------------|-------------------------|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Always|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|True로 부울 인수를 지정 하는 경우|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|True로 부울 인수를 지정 하는 경우|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Never|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Never|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Never|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Never|  
  
### <a name="configuring-static-range-partitioners-for-parallelforeach"></a>Parallel.ForEach에 대 한 파티 셔 너 정적 범위를 구성합니다.  
 에 <xref:System.Threading.Tasks.Parallel.For%2A> 루프 루프의 본문 메서드에 대리자도 제공 됩니다. 해당 대리자 호출의 비용은 가상 메서드 호출와 비슷합니다. 일부 시나리오에서는 병렬 루프의 본문을 각 루프 반복에서 대리자 호출의 비용이 중요 한 만큼 작을 수 있습니다. 이러한 경우 중 사용할 수 있습니다는 <xref:System.Collections.Concurrent.Partitioner.Create%2A> 를 만드는 오버 로드는 <xref:System.Collections.Generic.IEnumerable%601> 소스 요소에 대 한 범위 분할의 합니다. 그런 다음이 컬렉션의 범위를 전달할 수 있습니다는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 메서드 본문이 일반 이루어져 `for` 루프입니다. 이 방식의 이점은 요소 마다 한 번이 아니라 범위당 대리자 호출 비용이 한 번만 발생입니다. 다음 예제에서는 기본 패턴을 보여 줍니다.  
  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 루프의 모든 스레드는 자체 받는 <xref:System.Tuple%602> 시작 및 끝 지정 하위 범위의 인덱스 값을 포함 합니다. 내부 `for` 루프를 사용 하 여는 `fromInclusive` 및 `toExclusive` 배열을 반복 하는 값 또는 <xref:System.Collections.IList> 직접 합니다.  
  
 중 하나는 <xref:System.Collections.Concurrent.Partitioner.Create%2A> 오버 로드를 사용 하면 파티션과 파티션 수의 크기를 지정 합니다. 이 오버 로드 요소당 작업이 있는 요소가 하나라도 가상 메서드 호출 성능에 별다른 영향을 갖기 낮은 시나리오에서 사용할 수 있습니다.  
  
## <a name="custom-partitioners"></a>사용자 지정 파티셔너  
 일부 시나리오에서는 것이 권장 되거나 자신의 파티 셔 너 구현 하기 위해도 필요한 수 있습니다. 예를 들어 파티 셔 너 클래스의 내부 구조에 대 한 정보에 따라 수를 기본값 보다 더 효율적으로 분할할 수 있는 사용자 지정 컬렉션 클래스를 할 수 있습니다. 또는 소스 컬렉션의 여러 위치에서 프로세스 요소에 걸리는 시간에 대 한 정보에 따라 다양 한 크기의 범위 분할을 만들려고 할 수 있습니다.  
  
 기본 사용자 지정 파티 셔 너를 만들려면에서 클래스를 파생 <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=nameWithType> 다음 표에 설명 된 대로 가상 메서드를 재정의 합니다.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|이 메서드는 주 스레드에 의해 한 번 호출 되 고는 IList(IEnumerator(TSource))를 반환 합니다. 루프 또는 쿼리의 각 작업자 스레드를 호출할 수 `GetEnumerator` 를 검색 목록에는 <xref:System.Collections.Generic.IEnumerator%601> 고유한 이동해 합니다.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|반환할 `true` 구현 하는 경우 <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, 그렇지 않으면 `false`합니다.|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|경우 <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> 은 `true`, 대신 필요에 따라이 메서드를 호출할 수 <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>합니다.|  
  
 결과 정렬 가능한 이어야 합니다. 인덱싱된 액세스는 요소에 필요한,에서 다음 파생 <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> 다음 표에 설명 된 대로 가상 메서드를 재정의 합니다.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|이 메서드는 주 스레드에 의해 한 번만 호출 되며 반환 된 `IList(IEnumerator(TSource))`합니다. 루프 또는 쿼리의 각 작업자 스레드를 호출할 수 `GetEnumerator` 를 검색 목록에는 <xref:System.Collections.Generic.IEnumerator%601> 고유한 이동해 합니다.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|반환할 `true` 구현 하는 경우 <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>, 그러지 않으면 false입니다.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|일반적으로이 호출 <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>합니다.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|경우 <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> 은 `true`, 대신 필요에 따라이 메서드를 호출할 수 <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>합니다.|  
  
 다음 표에서 방법에 대 한 추가 정보를 제공 파티 셔 너 구현 부하 분산의 세 가지 종류의 <xref:System.Collections.Concurrent.OrderablePartitioner%601> 클래스입니다.  
  
|메서드/속성|IList 로드 균형 조정 하지 않고 배열 /|IList 부하 분산 배열 /|IEnumerable|  
|----------------------|-------------------------------------------|----------------------------------------|-----------------|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|범위 분할을 사용 하 여|청크 분할 사용 목록에 대 한 지정 된 partitionCount 위해 최적화|고정 된 수의 파티션 만들어 청크 분할을 사용 합니다.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=nameWithType>|지원 되지 않는 throw 예외|청크 분할 사용 목록에 대 한 액세스에 최적화 된 및 동적 파티션|동적 개수가 파티션 만들어 청크 분할 사용|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|`true`를 반환합니다.|`true`를 반환합니다.|`true`를 반환합니다.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|`true`를 반환합니다.|`false`를 반환합니다.|`false`를 반환합니다.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|`true`를 반환합니다.|`true`를 반환합니다.|`true`를 반환합니다.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|`false`를 반환합니다.|`true`를 반환합니다.|`true`를 반환합니다.|  
  
### <a name="dynamic-partitions"></a>동적 파티션  
 에 사용할 파티 셔 너 하려는 경우에 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 메서드를 있어야 파티션의 동적 값이 반환 되도록 합니다. 즉, 파티 셔 너가 루프 실행 중 언제 든 지는 새로운 요청 시 파티션에 대 한 열거자를 제공할 수 있습니다. 기본적으로, 루프는 새 병렬 작업에 추가 될 때마다 해당 작업에 대해 새 파티션을 요청 합니다. 정렬 가능한 데이터가 필요한 경우 다음에서 파생 <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> 고유 인덱스의 각 항목에 각 파티션에 할당 되도록 합니다.  
  
 자세한 내용 및 예제에 대 한 참조 [하는 방법: 동적 파티션 구현](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)합니다.  
  
### <a name="contract-for-partitioners"></a>파티 셔 너에 대 한 계약  
 사용자 지정 파티 셔 너 구현 하면 plinq 올바른 상호 작용 하지 확인 하려면 다음이 지침을 따르십시오 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A> TPL에서:  
  
-   경우 <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> 작거나 0의 인수와 함께 호출에 대 한 `partitionsCount`, throw <xref:System.ArgumentOutOfRangeException>합니다. PLINQ 및 TPL 전달 하지는 않지만 있지만 `partitionCount` 0 같음, 그럼에도 불구 하 고 권장 가능성을 방지 합니다.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>및 <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A> 항상 반환 `partitionsCount` 파티션 번호입니다. 파티 셔 너 데이터가 부족을 요청 하는 만큼의 파티션을 만들 수 없습니다 메서드가 각 서 나머지 파티션을 대 한 빈 열거자를 반환 해야 합니다. PLINQ 및 TPL 모두 그렇지 않은 경우 throw 됩니다는 <xref:System.InvalidOperationException>합니다.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A><xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, 및 <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> 반환 해서는 안 `null` (`Nothing` Visual basic에서). 그럴 경우 PLINQ TPL 시킵니다 /는 <xref:System.InvalidOperationException>합니다.  
  
-   파티션을 반환 하는 메서드가 항상 완벽 하 게 하 고 고유 하 게를 열거할 수 있는 데이터 원본 파티션이 되돌려야 합니다. 파티 셔 너 디자인으로 특별히 필요한 경우 데이터 원본이 나 건너뛴된 항목에 중복 되지 있어야 합니다. 이 규칙을 따르지 않으면 출력 순서가 스크램블 수 있습니다.  
  
-   다음 부울 getter 출력 순서가 스크램블 되지 않도록 항상 정확히 다음 값을 반환 합니다.  
  
    -   `KeysOrderedInEachPartition`: 각 파티션 키 인덱스 증가 따라 요소를 반환 합니다.  
  
    -   `KeysOrderedAcrossPartitions`: 반환 된 파티션 키 인덱스는 모든 파티션에 대 한 *i* 파티션 키 인덱스 보다 높은 *i*-1입니다.  
  
    -   `KeysNormalized`: 모든 키 인덱스 0부터 시작 간격 없이 일정 하 게 증가 합니다.  
  
-   모든 인덱스는 고유 해야 합니다. 중복 된 인덱스가 아닐 수 있습니다. 이 규칙을 따르지 않으면 출력 순서가 스크램블 수 있습니다.  
  
-   모든 인덱스는 음수가 아니어야 합니다. 이 규칙을 따르지 않으면 PLINQ/TPL이 예외를 throw 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [병렬 프로그래밍](../../../docs/standard/parallel-programming/index.md)  
 [방법: 동적 파티션 구현](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)  
 [방법: 정적 분할을 위한 파티셔너 구현](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
