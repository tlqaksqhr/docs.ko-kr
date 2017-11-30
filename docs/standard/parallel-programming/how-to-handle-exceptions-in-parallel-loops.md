---
title: "방법: 병렬 루프의 예외 처리"
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
helpviewer_keywords: parallel loops, how to handle exceptions
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 98e822bc148bbe5879a9ff0b7c47e9124b68e612
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-exceptions-in-parallel-loops"></a><span data-ttu-id="2fbcc-102">방법: 병렬 루프의 예외 처리</span><span class="sxs-lookup"><span data-stu-id="2fbcc-102">How to: Handle Exceptions in Parallel Loops</span></span>
<span data-ttu-id="2fbcc-103"><xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 오버로드에는 throw될 수 있는 예외를 처리하기 위한 특별한 메커니즘이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fbcc-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> overloads do not have any special mechanism to handle exceptions that might be thrown.</span></span> <span data-ttu-id="2fbcc-104">이런 점에서 일반 `for` 및 `foreach` 루프(Visual Basic의 `For` 및 `For Each`)와 비슷합니다. 처리되지 않은 예외로 인해 루프가 즉시 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fbcc-104">In this respect, they resemble regular `for` and `foreach` loops (`For` and `For Each` in Visual Basic); an unhandled exception causes the loop to terminate immediately.</span></span>  
  
 <span data-ttu-id="2fbcc-105">병렬 루프에 고유한 예외 처리 논리를 추가할 때 비슷한 예외가 여러 스레드에서 동시에 throw되는 경우와 한 스레드에서 throw된 예외로 인해 다른 스레드에서 다른 예외가 throw되는 경우를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbcc-105">When you add your own exception-handling logic to parallel loops, handle the case in which similar exceptions might be thrown on multiple threads concurrently, and the case in which an exception thrown on one thread causes another exception to be thrown on another thread.</span></span> <span data-ttu-id="2fbcc-106"><xref:System.AggregateException?displayProperty=nameWithType>에서 루프의 모든 예외를 래핑하여 두 경우 모두를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbcc-106">You can handle both cases by wrapping all exceptions from the loop in a <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2fbcc-107">다음 예제에서는 한 가지 가능한 접근 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2fbcc-107">The following example shows one possible approach.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2fbcc-108">“내 코드만”이 사용하도록 설정된 경우 Visual Studio가 예외를 발생시키는 줄에서 중단하고 "예외가 사용자 코드에서 처리되지 않았다"는 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbcc-108">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="2fbcc-109">이 오류는 심각하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fbcc-109">This error is benign.</span></span> <span data-ttu-id="2fbcc-110">F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fbcc-110">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the example below.</span></span> <span data-ttu-id="2fbcc-111">Visual Studio에서 첫 번째 오류에서 분리를 방지 하려면의 선택을 취소 하기만 하 고 "내 코드만" 확인란의 **도구, 옵션, 디버깅, 일반**합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbcc-111">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fbcc-112">예제</span><span class="sxs-lookup"><span data-stu-id="2fbcc-112">Example</span></span>  
 <span data-ttu-id="2fbcc-113">이 예제에서는 모든 예외가 catch되고 나서 throw된 <xref:System.AggregateException?displayProperty=nameWithType>로 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fbcc-113">In this example, all exceptions are caught and then wrapped in an <xref:System.AggregateException?displayProperty=nameWithType> which is thrown.</span></span> <span data-ttu-id="2fbcc-114">호출자는 처리할 예외를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fbcc-114">The caller can decide which exceptions to handle.</span></span>  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="2fbcc-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2fbcc-115">See Also</span></span>  
 [<span data-ttu-id="2fbcc-116">데이터 병렬 처리</span><span class="sxs-lookup"><span data-stu-id="2fbcc-116">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="2fbcc-117">PLINQ 및 TPL의 람다 식</span><span class="sxs-lookup"><span data-stu-id="2fbcc-117">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
