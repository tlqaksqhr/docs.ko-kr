---
title: "방법: PLINQ에서 병합 옵션 지정"
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
helpviewer_keywords: PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ec601e8bbefd31650fb91c438b032942cfc93101
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a>방법: PLINQ에서 병합 옵션 지정
이 예제에는 모든 후속 PLINQ 쿼리 연산자에 적용 되는 병합 옵션을 지정 하는 방법을 보여 줍니다. 병합 옵션을 명시적으로 설정할 필요는 없지만 성능이 향상 될 수 있습니다. 병합 옵션에 대 한 자세한 내용은 참조 [PLINQ의 병합 옵션](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)합니다.  
  
> [!WARNING]
>  이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다. 속도 대 한 자세한 내용은 참조 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에 순서가 지정 되지 않은 원본 및 모든 요소는 비용이 많이 드는 함수를 적용 하는 기본 시나리오에서 병합 옵션의 동작입니다.  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 경우에서 위치는 <xref:System.Linq.ParallelMergeOptions.AutoBuffered> 옵션 원하지 않는 지연이 그로 인해 첫 번째 요소에서을 생성 하기 전에, 시도 <xref:System.Linq.ParallelMergeOptions.NotBuffered> 빠르고 자연스럽 게 결과 요소를 생성 하는 옵션입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq.ParallelMergeOptions>  
 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
