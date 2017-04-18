---
title: "How to: Cancel a PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to cancel"
  - "cancellation, PLINQ"
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# How to: Cancel a PLINQ Query
다음 예제에서는 PLINQ 쿼리를 취소하는 두 가지 방법을 보여 줍니다.  첫 번째 예제에서는 대부분이 데이터 트래버스로 구성된 쿼리를 취소하는 방법을 보여 줍니다.  두 번째 예제에서는 많은 계산 과정이 필요한 사용자 함수가 들어 있는 쿼리를 취소하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  "내 코드만"을 사용하는 경우 Visual Studio에서는 예외를 throw하는 줄에서 실행을 중단하고 예외가 사용자 코드를 통해 처리되지 않았음을 알리는 오류 메시지를 표시할 수 있습니다. 이는 크게 심각한 오류는 아닙니다.  F5 키를 눌러 중단된 지점부터 실행을 계속하고 아래 예제에 나와 있는 것과 같은 예외 처리 동작을 확인할 수 있습니다.  맨 처음 오류 지점에서 Visual Studio가 실행을 중단하지 않도록 하려면 **도구, 옵션, 디버깅, 일반**을 차례로 선택하고 "내 코드만" 확인란의 선택을 취소하기만 하면 됩니다.  
>   
>  이 예제는 사용법을 보여 주기 위한 것이며, 이에 상응하는 순차 LINQ to Objects 쿼리보다 실행 속도가 느릴 수 있습니다.  속도 향상에 대한 자세한 내용은 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)를 참조하십시오.  
  
## 예제  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 PLINQ 프레임워크에서는 단일 <xref:System.OperationCanceledException>이 <xref:System.AggregateException?displayProperty=fullName>에 포함되지 않으므로 <xref:System.OperationCanceledException>은 별도의 catch 블록에서 처리해야 합니다.  하나 이상의 사용자 대리자에서 외부 <xref:System.Threading.CancellationToken?displayProperty=fullName>을 사용하여 OperationCanceledException\(externalCT\)을 throw하지만 다른 예외는 throw하지 않으며 쿼리가 `AsParallel().WithCancellation(externalCT)`으로 정의된 경우, PLINQ에서는 <xref:System.AggregateException?displayProperty=fullName>이 아닌 단일 <xref:System.OperationCanceledException>\(externalCT\)이 발생합니다.  그러나 한 사용자 대리자에서 <xref:System.OperationCanceledException>을 throw하고 다른 대리자에서 또 다른 예외 형식을 throw하는 경우에는 두 예외 모두 <xref:System.AggregateException>에 포함됩니다.  
  
 다음은 취소와 관련된 일반적인 지침입니다.  
  
1.  사용자 대리자 취소를 수행하는 경우 외부 <xref:System.Threading.CancellationToken>에 대한 정보를 PLINQ에 알리고 <xref:System.OperationCanceledException>\(externalCT\)을 throw해야 합니다.  
  
2.  취소가 발생했지만 다른 예외는 throw되지 않은 경우 <xref:System.AggregateException>이 아니라 <xref:System.OperationCanceledException>을 처리해야 합니다.  
  
## 예제  
 다음 예제에서는 사용자 코드에 많은 계산 과정이 필요한 함수가 있는 경우 취소를 처리하는 방법을 보여 줍니다.  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 사용자 코드에서 취소를 처리하는 경우에는 쿼리 정의에 <xref:System.Linq.ParallelEnumerable.WithCancellation%2A>을 사용할 필요가 없습니다.  그러나 <xref:System.Linq.ParallelEnumerable.WithCancellation%2A>은 쿼리 성능에 영향을 주지 않고 쿼리 연산자 및 사용자 코드에서 취소를 처리할 수 있게 해 주므로 이를 사용하는 것이 좋습니다.  
  
 시스템 응답성을 보장하기 위해 밀리초당 한 번씩 취소를 확인하는 것이 좋지만 최대 10밀리초까지 허용됩니다.  이 빈도는 코드의 성능에 부정적인 영향을 주지 않습니다.  
  
 코드가 쿼리 결과를 반복하는 foreach\(Visual Basic에서는 For Each\) 루프를 벗어나는 경우와 같이 열거자가 삭제될 경우 쿼리가 취소되지는 하지만 예외는 throw되지 않습니다.  
  
## 참고 항목  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)