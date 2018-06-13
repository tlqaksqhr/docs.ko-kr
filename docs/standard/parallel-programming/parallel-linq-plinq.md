---
title: PLINQ(병렬 LINQ)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ, overview
ms.assetid: 3d4d0cd3-bde4-490b-99e7-f4e41be96455
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccd30ee987fbc4ad75008a28c030c4f44a2368dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581383"
---
# <a name="parallel-linq-plinq"></a><span data-ttu-id="b1e50-102">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="b1e50-102">Parallel LINQ (PLINQ)</span></span>
<span data-ttu-id="b1e50-103">PLINQ(병렬 LINQ)는 LINQ to Objects의 병렬 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="b1e50-103">Parallel LINQ (PLINQ) is a parallel implementation of LINQ to Objects.</span></span> <span data-ttu-id="b1e50-104">PLINQ는 LINQ 표준 쿼리 연산자의 전체 집합을 <xref:System.Linq> 네임스페이스의 확장 메서드로 구현하고, 병렬 작업을 위한 추가 연산자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b1e50-104">PLINQ implements the full set of LINQ standard query operators as extension methods for the <xref:System.Linq> namespace and has additional operators for parallel operations.</span></span> <span data-ttu-id="b1e50-105">PLINQ는 LINQ의 간편성과 가독성을 병렬 프로그래밍의 기능과 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="b1e50-105">PLINQ combines the simplicity and readability of LINQ syntax with the power of parallel programming.</span></span> <span data-ttu-id="b1e50-106">작업 병렬 라이브러리를 대상으로 하는 코드와 마찬가지로 PLINQ 쿼리는 호스트 컴퓨터의 기능에 따라 동시성 수준 규모를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1e50-106">Just like code that targets the Task Parallel Library, PLINQ queries scale in the degree of concurrency based on the capabilities of the host computer.</span></span>  
  
 <span data-ttu-id="b1e50-107">대부분의 시나리오에서 PLINQ는 호스트 컴퓨터에서 사용 가능한 모든 코어를 보다 효율적으로 사용하여 LINQ to Objects 쿼리 속도를 상당히 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1e50-107">In many scenarios, PLINQ can significantly increase the speed of LINQ to Objects queries by using all available cores on the host computer more efficiently.</span></span> <span data-ttu-id="b1e50-108">이렇게 향상된 성능으로 고성능 컴퓨팅 기능을 데스크탑에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b1e50-108">This increased performance brings high performance computing power onto the desktop.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1e50-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b1e50-109">In This Section</span></span>  
 [<span data-ttu-id="b1e50-110">PLINQ 소개</span><span class="sxs-lookup"><span data-stu-id="b1e50-110">Introduction to PLINQ</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
  
 [<span data-ttu-id="b1e50-111">PLINQ의 속도 향상 이해</span><span class="sxs-lookup"><span data-stu-id="b1e50-111">Understanding Speedup in PLINQ</span></span>](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)  
  
 [<span data-ttu-id="b1e50-112">PLINQ에서 순서 유지</span><span class="sxs-lookup"><span data-stu-id="b1e50-112">Order Preservation in PLINQ</span></span>](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)  
  
 [<span data-ttu-id="b1e50-113">PLINQ의 병합 옵션</span><span class="sxs-lookup"><span data-stu-id="b1e50-113">Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)  
  
 [<span data-ttu-id="b1e50-114">방법: 간단한 PLINQ 쿼리 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="b1e50-114">How to: Create and Execute a Simple PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-create-and-execute-a-simple-plinq-query.md)  
  
 [<span data-ttu-id="b1e50-115">방법: PLINQ 쿼리의 순서 제어</span><span class="sxs-lookup"><span data-stu-id="b1e50-115">How to: Control Ordering in a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md)  
  
 [<span data-ttu-id="b1e50-116">방법: 병렬 및 순차적 LINQ 쿼리 결합</span><span class="sxs-lookup"><span data-stu-id="b1e50-116">How to: Combine Parallel and Sequential LINQ Queries</span></span>](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)  
  
 [<span data-ttu-id="b1e50-117">방법: PLINQ 쿼리의 예외 처리</span><span class="sxs-lookup"><span data-stu-id="b1e50-117">How to: Handle Exceptions in a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)  
  
 [<span data-ttu-id="b1e50-118">방법: PLINQ 쿼리 취소</span><span class="sxs-lookup"><span data-stu-id="b1e50-118">How to: Cancel a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)  
  
 [<span data-ttu-id="b1e50-119">방법: 사용자 지정 PLINQ 집계 함수 작성</span><span class="sxs-lookup"><span data-stu-id="b1e50-119">How to: Write a Custom PLINQ Aggregate Function</span></span>](../../../docs/standard/parallel-programming/how-to-write-a-custom-plinq-aggregate-function.md)  
  
 [<span data-ttu-id="b1e50-120">방법: PLINQ에 실행 모드 지정</span><span class="sxs-lookup"><span data-stu-id="b1e50-120">How to: Specify the Execution Mode in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)  
  
 [<span data-ttu-id="b1e50-121">방법: PLINQ에서 병합 옵션 지정</span><span class="sxs-lookup"><span data-stu-id="b1e50-121">How to: Specify Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)  
  
 [<span data-ttu-id="b1e50-122">방법: PLINQ를 사용하여 파일 디렉터리 열거</span><span class="sxs-lookup"><span data-stu-id="b1e50-122">How to: Iterate File Directories with PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)  
  
 [<span data-ttu-id="b1e50-123">방법: PLINQ 쿼리 성능 측정</span><span class="sxs-lookup"><span data-stu-id="b1e50-123">How to: Measure PLINQ Query Performance</span></span>](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)  
  
 [<span data-ttu-id="b1e50-124">PLINQ 데이터 샘플</span><span class="sxs-lookup"><span data-stu-id="b1e50-124">PLINQ Data Sample</span></span>](../../../docs/standard/parallel-programming/plinq-data-sample.md)  
  
## <a name="see-also"></a><span data-ttu-id="b1e50-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1e50-125">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="b1e50-126">병렬 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b1e50-126">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 [<span data-ttu-id="b1e50-127">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="b1e50-127">LINQ (Language-Integrated Query)</span></span>](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)
