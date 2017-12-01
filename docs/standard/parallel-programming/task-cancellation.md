---
title: "작업 취소"
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
- tasks, cancellation
- asynchronous task cancellation
ms.assetid: 3ecf1ea9-e399-4a6a-a0d6-8475f48dcb28
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 106c89ca9fcfb8bbab23b982cdc524ff78d21d15
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="task-cancellation"></a>작업 취소
<xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> 클래스는 .NET Framework에서 취소 토큰을 사용하는 방법으로 취소 기능을 지원합니다. 자세한 내용은 참조 [관리 되는 스레드의 취소](../../../docs/standard/threading/cancellation-in-managed-threads.md)합니다. 작업 클래스에서 취소하려면 취소할 수 있는 작업을 나타내는 사용자 대리자와 취소를 요청한 코드 간의 협조가 필요합니다.  성공적으로 취소 하려면 호출 하는 요청 코드는 <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> 메서드와 적절 한 시간 내에 작업을 종료 하는 사용자 대리자입니다. 다음 방법 중 하나를 사용하여 작업을 종료할 수 있습니다.  
  
-   단순히 대리자에서 반환합니다. 대부분의 경우에는 이 방법으로 충분하지만 이 방법으로 취소된 작업 인스턴스는 <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType> 상태가 아니라 <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> 상태로 전환됩니다.  
  
-   <xref:System.OperationCanceledException> 을 throw하고 취소가 요청된 토큰을 전달합니다. 이렇게 하려면 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> 메서드를 사용하는 것이 좋습니다. 이 방법으로 취소된 작업은 Canceled 상태로 전환되므로 호출 코드에서는 이 상태를 통해 작업이 취소 요청에 응답했음을 확인할 수 있습니다.  
  
 다음 예제에서는 예외를 throw하는 작업 취소의 기본적인 패턴을 보여 줍니다. 토큰은 사용자 대리자와 작업 인스턴스 자체에 전달됩니다.  
  
 [!code-csharp[TPL_Cancellation#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/snippet02.cs#02)]
 [!code-vb[TPL_Cancellation#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/module1.vb#02)]  
  
 자세한 예제를 참조 하십시오. [하는 방법: 작업 및 해당 자식 취소](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)합니다.  
  
 작업 인스턴스는 사용자 코드에서 throw된 <xref:System.OperationCanceledException> 이 관찰될 경우 예외의 토큰을 관련 토큰, 즉 해당 작업을 만든 API에 전달된 토큰과 비교합니다. 두 토큰이 동일하고 토큰의 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성이 true를 반환하면 해당 작업은 이를 취소 승인으로 해석하고 Canceled 상태로 전환됩니다. <xref:System.Threading.Tasks.Task.Wait%2A> 또는 <xref:System.Threading.Tasks.Task.WaitAll%2A> 메서드를 사용하여 작업이 완료될 때까지 대기하지 않는 경우 해당 작업은 단순히 상태를 <xref:System.Threading.Tasks.TaskStatus.Canceled>로 설정합니다.  
  
 Canceled 상태로 전환 되는 작업에서 대기 중인 경우에 <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> 예외 (에 래핑되는 <xref:System.AggregateException> 예외)이 throw 됩니다. 이 예외는 오류가 아니라 성공적인 취소를 나타냅니다. 따라서 작업의 <xref:System.Threading.Tasks.Task.Exception%2A> 속성은 `null`을 반환합니다.  
  
 토큰의 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성이 false를 반환하거나 예외의 토큰이 작업의 토큰과 일치하지 않는 경우 <xref:System.OperationCanceledException> 은 일반적인 예외처럼 처리되므로 작업이 Faulted 상태로 전환됩니다. 또한 다른 예외가 있는 경우에도 작업이 Faulted 상태로 전환됩니다. 완료된 작업의 상태는 <xref:System.Threading.Tasks.Task.Status%2A> 속성에서 가져올 수 있습니다.  
  
 취소를 요청한 후에도 작업에서 일부 항목의 처리를 계속 진행할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리되는 스레드의 취소](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 [방법: 작업 및 해당 자식 취소](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)
