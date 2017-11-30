---
title: "방법: 정적 분할을 위한 파티셔너 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b28ff0bb8436fefc4956918889435e258ae98b12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a><span data-ttu-id="4e232-102">방법: 정적 분할을 위한 파티셔너 구현</span><span class="sxs-lookup"><span data-stu-id="4e232-102">How to: Implement a Partitioner for Static Partitioning</span></span>
<span data-ttu-id="4e232-103">다음 예제에서는 정적 분할을 수행 하는 PLINQ에 대 한 간단한 사용자 지정 파티 셔를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e232-103">The following example shows one way to implement a simple custom partitioner for PLINQ that performs static partitioning.</span></span> <span data-ttu-id="4e232-104">사용 될 없는 파티 셔 너 동적 파티션을 지원 하지 않으므로, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="4e232-104">Because the partitioner does not support dynamic partitions, it is not consumable from <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4e232-105">이 파티 셔 각 요소에 많은 양의 처리 시간이 필요를 데이터 원본에 대 한 파티 셔 너는 기본 범위를 통해 빠른 속도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e232-105">This particular partitioner might provide speedup over the default range partitioner for data sources for which each element requires an increasing amount of processing time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e232-106">예제</span><span class="sxs-lookup"><span data-stu-id="4e232-106">Example</span></span>  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 <span data-ttu-id="4e232-107">이 예에서 파티션 각 요소에 대 한 처리 시간이 증가 하는 선형의 가정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e232-107">The partitions in this example are based on the assumption of a linear increase in processing time for each element.</span></span> <span data-ttu-id="4e232-108">실제 상황에서이 방식으로 처리 시간을 예측 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e232-108">In the real world, it might be difficult to predict processing times in this way.</span></span> <span data-ttu-id="4e232-109">정적 파티 셔 너의 특정 데이터 원본을 사용 하는 경우 있습니다 수 최적화 소스에 대 한 분할 수식, 부하 분산 논리를 추가 또는 청크에서와 같이 분할 방법을 사용 하 여 [하는 방법: 동적 파티션 구현](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="4e232-109">If you are using a static partitioner with a specific data source, you can optimize the partitioning formula for the source, add load-balancing logic, or use a chunk partitioning approach as demonstrated in [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e232-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e232-110">See Also</span></span>  
 [<span data-ttu-id="4e232-111">PLINQ 및 TPL에 대한 사용자 지정 파티셔너</span><span class="sxs-lookup"><span data-stu-id="4e232-111">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
