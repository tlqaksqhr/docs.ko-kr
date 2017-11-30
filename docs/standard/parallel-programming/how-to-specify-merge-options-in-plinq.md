---
title: "방법: PLINQ에서 병합 옵션 지정"
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
helpviewer_keywords: PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ec601e8bbefd31650fb91c438b032942cfc93101
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a><span data-ttu-id="e15ac-102">방법: PLINQ에서 병합 옵션 지정</span><span class="sxs-lookup"><span data-stu-id="e15ac-102">How to: Specify Merge Options in PLINQ</span></span>
<span data-ttu-id="e15ac-103">이 예제에는 모든 후속 PLINQ 쿼리 연산자에 적용 되는 병합 옵션을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e15ac-103">This example shows how to specify the merge options that will apply to all subsequent operators in a PLINQ query.</span></span> <span data-ttu-id="e15ac-104">병합 옵션을 명시적으로 설정할 필요는 없지만 성능이 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e15ac-104">You do not have to set merge options explicitly, but doing so may improve performance.</span></span> <span data-ttu-id="e15ac-105">병합 옵션에 대 한 자세한 내용은 참조 [PLINQ의 병합 옵션](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e15ac-105">For more information about merge options, see [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e15ac-106">이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e15ac-106">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="e15ac-107">속도 대 한 자세한 내용은 참조 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e15ac-107">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e15ac-108">예제</span><span class="sxs-lookup"><span data-stu-id="e15ac-108">Example</span></span>  
 <span data-ttu-id="e15ac-109">다음 예제에 순서가 지정 되지 않은 원본 및 모든 요소는 비용이 많이 드는 함수를 적용 하는 기본 시나리오에서 병합 옵션의 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e15ac-109">The following example demonstrates the behavior of merge options in a basic scenario that has an unordered source and applies an expensive function to every element.</span></span>  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 <span data-ttu-id="e15ac-110">경우에서 위치는 <xref:System.Linq.ParallelMergeOptions.AutoBuffered> 옵션 원하지 않는 지연이 그로 인해 첫 번째 요소에서을 생성 하기 전에, 시도 <xref:System.Linq.ParallelMergeOptions.NotBuffered> 빠르고 자연스럽 게 결과 요소를 생성 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e15ac-110">In cases where the <xref:System.Linq.ParallelMergeOptions.AutoBuffered> option incurs an undesirable latency before the first element is yielded, try the <xref:System.Linq.ParallelMergeOptions.NotBuffered> option to yield result elements faster and more smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e15ac-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e15ac-111">See Also</span></span>  
 <xref:System.Linq.ParallelMergeOptions>  
 [<span data-ttu-id="e15ac-112">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="e15ac-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
