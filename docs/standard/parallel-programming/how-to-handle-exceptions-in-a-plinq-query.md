---
title: '방법: PLINQ 쿼리의 예외 처리'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 162ef3849f025cae9196c2f595634f82cfc782df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a><span data-ttu-id="983ed-102">방법: PLINQ 쿼리의 예외 처리</span><span class="sxs-lookup"><span data-stu-id="983ed-102">How to: Handle Exceptions in a PLINQ Query</span></span>
<span data-ttu-id="983ed-103">이 항목의 첫 번째 예제에서는 실행될 때 PLINQ 쿼리에서 throw될 수 있는 <xref:System.AggregateException?displayProperty=nameWithType>을 처리하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-103">The first example in this topic shows how to handle the <xref:System.AggregateException?displayProperty=nameWithType> that can be thrown from a PLINQ query when it executes.</span></span> <span data-ttu-id="983ed-104">두 번째 예제에서는 대리자 내에서 예외가 throw될 위치에 가능한 한 가깝게 try-catch 블록을 넣는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-104">The second example shows how to put try-catch blocks within delegates, as close as possible to where the exception will be thrown.</span></span> <span data-ttu-id="983ed-105">이 방법으로 예외가 발생한 즉시 예외를 catch하고 쿼리 실행을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-105">In this way, you can catch them as soon as they occur and possibly continue query execution.</span></span> <span data-ttu-id="983ed-106">예외가 가입된 스레드로 다시 버블 업될 수 있는 경우 예외가 발생한 후에도 쿼리에서 일부 항목을 계속 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-106">When exceptions are allowed to bubble up back to the joining thread, then it is possible that a query may continue to process some items after the exception is raised.</span></span>  
  
 <span data-ttu-id="983ed-107">PLINQ가 순차적 실행으로 대체되고 예외가 발생하는 일부 경우에는 예외가 직접 전파되며 <xref:System.AggregateException>으로 래핑되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-107">In some cases when PLINQ falls back to sequential execution, and an exception occurs, the exception may be propagated directly, and not wrapped in an <xref:System.AggregateException>.</span></span> <span data-ttu-id="983ed-108"><xref:System.Threading.ThreadAbortException>은 항상 직접 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-108">Also, <xref:System.Threading.ThreadAbortException>s are always propagated directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="983ed-109">“내 코드만”이 사용하도록 설정된 경우 Visual Studio가 예외를 throw하는 줄에서 중단하고 “예외가 사용자 코드에서 처리되지 않았다”는 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-109">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="983ed-110">이 오류는 심각하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-110">This error is benign.</span></span> <span data-ttu-id="983ed-111">F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-111">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="983ed-112">첫 번째 오류 지점에서 Visual Studio가 실행을 중단하지 않도록 하려면 **도구, 옵션, 디버깅, 일반**을 차례로 선택하고 “내 코드만” 확인란의 선택을 취소하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-112">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
>   
>  <span data-ttu-id="983ed-113">이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-113">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="983ed-114">속도 향상에 대한 자세한 내용은 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="983ed-114">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="983ed-115">예</span><span class="sxs-lookup"><span data-stu-id="983ed-115">Example</span></span>  
 <span data-ttu-id="983ed-116">이 예제는 throw된 <xref:System.AggregateException?displayProperty=nameWithType>을 catch하는 쿼리를 실행하는 코드 주위에 try-catch 블록을 넣는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-116">This example shows how to put the try-catch blocks around the code that executes the query to catch any <xref:System.AggregateException?displayProperty=nameWithType>s that are thrown.</span></span>  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 <span data-ttu-id="983ed-117">이 예제에서는 예외가 throw된 후 쿼리를 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-117">In this example, the query cannot continue after the exception is thrown.</span></span> <span data-ttu-id="983ed-118">응용 프로그램 코드가 예외를 catch할 때까지 PLINQ가 모든 스레드에서 쿼리를 이미 중지했습니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-118">By the time your application code catches the exception, PLINQ has already stopped the query on all threads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="983ed-119">예</span><span class="sxs-lookup"><span data-stu-id="983ed-119">Example</span></span>  
 <span data-ttu-id="983ed-120">다음 예제는 예외를 catch하고 쿼리 실행을 계속할 수 있도록 대리자에 try-catch 블록을 넣는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-120">The following example shows how to put a try-catch block in a delegate to make it possible to catch an exception and continue with the query execution.</span></span>  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="983ed-121">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="983ed-121">Compiling the Code</span></span>  
  
-   <span data-ttu-id="983ed-122">이러한 예제를 컴파일하고 실행하려면 PLINQ 데이터 샘플 예제에 복사하고 Main에서 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="983ed-122">To compile and run these examples, copy them into the PLINQ Data Sample example and call the method from Main.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="983ed-123">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="983ed-123">Robust Programming</span></span>  
 <span data-ttu-id="983ed-124">프로그램 상태를 손상시키지 않도록 처리 방법을 아는 경우가 아니면 예외를 catch하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="983ed-124">Do not catch an exception unless you know how to handle it so that you do not corrupt the state of your program.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983ed-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="983ed-125">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="983ed-126">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="983ed-126">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
