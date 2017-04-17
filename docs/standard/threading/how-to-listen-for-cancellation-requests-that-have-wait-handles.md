---
title: "How to: Listen for Cancellation Requests That Have Wait Handles | Microsoft Docs"
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
  - "cancellation, waiting with wait handles"
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Listen for Cancellation Requests That Have Wait Handles
메서드가 신호를 받을 이벤트를 기다리는 중에 차단될 경우 해당 메시지는 컬렉션 토큰의 값을 확인하지 못하기 때문에 적시에 응답할 수 없습니다.  첫 번째 예제에서는 기본적으로 통합 취소 프레임워크를 지원하지 않는 <xref:System.Threading.ManualResetEvent?displayProperty=fullName> 같은 이벤트를 사용하여 작업할 때 이 문제를 해결하는 방법을 보여 줍니다.  두 번째 예제에서는 통합 취소를 지원하지 않는 <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>을 사용하는 더 효율적인 방법을 보여 줍니다.  
  
> [!NOTE]
>  "내 코드만"을 사용하는 경우 Visual Studio에서는 예외를 throw하는 줄에서 실행을 중단하고 예외가 사용자 코드를 통해 처리되지 않았음을 알리는 오류 메시지를 표시할 수 있습니다. 이는 크게 심각한 오류는 아닙니다.  F5 키를 눌러 중단된 지점부터 실행을 계속하고 아래 예제에 나와 있는 것과 같은 예외 처리 동작을 확인할 수 있습니다.  맨 처음 오류 지점에서 Visual Studio가 실행을 중단하지 않도록 하려면 **도구, 옵션, 디버깅, 일반**을 차례로 선택하고 "내 코드만" 확인란의 선택을 취소하기만 하면 됩니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Threading.ManualResetEvent>를 사용하여 통합 취소를 지원하지 않는 대기 핸들의 차단을 해제하는 방법을 보여 줍니다.  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## 예제  
 다음 예제에서는 <xref:System.Threading.ManualResetEventSlim>을 사용하여 통합 취소를 지원하지 않는 코디네이션 기본 형식의 차단을 해제하는 방법을 보여 줍니다.  이 방법은 <xref:System.Threading.Semaphore>`Slim` 및 <xref:System.Threading.CountdownEvent> 같은 다른 간단한 코디네이션 기본 형식에도 사용할 수 있습니다.  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## 참고 항목  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)