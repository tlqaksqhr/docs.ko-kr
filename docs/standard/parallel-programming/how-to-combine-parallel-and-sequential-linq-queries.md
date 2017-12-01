---
title: "방법: 병렬 및 순차적 LINQ 쿼리 결합"
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
helpviewer_keywords: parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4da91ff535059b181baa637164a854cd75d06334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a>방법: 병렬 및 순차적 LINQ 쿼리 결합
사용 하는 방법을 보여 주는이 예제는 <xref:System.Linq.ParallelEnumerable.AsSequential%2A> 메서드를 plinq 모든 후속 쿼리 연산자를 순서 대로 처리 하도록 합니다. 순차적 처리 병렬 보다 일반적으로 느린 경우에 경우 올바른 결과 생성 하는 데 필요한 합니다.  
  
> [!WARNING]
>  이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다. 속도 대 한 자세한 내용은 참조 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 한 가지 시나리오를 보여 줍니다. <xref:System.Linq.ParallelEnumerable.AsSequential%2A> 즉 하는데 필요한 이전 쿼리 절에 설정 된 순서를 유지 합니다.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 를 컴파일하고 실행이 코드를 붙여 넣습니다는 [PLINQ 데이터 샘플](../../../docs/standard/parallel-programming/plinq-data-sample.md) 프로젝트에서 선을 추가에서 메서드를 호출 하 여 `Main`, F5 키를 누릅니다.  
  
## <a name="see-also"></a>참고 항목  
 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
