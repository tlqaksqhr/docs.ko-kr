---
title: "두 시퀀스 연결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e7230e1f53f58f37dacbb1f22fbad1593768e01e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="concatenate-two-sequences"></a><span data-ttu-id="5a43b-102">두 시퀀스 연결</span><span class="sxs-lookup"><span data-stu-id="5a43b-102">Concatenate Two Sequences</span></span>
<span data-ttu-id="5a43b-103"><xref:System.Linq.Queryable.Concat%2A> 연산자를 사용하여 두 시퀀스를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="5a43b-103">Use the <xref:System.Linq.Queryable.Concat%2A> operator to concatenate two sequences.</span></span>  
  
 <span data-ttu-id="5a43b-104"><xref:System.Linq.Queryable.Concat%2A> 연산자는 수신자와 인수의 순서가 동일하게 정렬된 다중 집합에 대해 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a43b-104">The <xref:System.Linq.Queryable.Concat%2A> operator is defined for ordered multisets where the orders of the receiver and the argument are the same.</span></span>  
  
 <span data-ttu-id="5a43b-105">SQL의 정렬은 결과 생성 전에 수행되는 최종 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="5a43b-105">Ordering in SQL is the final step before results are produced.</span></span> <span data-ttu-id="5a43b-106">이러한 이유로 인해 <xref:System.Linq.Queryable.Concat%2A> 연산자는 `UNION ALL`을 사용하여 구현되며 해당 인수의 순서를 유지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a43b-106">For this reason, the <xref:System.Linq.Queryable.Concat%2A> operator is implemented by using `UNION ALL` and does not preserve the order of its arguments.</span></span> <span data-ttu-id="5a43b-107">결과에 정렬을 올바르게 하려면 결과를 명시적으로 정렬해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a43b-107">To make sure ordering is correct in the results, make sure to explicitly order the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a43b-108">예제</span><span class="sxs-lookup"><span data-stu-id="5a43b-108">Example</span></span>  
 <span data-ttu-id="5a43b-109">이 예제에서는 <xref:System.Linq.Queryable.Concat%2A>을 사용하여 모든 `Customer`와 `Employee`에 대한 전화 번호 및 팩스 번호의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a43b-109">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` telephone and fax numbers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a><span data-ttu-id="5a43b-110">예제</span><span class="sxs-lookup"><span data-stu-id="5a43b-110">Example</span></span>  
 <span data-ttu-id="5a43b-111">이 예제에서는 <xref:System.Linq.Queryable.Concat%2A>을 사용하여 모든 `Customer`와 `Employee`에 대한 이름 및 전화 번호 매핑의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a43b-111">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` name and telephone number mappings.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a><span data-ttu-id="5a43b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a43b-112">See Also</span></span>  
 [<span data-ttu-id="5a43b-113">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="5a43b-113">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="5a43b-114">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="5a43b-114">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
