---
title: "방법: 사용자 지정 PLINQ 집계 함수 작성"
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
helpviewer_keywords: PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b098f21e29d0d59cd99ddbb64af6246d9953a3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a><span data-ttu-id="71597-102">방법: 사용자 지정 PLINQ 집계 함수 작성</span><span class="sxs-lookup"><span data-stu-id="71597-102">How to: Write a Custom PLINQ Aggregate Function</span></span>
<span data-ttu-id="71597-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Linq.ParallelEnumerable.Aggregate%2A> 소스 시퀀스에는 사용자 지정 집계 함수를 적용할 방법을 합니다.</span><span class="sxs-lookup"><span data-stu-id="71597-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.Aggregate%2A> method to apply a custom aggregation function to a source sequence.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="71597-104">이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71597-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="71597-105">속도 대 한 자세한 내용은 참조 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="71597-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71597-106">예제</span><span class="sxs-lookup"><span data-stu-id="71597-106">Example</span></span>  
 <span data-ttu-id="71597-107">다음 예제에서는 정수 시퀀스의 표준 편차를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="71597-107">The following example calculates the standard deviation of a sequence of integers.</span></span>  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 <span data-ttu-id="71597-108">이 예제에서는 PLINQ에 고유한 집계 표준 쿼리 연산자의 오버 로드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="71597-108">This example uses an overload of the Aggregate standard query operator that is unique to PLINQ.</span></span> <span data-ttu-id="71597-109">이 오버 로드는 추가 <xref:System.Func%603?displayProperty=nameWithType> 을 세 번째 입력된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="71597-109">This overload takes an extra <xref:System.Func%603?displayProperty=nameWithType> as the third input parameter.</span></span> <span data-ttu-id="71597-110">이 대리자는 집계 된 결과에서 최종 계산을 수행 하기 전에 모든 스레드의 결과를 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="71597-110">This delegate combines the results from all threads before it performs the final calculation on the aggregated results.</span></span> <span data-ttu-id="71597-111">이 예제에서는 추가 함께 합은 모든 스레드에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="71597-111">In this example we add together the sums from all the threads.</span></span>  
  
 <span data-ttu-id="71597-112">단일 식의 반환 값의 람다 식 본문 구성 되어 있을 때 사용자에 게 유의 <xref:System.Func%602?displayProperty=nameWithType> 대리자는 식의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="71597-112">Note that when a lambda expression body consists of a single expression, the return value of the <xref:System.Func%602?displayProperty=nameWithType> delegate is the value of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71597-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71597-113">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="71597-114">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="71597-114">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
