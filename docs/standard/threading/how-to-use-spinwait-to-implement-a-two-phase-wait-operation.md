---
title: "방법: SpinWait을 사용하여 2단계 대기 작업 구현"
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
helpviewer_keywords: SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2717ba2d63e4ecf40638c369b66f2c696e396a5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a><span data-ttu-id="3315f-102">방법: SpinWait을 사용하여 2단계 대기 작업 구현</span><span class="sxs-lookup"><span data-stu-id="3315f-102">How to: Use SpinWait to Implement a Two-Phase Wait Operation</span></span>
<span data-ttu-id="3315f-103">사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Threading.SpinWait?displayProperty=nameWithType> 2 단계 대기 작업을 구현 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3315f-103">The following example shows how to use a <xref:System.Threading.SpinWait?displayProperty=nameWithType> object to implement a two-phase wait operation.</span></span> <span data-ttu-id="3315f-104">첫 번째 단계에서는 동기화 개체는 `Latch`, 잠금을 사용할 수 있게 되었는지 여부를 확인 하는 동안 몇 차례 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="3315f-104">In the first phase, the synchronization object, a `Latch`, spins for a few cycles while it checks whether the lock has become available.</span></span> <span data-ttu-id="3315f-105">잠금을 사용할 수 있게 하는 경우 두 번째 단계에서는 다음 `Wait` 메서드를 사용 하지 않고 반환는 <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> 대기 상태; 수행 하려면 그렇지 않으면 `Wait` 대기를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3315f-105">In the second phase, if the lock becomes available, then the `Wait` method returns without using the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> to perform its wait; otherwise, `Wait` performs the wait.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3315f-106">예제</span><span class="sxs-lookup"><span data-stu-id="3315f-106">Example</span></span>  
 <span data-ttu-id="3315f-107">이 예제에서는 기본 래치 동기화를 구현 하는 매우 기본적인를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3315f-107">This example shows a very basic implementation of a Latch synchronization primitive.</span></span> <span data-ttu-id="3315f-108">대기 시간이 매우 짧은 것으로 예상 되는이 데이터 구조를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3315f-108">You can use this data structure when wait times are expected to be very short.</span></span> <span data-ttu-id="3315f-109">이 예제는 예시용입니다.</span><span class="sxs-lookup"><span data-stu-id="3315f-109">This example is for demonstration purposes only.</span></span> <span data-ttu-id="3315f-110">프로그램에서 래치 형식 기능을 필요한 경우에 사용 하 여 고려 <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="3315f-110">If you require latch-type functionality in your program, consider using <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 <span data-ttu-id="3315f-111">래치를 사용 하 여는 <xref:System.Threading.SpinWait> 개체에 대 한 다음 호출 될 때까지 준비에서 회전 하는 데 `SpinOnce` 하면는 <xref:System.Threading.SpinWait> 스레드 시간 간격을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3315f-111">The latch uses the <xref:System.Threading.SpinWait> object to spin in place only until the next call to `SpinOnce` causes the <xref:System.Threading.SpinWait> to yield the time slice of the thread.</span></span> <span data-ttu-id="3315f-112">래치를 호출 하 여 컨텍스트 전환이 사용 하면 해당 시점에 <xref:System.Threading.WaitHandle.WaitOne%2A> 에 <xref:System.Threading.ManualResetEvent> 시간 제한 값의 나머지 부분에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="3315f-112">At that point, the latch causes its own context switch by calling <xref:System.Threading.WaitHandle.WaitOne%2A> on the <xref:System.Threading.ManualResetEvent> and passing in the remainder of the time-out value.</span></span>  
  
 <span data-ttu-id="3315f-113">로깅 출력 표시 얼마나 자주 래치를 사용 하지 않고 잠금을 획득 하 여 성능을 향상 시킬 수는 <xref:System.Threading.ManualResetEvent>합니다.</span><span class="sxs-lookup"><span data-stu-id="3315f-113">The logging output shows how often the Latch was able to increase performance by acquiring the lock without using the <xref:System.Threading.ManualResetEvent>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3315f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3315f-114">See Also</span></span>  
 [<span data-ttu-id="3315f-115">스핀 대기</span><span class="sxs-lookup"><span data-stu-id="3315f-115">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 [<span data-ttu-id="3315f-116">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="3315f-116">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
