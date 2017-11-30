---
title: "방법: 동적 파티션 구현"
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
helpviewer_keywords: tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1e5dc93997918e0f7da29fa1f94c434a556f19f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="e9651-102">방법: 동적 파티션 구현</span><span class="sxs-lookup"><span data-stu-id="e9651-102">How to: Implement Dynamic Partitions</span></span>
<span data-ttu-id="e9651-103">다음 예제에서는 사용자 지정을 구현 하는 방법을 보여 줍니다. <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> 동적 분할을 구현 하 고 특정 오버 로드에서 사용할 수 있는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 및 PLINQ 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9651-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9651-104">예제</span><span class="sxs-lookup"><span data-stu-id="e9651-104">Example</span></span>  
 <span data-ttu-id="e9651-105">파티션을 호출할 때마다 <xref:System.Collections.IEnumerator.MoveNext%2A> 파티션을 목록 요소를 하나 열거자에 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9651-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="e9651-106">PLINQ의 경우 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A>, 파티션이 <xref:System.Threading.Tasks.Task> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e9651-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="e9651-107">요청에서 발생 하 고 동시에 여러 스레드를 때문에 현재 인덱스에 대 한 액세스 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9651-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 <span data-ttu-id="e9651-108">이것이 청크 하나의 요소로 구성 되어 각 청크를 사용 하 여 분할의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e9651-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="e9651-109">더 많은 요소를 한 번에 제공 하 여 잠금을 통해 경합을 줄이려면 고 이론적으로 더 빠른 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9651-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="e9651-110">그러나 일부 시점에서는 더 큰 청크로 구성 필요할 수 있습니다 부하 분산 하는 추가 논리 작업을 모두 완료 될 때까지 모든 스레드를 사용 중 상태로 유지 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="e9651-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9651-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9651-111">See Also</span></span>  
 [<span data-ttu-id="e9651-112">PLINQ 및 TPL에 대한 사용자 지정 파티셔너</span><span class="sxs-lookup"><span data-stu-id="e9651-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [<span data-ttu-id="e9651-113">방법: 정적 분할을 위한 파티셔너 구현</span><span class="sxs-lookup"><span data-stu-id="e9651-113">How to: Implement a Partitioner for Static Partitioning</span></span>](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
