---
title: "방법: PLINQ 쿼리의 예외 처리"
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
helpviewer_keywords: PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 209e0c1bf89f231d03647ae4351279bfdb172e68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a><span data-ttu-id="c337d-102">방법: PLINQ 쿼리의 예외 처리</span><span class="sxs-lookup"><span data-stu-id="c337d-102">How to: Handle Exceptions in a PLINQ Query</span></span>
<span data-ttu-id="c337d-103">이 항목의 첫 번째 예제에서는 처리 하는 방법을 보여 줍니다.는 <xref:System.AggregateException?displayProperty=nameWithType> 실행 될 때 PLINQ 쿼리에서 발생할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-103">The first example in this topic shows how to handle the <xref:System.AggregateException?displayProperty=nameWithType> that can be thrown from a PLINQ query when it executes.</span></span> <span data-ttu-id="c337d-104">두 번째 예에서는 try / catch 블록을 대리자에서 예외가 throw 될에 최대한 가깝게 배치 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-104">The second example shows how to put try-catch blocks within delegates, as close as possible to where the exception will be thrown.</span></span> <span data-ttu-id="c337d-105">이러한 방식으로 catch 할 수 있습니다 하는 즉시 발생 하며 쿼리 실행을 계속 사용할 합니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-105">In this way, you can catch them as soon as they occur and possibly continue query execution.</span></span> <span data-ttu-id="c337d-106">예외가 가입된 스레드로 다시 버블 업될 수 있는 경우 예외가 발생한 후에도 쿼리에서 일부 항목을 계속 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-106">When exceptions are allowed to bubble up back to the joining thread, then it is possible that a query may continue to process some items after the exception is raised.</span></span>  
  
 <span data-ttu-id="c337d-107">일부 경우에 plinq가 순차적 실행 하 고 예외가 발생할 때 예외 및 될 수를 직접 전파에 래핑되지는 <xref:System.AggregateException>합니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-107">In some cases when PLINQ falls back to sequential execution, and an exception occurs, the exception may be propagated directly, and not wrapped in an <xref:System.AggregateException>.</span></span> <span data-ttu-id="c337d-108">또한 <xref:System.Threading.ThreadAbortException>s은 항상 직접 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-108">Also, <xref:System.Threading.ThreadAbortException>s are always propagated directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c337d-109">"내 코드만"을 사용 하는 경우 Visual Studio는 예외를 발생 시키는 줄에서 중단 하 고 "예외가 처리 되지 않았다 사용자 코드에 의해." 오류 메시지가 표시</span><span class="sxs-lookup"><span data-stu-id="c337d-109">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="c337d-110">이 오류는 심각하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-110">This error is benign.</span></span> <span data-ttu-id="c337d-111">F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-111">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="c337d-112">Visual Studio에서 첫 번째 오류에서 분리를 방지 하려면의 선택을 취소 하기만 하 고 "내 코드만" 확인란의 **도구, 옵션, 디버깅, 일반**합니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-112">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
>   
>  <span data-ttu-id="c337d-113">이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-113">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="c337d-114">속도 대 한 자세한 내용은 참조 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-114">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c337d-115">예제</span><span class="sxs-lookup"><span data-stu-id="c337d-115">Example</span></span>  
 <span data-ttu-id="c337d-116">Try / catch 블록 안에 catch 하도록 쿼리를 실행 하는 코드를 활용 하는 방법을 보여 주는이 예제 <xref:System.AggregateException?displayProperty=nameWithType>throw 되는 s입니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-116">This example shows how to put the try-catch blocks around the code that executes the query to catch any <xref:System.AggregateException?displayProperty=nameWithType>s that are thrown.</span></span>  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 <span data-ttu-id="c337d-117">이 예에서 쿼리는 예외가 throw 된 후 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-117">In this example, the query cannot continue after the exception is thrown.</span></span> <span data-ttu-id="c337d-118">PLINQ는 응용 프로그램 코드가 예외를 catch 하는 시점 모든 스레드에 대해 쿼리를 이미 중지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-118">By the time your application code catches the exception, PLINQ has already stopped the query on all threads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c337d-119">예제</span><span class="sxs-lookup"><span data-stu-id="c337d-119">Example</span></span>  
 <span data-ttu-id="c337d-120">다음 예제에서는 예외를 catch 하 고 쿼리 실행을 계속할 수 있게 되 면 대리자에서 try / catch 블록을 삽입 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-120">The following example shows how to put a try-catch block in a delegate to make it possible to catch an exception and continue with the query execution.</span></span>  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c337d-121">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c337d-121">Compiling the Code</span></span>  
  
-   <span data-ttu-id="c337d-122">컴파일 이러한 예제, PLINQ 데이터 샘플 예제에 복사 하 고 실행에서 Main 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c337d-122">To compile and run these examples, copy them into the PLINQ Data Sample example and call the method from Main.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c337d-123">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="c337d-123">Robust Programming</span></span>  
 <span data-ttu-id="c337d-124">프로그램의 상태가 손상 되지 않도록을 처리 하는 방법을 모르는 경우에 예외를 catch 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="c337d-124">Do not catch an exception unless you know how to handle it so that you do not corrupt the state of your program.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c337d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c337d-125">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="c337d-126">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="c337d-126">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
