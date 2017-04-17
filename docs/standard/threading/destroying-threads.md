---
title: "Destroying Threads | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "destroying threads"
  - "threading [.NET Framework], destroying threads"
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Destroying Threads
<xref:System.Threading.Thread.Abort%2A> 메서드는 관리되는 스레드를 영구적으로 중지하는 데 사용됩니다.  <xref:System.Threading.Thread.Abort%2A>를 호출하면 공용 언어 런타임에서 대상 스레드가 catch할 수 있는 <xref:System.Threading.ThreadAbortException>을 throw합니다.  자세한 내용은 <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>을 참조하십시오.  
  
> [!NOTE]
>  스레드에서 해당 <xref:System.Threading.Thread.Abort%2A> 메서드가 호출될 때 비관리 코드를 실행하는 경우 런타임에서 해당 코드를 <xref:System.Threading.ThreadState?displayProperty=fullName>로 만듭니다.  스레드가 관리 코드로 되돌아가면 예외가 throw됩니다.  
  
 일단 스레드가 중단되면 다시 시작할 수 없습니다.  
  
 <xref:System.Threading.Thread.Abort%2A> 메서드로 인해 스레드가 즉시 중단되지는 않습니다. 대상 스레드가 <xref:System.Threading.ThreadAbortException>을 catch하고 `finally` 블록에서 임의의 코드 크기를 실행할 수 있기 때문입니다.  스레드가 끝날 때까지 기다려야 하는 경우 <xref:System.Threading.Thread.Join%2A?displayProperty=fullName>을 호출할 수 있습니다.  <xref:System.Threading.Thread.Join%2A?displayProperty=fullName>은 스레드 실행이 실제로 중단되거나 선택적 제한 시간 간격이 경과될 때까지 반환되지 않는 차단 호출입니다.  중단된 스레드는 <xref:System.Threading.Thread.ResetAbort%2A> 메서드를 호출하거나 `finally` 블록에서 바인딩되지 않은 처리를 수행할 수 있으므로 제한 시간을 지정하지 않으면 해당 대기가 끝나지 않을 수 있습니다.  
  
 <xref:System.Threading.Thread.Join%2A?displayProperty=fullName> 메서드에 대한 호출을 기다리는 스레드는 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>를 호출하는 다른 스레드에 의해 중단될 수 있습니다.  
  
## ThreadAbortException 처리  
 사용자 코드에서 <xref:System.Threading.Thread.Abort%2A>를 호출하거나 스레드가 실행 중인 응용 프로그램 도메인을 언로드하여 스레드가 중단될 수 있는 경우\(<xref:System.AppDomain.Unload%2A?displayProperty=fullName>가 <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>를 사용하여 스레드 종료\) 해당 스레드는 다음 코드와 같이 <xref:System.Threading.ThreadAbortException>을 처리하고 `finally` 절에서 마지막 처리를 수행해야 합니다.  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.   
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception   
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try   
{  
    // Code that is executing when the thread is aborted.  
}   
catch (ThreadAbortException ex)   
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.   
}  
// Do not put clean-up code here, because the exception   
// is rethrown at the end of the Finally clause.  
```  
  
 `finally` 절의 끝에서 또는 `finally` 절이 없는 경우 `catch` 절의 끝에서 시스템에서 <xref:System.Threading.ThreadAbortException>이 다시 throw되므로 정리 코드는 `catch` 절 또는 `finally` 절에 있어야 합니다.  
  
 <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=fullName> 메서드를 사용하면 시스템에서 예외를 다시 throw하지 않도록 할 수 있습니다.  그러나 이 방법은 사용자 코드에서 <xref:System.Threading.ThreadAbortException>이 발생한 경우에만 사용해야 합니다.  
  
## 참고 항목  
 <xref:System.Threading.ThreadAbortException>   
 <xref:System.Threading.Thread>   
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)