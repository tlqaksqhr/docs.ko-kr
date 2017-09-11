---
title: "다중 스레드 응용 프로그램 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 02b0444b-2e68-4f2c-bc28-28c046004017
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8b68104fbc5eb0e0eb0f46401f3fcef0d3c4d023
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="multithreaded-applications-visual-basic"></a><span data-ttu-id="dbb42-102">다중 스레드 응용 프로그램 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dbb42-102">Multithreaded Applications (Visual Basic)</span></span>
<span data-ttu-id="dbb42-103">Visual basic에서 동시에 여러 작업을 수행 하는 응용 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-103">With Visual Basic, you can write applications that perform multiple tasks at the same time.</span></span> <span data-ttu-id="dbb42-104">가능성이 있는 작업은 다른 작업을 지연 시킬 프로세스 라고 별도 스레드에서 실행 *다중 스레딩* 또는 *자유 스레딩*합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-104">Tasks with the potential of holding up other tasks can execute on separate threads, a process known as *multithreading* or *free threading*.</span></span>  
  
 <span data-ttu-id="dbb42-105">다중 스레딩을 사용은 사용자 인터페이스의 별도 스레드에서 실행 하는 프로세서 집약적인 작업 들이 활성 상태로 유지 때문에 사용자 입력에 빠르게 응답 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-105">Applications that use multithreading are more responsive to user input because the user interface stays active as processor-intensive tasks execute on separate threads.</span></span> <span data-ttu-id="dbb42-106">또한 다중 스레딩을 사용 작업 부하가 증가 함에 따라 스레드를 추가할 수 있으므로 확장 가능한 응용 프로그램을 만들 때에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-106">Multithreading is also useful when you create scalable applications, because you can add threads as the workload increases.</span></span>  
  
## <a name="creating-and-using-threads"></a><span data-ttu-id="dbb42-107">스레드 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="dbb42-107">Creating and Using Threads</span></span>  
 <span data-ttu-id="dbb42-108">응용 프로그램의 스레드의 동작에 대해 더 많은 제어가 필요한 경우에 사용자가 직접 스레드 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-108">If you need more control over the behavior of your application's threads, you can manage the threads yourself.</span></span> <span data-ttu-id="dbb42-109">그러나 올바른 다중 스레드 응용 프로그램을 작성 어려울 수를 채택한: 응용 프로그램 응답 하지 않거나 경쟁 조건으로 인해 발생 하는 일시적인 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-109">However, realize that writing correct multithreaded applications can be difficult: Your application may stop responding or experience transient errors caused by race conditions.</span></span> <span data-ttu-id="dbb42-110">자세한 내용은 참조 [스레드로부터 안전한 구성 요소](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee)합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-110">For more information, see [Thread-Safe Components](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).</span></span>  
  
 <span data-ttu-id="dbb42-111">형식의 변수를 선언 하 여 새 스레드를 만들 <xref:System.Threading.Thread>프로시저 또는 새 스레드에서 실행 하려는 메서드의 이름을 제공 하는 생성자를 호출 하 고.</xref:System.Threading.Thread></span><span class="sxs-lookup"><span data-stu-id="dbb42-111">You create a new thread by declaring a variable of type <xref:System.Threading.Thread> and calling the constructor, providing the name of the procedure or method that you want to execute on the new thread.</span></span> <span data-ttu-id="dbb42-112">코드 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-112">The following code provides an example.</span></span>  
  
```vb  
Dim newThread As New System.Threading.Thread(AddressOf AMethod)  
```  
  
### <a name="starting-and-stopping-threads"></a><span data-ttu-id="dbb42-113">스레드 시작 및 중지</span><span class="sxs-lookup"><span data-stu-id="dbb42-113">Starting and Stopping Threads</span></span>  
 <span data-ttu-id="dbb42-114">새 스레드의 실행을 시작 하려면 사용 된 <xref:System.Threading.Thread.Start%2A>메서드를 다음 코드에 나와 있는 것 처럼.</xref:System.Threading.Thread.Start%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-114">To start the execution of a new thread, use the <xref:System.Threading.Thread.Start%2A> method, as shown in the following code.</span></span>  
  
```vb  
newThread.Start()  
```  
  
 <span data-ttu-id="dbb42-115">스레드 실행을 중지 하려면 사용 된 <xref:System.Threading.Thread.Abort%2A>메서드를 다음 코드에 나와 있는 것 처럼.</xref:System.Threading.Thread.Abort%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-115">To stop the execution of a thread, use the <xref:System.Threading.Thread.Abort%2A> method, as shown in the following code.</span></span>  
  
