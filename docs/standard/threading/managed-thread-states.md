---
title: 관리되는 스레드 상태
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], states
ms.assetid: 63890d5e-6025-4a7c-aaf0-d8bfd54b455f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4266aea9bf206d127e2837955dcc00cc23f4119b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587725"
---
# <a name="managed-thread-states"></a><span data-ttu-id="1eed5-102">관리되는 스레드 상태</span><span class="sxs-lookup"><span data-stu-id="1eed5-102">Managed Thread States</span></span>
<span data-ttu-id="1eed5-103"><xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> 속성은 스레드의 현재 상태를 나타내는 비트 마스크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-103">The property <xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> provides a bit mask that indicates the thread's current state.</span></span> <span data-ttu-id="1eed5-104">스레드는 항상 <xref:System.Threading.ThreadState> 열거형의 가능한 상태 중 하나 이상이며 동시에 여러 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-104">A thread is always in at least one of the possible states in the <xref:System.Threading.ThreadState> enumeration, and can be in multiple states at the same time.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1eed5-105">스레드 상태는 일부 디버깅 시나리오에서만 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-105">Thread state is only of interest in a few debugging scenarios.</span></span> <span data-ttu-id="1eed5-106">코드에서 스레드 상태를 사용하여 스레드 활동을 동기화하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-106">Your code should never use thread state to synchronize the activities of threads.</span></span>  
  
 <span data-ttu-id="1eed5-107">관리되는 스레드를 만드는 경우 <xref:System.Threading.ThreadState.Unstarted> 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-107">When you create a managed thread, it is in the <xref:System.Threading.ThreadState.Unstarted> state.</span></span> <span data-ttu-id="1eed5-108">스레드는 운영 체제에서 시작됨 상태로 이동할 때까지 <xref:System.Threading.ThreadState.Unstarted> 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-108">The thread remains in the <xref:System.Threading.ThreadState.Unstarted> state until it is moved into the started state by the operating system.</span></span> <span data-ttu-id="1eed5-109"><xref:System.Threading.Thread.Start%2A> 를 호출하면 운영 체제에서 스레드를 시작할 수 있음을 알게 됩니다. 스레드의 상태를 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-109">Calling <xref:System.Threading.Thread.Start%2A> lets the operating system know that the thread can be started; it does not change the state of the thread.</span></span>  
  
 <span data-ttu-id="1eed5-110">관리되는 환경으로 들어가는 관리되지 않는 스레드는 이미 시작됨 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-110">Unmanaged threads that enter the managed environment are already in the started state.</span></span> <span data-ttu-id="1eed5-111">스레드가 시작됨 상태이면 다양한 작업에 의해 스레드 상태가 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-111">Once a thread is in the started state, a number of actions can cause it to change states.</span></span> <span data-ttu-id="1eed5-112">다음 표에서는 상태 변경이 발생하는 작업 및 해당 새 상태를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-112">The following table lists the actions that cause a change of state, along with the corresponding new state.</span></span>  
  
