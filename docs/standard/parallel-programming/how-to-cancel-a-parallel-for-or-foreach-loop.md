---
title: "방법: Parallel.For 또는 ForEach 루프 취소"
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
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f82c5758e02b4beebf035fe8f43f856447855a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a>방법: Parallel.For 또는 ForEach 루프 취소
<xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 메서드는 취소 토큰을 사용 하 여 취소를 지원 합니다. 취소에 대 한 자세한 내용은 참조 일반적으로 [취소](../../../docs/standard/threading/cancellation-in-managed-threads.md)합니다. 병렬 루프에서 제공 하는 <xref:System.Threading.CancellationToken> 메서드에 <xref:System.Threading.Tasks.ParallelOptions> 매개 변수 다음 try catch 블록의 병렬에 호출을 포함 하 고 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에 대 한 호출을 취소 하는 방법을 보여 줍니다 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>합니다. 에 동일한 방법을 적용할 수는 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> 호출 합니다.  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 취소를 알리는 토큰이 동일한 경우 토큰에 지정 된 된 <xref:System.Threading.Tasks.ParallelOptions> 병렬 루프를 발생 시킵니다 단일 인스턴스인 <xref:System.OperationCanceledException> 취소 합니다. 다른 토큰 인해 취소 되는 경우 루프에서 throw는 <xref:System.AggregateException> 와 <xref:System.OperationCanceledException> 는 InnerException으로 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 병렬 처리](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [PLINQ 및 TPL의 람다 식](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
