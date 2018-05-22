---
title: '방법: 동적 파티션 구현'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bffc25cb5c3ae3671fdf6018158b81549c360e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="2c72c-102">방법: 동적 파티션 구현</span><span class="sxs-lookup"><span data-stu-id="2c72c-102">How to: Implement Dynamic Partitions</span></span>
<span data-ttu-id="2c72c-103">다음 예제는 동적 파티셔닝을 구현하고 특정 오버로드 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 및 PLINQ에서 사용할 수 있는 사용자 지정 <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType>를 구현하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c72c-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c72c-104">예</span><span class="sxs-lookup"><span data-stu-id="2c72c-104">Example</span></span>  
 <span data-ttu-id="2c72c-105">파티션이 열거자에 대해 <xref:System.Collections.IEnumerator.MoveNext%2A>를 호출할 때마다 열거자는 하나의 목록 요소가 있는 파티션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2c72c-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="2c72c-106">PLINQ 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A>의 경우 파티션은 <xref:System.Threading.Tasks.Task> 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="2c72c-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="2c72c-107">요청이 여러 스레드에서 동시에 발생하므로 현재 인덱스에 대한 액세스가 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c72c-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 <span data-ttu-id="2c72c-108">이는 청크 파티셔닝에 대한 예제이며, 각 청크는 하나의 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c72c-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="2c72c-109">많은 요소를 한 번에 제공하여 잠금에 대한 경합을 줄이고 이론적으로 성능을 빠르게 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c72c-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="2c72c-110">그러나 특정 지점에서는, 보다 큰 청크의 경우 모든 작업이 수행될 때까지 모든 스레드를 사용하려면 추가 로드 밸런싱 논리가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c72c-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c72c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c72c-111">See Also</span></span>  
 [<span data-ttu-id="2c72c-112">PLINQ 및 TPL에 대한 사용자 지정 파티셔너</span><span class="sxs-lookup"><span data-stu-id="2c72c-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [<span data-ttu-id="2c72c-113">방법: 정적 분할을 위한 파티셔너 구현</span><span class="sxs-lookup"><span data-stu-id="2c72c-113">How to: Implement a Partitioner for Static Partitioning</span></span>](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
