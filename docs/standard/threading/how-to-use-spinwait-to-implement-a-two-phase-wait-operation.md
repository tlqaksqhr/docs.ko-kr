---
title: '방법: SpinWait을 사용하여 2단계 대기 작업 구현'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af6e4e8d0d754b97478788422b4dd84eeddc6491
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583281"
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a><span data-ttu-id="dfa7e-102">방법: SpinWait을 사용하여 2단계 대기 작업 구현</span><span class="sxs-lookup"><span data-stu-id="dfa7e-102">How to: Use SpinWait to Implement a Two-Phase Wait Operation</span></span>
<span data-ttu-id="dfa7e-103">다음 예제는 <xref:System.Threading.SpinWait?displayProperty=nameWithType> 개체를 사용하여 2단계 대기 작업을 구현하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfa7e-103">The following example shows how to use a <xref:System.Threading.SpinWait?displayProperty=nameWithType> object to implement a two-phase wait operation.</span></span> <span data-ttu-id="dfa7e-104">첫 번째 단계에서 동기화 개체(`Latch`)는 잠금이 사용 가능해졌는지 여부를 확인하는 동안 몇 주기 동안 회전합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa7e-104">In the first phase, the synchronization object, a `Latch`, spins for a few cycles while it checks whether the lock has become available.</span></span> <span data-ttu-id="dfa7e-105">두 번째 단계에서는 잠금이 사용 가능하게 되면 `Wait` 메서드에서 <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>을 사용하여 대기를 수행하지 않고 반환합니다. 잠금이 사용 가능하지 않으면 `Wait`에서 대기를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa7e-105">In the second phase, if the lock becomes available, then the `Wait` method returns without using the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> to perform its wait; otherwise, `Wait` performs the wait.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfa7e-106">예</span><span class="sxs-lookup"><span data-stu-id="dfa7e-106">Example</span></span>  
 <span data-ttu-id="dfa7e-107">이 예제는 래치 동기화 기본 형식의 매우 기본적인 구현을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfa7e-107">This example shows a very basic implementation of a Latch synchronization primitive.</span></span> <span data-ttu-id="dfa7e-108">대기 시간이 매우 짧을 것으로 예상되는 경우 이 데이터 구조를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa7e-108">You can use this data structure when wait times are expected to be very short.</span></span> <span data-ttu-id="dfa7e-109">이 예제는 데모용으로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfa7e-109">This example is for demonstration purposes only.</span></span> <span data-ttu-id="dfa7e-110">프로그램에 래치 유형 기능이 필요한 경우 <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="dfa7e-110">If you require latch-type functionality in your program, consider using <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 <span data-ttu-id="dfa7e-111">`SpinOnce`에 대한 다음 호출로 인해 <xref:System.Threading.SpinWait>에서 스레드의 시간 조각을 생성할 때까지만 래치는 <xref:System.Threading.SpinWait> 개체를 사용하여 적절히 회전합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa7e-111">The latch uses the <xref:System.Threading.SpinWait> object to spin in place only until the next call to `SpinOnce` causes the <xref:System.Threading.SpinWait> to yield the time slice of the thread.</span></span> <span data-ttu-id="dfa7e-112">이 지점에서 래치는 <xref:System.Threading.ManualResetEvent>에서 <xref:System.Threading.WaitHandle.WaitOne%2A>을 호출하고 나머지 시간 제한 값을 전달하여 자체 컨텍스트 전환을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="dfa7e-112">At that point, the latch causes its own context switch by calling <xref:System.Threading.WaitHandle.WaitOne%2A> on the <xref:System.Threading.ManualResetEvent> and passing in the remainder of the time-out value.</span></span>  
  
 <span data-ttu-id="dfa7e-113">로깅 출력은 <xref:System.Threading.ManualResetEvent>를 사용하지 않고 잠금을 획득하여 래치가 성능을 향상시킬 수 있었던 빈도를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa7e-113">The logging output shows how often the Latch was able to increase performance by acquiring the lock without using the <xref:System.Threading.ManualResetEvent>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa7e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfa7e-114">See Also</span></span>  
 [<span data-ttu-id="dfa7e-115">스핀 대기</span><span class="sxs-lookup"><span data-stu-id="dfa7e-115">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 [<span data-ttu-id="dfa7e-116">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="dfa7e-116">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
