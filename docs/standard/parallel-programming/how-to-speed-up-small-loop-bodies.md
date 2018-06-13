---
title: '방법: 작은 루프 본문 속도 개선'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bff41416dd2263c185cc94de045b2c8a26ea194d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581153"
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="2094c-102">방법: 작은 루프 본문 속도 개선</span><span class="sxs-lookup"><span data-stu-id="2094c-102">How to: Speed Up Small Loop Bodies</span></span>
<span data-ttu-id="2094c-103"><xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> 루프에 작은 본문이 있는 경우 C#의 [for](~/docs/csharp/language-reference/keywords/for.md) 루프 및 Visual Basic의 [For](http://msdn.microsoft.com/library/c470a263-9b49-4308-8fd6-8592b84a7980) 루프와 같은 동등한 순차 루프보다 성능이 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2094c-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](~/docs/csharp/language-reference/keywords/for.md) loop in C# and the [For](http://msdn.microsoft.com/library/c470a263-9b49-4308-8fd6-8592b84a7980) loop in Visual Basic.</span></span> <span data-ttu-id="2094c-104">성능 저하는 데이터 분할과 관련된 오버헤드 및 각 루프 반복에서 대리자를 호출하는 비용으로 인해 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2094c-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="2094c-105">이러한 시나리오를 처리하기 위해 <xref:System.Collections.Concurrent.Partitioner> 클래스는 <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> 메서드를 제공합니다. 이 메서드를 통해 대리자가 반복당 한 번이 아니라 파티션당 한 번만 호출되도록 대리자 본문에 대한 순차 루프를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2094c-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="2094c-106">자세한 내용은 [PLINQ 및 TPL에 대한 사용자 지정 파티셔너](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2094c-106">For more information, see [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2094c-107">예</span><span class="sxs-lookup"><span data-stu-id="2094c-107">Example</span></span>  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="2094c-108">이 예제에서 설명하는 접근 방식은 루프가 최소한의 작업을 수행하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2094c-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="2094c-109">작업이 많은 계산을 포함하게 되면 기본 파티셔너와 함께 <xref:System.Threading.Tasks.Parallel.For%2A> 또는 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프를 사용하여 동일하거나 더 나은 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2094c-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2094c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2094c-110">See Also</span></span>  
 [<span data-ttu-id="2094c-111">데이터 병렬 처리</span><span class="sxs-lookup"><span data-stu-id="2094c-111">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="2094c-112">PLINQ 및 TPL에 대한 사용자 지정 파티셔너</span><span class="sxs-lookup"><span data-stu-id="2094c-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [<span data-ttu-id="2094c-113">반복기</span><span class="sxs-lookup"><span data-stu-id="2094c-113">Iterators</span></span>](https://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="2094c-114">PLINQ 및 TPL의 람다 식</span><span class="sxs-lookup"><span data-stu-id="2094c-114">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
