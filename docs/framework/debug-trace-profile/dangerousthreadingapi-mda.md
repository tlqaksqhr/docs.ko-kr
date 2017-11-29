---
title: dangerousThreadingAPI MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- DangerousThreadingAPI MDA
- managed debugging assistants (MDAs), dangerous threading operations
- threading [.NET Framework], suspending
- MDAs (managed debugging assistants), dangerous threading operations
- Suspend method
- threading [.NET Framework], managed debugging assistants
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a84fd957800f0cedcd92b36929721b4d0d51b7fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="dangerousthreadingapi-mda"></a><span data-ttu-id="f6548-102">dangerousThreadingAPI MDA</span><span class="sxs-lookup"><span data-stu-id="f6548-102">dangerousThreadingAPI MDA</span></span>
<span data-ttu-id="f6548-103">`dangerousThreadingAPI` MDA(관리 디버깅 도우미)는 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> 메서드가 현재 스레드 이외의 스레드에서 호출될 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-103">The `dangerousThreadingAPI` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> method is called on a thread other than the current thread.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f6548-104">증상</span><span class="sxs-lookup"><span data-stu-id="f6548-104">Symptoms</span></span>  
 <span data-ttu-id="f6548-105">응용 프로그램이 응답하지 않거나 무기한으로 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-105">An application is unresponsive or hangs indefinitely.</span></span> <span data-ttu-id="f6548-106">시스템 또는 응용 프로그램 데이터가 일시적으로 또는 응용 프로그램이 종료된 후에도 예측 가능한 상태로 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-106">System or application data might be left in an unpredictable state temporarily or even after an application has been shut down.</span></span> <span data-ttu-id="f6548-107">일부 작업이 예상대로 완료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-107">Some operations are not completing as expected.</span></span>  
  
 <span data-ttu-id="f6548-108">문제에 상속되는 임의성으로 인해 증상이 크게 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-108">Symptoms can vary widely due to the randomness inherent to the problem.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f6548-109">원인</span><span class="sxs-lookup"><span data-stu-id="f6548-109">Cause</span></span>  
 <span data-ttu-id="f6548-110">스레드는 <xref:System.Threading.Thread.Suspend%2A> 메서드를 사용하는 다른 스레드에 의해 비동기적으로 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-110">A thread is asynchronously suspended by another thread using the <xref:System.Threading.Thread.Suspend%2A> method.</span></span> <span data-ttu-id="f6548-111">작업 중간에 있을 수 있는 다른 스레드를 언제 안전하게 일시 중단할 수 있는지 확인할 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-111">There is no way to determine when it is safe to suspend another thread which might be in the middle of an operation.</span></span> <span data-ttu-id="f6548-112">스레드를 일시 중단하면 데이터가 손상되거나 고정이 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-112">Suspending the thread can result in the corruption of data or the breaking of invariants.</span></span> <span data-ttu-id="f6548-113">스레드가 일시 중단 상태로 전환되고 <xref:System.Threading.Thread.Resume%2A> 메서드를 통해 다시 시작되지 않으면 응용 프로그램이 무기한 중단되고 응용 프로그램 데이터가 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-113">Should a thread be placed into a suspended state and never resumed using the <xref:System.Threading.Thread.Resume%2A> method, the application can hang indefinitely and possibly damage application data.</span></span> <span data-ttu-id="f6548-114">이러한 메서드는 사용되지 않는 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-114">These methods have been marked as obsolete.</span></span>  
  
 <span data-ttu-id="f6548-115">동기화 기본 형식이 대상 스레드에서 보류되는 경우 일시 중단 중에 계속 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-115">If synchronization primitives are held by the target thread, they remain held during suspension.</span></span> <span data-ttu-id="f6548-116">기본 형식에 대한 잠금을 획득하려는 시도인 <xref:System.Threading.Thread.Suspend%2A>를 수행하는 스레드 같은 또 다른 스레드인 경우 이로 인해 교착 상태가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-116">This can lead to deadlocks should another thread, for example the thread performing the <xref:System.Threading.Thread.Suspend%2A>, attempt to acquire a lock on the primitive.</span></span> <span data-ttu-id="f6548-117">이 상황에서는 문제가 교착 상태로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-117">In this situation, the problem manifests itself as a deadlock.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f6548-118">해결</span><span class="sxs-lookup"><span data-stu-id="f6548-118">Resolution</span></span>  
 <span data-ttu-id="f6548-119"><xref:System.Threading.Thread.Suspend%2A> 및 <xref:System.Threading.Thread.Resume%2A>을 사용해야 하는 디자인을 피합니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-119">Avoid designs that require the use of <xref:System.Threading.Thread.Suspend%2A> and <xref:System.Threading.Thread.Resume%2A>.</span></span> <span data-ttu-id="f6548-120">스레드 간 상호 작용의 경우 <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex> 또는 C# `lock` 문과 같은 동기화 기본 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-120">For cooperation between threads, use synchronization primitives such as <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex>, or the C# `lock` statement.</span></span> <span data-ttu-id="f6548-121">이러한 메서드를 사용해야 할 경우 스레드가 일시 중단 상태인 동안 실행되는 기간을 단축하거나 코드 양을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-121">If you must use these methods, reduce the window of time and minimize the amount of code that executes while the thread is in a suspended state.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f6548-122">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="f6548-122">Effect on the Runtime</span></span>  
 <span data-ttu-id="f6548-123">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-123">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="f6548-124">위험한 스레딩 작업에 대한 데이터만 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-124">It only reports data about dangerous threading operations.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f6548-125">출력</span><span class="sxs-lookup"><span data-stu-id="f6548-125">Output</span></span>  
 <span data-ttu-id="f6548-126">MDA는 MDA를 활성화시키는 위험한 스레딩 메서드를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-126">The MDA identifies the dangerous threading method that caused it to be activated.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f6548-127">구성</span><span class="sxs-lookup"><span data-stu-id="f6548-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="f6548-128">예제</span><span class="sxs-lookup"><span data-stu-id="f6548-128">Example</span></span>  
 <span data-ttu-id="f6548-129">다음 코드 예제에서는 `dangerousThreadingAPI`를 활성화시키는 <xref:System.Threading.Thread.Suspend%2A> 메서드에 대한 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6548-129">The following code example demonstrates a call to the <xref:System.Threading.Thread.Suspend%2A> method that causes the activation of the `dangerousThreadingAPI`.</span></span>  
  
```  
using System.Threading;  
void FireMda()  
{  
Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();   
    t.Resume();  
    t.Join();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6548-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6548-130">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="f6548-131">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="f6548-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="f6548-132">lock 문</span><span class="sxs-lookup"><span data-stu-id="f6548-132">lock Statement</span></span>](~/docs/csharp/language-reference/keywords/lock-statement.md)
