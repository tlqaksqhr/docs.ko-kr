---
title: "How to: Handle Exceptions in a PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to handle exceptions"
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# How to: Handle Exceptions in a PLINQ Query
이 항목의 첫 번째 예제에서는 PLINQ 쿼리를 실행할 때 이 쿼리에서 throw될 수 있는 <xref:System.AggregateException?displayProperty=fullName>을 처리하는 방법을 보여 줍니다.  두 번째 예제에서는 대리자 내에서 예외가 throw되는 지점과 가능한 한 가까운 지점에 try\-catch 블록을 배치하는 방법을 보여 줍니다.  이렇게 하면 예외가 발생하는 즉시 이를 catch하고 쿼리 실행을 계속할 수 있습니다.  조인하는 스레드까지 버블링할 수 있도록 예외가 허용되는 경우 예외가 발생한 후에도 쿼리에서 일부 항목을 계속하여 처리할 수 있습니다.  
  
 경우에 따라서는 PLINQ가 순차 실행을 진행하는 동안 예외가 발생했을 때 예외를 <xref:System.AggregateException>에 래핑하지 않고 직접 전파할 수 있습니다.  또한 <xref:System.Threading.ThreadAbortException>은 항상 직접 전파됩니다.  
  
> [!NOTE]
>  "내 코드만"을 사용하는 경우 Visual Studio에서는 예외를 throw하는 줄에서 실행을 중단하고 예외가 사용자 코드를 통해 처리되지 않았음을 알리는 오류 메시지를 표시할 수 있습니다. 이는 크게 심각한 오류는 아닙니다.  F5 키를 눌러 중단된 지점부터 실행을 계속하고 아래 예제에 나와 있는 것과 같은 예외 처리 동작을 확인할 수 있습니다.  맨 처음 오류 지점에서 Visual Studio가 실행을 중단하지 않도록 하려면 **도구, 옵션, 디버깅, 일반**을 차례로 선택하고 "내 코드만" 확인란의 선택을 취소하기만 하면 됩니다.  
>   
>  이 예제는 사용법을 보여 주기 위한 것이며, 이에 상응하는 순차 LINQ to Objects 쿼리보다 실행 속도가 느릴 수 있습니다.  속도 향상에 대한 자세한 내용은 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)를 참조하십시오.  
  
## 예제  
 이 예제에서는 쿼리를 실행하는 코드에 try\-catch 블록을 배치하여 throw되는 <xref:System.AggregateException?displayProperty=fullName>을 catch하는 방법을 보여 줍니다.  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 이 예제에서는 예외가 throw된 후 쿼리를 계속할 수 없습니다.  응용 프로그램 코드에서 예외를 catch할 때 PLINQ가 이미 모든 스레드에서 쿼리를 중지했기 때문입니다.  
  
## 예제  
 다음 예제에서는 대리자에 try\-catch 블록을 배치하여 예외를 catch하고 쿼리 실행을 계속할 수 있도록 하는 방법을 보여 줍니다.  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## 코드 컴파일  
  
-   이러한 예제를 컴파일하고 실행하려면 해당 예제를 PLINQ 데이터 샘플 예제에 복사하고 Main에서 해당 메서드를 호출합니다.  
  
## 강력한 프로그래밍  
 프로그램 상태가 손상되지 않도록 예외를 처리하는 방법을 모르는 경우에는 예외를 catch하지 않습니다.  
  
## 참고 항목  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)