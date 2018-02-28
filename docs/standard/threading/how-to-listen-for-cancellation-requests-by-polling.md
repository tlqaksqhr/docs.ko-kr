---
title: "방법: 폴링을 통해 취소 요청 수신 대기"
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
- cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 56a927e10cb026814302728a72acb2f32223b29b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a>방법: 폴링을 통해 취소 요청 수신 대기
다음 예제는 사용자 코드가 정기적으로 취소 토큰을 폴링하여 호출 스레드에서 취소가 요청되었는지 여부를 확인하는 방법을 보여줍니다. 이 예제에서는 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 유형을 사용하지만, 동일한 패턴이 <xref:System.Threading.ThreadPool?displayProperty=nameWithType> 유형 또는 <xref:System.Threading.Thread?displayProperty=nameWithType> 유형으로 직접 생성된 비동기 작업에 적용됩니다.  
  
## <a name="example"></a>예  
 폴링에는 부울 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성의 값을 정기적으로 읽을 수 있는 특정한 종류의 루프 또는 순환 코드가 필요합니다. <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 유형을 사용 중이고 작업이 호출 스레드에서 완료될 때까지 대기 중인 경우 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> 메서드를 사용하여 속성을 확인하고 예외를 throw할 수 있습니다. 이 메서드를 사용하여 요청에 대한 응답으로 올바른 예외가 throw되도록 합니다. <xref:System.Threading.Tasks.Task>를 사용하는 경우 이 메서드를 호출하는 것이 <xref:System.OperationCanceledException>를 수동으로 throw하는 것보다 좋습니다. 예외를 throw할 필요가 없는 경우 속성을 확인하고 속성이 `true`인 경우 메서드에서 반환할 수 있습니다.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> 호출은 매우 빠르며 루프에서 오버헤드를 그다지 유발하지 않습니다.  
  
 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>를 호출하는 경우 예외를 throw하는 것 외에 취소에 대한 응답으로 수행해야 할 다른 작업이 있는 경우에만 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성을 명시적으로 확인해야 합니다. 이 예제에서는 코드가 실제로 속성에 두 번 액세스하는 것을 볼 수 있습니다. 명시적으로 한 번 액세스하고 <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> 메서드에서 다시 액세스할 수 있습니다. 그러나 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성을 읽는 작업에는 액세스당 하나의 volatile 읽기 명령만 포함되므로 성능상의 관점에서는 두 번의 액세스가 중요하지 않습니다. <xref:System.OperationCanceledException>을 수동으로 throw하는 것보다 메서드를 호출하는 것이 여전히 더 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리되는 스레드의 취소](../../../docs/standard/threading/cancellation-in-managed-threads.md)
