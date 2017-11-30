---
title: "방법: 스핀 잠금에서 스레드-추적 모드 사용"
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
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5f1b6eace7a24a6bbb7fd541858246828fa757
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="59398-102">방법: 스핀 잠금에서 스레드-추적 모드 사용</span><span class="sxs-lookup"><span data-stu-id="59398-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>
<span data-ttu-id="59398-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType>낮은 수준의 상호 배제 하는 매우 짧은 대기 시간이 없는 시나리오에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59398-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="59398-104"><xref:System.Threading.SpinLock>재진입 성이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="59398-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="59398-105">스레드가 이미 잠금을 획득을 종료 해야 잠금을 잘못 다시 시작할 수 있으려면 먼저 합니다.</span><span class="sxs-lookup"><span data-stu-id="59398-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="59398-106">일반적으로 잠금을 다시 시작 하려는 시도 인해 교착 상태를 하 고 교착 상태 디버깅이 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59398-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="59398-107">개발, 높이기 위해 <xref:System.Threading.SpinLock?displayProperty=nameWithType> 스레드가 이미 획득 한 잠금을 다시 입력 하려고 할 때 throw 되는 예외를 발생 시킨 스레드-추적 모드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="59398-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="59398-108">이는 잠금을 올바르게 종료 되지 않은 지점 보다 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59398-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="59398-109">스레드-추적 모드를 사용 하 여 켤 수 있습니다는 <xref:System.Threading.SpinLock> 부울 값을 사용 하는 생성자의 인수에 전달 하 고 매개 변수를 입력 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="59398-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="59398-110">개발 및 테스트 단계를 완료 한 후 성능 향상을 위해 스레드-추적 모드를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="59398-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59398-111">예제</span><span class="sxs-lookup"><span data-stu-id="59398-111">Example</span></span>  
 <span data-ttu-id="59398-112">다음 예제에서는 스레드-추적 모드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59398-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="59398-113">올바르게 잠금을 종료 하는 줄은 다음 결과 중 하나를 발생 시키는 코딩 오류를 시뮬레이션 하 주석 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59398-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
-   <span data-ttu-id="59398-114">예외가 발생 하는 경우는 <xref:System.Threading.SpinLock> 의 인수를 사용 하 여 만든 `true` (`True` Visual basic에서).</span><span class="sxs-lookup"><span data-stu-id="59398-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
-   <span data-ttu-id="59398-115">경우 교착 상태는 <xref:System.Threading.SpinLock> 의 인수를 사용 하 여 만든 `false` (`False` Visual basic에서).</span><span class="sxs-lookup"><span data-stu-id="59398-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="59398-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59398-116">See Also</span></span>  
 [<span data-ttu-id="59398-117">스핀 잠금</span><span class="sxs-lookup"><span data-stu-id="59398-117">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)