```vb  
newThread.Abort()  
```  
  
 <span data-ttu-id="dbb42-116">스레드 시작 및 중지, 외에도 또한 일시 중지할 수 있습니다 스레드를 호출 하 여는 <xref:System.Threading.Thread.Sleep%2A>또는 <xref:System.Threading.Thread.Suspend%2A>메서드를 사용 하 여 일시 중단 된 스레드 재개는 <xref:System.Threading.Thread.Resume%2A>메서드를 <xref:System.Threading.Thread.Abort%2A>메서드</xref:System.Threading.Thread.Abort%2A> 를 사용 하 여 스레드를 제거 하 고</xref:System.Threading.Thread.Resume%2A> </xref:System.Threading.Thread.Suspend%2A> </xref:System.Threading.Thread.Sleep%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-116">Besides starting and stopping threads, you can also pause threads by calling the <xref:System.Threading.Thread.Sleep%2A> or <xref:System.Threading.Thread.Suspend%2A> method, resume a suspended thread by using the <xref:System.Threading.Thread.Resume%2A> method, and destroy a thread by using the <xref:System.Threading.Thread.Abort%2A> method</span></span>  
  
### <a name="thread-methods"></a><span data-ttu-id="dbb42-117">스레드 메서드</span><span class="sxs-lookup"><span data-stu-id="dbb42-117">Thread Methods</span></span>  
 <span data-ttu-id="dbb42-118">다음 표에서 각 스레드를 제어 하는 데 사용할 수 있는 방법 중 일부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-118">The following table shows some of the methods that you can use to control individual threads.</span></span>  
  
|<span data-ttu-id="dbb42-119">메서드</span><span class="sxs-lookup"><span data-stu-id="dbb42-119">Method</span></span>|<span data-ttu-id="dbb42-120">작업</span><span class="sxs-lookup"><span data-stu-id="dbb42-120">Action</span></span>|  
|------------|------------|  
|<span data-ttu-id="dbb42-121"><xref:System.Threading.Thread.Start%2A></xref:System.Threading.Thread.Start%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-121"><xref:System.Threading.Thread.Start%2A></span></span>|<span data-ttu-id="dbb42-122">스레드의 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-122">Causes a thread to start to run.</span></span>|  
|<span data-ttu-id="dbb42-123"><xref:System.Threading.Thread.Sleep%2A></xref:System.Threading.Thread.Sleep%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-123"><xref:System.Threading.Thread.Sleep%2A></span></span>|<span data-ttu-id="dbb42-124">지정된 된 시간에 대 한 스레드를 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-124">Pauses a thread for a specified time.</span></span>|  
|<span data-ttu-id="dbb42-125"><xref:System.Threading.Thread.Suspend%2A></xref:System.Threading.Thread.Suspend%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-125"><xref:System.Threading.Thread.Suspend%2A></span></span>|<span data-ttu-id="dbb42-126">안전한 시점에 도달 하면 스레드를 일시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-126">Pauses a thread when it reaches a safe point.</span></span>|  
|<span data-ttu-id="dbb42-127"><xref:System.Threading.Thread.Abort%2A></xref:System.Threading.Thread.Abort%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-127"><xref:System.Threading.Thread.Abort%2A></span></span>|<span data-ttu-id="dbb42-128">안전한 시점에 도달 하면 스레드를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-128">Stops a thread when it reaches a safe point.</span></span>|  
|<span data-ttu-id="dbb42-129"><xref:System.Threading.Thread.Resume%2A></xref:System.Threading.Thread.Resume%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-129"><xref:System.Threading.Thread.Resume%2A></span></span>|<span data-ttu-id="dbb42-130">일시 중지 된 스레드를 다시 시작</span><span class="sxs-lookup"><span data-stu-id="dbb42-130">Restarts a suspended thread</span></span>|  
|<span data-ttu-id="dbb42-131"><xref:System.Threading.Thread.Join%2A></xref:System.Threading.Thread.Join%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-131"><xref:System.Threading.Thread.Join%2A></span></span>|<span data-ttu-id="dbb42-132">현재 스레드를 다른 스레드가 끝나기를 기다리는 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-132">Causes the current thread to wait for another thread to finish.</span></span> <span data-ttu-id="dbb42-133">이 메서드가 반환 하는 시간 제한 값을 사용 하는 경우 `True` 스레드가 할당된 된 시간 안에 완료 된 경우.</span><span class="sxs-lookup"><span data-stu-id="dbb42-133">If used with a time-out value, this method returns `True` if the thread finishes in the allocated time.</span></span>|  
  
