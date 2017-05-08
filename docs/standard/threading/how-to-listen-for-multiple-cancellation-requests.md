---
title: "How to: Listen for Multiple Cancellation Requests | Microsoft Docs"
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
  - "cancellation tokens, joining"
  - "LinkedTokenSource, how to"
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Listen for Multiple Cancellation Requests
이 예제에서는 둘 중 한 토큰의 요청이 있을 경우 작업을 취소할 수 있도록 두 개의 취소 토큰을 동시에 수신하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  "내 코드만"을 사용하는 경우 Visual Studio에서는 예외를 throw하는 줄에서 실행을 중단하고 예외가 사용자 코드를 통해 처리되지 않았음을 알리는 오류 메시지를 표시할 수 있습니다. 이는 크게 심각한 오류는 아닙니다.  F5 키를 눌러 중단된 지점부터 실행을 계속하고 아래 예제에 나와 있는 것과 같은 예외 처리 동작을 확인할 수 있습니다.  맨 처음 오류 지점에서 Visual Studio가 실행을 중단하지 않도록 하려면 **도구, 옵션, 디버깅, 일반**을 차례로 선택하고 "내 코드만" 확인란의 선택을 취소하기만 하면 됩니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> 메서드를 사용하여 두 개의 토큰을 하나의 토큰으로 조인합니다.  이렇게 하면 하나의 취소 토큰만 인수로 사용하는 메서드에 토큰을 전달할 수 있습니다.  이 예제에서는 메서드가 클래스 밖에서 전달된 토큰과 클래스 안에서 생성된 토큰을 둘 다 관찰하는 일반적인 시나리오를 보여 줍니다.  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 연결된 토큰이 <xref:System.OperationCanceledException>을 throw하면 선행 작업 토큰이 아닌 연결된 토큰이 예외에 전달됩니다.  취소된 토큰을 확인하려면 선행 작업 토큰의 상태를 직접 확인합니다.  
  
 이 예제에서 <xref:System.AggregateException>은 전혀 throw되지 않지만 여기서는 이 예외를 catch합니다. 실제 상황에서는 <xref:System.OperationCanceledException> 외에 작업 대리자에서 throw되는 다른 모든 예외가 <xref:System.OperationCanceledException>에 래핑되기 때문입니다.  
  
## 참고 항목  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)