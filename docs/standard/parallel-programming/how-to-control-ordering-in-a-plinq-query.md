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
# <a name="how-to-control-ordering-in-a-plinq-query"></a><span data-ttu-id="04281-102">방법: PLINQ 쿼리의 순서 제어</span><span class="sxs-lookup"><span data-stu-id="04281-102">How to: Control Ordering in a PLINQ Query</span></span>
<span data-ttu-id="04281-103">이 예제를 사용 하 여 PLINQ 쿼리의 순서를 제어 하는 방법을 보여는 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 확장 메서드.</span><span class="sxs-lookup"><span data-stu-id="04281-103">These examples show how to control the ordering in a PLINQ query by using the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> extension method.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="04281-104">이 예에서는, 사용법을 보여 주기는 주로 및 그렇지 to Objects 쿼리보다 동일한 순차 LINQ 보다 빠르게 실행 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04281-104">These examples are primarily intended to demonstrate usage, and may or may not run faster than the equivalent sequential LINQ to Objects queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04281-105">예제</span><span class="sxs-lookup"><span data-stu-id="04281-105">Example</span></span>  
 <span data-ttu-id="04281-106">다음 예제에서는 소스 시퀀스의 순서를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="04281-106">The following example preserves the ordering of the source sequence.</span></span> <span data-ttu-id="04281-107">이 경우가 가끔 있습니다. 예를 들어 일부 쿼리 연산자에는 올바른 결과 생성 하는 정렬 된 소스 시퀀스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="04281-107">This is sometimes necessary; for example some query operators require an ordered source sequence to produce correct results.</span></span>  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="04281-108">예제</span><span class="sxs-lookup"><span data-stu-id="04281-108">Example</span></span>  
 <span data-ttu-id="04281-109">다음 예제에서는 몇 가지 쿼리 연산자를 지정 된 소스 시퀀스를 사용할 수 것 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04281-109">The following example shows some query operators whose source sequence is probably expected to be ordered.</span></span> <span data-ttu-id="04281-110">이러한 연산자는 순서가 지정 되지 않은 시퀀스 작동 하지만 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04281-110">These operators will work on unordered sequences, but they might produce unexpected results.</span></span>  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 <span data-ttu-id="04281-111">이 메서드를 실행 하려면 PLINQDataSample 클래스에 붙여넣습니다는 [PLINQ 데이터 샘플](../../../docs/standard/parallel-programming/plinq-data-sample.md) 프로젝트 및 F5 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="04281-111">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04281-112">예제</span><span class="sxs-lookup"><span data-stu-id="04281-112">Example</span></span>  
 <span data-ttu-id="04281-113">다음 예에서는 쿼리의 첫 번째 부분에 대 한 순서를 유지 한 다음 join ' 절의 성능을 향상 시키기 위해 순서를 제거 하 고, 최종 결과 시퀀스에 순서를 다시 적용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04281-113">The following example shows how to preserve ordering for the first part of a query, then remove the ordering to increase the performance of a join clause, and then reapply ordering to the final result sequence.</span></span>  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 <span data-ttu-id="04281-114">이 메서드를 실행 하려면 PLINQDataSample 클래스에 붙여넣습니다는 [PLINQ 데이터 샘플](../../../docs/standard/parallel-programming/plinq-data-sample.md) 프로젝트 및 F5 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="04281-114">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04281-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04281-115">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="04281-116">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="04281-116">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
