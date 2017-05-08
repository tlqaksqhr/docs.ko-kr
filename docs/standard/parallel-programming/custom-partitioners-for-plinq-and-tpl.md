---
title: "Custom Partitioners for PLINQ and TPL | Microsoft Docs"
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
  - "tasks, partitioners"
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Custom Partitioners for PLINQ and TPL
데이터 소스에 대한 작업을 병렬화하기 위한 필수 단계 중 하나는 다중 스레드에서 동시에 액세스 가능한 여러 섹션으로 데이터 소스를 *분할*하는 것입니다.  병렬 쿼리 또는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프를 작성할 경우 PLINQ 및 TPL\(작업 병렬 라이브러리\)에서는 투명하게 작동하는 기본 파티셔너를 제공합니다.  고급 시나리오의 경우에는 고유한 파티셔너를 플러그 인으로 추가할 수 있습니다.  
  
## 분할의 종류  
 데이터 소스는 여러 방법으로 분할할 수 있습니다.  가장 효율적인 방법은 해당 소스를 실제로 여러 개의 하위 시퀀스로 분할하는 대신 다중 스레드가 협력을 통해 원본 소스 시퀀스를 처리하는 것입니다.  배열 및 인덱싱된 <xref:System.Collections.IList> 컬렉션 등의 다른 소스처럼 길이를 미리 알 수 있는 경우에는 *범위 분할*이 가장 간단한 분할 유형입니다.  각 스레드에는 고유한 시작 및 끝 인덱스가 전달되므로 다른 스레드를 덮어쓰거나 다른 스레드에 의해 덮어쓰이지 않고 해당 소스 범위를 처리할 수 있습니다.  범위 분할에 따르는 유일한 오버헤드는 범위를 만드는 초기 작업뿐이며 그 이후에는 추가적인 동기화가 필요하지 않습니다.  따라서 작업 부하가 균일하게 분산되어 있으면 우수한 성능을 제공할 수 있습니다.  그러나 특정 스레드가 일찍 종료될 경우 다른 스레드의 작업 완료를 도울 수 없다는 것이 범위 분할의 단점입니다.  
  
 길이를 알 수 없는 연결된 목록 또는 다른 컬렉션에 대해서는 *청크 분할*을 사용할 수 있습니다.  청크 분할에서 병렬 루프 또는 쿼리의 모든 스레드나 작업은 일정 수의 소스 요소를 하나의 청크로 사용하고, 해당 요소를 처리한 다음 다른 요소를 다시 검색합니다.  파티셔너는 모든 요소가 분산되고 중복이 없도록 합니다.  청크의 크기에는 제한이 없습니다.  예를 들어, [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)에서 예시된 파티셔너는 요소 하나만 포함하는 청크를 만듭니다.  스레드에 대한 요소 할당은 미리 결정되지 않기 때문에 청크가 너무 크지 않는 한 이 분할 유형에서는 본질적으로 부하가 분산됩니다.  그러나 스레드가 다른 청크를 가져와야 할 때마다 파티셔너 때문에 동기화 오버헤드가 발생합니다.  이러한 경우에 유발되는 동기화 오버헤드의 양은 청크 크기와 반비례합니다.  
  
 일반적으로 범위 분할은 대리자의 실행 시간이 짧거나 중간 정도이고, 소스에 많은 요소가 있고, 각 파티션의 모든 작업이 비교적 균일한 경우에만 더 빠른 속도를 보여 줍니다.  따라서 대부분의 경우에는 청크 분할이 일반적으로 더 빠릅니다.  요소 수가 적거나 대리자의 실행 시간이 긴 소스에 대해서는 청크 분할과 범위 분할의 성능이 거의 동일합니다.  
  
 TPL 파티셔너는 파티션의 개수가 동적일 수 있게 지원하기도 합니다.  즉, 이러한 파티셔너는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프에서 새 작업이 생성되는 경우 등에 즉석으로 파티션을 만들 수 있습니다.  이 기능을 통해 파티셔너는 루프에 맞춰 확장 또는 축소될 수 있습니다.  동적 파티셔너에서도 본질적으로 부하가 분산됩니다.  사용자 지정 파티셔너를 만드는 경우 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프에서 동적 분할을 사용할 수 있도록 지원해야 합니다.  
  
