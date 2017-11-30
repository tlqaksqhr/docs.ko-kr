---
title: "방법: 동시 작업을 배리어와 동기화"
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
helpviewer_keywords: Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b2e32fe3cec30a4da7467447aee625dfe7e379b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a><span data-ttu-id="3374b-102">방법: 동시 작업을 배리어와 동기화</span><span class="sxs-lookup"><span data-stu-id="3374b-102">How to: Synchronize Concurrent Operations with a Barrier</span></span>
<span data-ttu-id="3374b-103">다음 예제에서는 동시 작업을 동기화 하는 <xref:System.Threading.Barrier>합니다.</span><span class="sxs-lookup"><span data-stu-id="3374b-103">The following example shows how to synchronize concurrent tasks with a <xref:System.Threading.Barrier>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3374b-104">예제</span><span class="sxs-lookup"><span data-stu-id="3374b-104">Example</span></span>  
 <span data-ttu-id="3374b-105">다음 프로그램의 목적은 개수 반복 (또는 단계)를 계산 하 스레드를 각 찾기 두 개에 대 한 솔루션의 절반 동일한 단계에서 사용 하 여 필요한 섞은 알고리즘으로 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="3374b-105">The purpose of the following program is to count how many iterations (or phases) are required for two threads to each find their half of the solution on the same phase by using a randomizing algorithm to reshuffle the words.</span></span> <span data-ttu-id="3374b-106">각 스레드는 해당 단어 섞은 후, 후 장벽 사후 단계 작업 전체 문장 올바른 단어 순서 대로 렌더링 된 경우를 확인 하려면 두 개의 결과 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="3374b-106">After each thread has shuffled its words, the barrier post-phase operation compares the two results to see if the complete sentence has been rendered in correct word order.</span></span>  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <span data-ttu-id="3374b-107">A <xref:System.Threading.Barrier> 는 모든 작업 장벽에 도달할 때까지 계속에서 병렬 작업에서 개별 작업을 방지 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3374b-107">A <xref:System.Threading.Barrier> is an object that prevents individual tasks in a parallel operation from continuing until all tasks reach the barrier.</span></span> <span data-ttu-id="3374b-108">병렬 작업 단계에서 발생 하 고 각 단계는 작업 간의 동기화를 필요로 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3374b-108">It is useful when a parallel operation occurs in phases, and each phase requires synchronization between tasks.</span></span> <span data-ttu-id="3374b-109">이 예제에서는 작업에는 방법은 두 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3374b-109">In this example, there are two phases to the operation.</span></span> <span data-ttu-id="3374b-110">첫 번째 단계에서 각 작업은 데이터를 사용 하 여 버퍼의 항목을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="3374b-110">In the first phase, each task fills its section of the buffer with data.</span></span> <span data-ttu-id="3374b-111">각 작업 항목을 채우는 완료 되 면 작업을 계속 하려면 준비 된 장벽 및 대기를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3374b-111">When each task finishes filling its section, the task signals the barrier that it is ready to continue, and then waits.</span></span> <span data-ttu-id="3374b-112">모든 작업이 장벽 신호를 받을 때에 차단 해제 되 고 두 번째 단계를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3374b-112">When all tasks have signaled the barrier, they are unblocked and the second phase starts.</span></span> <span data-ttu-id="3374b-113">장벽은 두 번째 단계를 사용 하려면 각 작업 있어야이 지점에 생성 된 모든 데이터에 액세스할 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3374b-113">The barrier is necessary because the second phase requires that each task have access to all the data that has been generated to this point.</span></span> <span data-ttu-id="3374b-114">장벽이 없으면 첫 번째 작업이 완료 되지 채워 졌을 아직 다른 작업에서 버퍼에서 읽을 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3374b-114">Without the barrier, the first tasks to complete might try to read from buffers that have not been filled in yet by other tasks.</span></span> <span data-ttu-id="3374b-115">이런이 방식으로 단계 개수에 관계 없이 동기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3374b-115">You can synchronize any number of phases in this manner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3374b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3374b-116">See Also</span></span>  
 [<span data-ttu-id="3374b-117">병렬 프로그래밍을 위한 데이터 구조</span><span class="sxs-lookup"><span data-stu-id="3374b-117">Data Structures for Parallel Programming</span></span>](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