### <a name="safe-points"></a><span data-ttu-id="dbb42-134">안전한 시점</span><span class="sxs-lookup"><span data-stu-id="dbb42-134">Safe Points</span></span>  
 <span data-ttu-id="dbb42-135">이러한 메서드의 대부분은 새로울 하지만의 개념은 *안전 지점* 게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-135">Most of these methods are self-explanatory, but the concept of *safe points* may be new to you.</span></span> <span data-ttu-id="dbb42-136">안전 지점 있는 것은 안전 공용 언어 런타임에서 자동으로 수행 하는 코드의 위치는 *가비지 수집*, 사용 되지 않은 변수를 해제 하 고 메모리를 회수 하는 데는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-136">Safe points are locations in code where it is safe for the common language runtime to perform automatic *garbage collection*, the process of releasing unused variables and reclaiming memory.</span></span> <span data-ttu-id="dbb42-137">호출 하는 경우는 <xref:System.Threading.Thread.Abort%2A>또는 <xref:System.Threading.Thread.Suspend%2A>공용 언어 런타임 스레드 메서드 코드를 분석 하 고 실행을 중지 하려면 스레드에 대 한 적절 한 위치의 위치를 결정 합니다.</xref:System.Threading.Thread.Suspend%2A> </xref:System.Threading.Thread.Abort%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-137">When you call the <xref:System.Threading.Thread.Abort%2A> or <xref:System.Threading.Thread.Suspend%2A> method of a thread, the common language runtime analyzes the code and determines the location of an appropriate location for the thread to stop running.</span></span>  
  
### <a name="thread-properties"></a><span data-ttu-id="dbb42-138">스레드 속성</span><span class="sxs-lookup"><span data-stu-id="dbb42-138">Thread Properties</span></span>  
 <span data-ttu-id="dbb42-139">스레드는 다음 표에 나와 있는 것 처럼 여러 가지 유용한 속성을 포함 될.</span><span class="sxs-lookup"><span data-stu-id="dbb42-139">Threads also contain several useful properties, as shown in the following table:</span></span>  
  
|<span data-ttu-id="dbb42-140">속성</span><span class="sxs-lookup"><span data-stu-id="dbb42-140">Property</span></span>|<span data-ttu-id="dbb42-141">값</span><span class="sxs-lookup"><span data-stu-id="dbb42-141">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="dbb42-142"><xref:System.Threading.Thread.IsAlive%2A></xref:System.Threading.Thread.IsAlive%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-142"><xref:System.Threading.Thread.IsAlive%2A></span></span>|<span data-ttu-id="dbb42-143">값이 포함 된 `True` 스레드가 실행 중인 경우.</span><span class="sxs-lookup"><span data-stu-id="dbb42-143">Contains the value `True` if a thread is active.</span></span>|  
|<span data-ttu-id="dbb42-144"><xref:System.Threading.Thread.IsBackground%2A></xref:System.Threading.Thread.IsBackground%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-144"><xref:System.Threading.Thread.IsBackground%2A></span></span>|<span data-ttu-id="dbb42-145">스레드는 또는 백그라운드 스레드에서 해야 하는 경우를 나타내는 부울 값을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-145">Gets or sets a Boolean that indicates if a thread is or should be a background thread.</span></span> <span data-ttu-id="dbb42-146">백그라운드 스레드는 포그라운드 스레드 유사 하지만 백그라운드 스레드에서 않습니다 막지 프로세스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-146">Background threads are like foreground threads, but a background thread does not prevent a process from stopping.</span></span> <span data-ttu-id="dbb42-147">공용 언어 런타임에서 호출 하 여 프로세스를 종료 하는 프로세스에 속하는 모든 포그라운드 스레드가 중지 되 면는 <xref:System.Threading.Thread.Abort%2A>메서드는 아직 활성화 되어 백그라운드 스레드를.</xref:System.Threading.Thread.Abort%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-147">Once all foreground threads that belong to a process have stopped, the common language runtime ends the process by calling the <xref:System.Threading.Thread.Abort%2A> method on background threads that are still alive.</span></span>|  
|<span data-ttu-id="dbb42-148"><xref:System.Threading.Thread.Name%2A></xref:System.Threading.Thread.Name%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-148"><xref:System.Threading.Thread.Name%2A></span></span>|<span data-ttu-id="dbb42-149">스레드의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-149">Gets or sets the name of a thread.</span></span> <span data-ttu-id="dbb42-150">디버깅할 때 개별 스레드를 찾는 가장 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-150">Most frequently used to discover individual threads when you debug.</span></span>|  
|<span data-ttu-id="dbb42-151"><xref:System.Threading.Thread.Priority%2A></xref:System.Threading.Thread.Priority%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-151"><xref:System.Threading.Thread.Priority%2A></span></span>|<span data-ttu-id="dbb42-152">스레드의 예약 우선 순위를 지정 하는 운영 체제에서 사용 되는 값을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-152">Gets or sets a value that is used by the operating system to prioritize thread scheduling.</span></span>|  
|<span data-ttu-id="dbb42-153"><xref:System.Threading.Thread.ThreadState%2A></xref:System.Threading.Thread.ThreadState%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-153"><xref:System.Threading.Thread.ThreadState%2A></span></span>|<span data-ttu-id="dbb42-154">스레드 상태 또는 상태를 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-154">Contains a value that describes a thread's state or states.</span></span>|  
  
