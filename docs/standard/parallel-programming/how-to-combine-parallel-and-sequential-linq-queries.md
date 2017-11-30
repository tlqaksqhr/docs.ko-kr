---
title: "방법: 병렬 및 순차적 LINQ 쿼리 결합"
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
helpviewer_keywords: parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4da91ff535059b181baa637164a854cd75d06334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="a9a2d-102">방법: 병렬 및 순차적 LINQ 쿼리 결합</span><span class="sxs-lookup"><span data-stu-id="a9a2d-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>
<span data-ttu-id="a9a2d-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Linq.ParallelEnumerable.AsSequential%2A> 메서드를 plinq 모든 후속 쿼리 연산자를 순서 대로 처리 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9a2d-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="a9a2d-104">순차적 처리 병렬 보다 일반적으로 느린 경우에 경우 올바른 결과 생성 하는 데 필요한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9a2d-104">Although sequential processing is generally slower than parallel, sometimes it is necessary to produce correct results.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="a9a2d-105">이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9a2d-105">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="a9a2d-106">속도 대 한 자세한 내용은 참조 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a9a2d-106">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9a2d-107">예제</span><span class="sxs-lookup"><span data-stu-id="a9a2d-107">Example</span></span>  
 <span data-ttu-id="a9a2d-108">다음 예제는 한 가지 시나리오를 보여 줍니다. <xref:System.Linq.ParallelEnumerable.AsSequential%2A> 즉 하는데 필요한 이전 쿼리 절에 설정 된 순서를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9a2d-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a9a2d-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a9a2d-109">Compiling the Code</span></span>  
 <span data-ttu-id="a9a2d-110">를 컴파일하고 실행이 코드를 붙여 넣습니다는 [PLINQ 데이터 샘플](../../../docs/standard/parallel-programming/plinq-data-sample.md) 프로젝트에서 선을 추가에서 메서드를 호출 하 여 `Main`, F5 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a9a2d-110">To compile and run this code, paste it into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project, add a line to call the method from `Main`, and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9a2d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9a2d-111">See Also</span></span>  
 [<span data-ttu-id="a9a2d-112">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="a9a2d-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
