---
title: '방법: 병렬 및 순차적 LINQ 쿼리 결합'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c69d4d423bbdf72f2af7dad38812aa508df0067c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580252"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="aef80-102">방법: 병렬 및 순차적 LINQ 쿼리 결합</span><span class="sxs-lookup"><span data-stu-id="aef80-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>
<span data-ttu-id="aef80-103">이 예제는 <xref:System.Linq.ParallelEnumerable.AsSequential%2A> 메서드를 사용하여 쿼리의 모든 후속 연산자를 순차적으로 처리하도록 PLINQ에 지시하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="aef80-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="aef80-104">순차적 처리는 일반적으로 병렬보다 느리지만 올바른 결과를 생성하는 데 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef80-104">Although sequential processing is generally slower than parallel, sometimes it is necessary to produce correct results.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="aef80-105">이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aef80-105">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="aef80-106">속도 향상에 대한 자세한 내용은 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aef80-106">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aef80-107">예</span><span class="sxs-lookup"><span data-stu-id="aef80-107">Example</span></span>  
 <span data-ttu-id="aef80-108">다음 예제에서는 쿼리의 이전 절에서 설정된 순서를 유지하기 위해 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>이 필요한 하나의 시나리오를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="aef80-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aef80-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="aef80-109">Compiling the Code</span></span>  
 <span data-ttu-id="aef80-110">이 코드를 컴파일하고 실행하려면 [PLINQ 데이터 샘플](../../../docs/standard/parallel-programming/plinq-data-sample.md) 프로젝트에 붙여넣고, `Main`에서 메서드를 호출하는 줄을 추가하고 F5 키를 누르세요.</span><span class="sxs-lookup"><span data-stu-id="aef80-110">To compile and run this code, paste it into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project, add a line to call the method from `Main`, and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef80-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aef80-111">See Also</span></span>  
 [<span data-ttu-id="aef80-112">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="aef80-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
