---
title: '방법: 간단한 Parallel.ForEach 루프 작성'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 90b900bf98ab664e0fce5c70573f01e044d70803
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="1c33d-102">방법: 간단한 Parallel.ForEach 루프 작성</span><span class="sxs-lookup"><span data-stu-id="1c33d-102">How to: Write a Simple Parallel.ForEach Loop</span></span>
<span data-ttu-id="1c33d-103">이 예제는 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 루프를 사용하여 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 데이터 소스에 대해 데이터 병렬 처리를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c33d-103">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c33d-104">이 문서에서는 람다 식을 사용하여 PLINQ에 대리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1c33d-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="1c33d-105">C# 또는 Visual Basic의 람다 식을 잘 모르는 경우 [PLINQ 및 TPL의 람다 식](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c33d-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c33d-106">예</span><span class="sxs-lookup"><span data-stu-id="1c33d-106">Example</span></span>  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 <span data-ttu-id="1c33d-107"><xref:System.Threading.Tasks.Parallel.ForEach%2A> 루프는 <xref:System.Threading.Tasks.Parallel.For%2A> 루프처럼 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="1c33d-107">A <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A> loop.</span></span> <span data-ttu-id="1c33d-108">소스 컬렉션은 파티셔닝되고 작업은 시스템 환경을 기반으로 여러 스레드에서 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c33d-108">The source collection is partitioned and the work is scheduled on multiple threads based on the system environment.</span></span> <span data-ttu-id="1c33d-109">시스템에 프로세서가 많을수록 병렬 메서드가 더 빠르게 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c33d-109">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="1c33d-110">일부 소스 컬렉션의 경우, 소스의 크기 및 수행되는 작업의 종류에 따라 순차 루프가 더 빠를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c33d-110">For some source collections, a sequential loop may be faster, depending on the size of the source, and the kind of work being performed.</span></span> <span data-ttu-id="1c33d-111">성능에 대한 자세한 내용은 [데이터 및 작업 병렬 처리에서 발생할 수 있는 문제](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c33d-111">For more information about performance, see [Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)</span></span>  
  
 <span data-ttu-id="1c33d-112">병렬 루프에 대한 자세한 내용은 [방법: 간단한 Parallel.For 루프 작성](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c33d-112">For more information about parallel loops, see [How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span></span>  
  
 <span data-ttu-id="1c33d-113">제네릭이 아닌 컬렉션에 <xref:System.Threading.Tasks.Parallel.ForEach%2A>를 사용하려면 다음 예제와 같이 <xref:System.Linq.Enumerable.Cast%2A> 확장 메서드를 사용하여 컬렉션을 일반 컬렉션으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c33d-113">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 <span data-ttu-id="1c33d-114">병렬 LINQ(PLINQ)를 사용하여 <xref:System.Collections.Generic.IEnumerable%601> 데이터 소스의 처리를 병렬 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c33d-114">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="1c33d-115">PLINQ를 통해 선언 쿼리 구문을 사용하여 루프 동작을 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c33d-115">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="1c33d-116">자세한 내용은 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c33d-116">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1c33d-117">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="1c33d-117">Compiling the Code</span></span>  
  
-   <span data-ttu-id="1c33d-118">이 코드를 복사하여 Visual Studio 2010 콘솔 응용 프로그램 프로젝트에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1c33d-118">Copy and paste this code into a Visual Studio 2010 Console Application project.</span></span>  
  
-   <span data-ttu-id="1c33d-119">System.Drawing.dll에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1c33d-119">Add a reference to System.Drawing.dll</span></span>  
  
-   <span data-ttu-id="1c33d-120">F5 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1c33d-120">Press F5</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c33d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c33d-121">See Also</span></span>  
 [<span data-ttu-id="1c33d-122">데이터 병렬 처리</span><span class="sxs-lookup"><span data-stu-id="1c33d-122">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="1c33d-123">병렬 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="1c33d-123">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 [<span data-ttu-id="1c33d-124">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="1c33d-124">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
