---
title: "방법: PLINQ 쿼리의 순서 제어"
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
helpviewer_keywords: PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9e29aa825a68154e32a34a23ca170258092b88a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a>방법: PLINQ 쿼리의 순서 제어
이 예제를 사용 하 여 PLINQ 쿼리의 순서를 제어 하는 방법을 보여는 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 확장 메서드.  
  
> [!WARNING]
>  이 예에서는, 사용법을 보여 주기는 주로 및 그렇지 to Objects 쿼리보다 동일한 순차 LINQ 보다 빠르게 실행 되지 않을 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 소스 시퀀스의 순서를 유지 합니다. 이 경우가 가끔 있습니다. 예를 들어 일부 쿼리 연산자에는 올바른 결과 생성 하는 정렬 된 소스 시퀀스가 필요 합니다.  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 몇 가지 쿼리 연산자를 지정 된 소스 시퀀스를 사용할 수 것 보여 줍니다. 이러한 연산자는 순서가 지정 되지 않은 시퀀스 작동 하지만 예기치 않은 결과가 발생할 수 있습니다.  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 이 메서드를 실행 하려면 PLINQDataSample 클래스에 붙여넣습니다는 [PLINQ 데이터 샘플](../../../docs/standard/parallel-programming/plinq-data-sample.md) 프로젝트 및 F5 키를 누릅니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 쿼리의 첫 번째 부분에 대 한 순서를 유지 한 다음 join ' 절의 성능을 향상 시키기 위해 순서를 제거 하 고, 최종 결과 시퀀스에 순서를 다시 적용 하는 방법을 보여 줍니다.  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 이 메서드를 실행 하려면 PLINQDataSample 클래스에 붙여넣습니다는 [PLINQ 데이터 샘플](../../../docs/standard/parallel-programming/plinq-data-sample.md) 프로젝트 및 F5 키를 누릅니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq.ParallelEnumerable>  
 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
