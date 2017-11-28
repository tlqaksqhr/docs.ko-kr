---
title: "스레드 타이머(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 52ed71e8-4fd9-43a4-ae40-04cce7cff23f
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9702360408340b28fcdcc8f197467a002f77ee51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="thread-timers-c"></a><span data-ttu-id="3c16e-102">스레드 타이머(C#)</span><span class="sxs-lookup"><span data-stu-id="3c16e-102">Thread Timers (C#)</span></span>
<span data-ttu-id="3c16e-103"><xref:System.Threading.Timer?displayProperty=nameWithType> 클래스는 별도 스레드에서 정기적으로 작업을 실행하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c16e-103">The <xref:System.Threading.Timer?displayProperty=nameWithType> class is useful for periodically running a task on a separate thread.</span></span> <span data-ttu-id="3c16e-104">예를 들어 스레드 타이머를 사용하여 데이터베이스의 상태 및 무결성을 확인하거나 중요한 파일을 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c16e-104">For example, you could use a thread timer to check the status and integrity of a database or to back up critical files.</span></span>  
  
## <a name="thread-timer-example"></a><span data-ttu-id="3c16e-105">스레드 타이머 예제</span><span class="sxs-lookup"><span data-stu-id="3c16e-105">Thread Timer Example</span></span>  
 <span data-ttu-id="3c16e-106">다음 예제에서는 2초마다 작업을 시작하고 플래그를 사용하여 타이머를 중지하는 <xref:System.IDisposable.Dispose%2A> 메서드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3c16e-106">The following example starts a task every two seconds and uses a flag to initiate the <xref:System.IDisposable.Dispose%2A> method that stops the timer.</span></span> <span data-ttu-id="3c16e-107">이 예제에서는 출력 창에 상태를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3c16e-107">This example posts status to the output window.</span></span>  
  
```csharp  
private class StateObjClass  
{  
    // Used to hold parameters for calls to TimerTask.  
    public int SomeValue;  
    public System.Threading.Timer TimerReference;  
    public bool TimerCanceled;  
}  
  
public void RunTimer()  
{  
    StateObjClass StateObj = new StateObjClass();  
    StateObj.TimerCanceled = false;  
    StateObj.SomeValue = 1;  
    System.Threading.TimerCallback TimerDelegate =  
        new System.Threading.TimerCallback(TimerTask);  
  
    // Create a timer that calls a procedure every 2 seconds.  
    // Note: There is no Start method; the timer starts running as soon as   
    // the instance is created.  
    System.Threading.Timer TimerItem =  
        new System.Threading.Timer(TimerDelegate, StateObj, 2000, 2000);  
  
    // Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem;    
  
    // Run for ten loops.  
    while (StateObj.SomeValue < 10)   
    {  
        // Wait one second.  
        System.Threading.Thread.Sleep(1000);    
    }  
  
    // Request Dispose of the timer object.  
    StateObj.TimerCanceled = true;    
}  
  
private void TimerTask(object StateObj)  
{  
    StateObjClass State = (StateObjClass)StateObj;  
    // Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(ref State.SomeValue);  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " + DateTime.Now.ToString());  
    if (State.TimerCanceled)      
    // Dispose Requested.  
    {  
        State.TimerReference.Dispose();  
        System.Diagnostics.Debug.WriteLine("Done  " + DateTime.Now.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="3c16e-108">스레드 타이머는 콘솔 응용 프로그램을 개발하는 경우 등 <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> 개체를 사용할 수 없는 경우에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c16e-108">Thread timers are particularly useful when the <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> object is unavailable, such as when you are developing console applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c16e-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c16e-109">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="3c16e-110">다중 스레드 응용 프로그램(C#)</span><span class="sxs-lookup"><span data-stu-id="3c16e-110">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)
