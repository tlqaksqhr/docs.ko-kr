---
title: '방법: 동시 작업을 배리어와 동기화'
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
- Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 616229abed93c6793b392724d038d8f9160cd6ae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a><span data-ttu-id="45444-102">방법: 동시 작업을 배리어와 동기화</span><span class="sxs-lookup"><span data-stu-id="45444-102">How to: Synchronize Concurrent Operations with a Barrier</span></span>
<span data-ttu-id="45444-103">다음 예제는 <xref:System.Threading.Barrier>와 동시 작업을 동기화하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="45444-103">The following example shows how to synchronize concurrent tasks with a <xref:System.Threading.Barrier>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45444-104">예</span><span class="sxs-lookup"><span data-stu-id="45444-104">Example</span></span>  
 <span data-ttu-id="45444-105">다음 프로그램의 목적은 무작위 알고리즘을 사용하여 단어를 다시 섞어서 동일한 단계에서 두 스레드가 솔루션의 절반을 서로 찾는 데 필요한 반복(또는 단계) 수를 계산하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45444-105">The purpose of the following program is to count how many iterations (or phases) are required for two threads to each find their half of the solution on the same phase by using a randomizing algorithm to reshuffle the words.</span></span> <span data-ttu-id="45444-106">각 스레드가 해당 단어를 섞은 후 장벽 사후 단계 작업은 두 결과를 비교하여 전체 문장이 올바른 단어 순서로 렌더링되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="45444-106">After each thread has shuffled its words, the barrier post-phase operation compares the two results to see if the complete sentence has been rendered in correct word order.</span></span>  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <span data-ttu-id="45444-107"><xref:System.Threading.Barrier>는 모든 작업이 장벽에 도달할 때까지 병렬 작업의 개별 작업이 계속되는 것을 방지하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="45444-107">A <xref:System.Threading.Barrier> is an object that prevents individual tasks in a parallel operation from continuing until all tasks reach the barrier.</span></span> <span data-ttu-id="45444-108">이 개체는 병렬 작업이 단계에서 발생하는 경우에 유용하며, 각 단계에서는 작업 간 동기화가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="45444-108">It is useful when a parallel operation occurs in phases, and each phase requires synchronization between tasks.</span></span> <span data-ttu-id="45444-109">이 예제에서, 작업의 단계는 두 개입니다.</span><span class="sxs-lookup"><span data-stu-id="45444-109">In this example, there are two phases to the operation.</span></span> <span data-ttu-id="45444-110">첫 번째 단계에서 각 작업은 데이터를 사용하여 버퍼의 섹션을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="45444-110">In the first phase, each task fills its section of the buffer with data.</span></span> <span data-ttu-id="45444-111">각 작업이 해당 섹션 채우기를 완료하면 작업은 장벽에 계속할 준비가 되었음을 알리는 신호를 보낸 후 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="45444-111">When each task finishes filling its section, the task signals the barrier that it is ready to continue, and then waits.</span></span> <span data-ttu-id="45444-112">모든 작업이 장벽에 신호를 보내면 장벽이 잠금 해제되고 두 번째 단계가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="45444-112">When all tasks have signaled the barrier, they are unblocked and the second phase starts.</span></span> <span data-ttu-id="45444-113">두 번째 단계에서는 각 작업이 이 지점까지 생성된 모든 데이터에 액세스해야 하므로 장벽이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="45444-113">The barrier is necessary because the second phase requires that each task have access to all the data that has been generated to this point.</span></span> <span data-ttu-id="45444-114">장벽이 없으면 완료할 첫 번째 작업이 다른 작업에 의해 아직 채워지지 않은 버퍼에서 읽으려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45444-114">Without the barrier, the first tasks to complete might try to read from buffers that have not been filled in yet by other tasks.</span></span> <span data-ttu-id="45444-115">이런 방식으로 개수와 관계없이 모든 단계를 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45444-115">You can synchronize any number of phases in this manner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45444-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45444-116">See Also</span></span>  
 [<span data-ttu-id="45444-117">병렬 프로그래밍을 위한 데이터 구조</span><span class="sxs-lookup"><span data-stu-id="45444-117">Data Structures for Parallel Programming</span></span>](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
