---
title: "방법: PLINQ에 실행 모드 지정"
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
helpviewer_keywords: PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 745ceae9832582c7b66a56075d128f9cf1c8ff69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="fcceb-102">방법: PLINQ에 실행 모드 지정</span><span class="sxs-lookup"><span data-stu-id="fcceb-102">How to: Specify the Execution Mode in PLINQ</span></span>
<span data-ttu-id="fcceb-103">이 예의 기본 휴리스틱 무시 하 고 쿼리의 형태에 관계 없이 쿼리를 병렬화는 PLINQ 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="fcceb-104">이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="fcceb-105">속도 대 한 자세한 내용은 참조 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcceb-106">예제</span><span class="sxs-lookup"><span data-stu-id="fcceb-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="fcceb-107">PLINQ는 병렬화에 대 한 기회를 이용 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="fcceb-108">그러나 일부 쿼리 병렬 실행의 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="fcceb-109">예를 들어 매우 적은 양의 작업을 수행 하는 단일 사용자 대리자, 포함 된 쿼리는 일반적으로 더 빠르게 순차적으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-109">For example, when a query contains a single user delegate that does very little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="fcceb-110">즉, 병렬화 실행에 관련 된 오버 헤드는 지금까지 가져온 보다 더 비쌉니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-110">This is because the overhead involved in enabling parallelizing execution is more expensive than the speedup that is obtained.</span></span> <span data-ttu-id="fcceb-111">따라서 PLINQ는 자동으로 모든 쿼리를 병렬화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="fcceb-112">먼저 쿼리 및 구성 하는 다양 한 연산자의 셰이프를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="fcceb-113">이 분석에 따라, 기본 실행 모드에서 PLINQ 쿼리의 일부 또는 전부를 순차적으로 실행을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="fcceb-114">그러나 경우에 따라 알고 있습니다 더는 쿼리에 대 한 PLINQ에서 분석을 통해 확인할 수 있는 것 보다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="fcceb-115">예를 들어 대리자 매우 상당히 소모 되며 쿼리에 평행에서 확실 하 게 이점이 있는지 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-115">For example, you may know that a delegate is very expensive, and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="fcceb-116">이러한 경우에 사용할 수 있습니다는 <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> 메서드를 지정 하 고는 <xref:System.Linq.ParallelExecutionMode.ForceParallelism> plinq 항상를 병렬로 쿼리를 실행 하도록 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fcceb-117">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fcceb-117">Compiling the Code</span></span>  
 <span data-ttu-id="fcceb-118">잘라내기 및 붙여넣기에이 코드는 [PLINQ 데이터 샘플](../../../docs/standard/parallel-programming/plinq-data-sample.md) 에서 메서드를 호출 하 고 `Main`합니다.</span><span class="sxs-lookup"><span data-stu-id="fcceb-118">Cut and paste this code into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcceb-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcceb-119">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>  
 [<span data-ttu-id="fcceb-120">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="fcceb-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
