---
title: '방법: PLINQ 쿼리 취소'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 074371a929d5dd2cf0efb763ec45395a8dfd0432
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-cancel-a-plinq-query"></a><span data-ttu-id="9d21b-102">방법: PLINQ 쿼리 취소</span><span class="sxs-lookup"><span data-stu-id="9d21b-102">How to: Cancel a PLINQ Query</span></span>
<span data-ttu-id="9d21b-103">다음 예제는 PLINQ 쿼리를 취소하는 두 가지 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-103">The following examples show two ways to cancel a PLINQ query.</span></span> <span data-ttu-id="9d21b-104">첫 번째 예제에서는 주로 데이터 트래버스로 구성되는 쿼리를 취소하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-104">The first example shows how to cancel a query that consists mostly of data traversal.</span></span> <span data-ttu-id="9d21b-105">두 번째 예제에서는 계산을 많이 해야 하는 사용자 함수를 포함하는 쿼리를 취소하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-105">The second example shows how to cancel a query that contains a user function that is computationally expensive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d21b-106">“내 코드만”이 사용하도록 설정된 경우 Visual Studio가 예외를 throw하는 줄에서 중단하고 “예외가 사용자 코드에서 처리되지 않았다”는 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-106">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="9d21b-107">이 오류는 심각하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-107">This error is benign.</span></span> <span data-ttu-id="9d21b-108">F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="9d21b-109">첫 번째 오류 지점에서 Visual Studio가 실행을 중단하지 않도록 하려면 **도구, 옵션, 디버깅, 일반**을 차례로 선택하고 “내 코드만” 확인란의 선택을 취소하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
>   
>  <span data-ttu-id="9d21b-110">이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="9d21b-111">속도 향상에 대한 자세한 내용은 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d21b-111">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d21b-112">예</span><span class="sxs-lookup"><span data-stu-id="9d21b-112">Example</span></span>  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 <span data-ttu-id="9d21b-113">PLINQ 프레임워크는 단일 <xref:System.OperationCanceledException>을 <xref:System.AggregateException?displayProperty=nameWithType>으로 롤링하지 않습니다. <xref:System.OperationCanceledException>은 별도의 catch 블록에서 처리되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-113">The PLINQ framework does not roll a single <xref:System.OperationCanceledException> into an <xref:System.AggregateException?displayProperty=nameWithType>; the <xref:System.OperationCanceledException> must be handled in a separate catch block.</span></span> <span data-ttu-id="9d21b-114">하나 이상의 사용자 대리자가 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>을 사용하여 OperationCanceledException(externalCT)을 throw하지만 다른 예외를 throw하지 않고 쿼리가 `AsParallel().WithCancellation(externalCT)`로 정의된 경우 PLINQ는 <xref:System.AggregateException?displayProperty=nameWithType>이 아닌 단일 <xref:System.OperationCanceledException> (externalCT)을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-114">If one or more user delegates throws an OperationCanceledException(externalCT) (by using an external <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) but no other exception, and the query was defined as `AsParallel().WithCancellation(externalCT)`, then PLINQ will issue a single <xref:System.OperationCanceledException> (externalCT) rather than an <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9d21b-115">그러나 하나의 사용자 대리자가 <xref:System.OperationCanceledException>을 throw하고 다른 대리자가 다른 예외 형식을 throw할 경우에는 두 예외가 모두 <xref:System.AggregateException>으로 롤링됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-115">However, if one user delegate throws an <xref:System.OperationCanceledException>, and another delegate throws another exception type, then both exceptions will be rolled into an <xref:System.AggregateException>.</span></span>  
  
 <span data-ttu-id="9d21b-116">취소에 대한 일반 지침은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-116">The general guidance on cancellation is as follows:</span></span>  
  
1.  <span data-ttu-id="9d21b-117">사용자 대리자 취소를 수행하는 경우 외부 <xref:System.Threading.CancellationToken>에 대해 PLINQ에 알리고 <xref:System.OperationCanceledException>(externalCT)을 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-117">If you perform user-delegate cancellation you should inform PLINQ about the external <xref:System.Threading.CancellationToken> and throw an <xref:System.OperationCanceledException>(externalCT).</span></span>  
  
2.  <span data-ttu-id="9d21b-118">취소가 발생하고 다른 예외가 throw되지 않으면 <xref:System.AggregateException>이 아닌 <xref:System.OperationCanceledException>을 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-118">If cancellation occurs and no other exceptions are thrown, then you should handle an <xref:System.OperationCanceledException> rather than an <xref:System.AggregateException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d21b-119">예</span><span class="sxs-lookup"><span data-stu-id="9d21b-119">Example</span></span>  
 <span data-ttu-id="9d21b-120">다음 예제는 사용자 코드에서 계산을 많이 해야 하는 경우 취소를 처리하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-120">The following example shows how to handle cancellation when you have a computationally expensive function in user code.</span></span>  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 <span data-ttu-id="9d21b-121">사용자 코드에서 취소를 처리하면 쿼리 정의에서 <xref:System.Linq.ParallelEnumerable.WithCancellation%2A>을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-121">When you handle the cancellation in user code, you do not have to use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in the query definition.</span></span> <span data-ttu-id="9d21b-122">그러나 <xref:System.Linq.ParallelEnumerable.WithCancellation%2A>은 쿼리 성능에 영향을 주지 않고 이를 통해 쿼리 연산자 및 사용자 코드에서 취소를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-122">However, we recommended that you do this because <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> has no effect on query performance and it enables the cancellation to be handled by query operators and your user code.</span></span>  
  
 <span data-ttu-id="9d21b-123">시스템 응답성을 보장하기 위해 밀리초마다 한 번 정도 취소를 확인하는 것이 좋지만 최대 10밀리초의 기간이 허용되는 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-123">In order to ensure system responsiveness, we recommend that you check for cancellation around once per millisecond; however, any period up to 10 milliseconds is considered acceptable.</span></span> <span data-ttu-id="9d21b-124">이 빈도는 코드 성능에 부정적인 영향을 주면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-124">This frequency should not have a negative impact on your code's performance.</span></span>  
  
 <span data-ttu-id="9d21b-125">쿼리 결과에 대해 반복 중인 foreach(Visual Basic의 For Each) 루프에서 코드가 중단되는 경우와 같이 열거자가 삭제되는 경우에는 쿼리가 취소되지만 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d21b-125">When an enumerator is disposed, for example when code breaks out of a foreach (For Each in Visual Basic) loop that is iterating over query results, then the query is cancelled, but no exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d21b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d21b-126">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="9d21b-127">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="9d21b-127">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [<span data-ttu-id="9d21b-128">관리되는 스레드의 취소</span><span class="sxs-lookup"><span data-stu-id="9d21b-128">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
