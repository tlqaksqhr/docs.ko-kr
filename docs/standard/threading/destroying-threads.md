---
title: "스레드 제거"
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
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a41dce5db707d0be49c283256de665d316e1a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="destroying-threads"></a>스레드 제거
<xref:System.Threading.Thread.Abort%2A> 메서드 영구적으로 관리 되는 스레드를 중지 하는 데 사용 됩니다. 호출 하는 경우 <xref:System.Threading.Thread.Abort%2A>, 공용 언어 런타임에서 <xref:System.Threading.ThreadAbortException> 대상 스레드가 catch 할 수 있는 대상 스레드에서 합니다. 자세한 내용은 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>을 참조하십시오.  
  
> [!NOTE]
>  스레드가 실행 되는 경우 관리 되지 않는 때 코드는 <xref:System.Threading.Thread.Abort%2A> 메서드가 호출 되 면 런타임에서 <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>합니다. 스레드가 관리 코드에 반환 될 때 예외가 throw 됩니다.  
  
 스레드가 중단 되 면 다시 시작할 수 없습니다.  
  
 <xref:System.Threading.Thread.Abort%2A> 메서드에서 대상 스레드가 catch 할 수 있으므로 즉시 중단 하는 스레드에서 발생 하지 않습니다는 <xref:System.Threading.ThreadAbortException> 임의의 양의에 코드를 실행 하 고는 `finally` 블록입니다. 호출할 수 있습니다 <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> 스레드가 종료 될 때까지 대기 하는 경우. <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>스레드 실행이 실제로 중단 될 때까지 반환 하지 않는 차단 호출 되었거나 선택적 시간 제한 간격이 경과 합니다. 중단 된 스레드를 호출할 수는 <xref:System.Threading.Thread.ResetAbort%2A> 메서드에 제한 없이 처리를 수행 하거나는 `finally` 블록에 있으므로 대기 제한 시간을 지정 하지 않으면 경우 종료를 보장 되지 않습니다.  
  
 에 대 한 호출에서 대기 중인 스레드는 <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> 메서드를 호출 하는 다른 스레드에 의해 중단 될 수 있습니다 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>합니다.  
  
## <a name="handling-threadabortexception"></a>ThreadAbortException 처리  
 스레드 중단 될 호출의 결과로 것으로 예상한 경우 <xref:System.Threading.Thread.Abort%2A> 스레드가 실행 중인 응용 프로그램 도메인을 언로드하여 또는 사용자 고유의 코드에서 (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> 사용 하 여 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 스레드를 종료 하기), 스레드를 처리 해야 합니다 <xref:System.Threading.ThreadAbortException> 에서 최종 처리를 수행 하 고는 `finally` 절, 다음 코드에 나와 있는 것 처럼 합니다.  
  
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
  
 정리 코드 내에 있어야는 `catch` 절 또는 `finally` 절 때문에 <xref:System.Threading.ThreadAbortException> 시스템의 끝에 의해 다시 throw 됩니다는 `finally` 절 또는 끝날 때는 `catch` 절 없는 경우 없는 `finally` 절.  
  
 호출 하 여 예외를 다시 throw에서 시스템을 방지할 수 있습니다는 <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> 메서드. 하지만 경우에만이 발생 하는 사용자 고유의 코드 수행 해야는 <xref:System.Threading.ThreadAbortException>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [스레드 및 스레딩 사용](../../../docs/standard/threading/using-threads-and-threading.md)
