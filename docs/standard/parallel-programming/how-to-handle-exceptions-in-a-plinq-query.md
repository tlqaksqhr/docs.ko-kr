---
title: "방법: PLINQ 쿼리의 예외 처리"
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
helpviewer_keywords: PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 209e0c1bf89f231d03647ae4351279bfdb172e68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a>방법: PLINQ 쿼리의 예외 처리
이 항목의 첫 번째 예제에서는 처리 하는 방법을 보여 줍니다.는 <xref:System.AggregateException?displayProperty=nameWithType> 실행 될 때 PLINQ 쿼리에서 발생할 수 있는 합니다. 두 번째 예에서는 try / catch 블록을 대리자에서 예외가 throw 될에 최대한 가깝게 배치 하는 방법을 보여 줍니다. 이러한 방식으로 catch 할 수 있습니다 하는 즉시 발생 하며 쿼리 실행을 계속 사용할 합니다. 예외가 가입된 스레드로 다시 버블 업될 수 있는 경우 예외가 발생한 후에도 쿼리에서 일부 항목을 계속 처리할 수 있습니다.  
  
 일부 경우에 plinq가 순차적 실행 하 고 예외가 발생할 때 예외 및 될 수를 직접 전파에 래핑되지는 <xref:System.AggregateException>합니다. 또한 <xref:System.Threading.ThreadAbortException>s은 항상 직접 전파 합니다.  
  
> [!NOTE]
>  "내 코드만"을 사용 하는 경우 Visual Studio는 예외를 발생 시키는 줄에서 중단 하 고 "예외가 처리 되지 않았다 사용자 코드에 의해." 오류 메시지가 표시 이 오류는 심각하지는 않습니다. F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다. Visual Studio에서 첫 번째 오류에서 분리를 방지 하려면의 선택을 취소 하기만 하 고 "내 코드만" 확인란의 **도구, 옵션, 디버깅, 일반**합니다.  
>   
>  이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다. 속도 대 한 자세한 내용은 참조 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)합니다.  
  
## <a name="example"></a>예제  
 Try / catch 블록 안에 catch 하도록 쿼리를 실행 하는 코드를 활용 하는 방법을 보여 주는이 예제 <xref:System.AggregateException?displayProperty=nameWithType>throw 되는 s입니다.  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 이 예에서 쿼리는 예외가 throw 된 후 계속할 수 없습니다. PLINQ는 응용 프로그램 코드가 예외를 catch 하는 시점 모든 스레드에 대해 쿼리를 이미 중지 되었습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 예외를 catch 하 고 쿼리 실행을 계속할 수 있게 되 면 대리자에서 try / catch 블록을 삽입 하는 방법을 보여 줍니다.  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   컴파일 이러한 예제, PLINQ 데이터 샘플 예제에 복사 하 고 실행에서 Main 메서드를 호출 합니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 프로그램의 상태가 손상 되지 않도록을 처리 하는 방법을 모르는 경우에 예외를 catch 하지 마십시오.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq.ParallelEnumerable>  
 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
