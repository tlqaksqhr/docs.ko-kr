---
title: "스레드 타이머(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 52ed71e8-4fd9-43a4-ae40-04cce7cff23f
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 30037b5b6d798796e7f76fa045f882b7f335e0d7
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="thread-timers-c"></a><span data-ttu-id="75987-102">스레드 타이머(C#)</span><span class="sxs-lookup"><span data-stu-id="75987-102">Thread Timers (C#)</span></span>
<span data-ttu-id="75987-103"><xref:System.Threading.Timer?displayProperty=fullName> 클래스는 별도 스레드에서 정기적으로 작업을 실행하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="75987-103">The <xref:System.Threading.Timer?displayProperty=fullName> class is useful for periodically running a task on a separate thread.</span></span> <span data-ttu-id="75987-104">예를 들어 스레드 타이머를 사용하여 데이터베이스의 상태 및 무결성을 확인하거나 중요한 파일을 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75987-104">For example, you could use a thread timer to check the status and integrity of a database or to back up critical files.</span></span>  
  
## <a name="thread-timer-example"></a><span data-ttu-id="75987-105">스레드 타이머 예제</span><span class="sxs-lookup"><span data-stu-id="75987-105">Thread Timer Example</span></span>  
 <span data-ttu-id="75987-106">다음 예제에서는 2초마다 작업을 시작하고 플래그를 사용하여 타이머를 중지하는 <xref:System.IDisposable.Dispose%2A> 메서드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="75987-106">The following example starts a task every two seconds and uses a flag to initiate the <xref:System.IDisposable.Dispose%2A> method that stops the timer.</span></span> <span data-ttu-id="75987-107">이 예제에서는 출력 창에 상태를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="75987-107">This example posts status to the output window.</span></span>  
  
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
  
 <span data-ttu-id="75987-108">스레드 타이머는 콘솔 응용 프로그램을 개발하는 경우 등 <xref:System.Windows.Forms.Timer?displayProperty=fullName> 개체를 사용할 수 없는 경우에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="75987-108">Thread timers are particularly useful when the <xref:System.Windows.Forms.Timer?displayProperty=fullName> object is unavailable, such as when you are developing console applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75987-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75987-109">See Also</span></span>  
 <span data-ttu-id="75987-110"><xref:System.Threading></span><span class="sxs-lookup"><span data-stu-id="75987-110"><xref:System.Threading></span></span>   
 [<span data-ttu-id="75987-111">다중 스레드 응용 프로그램(C#)</span><span class="sxs-lookup"><span data-stu-id="75987-111">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)

