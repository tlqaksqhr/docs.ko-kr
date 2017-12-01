---
title: "방법: PLINQ 쿼리 취소"
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
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8031758462df45c030b8b75a3507f1bfb44bfd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-plinq-query"></a>방법: PLINQ 쿼리 취소
다음 예에서는 두 가지 방법으로 PLINQ 쿼리 취소를 보여 줍니다. 첫 번째 예에는 데이터 탐색 대부분의 구성 된 쿼리를 취소 하는 방법을 보여 줍니다. 두 번째 예에는 많은 계산이 요구 하는 사용자 함수를 포함 하는 쿼리를 취소 하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  "내 코드만"을 사용 하는 경우 Visual Studio는 예외를 발생 시키는 줄에서 중단 하 고 "예외가 처리 되지 않았다 사용자 코드에 의해." 오류 메시지가 표시 이 오류는 심각하지는 않습니다. F5 키를 눌러 계속하고 아래 예제에 설명된 예외 처리 동작을 확인할 수 있습니다. Visual Studio에서 첫 번째 오류에서 분리를 방지 하려면의 선택을 취소 하기만 하 고 "내 코드만" 확인란의 **도구, 옵션, 디버깅, 일반**합니다.  
>   
>  이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다. 속도 대 한 자세한 내용은 참조 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 PLINQ 프레임 워크는 단일 롤백하지 않습니다 <xref:System.OperationCanceledException> 에 <xref:System.AggregateException?displayProperty=nameWithType>; <xref:System.OperationCanceledException> 별도 catch 블록에서 처리 되어야 합니다. 하나 이상의 사용자 대리자는 OperationCanceledException(externalCT) throw 하는 경우 (외부를 사용 하 여 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>)로 정의 된 다른 예외가 없습니다 및 쿼리 `AsParallel().WithCancellation(externalCT)`, PLINQ에서 발생 한 단일 한 다음 <xref:System.OperationCanceledException> (externalCT) 아닌 <xref:System.AggregateException?displayProperty=nameWithType>. 한 명의 사용자를 위임 하는 경우 throw 되는 반면는 <xref:System.OperationCanceledException>, 다른 대리자에 또 다른 예외 형식을 throw 하 고 다음 두 예외에 통합 되는 <xref:System.AggregateException>합니다.  
  
 취소에 대 한 일반 지침은 다음과 같습니다.  
  
1.  사용자 대리자에 취소를 수행 하는 경우 PLINQ 외부에 대 한 알려야 <xref:System.Threading.CancellationToken> throw 한 <xref:System.OperationCanceledException>(externalCT).  
  
2.  취소 발생 다른 예외가 throw 되지 않을 경우 처리 해야 합니다는 <xref:System.OperationCanceledException> 아닌 <xref:System.AggregateException>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 계산이 함수 사용자 코드에 있는 경우 취소를 처리 하는 방법을 보여 줍니다.  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 사용자 코드에서 취소를 처리 하는 경우 사용할 필요가 없습니다 <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> 쿼리 정의에 있습니다. 그러나 이렇게 하기 때문에 권장 म <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> 쿼리 성능에 영향을 주지 및 취소 쿼리 연산자 및 사용자 코드에서 처리할 수 있습니다.  
  
 시스템 응답성을 보장 하기 위해; 밀리초 당 한 번씩 취소를 확인 하 권장 그러나 10 밀리초까지 모든 기간이 허용 간주 됩니다. 코드의 성능에 부정적인 영향을 없어야이 주파수 합니다.  
  
 열거자가 삭제 예를 들어 코드 중단 시 (각각에 대해 Visual basic에서) foreach 루프에서 반복 하는 쿼리 결과 외부로 다음 쿼리를 취소 하지만 예외가 throw 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq.ParallelEnumerable>  
 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [관리되는 스레드의 취소](../../../docs/standard/threading/cancellation-in-managed-threads.md)