### PLINQ에 대한 부하 분산 파티셔너 구성  
 <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=fullName> 메서드의 일부 오버로드를 사용하면 배열 또는 <xref:System.Collections.IList> 소스에 대한 파티셔너를 만들 수 있고, 파티셔너에서 스레드 간 작업 부하 분산을 시도해야 하는지 여부를 지정할 수 있습니다.  부하를 분산하도록 파티셔너가 구성되어 있고 청크 분할이 사용되는 경우 요소를 요청하면 해당 요소는 작은 청크 단위로 각 파티션에 전달됩니다.  이 방법을 통해 모든 파티션은 전체 루프 또는 쿼리가 완료될 때까지 처리할 요소를 계속 보유하게 됩니다.  <xref:System.Collections.IEnumerable> 소스의 부하 분산 분할을 제공하려면 추가적인 오버헤드가 사용될 수 있습니다.  
  
 일반적으로 부하 분산에서는 파티션이 파티셔너로부터 요소를 비교적 자주 요청하게 됩니다.  그에 반해 정적 분할을 수행하는 파티셔너는 범위 또는 청크 분할을 사용하여 각 파티셔너에 요소를 한 번에 모두 할당할 수 있습니다.  따라서 부하 분산에 비해 오버헤드는 적지만 특정 스레드에서 처리할 작업이 다른 스레드보다 훨씬 많은 경우에는 실행에 긴 시간이 소요될 수 있습니다.  IList 또는 배열이 전달되면 PLINQ에서는 기본적으로 항상 부하 분산 없이 범위 분할을 사용합니다.  PLINQ에 대해 부하 분산이 사용되도록 하려면 다음 예제와 같이 `Partitioner.Create` 메서드를 사용합니다.  
  
 [!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
 [!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]  
  
 해당 시나리오에서 부하 분산을 사용할지 여부를 결정하려면 대표적인 부하 및 컴퓨터 구성에서 작업 완료에 걸리는 시간을 실제로 측정하는 것이 가장 좋습니다.  예를 들어, 정적 분할은 코어가 많지 않은 다중 코어 컴퓨터에서 속도를 상당히 높일 수 있지만 코어가 비교적 많은 컴퓨터에서는 속도 저하를 유발할 수 있습니다.  
  
 다음 표에서는 사용 가능한 <xref:System.Collections.Concurrent.Partitioner.Create%2A> 메서드의 오버로드를 나열합니다.  이러한 파티셔너의 사용 범위는 PLINQ 또는 <xref:System.Threading.Tasks.Task>로 제한되지 않습니다.  모든 사용자 지정 병렬 구문과 함께 사용될 수 있습니다.  
  
|오버로드|부하 분산 사용|  
|----------|--------------|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|항상|  
|[Create\<TSource\>\(TSource\<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|부울 인수가 true로 지정된 경우|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|부울 인수가 true로 지정된 경우|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|절대 지원되지 않음|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|절대 지원되지 않음|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|절대 지원되지 않음|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|절대 지원되지 않음|  
  
### Parallel.ForEach에 대한 정적 범위 파티셔너 구성  
 <xref:System.Threading.Tasks.Parallel.For%2A> 루프에서 루프 본문은 메서드에 대리자로 전달됩니다.  대리자 호출에 따르는 비용은 가상 메서드 호출의 경우와 거의 같습니다.  일부 시나리오에서는 병렬 루프의 본문이 너무 작아 각 루프 반복에서의 대리자 호출 비용이 매우 클 수도 있습니다.  이러한 경우에는 <xref:System.Collections.Concurrent.Partitioner.Create%2A> 오버로드 중 하나를 사용하여 소스 요소에 대한 범위 분할의 <xref:System.Collections.Generic.IEnumerable%601>을 만들 수 있습니다.  그런 다음 이 범위 컬렉션을 본문이 일반적인 `for` 루프로 구성된 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 메서드에 전달할 수 있습니다.  이 방법에는 대리자 호출 비용이 요소당 한 번이 아니라 범위당 한 번만 발생한다는 이점이 있습니다.  다음 예제에서는 기본적 패턴을 보여 줍니다.  
  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 루프에서 각 스레드는 지정된 하위 범위의 시작 및 끝 인덱스 값을 포함하는 <xref:System.Tuple%602>를 각각 받습니다.  내부 `for` 루프에서는 `fromInclusive` 및 `toExclusive` 값을 사용하여 배열 또는 <xref:System.Collections.IList>에 대해 루프를 직접 반복합니다.  
  
 <xref:System.Collections.Concurrent.Partitioner.Create%2A> 오버로드 중 하나를 사용하면 파티션의 크기 및 수를 지정할 수 있습니다.  이 오버로드는 요소당 작업이 너무 적어 요소에 대한 한 번의 가상 메서드 호출로 성능에 상당한 영향을 주는 시나리오에서 사용될 수 있습니다.  
  
## 사용자 지정 파티셔너  
 일부 시나리오에서는 고유한 파티셔너를 구현하는 것이 권장되거나 필수적일 수 있습니다.  예를 들어, 기본 파티셔너보다 더 효율적으로 분할할 수 있는 사용자 지정 컬렉션 클래스가 있다는 것을 클래스의 내부 구조에 대한 지식을 통해 알고 있을 수 있습니다.  또는 소스 컬렉션의 서로 다른 위치에 있는 요소를 처리하는 데 어느 정도의 시간이 걸리는지 알고 있기 때문에 가변 크기의 범위 분할을 만들려고 할 수도 있습니다.  
  
 기본 사용자 지정 파티셔너를 만들려면 다음 표에 설명된 대로 <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=fullName>에서 클래스를 파생시키고 가상 메서드를 재정의합니다.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|이 메서드는 주 스레드에 의해 한 번 호출되고 IList\(IEnumerator\(TSource\)\)를 반환합니다.  루프 또는 쿼리에서 각 작업자 스레드는 목록에 대해 `GetEnumerator`를 호출하여 각 파티션에서 <xref:System.Collections.Generic.IEnumerator%601>을 검색할 수 있습니다.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>를 구현한 경우 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>가 `true`인 경우 이 메서드는 <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> 대신 선택적으로 호출될 수 있습니다.|  
  
 결과가 정렬 가능해야 하거나 인덱스로 해당 요소에 액세스해야 하는 경우에는 다음 표에 설명된 대로 <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=fullName>에서 파생시키고 가상 메서드를 재정의합니다.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|이 메서드는 주 스레드에 의해 한 번 호출되고 `IList(IEnumerator(TSource))`를 반환합니다.  루프 또는 쿼리에서 각 작업자 스레드는 목록에 대해 `GetEnumerator`를 호출하여 각 파티션에서 <xref:System.Collections.Generic.IEnumerator%601>을 검색할 수 있습니다.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>를 구현한 경우 `true`를 반환하고, 그렇지 않으면 false를 반환합니다.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|일반적으로 <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>만 호출합니다.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>가 `true`인 경우 이 메서드는 <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> 대신 선택적으로 호출될 수 있습니다.|  
  
 다음 표에서는 세 가지 유형의 부하 분산 파티셔너가 <xref:System.Collections.Concurrent.OrderablePartitioner%601> 클래스를 구현하는 방법에 대한 자세한 정보를 제공합니다.  
  
|메서드\/속성|부하 분산 없는 IList\/배열|부하 분산 있는 IList\/배열|IEnumerable|  
|-------------|------------------------|------------------------|-----------------|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|범위 분할 사용|지정된 partitionCount에 따라 목록에 최적화된 청크 분할 사용|개수가 정적인 파티션을 만들어 청크 분할 사용|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=fullName>|not\-supported 예외 throw|목록 및 동적 파티션에 최적화된 청크 분할 사용|개수가 동적인 파티션을 만들어 청크 분할 사용|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|`true` 반환|`true` 반환|`true` 반환|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|`true` 반환|`false` 반환|`false` 반환|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|`true` 반환|`true` 반환|`true` 반환|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|`false` 반환|`true` 반환|`true` 반환|  
  
### 동적 파티션  
 파티셔너가 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 메서드에서 사용되도록 하려면 파티션의 동적 개수를 전달할 수 있어야 합니다.  즉, 파티셔너는 루프 실행 중 어느 때라도 요청이 있으면 새 파티션에 대한 열거자를 제공할 수 있어야 합니다.  기본적으로 루프는 새 병렬 작업을 추가할 때마다 해당 작업을 위한 새 파티션을 요청합니다.  정렬 가능한 데이터가 필요하면 <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=fullName>에서 파생시켜 각 파티션의 각 항목에 고유한 인덱스가 할당되도록 합니다.  
  
 자세한 내용과 예제는 [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)을 참조하십시오.  
  
### 파티셔너에 대한 계약  
 사용자 지정 파티셔너를 구현하는 경우 다음 지침에 따라 TPL에서 PLINQ 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A>와의 상호 작용이 올바로 수행되도록 합니다.  
  
-   `partitionsCount`에 대한 인수로 0 이하의 값이 지정되어 <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>가 호출되면 <xref:System.ArgumentOutOfRangeException>이 throw됩니다.  PLINQ 및 TPL에서 `partitionCount`로 0을 전달하지는 않지만 만약의 경우에 대비하는 것이 좋습니다.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> 및 <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>에서는 항상 파티션의 개수로 `partitionsCount`를 반환합니다.  데이터가 부족하여 요청된 만큼의 파티션을 파티셔너에서 만들 수 없는 경우 해당 메서드는 나머지 각 파티션에 대한 빈 열거자를 반환해야 합니다.  그렇지 않으면 PLINQ 및 TPL에서 <xref:System.InvalidOperationException>을 throw합니다.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>, <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A> 및 <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>는 `null` \(Visual Basic의 경우 `Nothing` \)을 반환하지 않아야 합니다.  그렇지 않으면 PLINQ\/TPL에서 <xref:System.InvalidOperationException>을 throw합니다.  
  
-   파티션을 반환하는 메서드는 데이터 소스를 완전하고 고유하게 열거할 수 있는 파티션을 항상 반환해야 합니다.  파티셔너 디자인에서 특별히 요청된 경우가 아니라면 생략된 항목이나 데이터 소스에서의 중복이 없어야 합니다.  이 규칙을 따르지 않으면 출력 순서가 스크램블될 수 있습니다.  
  
-   다음 부울 getter에서는 출력 순서가 스크램블되지 않도록 다음 값을 항상 정확히 반환합니다.  
  
    -   `KeysOrderedInEachPartition`: 각 파티션은 증가하는 키 인덱스가 있는 요소를 반환합니다.  
  
    -   `KeysOrderedAcrossPartitions`: 반환되는 모든 파티션에서 파티션 *i* 의 키 인덱스는 파티션*i*\-1 의 키 인덱스보다 큽니다.  
  
    -   `KeysNormalized`: 모든 키 인덱스는 0부터 시작하여 건너뛰지 않고 순차적으로 증가합니다.  
  
-   모든 인덱스는 고유해야 합니다.  중복된 인덱스가 있으면 안 됩니다.  이 규칙을 따르지 않으면 출력 순서가 스크램블될 수 있습니다.  
  
-   모든 인덱스는 음수가 아니어야 합니다.  이 규칙을 따르지 않으면 PLINQ\/TPL에서 예외가 throw될 수 있습니다.  
  
## 참고 항목  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)   
 [How to: Implement a Partitioner for Static Partitioning](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)