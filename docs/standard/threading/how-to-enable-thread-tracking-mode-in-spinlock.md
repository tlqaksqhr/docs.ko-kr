---
title: '방법: 스핀 잠금에서 스레드-추적 모드 사용'
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
- SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f3d5b40f1f7b4b7534a44f4f7ab542d33d373702
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="b4d0c-102">방법: 스핀 잠금에서 스레드-추적 모드 사용</span><span class="sxs-lookup"><span data-stu-id="b4d0c-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>
<span data-ttu-id="b4d0c-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType>은 대기 시간이 매우 짧은 시나리오에 사용할 수 있는 하위 수준의 상호 배제적인 잠금입니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0c-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="b4d0c-104"><xref:System.Threading.SpinLock>은 재진입 항목이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0c-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="b4d0c-105">스레드가 잠금 상태가 된 후에는 잠금을 올바르게 종료해야 다시 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0c-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="b4d0c-106">일반적으로 잠금을 다시 설정하려고 하면 교착 상태가 발생하고, 교착 상태는 디버그하기가 매우 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0c-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="b4d0c-107">개발에 대한 지원으로 <xref:System.Threading.SpinLock?displayProperty=nameWithType>은 스레드가 이미 보유하고 있는 잠금을 다시 설정하려고 할 때 예외가 throw되도록 하는 스레드 추적 모드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0c-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="b4d0c-108">따라서 잠금이 올바르게 종료되지 않은 지점을 쉽게 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0c-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="b4d0c-109">부울 입력 매개 변수를 사용하고 `true`의 인수를 전달하는 <xref:System.Threading.SpinLock> 생성자를 사용하여 스레드 추적 모드를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0c-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="b4d0c-110">개발 및 테스트 단계를 완료한 후에는 성능을 향상시키기 위해 스레드 추적 모드를 끄세요.</span><span class="sxs-lookup"><span data-stu-id="b4d0c-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4d0c-111">예</span><span class="sxs-lookup"><span data-stu-id="b4d0c-111">Example</span></span>  
 <span data-ttu-id="b4d0c-112">다음 예제는 스레드 추적 모드를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0c-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="b4d0c-113">잠금을 올바르게 종료하는 줄은 다음 결과 중 하나를 발생시키는 코딩 오류를 시뮬레이트하기 위해 주석으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0c-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
-   <span data-ttu-id="b4d0c-114"><xref:System.Threading.SpinLock>이 `true`(Visual Basic의 경우 `True`)의 인수를 사용하여 생성된 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0c-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
-   <span data-ttu-id="b4d0c-115"><xref:System.Threading.SpinLock>이 `false`(Visual Basic의 경우 `False`)의 인수를 사용하여 생성된 경우 교착 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4d0c-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="b4d0c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4d0c-116">See Also</span></span>  
 [<span data-ttu-id="b4d0c-117">스핀 잠금</span><span class="sxs-lookup"><span data-stu-id="b4d0c-117">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)
