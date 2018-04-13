---
title: '방법: PLINQ에서 병합 옵션 지정'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 59ffff3019f10874bd2df977b80d46e903d13613
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a><span data-ttu-id="8a575-102">방법: PLINQ에서 병합 옵션 지정</span><span class="sxs-lookup"><span data-stu-id="8a575-102">How to: Specify Merge Options in PLINQ</span></span>
<span data-ttu-id="8a575-103">이 예제는 PLINQ 쿼리의 모든 후속 연산자에 적용할 병합 옵션을 지정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a575-103">This example shows how to specify the merge options that will apply to all subsequent operators in a PLINQ query.</span></span> <span data-ttu-id="8a575-104">병합 옵션을 명시적으로 설정할 필요는 없지만 이를 수행하면 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a575-104">You do not have to set merge options explicitly, but doing so may improve performance.</span></span> <span data-ttu-id="8a575-105">병합 옵션에 대한 자세한 내용은 [PLINQ의 병합 옵션](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a575-105">For more information about merge options, see [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="8a575-106">이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a575-106">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="8a575-107">속도 향상에 대한 자세한 내용은 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a575-107">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a575-108">예</span><span class="sxs-lookup"><span data-stu-id="8a575-108">Example</span></span>  
 <span data-ttu-id="8a575-109">다음 예제에서는 정렬되지 않은 소스가 있는 기본 시나리오의 병합 옵션 동작을 보여주고 모든 요소에 비용이 많이 드는 함수를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8a575-109">The following example demonstrates the behavior of merge options in a basic scenario that has an unordered source and applies an expensive function to every element.</span></span>  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 <span data-ttu-id="8a575-110">첫 번째 요소가 생성되기 전에 <xref:System.Linq.ParallelMergeOptions.AutoBuffered> 옵션이 바람직하지 않은 대기 시간을 발생시키는 경우, <xref:System.Linq.ParallelMergeOptions.NotBuffered> 옵션을 사용하여 결과 요소를 더욱 빠르고 원활하게 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="8a575-110">In cases where the <xref:System.Linq.ParallelMergeOptions.AutoBuffered> option incurs an undesirable latency before the first element is yielded, try the <xref:System.Linq.ParallelMergeOptions.NotBuffered> option to yield result elements faster and more smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a575-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a575-111">See Also</span></span>  
 <xref:System.Linq.ParallelMergeOptions>  
 [<span data-ttu-id="8a575-112">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="8a575-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