|<span data-ttu-id="1eed5-113">작업</span><span class="sxs-lookup"><span data-stu-id="1eed5-113">Action</span></span>|<span data-ttu-id="1eed5-114">새 상태</span><span class="sxs-lookup"><span data-stu-id="1eed5-114">Resulting new state</span></span>|  
|------------|-------------------------|  
|<span data-ttu-id="1eed5-115"><xref:System.Threading.Thread> 클래스의 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-115">The constructor for the <xref:System.Threading.Thread> class is called.</span></span>|<xref:System.Threading.ThreadState.Unstarted>|  
|<span data-ttu-id="1eed5-116">다른 스레드가 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-116">Another thread calls <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.Unstarted>|  
|<span data-ttu-id="1eed5-117">스레드가 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>에 응답하고 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-117">The thread responds to <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> and starts running.</span></span>|<xref:System.Threading.ThreadState.Running>|  
|<span data-ttu-id="1eed5-118">스레드가 <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-118">The thread calls <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|<span data-ttu-id="1eed5-119">스레드가 다른 개체에서 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-119">The thread calls <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> on another object.</span></span>|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|<span data-ttu-id="1eed5-120">스레드가 다른 스레드에서 <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-120">The thread calls <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> on another thread.</span></span>|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|<span data-ttu-id="1eed5-121">다른 스레드가 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-121">Another thread calls <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.SuspendRequested>|  
|<span data-ttu-id="1eed5-122">스레드가 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> 요청에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-122">The thread responds to a <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> request.</span></span>|<xref:System.Threading.ThreadState.Suspended>|  
|<span data-ttu-id="1eed5-123">다른 스레드가 <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-123">Another thread calls <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.Running>|  
|<span data-ttu-id="1eed5-124">다른 스레드가 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-124">Another thread calls <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.AbortRequested>|  
|<span data-ttu-id="1eed5-125">스레드가 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-125">The thread responds to an <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>|<span data-ttu-id="1eed5-126"><xref:System.Threading.ThreadState.Aborted>, <xref:System.Threading.ThreadState.Stopped></span><span class="sxs-lookup"><span data-stu-id="1eed5-126"><xref:System.Threading.ThreadState.Aborted>, then <xref:System.Threading.ThreadState.Stopped></span></span>|  
  
 <span data-ttu-id="1eed5-127"><xref:System.Threading.ThreadState.Running> 상태는 값이 0이므로 비트 테스트를 통해 이 상태를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-127">Because the <xref:System.Threading.ThreadState.Running> state has a value of 0, it is not possible to perform a bit test to discover this state.</span></span> <span data-ttu-id="1eed5-128">대신, 의사 코드에서 다음 테스트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-128">Instead, the following test (in pseudo-code) can be used:</span></span>  
  
```  
if ((state & (Unstarted | Stopped)) == 0)   // implies Running     
```  
  
 <span data-ttu-id="1eed5-129">스레드가 지정된 시간에 둘 이상의 상태인 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-129">Threads are often in more than one state at any given time.</span></span> <span data-ttu-id="1eed5-130">예를 들어 한 스레드가 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> 호출에서 차단되고 다른 스레드가 동일한 스레드에서 <xref:System.Threading.Thread.Abort%2A>를 호출할 경우 스레드는 동시에 <xref:System.Threading.ThreadState.WaitSleepJoin> 및 <xref:System.Threading.ThreadState.AbortRequested> 상태를 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-130">For example, if a thread is blocked on a <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> call and another thread calls <xref:System.Threading.Thread.Abort%2A> on that same thread, the thread will be in both the <xref:System.Threading.ThreadState.WaitSleepJoin> and the <xref:System.Threading.ThreadState.AbortRequested> states at the same time.</span></span> <span data-ttu-id="1eed5-131">이 경우 스레드가 <xref:System.Threading.Monitor.Wait%2A> 호출에서 반환되거나 중단되는 즉시 <xref:System.Threading.ThreadAbortException>이 수신됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-131">In that case, as soon as the thread returns from the call to <xref:System.Threading.Monitor.Wait%2A> or is interrupted, it will receive the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 <span data-ttu-id="1eed5-132"><xref:System.Threading.ThreadState.Unstarted> 호출의 결과로 스레드가 <xref:System.Threading.Thread.Start%2A>상태를 벗어난 후에는 <xref:System.Threading.ThreadState.Unstarted> 상태로 돌아갈 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-132">Once a thread leaves the <xref:System.Threading.ThreadState.Unstarted> state as the result of a call to <xref:System.Threading.Thread.Start%2A>, it can never return to the <xref:System.Threading.ThreadState.Unstarted> state.</span></span> <span data-ttu-id="1eed5-133">스레드는 <xref:System.Threading.ThreadState.Stopped> 상태를 벗어날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1eed5-133">A thread can never leave the <xref:System.Threading.ThreadState.Stopped> state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eed5-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1eed5-134">See Also</span></span>  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadState>  
 [<span data-ttu-id="1eed5-135">스레딩</span><span class="sxs-lookup"><span data-stu-id="1eed5-135">Threading</span></span>](../../../docs/standard/threading/index.md)