## <a name="thread-priorities"></a><span data-ttu-id="dbb42-155">스레드 우선 순위</span><span class="sxs-lookup"><span data-stu-id="dbb42-155">Thread Priorities</span></span>  
 <span data-ttu-id="dbb42-156">모든 스레드는 실행 하는 프로세서 시간을 결정 하는 priority 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-156">Every thread has a priority property that determines how big or small a slice of processor time it has to execute.</span></span> <span data-ttu-id="dbb42-157">운영 체제에는 우선 순위가 높은 스레드 더 긴 시간 간격 및 우선 순위가 낮은 스레드 짧은 시간 조각 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-157">The operating system allocates longer time slices to high-priority threads and shorter time slices to low-priority threads.</span></span> <span data-ttu-id="dbb42-158">새 스레드 값을 사용 하 여 만들어집니다 `Normal`, 변경할 수 있지만 <xref:System.Threading.Thread.Priority%2A>속성의 값을는 <xref:System.Threading.ThreadPriority>열거형.</xref:System.Threading.ThreadPriority> </xref:System.Threading.Thread.Priority%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-158">New threads are created with the value of `Normal`, but you can change the <xref:System.Threading.Thread.Priority%2A> property to any value in the <xref:System.Threading.ThreadPriority> enumeration.</span></span>  
  
 <span data-ttu-id="dbb42-159">참조 <xref:System.Threading.ThreadPriority>에 대 한 자세한 설명은 다양 한 스레드 우선 순위.</xref:System.Threading.ThreadPriority></span><span class="sxs-lookup"><span data-stu-id="dbb42-159">See <xref:System.Threading.ThreadPriority> for a detailed description of the various thread priorities.</span></span>  
  
## <a name="foreground-and-background-threads"></a><span data-ttu-id="dbb42-160">포그라운드 및 백그라운드 스레드</span><span class="sxs-lookup"><span data-stu-id="dbb42-160">Foreground and Background Threads</span></span>  
 <span data-ttu-id="dbb42-161">A *포그라운드 스레드* 무기한 실행 되는 반면는 *백그라운드 스레드* 마지막 포그라운드 스레드가 중지 되는 즉시 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbb42-161">A *foreground thread* runs indefinitely, whereas a *background thread* stops as soon as the last foreground thread has stopped.</span></span> <span data-ttu-id="dbb42-162">사용할 수는 <xref:System.Threading.Thread.IsBackground%2A>속성을 확인 하거나 스레드 백그라운드 상태를 변경 합니다.</xref:System.Threading.Thread.IsBackground%2A></span><span class="sxs-lookup"><span data-stu-id="dbb42-162">You can use the <xref:System.Threading.Thread.IsBackground%2A> property to determine or change the background status of a thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb42-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbb42-163">See Also</span></span>  
 <span data-ttu-id="dbb42-164"><xref:System.Threading.Thread></xref:System.Threading.Thread></span><span class="sxs-lookup"><span data-stu-id="dbb42-164"><xref:System.Threading.Thread></span></span>   
<span data-ttu-id="dbb42-165"> [스레드 동기화 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="dbb42-165"> [Thread Synchronization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md) </span></span>  
<span data-ttu-id="dbb42-166"> [매개 변수 및 반환 값에 대 한 다중 스레드 프로시저 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="dbb42-166"> [Parameters and Return Values for Multithreaded Procedures (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md) </span></span>  
<span data-ttu-id="dbb42-167"> [스레딩 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)</span><span class="sxs-lookup"><span data-stu-id="dbb42-167"> [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)</span></span>
